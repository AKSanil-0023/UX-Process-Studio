---
name: create-persona
description: Create user personas by gathering data through questions or using existing research
---

# User Persona Creation Skill

## Skill Objective
Guide the creation of research-based user personas by collecting inputs through interactive questions, analyzing existing data if available, and generating comprehensive persona deliverables in multiple formats.

## Execution Flow

### Phase 1: Assess Data Availability
**Action**: Check if user has existing research data

**Check for:**
- User research files (interviews, surveys, notes)
- BRD or product requirements documents
- Analytics data or user behavior reports
- Competitive analysis or market research

**Decision:**
- IF data exists or given by the user in prompt → Proceed to Phase 2 (Data Analysis)
- IF NO data exists → Proceed to Phase 1B (Question Gathering)

---

### Phase 1B: Gather Information Through Questions
**Action**: Collect required inputs through structured questions

**Questions to Ask:**

1. **Product/Service Context**
   - What is the product or service name?
   - What problem does it solve?
   - What stage is it in? (Concept / Development / Live / Redesign)

2. **User Research Status**
   - Have you conducted any user interviews? If yes, how many?
   - Do you have survey data? If yes, how many responses?
   - Do you have any analytics or behavioral data?
   - Have you done any competitive research on user types?

3. **Target Audience Assumptions**
   - Who do you think your primary users are?
   - What are their likely goals when using your product?
   - What problems or pain points might they have?
   - Are there different user types or segments?

4. **Business Context**
   - What are the primary business objectives?
   - Who are your target customers/market?
   - Any budget or timeline constraints?
   - Any compliance or regulatory considerations?

5. **Persona Scope**
   - How many personas do you need? (Recommend 3-5)
   - What level of detail? (High-level overview / Detailed profiles)
   - Primary use case? (Design decisions / Marketing / Development / Stakeholder alignment)
   - Will these personas be updated regularly?

---

### Phase 2: Determine Persona Approach
**Action**: Based on data quality, choose appropriate persona type

**Persona Types:**

1. **Research-Based Personas** (8+ interviews OR 50+ survey responses)
   - High confidence in all attributes
   - Detailed behavioral patterns
   - Direct quotes from research
   - Validated goals and pain points

2. **Proto-Personas** (3-7 interviews OR 20-50 survey responses)
   - Medium confidence with marked assumptions
   - Focus on behavioral patterns over demographics
   - Include validation plan
   - Clear "needs testing" indicators

3. **Assumption-Based Personas** (No research data)
   - Low confidence, marked as hypothetical
   - Based on stakeholder knowledge and best practices
   - Heavy emphasis on validation roadmap
   - Quick research plan included

---

### Phase 3: Generate Persona Deliverables
**Action**: Create comprehensive persona package

**Required Outputs:**

1. **Primary Persona Documents** (1-5 personas)
   - Full detailed profile for each persona
   - Include confidence indicators if proto/assumption-based
   - Format: Standard Persona Profile (see Format Library)

2. **One-Page Persona Cards**
   - Condensed reference cards for each persona
   - Suitable for printing/posting
   - Format: Persona Card (Compact)

---

### Phase 4: Package and Document
**Action**: Create organized deliverable package

**Final Deliverables:**

Create folder: `[ProductName]-Personas/`

**Files to generate:**
1. ✅ `persona-[name-1].md` - Full profile for Persona with names. Generate different files for all personas decided by user in prior steps.
3. ✅ `persona-cards.md` - One-page summaries for all personas, DO NOT INCLUDE ANY CONTENT OTHER THAN CARDS
4. ✅ `README.md` - Package overview and file index - DO NOT INCLUDE ANY TECHINCAL DETAILS (Purely Designer Centric)

---

## Persona Format Library

### Format 1: Standard Persona Profile
Use this for primary persona documents.

```
# PERSONA: [Name] - [Archetype Title]

## Overview
[2-3 sentence summary of who this persona represents]

## Demographics
- **Age**: [Range or specific]
- **Role/Occupation**: [Job title or role]
- **Location**: [Geographic context]
- **Education**: [Level and field]
- **Income**: [Range if relevant]
- **Tech Savviness**: [Low / Medium / High]

## Goals
[What they want to achieve - list 3-5 primary goals]
1. **Goal 1**: Description
2. **Goal 2**: Description
3. **Goal 3**: Description

## Pain Points
[Current frustrations and challenges - list 3-5]
1. **Pain Point 1**: Description
2. **Pain Point 2**: Description
3. **Pain Point 3**: Description

## Behaviors & Preferences
[How they act and what they prefer]
- Behavior pattern 1
- Behavior pattern 2
- Preference 1
- Preference 2

## Motivations
[What drives their decisions and actions]
- Motivation 1
- Motivation 2

## Quote
"[Direct quote from research or representative statement that captures their mindset]"

## Scenarios
[2-3 typical use cases or day-in-the-life moments]

### Scenario 1: [Title]
[Description of how they would interact with your product]

### Scenario 2: [Title]
[Description]

## Tools & Technology
[Current tools they use, tech stack, platforms]
- Tool/Platform 1
- Tool/Platform 2

---

**Data Confidence**: [HIGH ✓ / MEDIUM ⚠️ / LOW ⚠️]
**Based on**: [X interviews, Y survey responses, Z data sources]
**Last Updated**: [Date]
```

### Format 2: Proto-Persona (With Confidence Indicators)
Use when data is limited but some research exists.

```
# PROTO-PERSONA: [Name] - [Archetype]

⚠️ **CONFIDENCE LEVEL**: PROVISIONAL
**Data Foundation**: [X interviews, Y surveys, Z sources]

## Profile [Confidence: HIGH/MEDIUM/LOW]
[Demographic information with confidence markers]

## Validated Attributes ✓
[List only attributes confirmed by research]
- Attribute 1
- Attribute 2

## Assumed Attributes ⚠️
[List assumptions that need validation]
- Assumption 1
- Assumption 2

## Research Gaps
[What you still need to learn]
1. Gap 1
2. Gap 2

## Validation Plan
[How to test assumptions]
- [ ] Activity 1
- [ ] Activity 2
```

### Format 4: Persona Card (Compact)
Use for one-page reference cards.

```
[NAME] - [Archetype Title]                             

 PROFILE                                              
 Age: [X] | [Role] | [Location]                         
 Tech Comfort: [Level] | Price Sensitivity: [Level] 
 Job Responsibilities: [Responsibilities]               
                                                         
 TOP GOALS                                            
 1. [Goal 1]                                            
 2. [Goal 2]                                            
 3. [Goal 3]                                            
                                                         
 FRUSTRATIONS                                         
 • [Pain point 1]                                       
 • [Pain point 2]                                       
 • [Pain point 3]                                       
                                                         
 MOTIVATIONS                                          
 [Motivation 1] | [Motivation 2] | [Motivation 3]       
                                                         
 QUOTE                                                
 "[Representative quote]"                                

```

---

## Quality Checklist

Before finalizing, ensure:
- [ ] Each persona is distinct and non-overlapping
- [ ] Personas are based on real data (not stereotypes)
- [ ] Confidence levels are clearly marked
- [ ] All files follow naming convention
- [ ] README provides clear navigation

---

## Notes
- Minimum 1 persona, maximum 5 for primary set
- Focus on behavioral differences over demographics
- Include negative personas (who NOT to design for) if relevant
- Always ground in research data, never stereotypes
