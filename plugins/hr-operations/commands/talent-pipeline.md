---
description: Talent pipeline health assessment with succession planning insights
argument-hint: [level]
version: "1.0.0"
tags: [succession, pipeline, talent, readiness]
tool_access: [Read, Write, Bash]
model: sonnet
---

# Talent Pipeline & Succession Analysis

Assess talent pipeline health, succession readiness, internal mobility potential, and high-potential development.

## Requirements
- **Level**: Focus level (e.g., "Director+", "Manager", "all")
- **Critical Roles**: Key positions requiring succession coverage
- **Talent Data**: Performance ratings, potential ratings, readiness, flight risk

## Instructions

### 1. Pipeline Inventory
- Identify high-potential employees by level
- Performance + potential assessment (9-box grid)
- Readiness timeline (ready now, 1-2 years, 2-3 years)
- Career aspirations and mobility preferences

### 2. Succession Coverage
For critical roles:
- Identify 2-3 successors per role
- Assess readiness level (ready now, developing, long-term)
- Identify gaps (no successors, not ready)
- Risk assessment (single points of failure)

### 3. Internal Mobility Analysis
- Promotion-ready candidates by function
- Cross-functional mobility opportunities
- Lateral move potential to build breadth
- Blocked talent (ready but no openings)

### 4. Development Needs
- Skills gaps for succession candidates
- Development programs required (training, rotations, stretch assignments)
- Mentorship and sponsorship recommendations
- Timeline to readiness

### 5. Pipeline Risks
- Flight risk among high-potentials
- Insufficient pipeline depth for key roles
- Diversity of succession candidates
- Retention strategies for critical successors

## Output Format
- Executive summary of pipeline health
- 9-box talent grid (performance × potential)
- Succession coverage by critical role
- Development plans for high-potentials
- Risk mitigation recommendations
- Diversity representation in pipeline

## Related Plugins
**Skills**: workforce-planning-models, skills-gap-analysis
**Agents**: workforce-planner, attrition-predictor
**Commands**: /skills-gap-analysis, /retention-analysis
