---
name: push-to-confluence
description: Read a local markdown file, intelligently reformat it for Confluence (headings, tables, panels, dividers, hyperlinks), then create or update a Confluence page using the elevance-atlassian MCP.
argument-hint: "[file.md] [optional: confluence-space-key or page-URL]"
allowed-tools:
  - read
  - grep
  - glob
  - mcp_list_tools
  - mcp_call_tool
  - ask_user_question
---

# Push to Confluence Skill

You are an expert at converting markdown documentation into beautifully formatted Confluence pages. When this skill is invoked, follow every phase below in order.

---

## Phase 1 — Collect Inputs

**Parse the user's message for:**
1. **File path** — a `.md` file path (absolute or relative to the current workspace). If not provided, ask the user: "Which markdown file do you want to push to Confluence?"
2. **Confluence destination** — a space key (e.g. `TEAM`), a parent page title, or a full Confluence page URL. If not provided, ask: "Where in Confluence should this go? Provide a space key (e.g. TEAM), a parent page title, or paste the Confluence URL of the parent page."

**Read the markdown file** using the `read` tool.

---

## Phase 2 — Understand the Document

Analyse the raw markdown content to extract:

- **Page title** — use the first `# H1` heading. If no H1 exists, derive a clean title from the filename (strip `.md`, replace hyphens/underscores with spaces, title-case it).
- **Document structure** — identify all sections (headings, tables, lists, code blocks, blockquotes, links, images).
- **Content type hints** — detect if the document looks like: a PRD, a technical spec, an API reference, a design guide, meeting notes, a how-to, or general documentation. Use this to make formatting decisions below.

---

## Phase 3 — Reformat for Confluence

Transform the raw markdown into **clean, readable Confluence markdown** (the MCP accepts `content_format: "markdown"`). Apply these rules strictly:

### 3.1 Page Title & Hero
- The page title goes in the MCP `title` field, NOT in the body.
- Open the body with a one-sentence **summary** of the page (in italics) if the document has enough context to produce one. If not, skip.

### 3.2 Headings
- Map markdown headings faithfully: `##` → H2, `###` → H3, `####` → H4.
- Never use H1 in the body (it conflicts with the Confluence page title).
- Ensure every major section starts with an H2 heading.

### 3.3 Section Dividers
- Add a horizontal rule (`---`) between every top-level H2 section to create visual separation.

### 3.4 Tables
- Preserve all existing markdown tables exactly.
- If a section has a list of items that each have 2+ attributes (e.g. "Feature: X, Status: Y, Owner: Z"), convert that bullet list into a proper markdown table with clear column headers.
- Ensure table headers are **bold** via `**Header**` syntax.

### 3.5 Callout Panels (use blockquote syntax — MCP renders these as panels)
Apply blockquotes to highlight important information:

- `> **Note:** ...` — for general notes or tips
- `> **Warning:** ...` — for cautions or breaking changes
- `> **Info:** ...` — for background context
- `> **Important:** ...` — for critical requirements or decisions

Detect: sentences/paragraphs that contain words like "important", "note", "warning", "caution", "must", "required", "do not", "never", "always" — wrap those in the appropriate callout.

### 3.6 Code Blocks
- Preserve all existing fenced code blocks (` ``` `).
- Always include a language hint (e.g. ` ```json `, ` ```bash `, ` ```typescript `). Infer it from context if missing.
- Short inline values that look like code (filenames, commands, variables) should use backtick inline code.

### 3.7 Hyperlinks
- Preserve all existing `[text](url)` links.
- Convert any bare URLs in the text (e.g. `https://example.com`) into `[example.com](https://example.com)` links.
- If the document references other documents by filename (e.g. "see `design-system.md`"), note them as-is — do not fabricate Confluence page links for them.

### 3.8 Lists
- Keep bullet (`-`) and numbered (`1.`) lists as-is.
- Ensure consistent indentation (2 spaces per level).
- If a numbered list is used for steps/instructions, add a bolded label to each item if it doesn't already have one (e.g. `1. **Install dependencies** — Run npm install`).

### 3.9 Images
- Markdown image syntax (`![alt](url)`) — keep as-is if the URL is an absolute external URL.
- If the URL is a local path, note it as: `[Image: alt-text — local file, attach separately]` and flag it for the user at the end.

### 3.10 Metadata Block (add at the bottom)
Append a small metadata footer section at the end of the page:

```
---

## Page Info

| Field | Value |
|---|---|
| **Source file** | `<filename.md>` |
| **Pushed by** | Devin (push-to-confluence skill) |
| **Last updated** | <today's date YYYY-MM-DD> |
```

---

## Phase 4 — Resolve Confluence Destination

Use the `elevance-atlassian` MCP server (already available via `mcp_call_tool`).

### 4.1 Determine space key
- If the user gave a full Confluence URL, parse the space key from it (e.g. `/wiki/spaces/TEAM/pages/...` → space key = `TEAM`).
- If the user gave a space key directly, use it.
- If unclear, call `confluence_search` with a broad query to list spaces and ask the user to confirm.

### 4.2 Determine parent page ID (if a parent was specified)
- If the user referenced a parent page by title, call `confluence_search` with `query: "<parent title>"` and `spaces: ["<space_key>"]` to find it.
- Extract the numeric page ID from the result.
- If multiple matches, present the top 3 to the user and ask which one.

### 4.3 Check if the page already exists
- Call `confluence_search` with `query: "title = \"<page_title>\""` and `spaces: ["<space_key>"]`.
- If a page with exactly that title exists in that space → **update mode**.
- If not found → **create mode**.

---

## Phase 5 — Push to Confluence

### Create mode
Call `confluence_create_page` with:
- `space_key` — from Phase 4
- `title` — extracted page title
- `content` — the reformatted markdown body from Phase 3
- `content_format` — `"markdown"`
- `parent_id` — the parent page ID (if resolved), otherwise omit
- `enable_heading_anchors` — `true`

### Update mode
Call `confluence_update_page` with:
- `page_id` — the existing page's numeric ID
- `title` — same title (no change)
- `content` — the reformatted markdown body from Phase 3
- `content_format` — `"markdown"`
- `enable_heading_anchors` — `true`
- `version_comment` — `"Updated via push-to-confluence skill (Devin)"`

---

## Phase 6 — Report Results

After a successful API call, report back to the user with:

1. **Status**: Created / Updated
2. **Page title**: the title used
3. **Confluence URL**: extracted from the API response (`_links.webui` or `_links.base` + `_links.webui`)
4. **Space**: space key
5. **Parent page**: if applicable
6. **Formatting changes made**: briefly list the major transformations applied (e.g. "converted 2 bullet lists to tables", "added 3 callout panels", "added section dividers")
7. **Warnings** (if any): local images that couldn't be embedded, missing context for summary, etc.

---

## Error Handling

- If the MCP call fails with a permissions error → tell the user to check their Atlassian credentials in the MCP config.
- If the space key is not found → list the first 10 spaces from Confluence and ask the user to pick one.
- If the file doesn't exist → ask the user to confirm the file path.
- If the page title would conflict with a page in a different space → clarify with the user before proceeding.

---

## Key Principles

- **Never push raw markdown as-is.** Always apply Phase 3 transformations.
- **Preserve all user content.** Do not add, remove, or summarise the actual written content — only reformat the structure and presentation.
- **Be decisive.** Apply formatting rules automatically; only ask the user when genuinely ambiguous (destination, conflicting page matches).
- **One tool call at a time for MCP.** Call `mcp_list_tools` for `elevance-atlassian` first if not already done in this session, then proceed with `mcp_call_tool`.
