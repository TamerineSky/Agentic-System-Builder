---
description: Skills gap identification with development recommendations and planning
argument-hint: [org] [initiative]
version: "1.0.0"
tags: [skills, capabilities, development, training]
tool_access: [Read, Write, Bash]
model: sonnet
---

# Skills Gap Analysis

Assess organizational skills inventory, identify critical capability gaps, and develop workforce development strategy.

## Requirements
- **Organization**: Department or "all" for company-wide
- **Initiative**: Strategic initiative requiring skills (optional, e.g., "AI/ML expansion", "Cloud migration")
- **Skills Data**: Employee skills assessments, proficiency levels (1-5 scale)

## Instructions

### 1. Current Skills Inventory
- Aggregate organizational skills by category (technical, functional, leadership)
- Proficiency distribution (1-5 scale) per skill
- Expert identification (proficiency 4-5)
- Single points of failure (skills with <2 experts)

### 2. Strategic Skills Requirements
- Identify required skills for business strategy/initiatives
- Target proficiency levels needed
- Timeline for capability needs
- Critical vs. nice-to-have skills

### 3. Gap Analysis
- Calculate gap (required - current) per skill
- Prioritize by strategic importance and gap severity
- Identify immediate vs. long-term needs
- Assess risk of missing capabilities

### 4. Build vs. Buy Assessment
For each gap:
- Internal development feasibility (time, cost, candidates)
- External hiring option (market availability, time-to-fill, cost)
- Hybrid approach (hire + develop)
- Recommendation with rationale

### 5. Development Plan
- Training programs required
- Individual development plans for high-potentials
- Mentorship and knowledge transfer
- Timeline and resource requirements
- Budget implications

## Output Format
- Executive summary with critical skills gaps
- Skills inventory heatmap (skill × proficiency distribution)
- Gap analysis prioritized by strategic importance
- Build vs. buy recommendations per skill
- Development roadmap with timeline and costs
- Success metrics and tracking plan

## Related Plugins
**Skills**: skills-gap-analysis, workforce-planning-models
**Agents**: workforce-planner
**Commands**: /headcount-plan, /talent-pipeline
