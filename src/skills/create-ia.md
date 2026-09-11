---
name: create-ia
description: Execute the complete Information Architecture creation process for a product, from research to deliverables
---

# Information Architecture Creation Skill

## Skill Objective
Guide the designer/agent through creating a comprehensive Information Architecture by collecting inputs, executing research activities, and generating all required deliverables in documented formats.

## Execution Flow

### Phase 1: Gather Prerequisites
**Action**: Collect all required inputs before proceeding

**Questions to Ask:**
1. **Product Context**
   - What is the product name and description?
   - What problem does it solve?
   - Who are the target users (primary and secondary)?

2. **Business Requirements**
   - What are the key business goals?
   - What are the success metrics?
   - Are there any technical constraints or platform limitations?

3. **Content Scope**
   - Do you have an existing content inventory? (If yes, request file/list)
   - What are the main content types? (e.g., products, articles, documentation)
   - Estimated volume of content items?

4. **Research Assets**
   - Do you have user research data? (personas, journey maps, interviews)
   - Do you have competitive analysis data?
   - Do you have analytics data from existing site/app?

5. **Requirements**
   - Any SEO requirements or URL structure needs?
   - Accessibility standards to follow? (WCAG 2.1 AA by default)
   - Any specific navigation patterns required?

---

### Phase 2: Define Taxonomy & Organization
**Action**: Create the information grouping structure

**Tasks:**
1. Based on user mental models (or best practices if no research):
   - Define 5-7 primary categories
   - Create hierarchical structure (max 3-4 levels deep)
   - Establish naming conventions

**Questions to Ask:**
- How would users naturally group this content?
- What are the most important user tasks?
- Should organization be by: topic, task, audience, or hybrid?

**Output Format**: Generate `taxonomy.md` and only include:
- Format 1: Hierarchical Sitemap (Indented Text)
- User Role Labels
- Category Definitions


### Phase 3: Generate Final Deliverables
**Action**: Compile all outputs into final package

**Deliverables to Create:**
1. ✅ `taxonomy.md` - Information grouping and metadata
2. ✅ `ia-summary.md` - Executive summary, Project Context, IA Approach, User Role Summary, and Conclusion (Only include these section, dont add any other)

**Final Action**: Create [README.md] in IA folder with:
- Project overview
- File index with descriptions
- DO NOT INCLUDE ANY TECHINCAL DETAILS (Purely Designer Centric)

## FORMATS:
- Format 1:
  Product Name
├── Option A
│   ├── Option A1
│   ├── Option A2
│
├── Option B
│   ├── Option B1
│   │   ├── Option B1.1
│   │   ├── Option B1.2
│   │   ├── Option B1.3
│   │   └── Option B1.4
│   │
│   ├── Option B2
│   │   ├── Option B2.1
│   │   ├── Option B2.2
│   │   └── Option B2.3
│   │
│   ├── Option B3
│   │   ├── Option B3.1
│   │   │   ├── Option B3.1.1
