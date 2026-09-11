---
name: create-prd
description: Create Product Requirements Documents (PRD) through guided problem framing and requirements gathering
---

# PRD Creation Skill

## Skill Objective
Guide the creation of focused Product Requirements Documents by gathering problem context, user needs, and feature requirements through interactive questions, then generating a structured PRD deliverable.

---

## Execution Flow

### Phase 1: Problem Discovery
**Action**: Understand the core problem and context

**Ask the user:**
1. **What problem are you trying to solve?** (2-3 sentences)
2. **What are the top 3 pain points in the current state?**
3. **What does success look like?** (Desired state)
4. **What's the product/feature name?**

**Output**: Problem Statement section

---

### Phase 2: User Identification
**Action**: Identify target users and their needs

**Ask the user:**
1. **Who are the primary user roles?** (e.g., Admin, End User, Manager)
2. **For each role, what are their:**
   - Description (who they are)
   - Primary needs
   - Access level/permissions
3. **Which roles are PRIMARY vs SECONDARY users?**

**Output**: Target Users section with table

---

### Phase 3: Business Goals & Metrics
**Action**: Define objectives and success criteria

**Ask the user:**
1. **What are the top 3 business objectives?**
2. **How will you measure success?** (Specific metrics with targets)
3. **What are the key KPIs to track?**

**Output**: Business Goals & Success Metrics section

---

### Phase 4: Feature Definition
**Action**: Identify and prioritize features

**Ask the user:**
1. **What are the MUST-HAVE core features?** (3-5 features)
   - For each: What does it do? Why does it matter to users?
2. **What are SHOULD-HAVE secondary features?**
3. **What are NICE-TO-HAVE future considerations?**

**Output**: Features & Functionalities section

---

### Phase 5: User Flows
**Action**: Map primary user journeys

**Ask the user:**
1. **What is the primary user journey?** (Step-by-step flow)
2. **Are there decision points or branching paths?**
3. **What is the expected outcome?**
4. **Any secondary journeys to document?**

**Output**: User Flows section

---

### Phase 6: Rules & Constraints
**Action**: Define boundaries and requirements

**Ask the user:**
1. **What business rules must be enforced?**
2. **What are the technical constraints?** (Platform, integrations, performance, security)
3. **What are the design constraints?** (Accessibility, browser support, responsive needs)

**Output**: Business Rules & Constraints section

---

### Phase 7: Scope Boundaries
**Action**: Clarify what's included and excluded

**Ask the user:**
1. **What features/capabilities are IN SCOPE for this release?**
2. **What is explicitly OUT OF SCOPE?**
3. **What's planned for future phases?**

**Output**: Scope Definition section

---

### Phase 8: Dependencies & Assumptions
**Action**: Document critical dependencies and assumptions

**Ask the user:**
1. **What external dependencies exist?** (Systems, teams, data sources)
2. **What assumptions are you making?** (About users, data, technology)

**Output**: Dependencies & Assumptions section

---

## Final Deliverable Generation

### Phase 9: Generate PRD Document
**Action**: Create complete PRD file

**File to generate:**
- `[ProductName]-PRD.md` - Complete PRD using the format below

---

## PRD Template Format

```markdown
# Product Requirements Document (PRD)
## [Product Name]

---

## 1. Problem Statement
**What problem are we trying to solve?**

[Describe the core problem in 2-3 sentences. Focus on user pain points and business impact.]

**Current State:**
- [Pain point 1]
- [Pain point 2]
- [Pain point 3]

**Desired State:**
[What success looks like after solving this problem]

---

## 2. Target Users

| User Role | Description | Primary Needs | Access Level |
|-----------|-------------|---------------|--------------|
| [Role 1] | [Who they are] | [What they need] | [Permission level] |
| [Role 2] | [Who they are] | [What they need] | [Permission level] |
| [Role 3] | [Who they are] | [What they need] | [Permission level] |

**User Prioritization:**
- **Primary Users:** [Roles that are most critical]
- **Secondary Users:** [Supporting roles]

---

## 3. Business Goals & Success Metrics

### Business Objectives
1. **[Objective 1]**: [Brief description]
2. **[Objective 2]**: [Brief description]
3. **[Objective 3]**: [Brief description]

### Success Metrics (How will success be measured?)

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| [Metric 1] | [Target value] | [How to measure] |
| [Metric 2] | [Target value] | [How to measure] |
| [Metric 3] | [Target value] | [How to measure] |

**Key Performance Indicators (KPIs):**
- [KPI 1]: [Description]
- [KPI 2]: [Description]

---

## 4. Features & Functionalities

### Core Features (Must Have)
1. **[Feature 1]**
   - Description: [What it does]
   - User Value: [Why it matters]
   
2. **[Feature 2]**
   - Description: [What it does]
   - User Value: [Why it matters]

3. **[Feature 3]**
   - Description: [What it does]
   - User Value: [Why it matters]

### Secondary Features (Should Have)
- [Feature A]: [Brief description]
- [Feature B]: [Brief description]

### Future Considerations (Nice to Have)
- [Feature X]: [Brief description]
- [Feature Y]: [Brief description]

---

## 5. User Flows

### Primary User Journey: [Journey Name]
**Actor:** [User Role]

1. [Step 1] → [Step 2] → [Step 3]
2. **Decision Point:** [Choice A or Choice B]
   - If A: [Next steps]
   - If B: [Alternative steps]
3. [Final outcome]

### Secondary User Journey: [Journey Name]
**Actor:** [User Role]

[Simplified flow description]

---

## 6. Business Rules & Constraints

### Business Rules
1. **[Rule 1]**: [Description and rationale]
2. **[Rule 2]**: [Description and rationale]
3. **[Rule 3]**: [Description and rationale]

### Technical Constraints
- **Platform:** [Technology stack or platform requirements]
- **Integrations:** [Required system integrations]
- **Performance:** [Speed, scalability requirements]
- **Security:** [Authentication, authorization, compliance needs]

### Design Constraints
- **Accessibility:** [WCAG 2.1 AA or other standards]
- **Browser Support:** [Supported browsers/devices]
- **Responsive:** [Mobile, tablet, desktop requirements]

---

## 7. Scope Definition

### ✅ In Scope
- [Feature/capability 1]
- [Feature/capability 2]
- [Feature/capability 3]
- [Integration 1]
- [User role 1 functionality]

### ❌ Out of Scope
- [Feature/capability to exclude]
- [Future phase items]
- [Non-supported use cases]

### 🔮 Future Phases
- **Phase 2:** [Planned features]
- **Phase 3:** [Long-term vision]

---

## 8. Dependencies & Assumptions

### Dependencies
- [External system/team dependency 1]
- [Data source dependency 2]
- [Third-party service dependency 3]

### Assumptions
- [Assumption 1 about users, data, or technology]
- [Assumption 2]
- [Assumption 3]

---

## Document Control

| Field | Value |
|-------|-------|
| **Version** | 1.0 |
| **Last Updated** | [Date] |
| **Author** | [Name, Role] |
| **Stakeholders** | [List of reviewers/approvers] |
| **Status** | Draft / In Review / Approved |