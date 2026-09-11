UX Process Studio — Figma Make Brief

Internal tool for a 25–30 person design team supporting Elevance Health (via Carelon). Two tabs: Process (reference) and Planner (build-your-own-plan). Every activity in both tabs is tied to a Windsurf skill.

1. Visual direction
Elegant, trendy, but clean and uncluttered — premium internal tool, not a dense dashboard
Generous white space, soft neutral background (off-white / very light gray)
One confident accent color (deep teal or indigo)
Clean sans-serif type (Inter / Söhne style)
Rounded corners, soft shadows, minimal borders
No visual clutter — every element should feel intentional and easy to scan at a glance
Subtle micro-interactions on hover/drag, nothing flashy
2. Information architecture

Content is organized into 7 phases, each containing several activities. Every activity maps to one skill.

# Phase Activities
1 Framing & Discovery Discovery, Secondary research, Problem framing, Stakeholder alignment, Competitive analysis
2 Primary Research & Synthesis User interviews, Journey mapping, Persona creation, Task analysis
3 Structure Information architecture, User flows, Wireframes
4 Craft Interaction design, Visual design, UX writing, Accessibility
5 Validation Prototyping, Usability testing, Analytics, Iteration
6 Delivery Developer handoff, Design QA, Release
7 Systems & Continuity Design system, Continuous improvement

Each activity carries an autonomy mode — this is the badge shown on its Skill Card:

Mode Meaning
Human-led AI contributes inputs or checks. A human does the work and owns the output.
AI-assisted AI produces a draft or structure. A human edits, decides, and owns the output.
AI-driven AI executes and produces the output. A human spot-checks and owns the release.
Activity → mode → responsibility reference

Use this table to populate each Skill Card. "Designer's responsibility" is written from the primary risk of over-relying on AI at that stage — the designer's job is to guard against exactly that failure mode.

Activity Mode Designer's responsibility (guard against)
Discovery AI-assisted Don't mistake AI's synthesis for real domain understanding — validate with SMEs
Secondary research AI-assisted Verify every citation; AI can fabricate sources
Problem framing Human-led Don't anchor on AI's first framing of the problem
Stakeholder alignment AI-assisted Polished output can outrun real alignment — confirm actual buy-in
Competitive analysis AI-assisted Verify competitor capabilities before citing them; AI can hallucinate features
User interviews Human-led Own data handling and question framing; avoid leading questions
Journey mapping AI-assisted Check the mapped journey against real user behavior, not just plausibility
Persona creation AI-assisted Guard against fictional personas or encoded bias — ground in real data
Task analysis AI-assisted Confirm AI modeled actual process, not just documented process
Information architecture AI-assisted Check for invented domain terminology
User flows AI-assisted Have SMEs verify exception paths — don't accept them automatically
Wireframes AI-assisted Don't let premature fidelity shut down exploration
Interaction design AI-assisted Don't mistake completeness for quality
Visual design Human-led Own brand and craft decisions — guard against generic output
UX writing AI-assisted Verify regulatory/compliance copy carefully — confident wrong copy is a real risk
Accessibility Mixed Don't let AI checks create false confidence in compliance
Prototyping AI-driven Make sure prototype code doesn't leak into production
Usability testing AI-assisted Don't substitute synthetic participants for real users
Analytics AI-assisted Watch for correlation being asserted as causation
Iteration AI-assisted Prioritize by importance, not just frequency of AI suggestions
Developer handoff AI-driven Confirm specs describe behavior, not just pixels
Design QA AI-driven Make sure real defects aren't buried in diff noise
Release AI-assisted Check that change descriptions aren't overstated
Design system AI-driven Watch for docs drifting from actual implementation
Continuous improvement AI-assisted Guard against "metric theater" — real signal, not vanity metrics
3. Tab 1 — Process

A reference view of the whole UX process.

Vertical stepper or accordion listing the 7 phases in sequence
Each phase expands to show its activities as clean pill/card items — name + one-line description only, no heavy text
Clicking an activity opens a Skill Card (side panel or modal) with:
Activity name + parent phase
Skill name (the corresponding Windsurf skill)
Short description of what the skill does
Mode badge: Human-led / AI-assisted / AI-driven (three distinct colors)
Designer's Responsibility — bullet points, even when using the skill (see table above)
"Get the skill" button linking out to GitHub (placeholder link)
4. Tab 2 — Planner

A drag-and-drop workspace for building a plan for a specific project, since the generalized process doesn't fit every project.

Left sidebar: all activities grouped by phase (same taxonomy as Tab 1), shown as small draggable cards
Center/right: empty canvas labeled "Your Project Plan" where designers drag activities into a custom sequence
Toolbar above canvas: project name field, "Save Plan" button, "Clear" button
Clicking any placed activity card opens the same Skill Card component used in Tab 1 — identical fields, same component reused
Light grid background, drag handles, minimal borders — keep it as uncluttered as Tab 1
5. Shared component: Skill Card

Reused identically across both tabs. Fields, in order:

Activity name + parent phase
Skill name
What the skill does (1–3 sentences)
Mode badge (Human-led / AI-assisted / AI-driven)
Designer's Responsibility (bullets)
"Get the skill" → GitHub link (placeholder)
6. Build notes
Desktop-first, fully responsive
Skill Card is one component, reused in both tabs — don't rebuild it twice
Skill name and description content are placeholders for now — real Windsurf skill names/descriptions will be filled in as skills are built