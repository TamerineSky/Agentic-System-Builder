---
description: Generate headcount forecast and workforce plan with scenario modeling
argument-hint: [timeframe] [org] [growth-rate]
version: "1.0.0"
tags: [workforce-planning, forecasting, capacity, headcount]
tool_access: [Read, Write, Bash]
model: sonnet
---

# Headcount Planning & Forecasting

Generate comprehensive headcount forecast with scenario analysis, capacity modeling, and strategic workforce planning aligned with business objectives.

## Context
Strategic workforce planning requires forecasting headcount needs based on business growth, attrition patterns, capacity requirements, and budget constraints. This command generates data-driven headcount plans with multiple scenarios.

## Requirements
$ARGUMENTS

Required inputs:
- **Timeframe**: Planning horizon (e.g., "12 months", "FY2025", "Q1-Q4 2025")
- **Organization**: Department/function or "all" for company-wide
- **Growth Rate**: Expected business growth rate (e.g., "50% ARR growth", "stable", "conservative/base/aggressive")
- **Current State**: Current headcount by function/role
- **Attrition Assumptions**: Historical or forecasted attrition rates
- **Budget Constraints**: Headcount budget or FTE cap (optional)

## Instructions

### 1. Current State Assessment

Analyze baseline workforce:
- Current headcount by department, function, role, and level
- Span of control analysis for managers
- Current capacity utilization and workload assessment
- Revenue per employee and productivity metrics
- Recent hiring velocity and attrition trends
- Open requisitions and pending hires

Generate summary dashboard showing:
- Total headcount and breakdown by org
- Key ratios (revenue/employee, managers/ICs, etc.)
- Capacity health indicators (underutilized, at capacity, overloaded)
- Organizational structure and reporting relationships

### 2. Demand Forecasting

Model headcount needs based on business drivers:

**Driver-Based Forecasting:**
- Sales team: Revenue target ÷ quota per rep × (1 + ramp factor)
- Customer Success: Customer count ÷ CSM capacity
- Engineering: Product roadmap capacity ÷ team velocity
- Operations: Transaction volume ÷ productivity rate
- G&A: Headcount ratios to total company size

**Growth-Based Forecasting:**
- Apply growth rate to current headcount by function
- Adjust for efficiency improvements or automation
- Account for new initiatives requiring dedicated resources
- Factor in productivity curves (new hire ramp time)

**Scenario Modeling:**
- Conservative: Lower growth, higher attrition, constrained budget
- Base: Expected growth, normal attrition, planned budget
- Aggressive: Higher growth, lower attrition, expanded investment

### 3. Supply Planning & Attrition Impact

Account for workforce supply changes:
- **Attrition Forecast**: Apply historical or segment-specific attrition rates
- **Internal Mobility**: Promotions, lateral moves, backfills needed
- **Departures Pipeline**: Known departures (resignations, PIPs, retirements)
- **Net Headcount**: Hires needed = Demand - Current HC + Attrition - Internal Moves

Calculate quarterly phasing:
- Month-by-month headcount trajectory
- Hiring needs by quarter with start date targets
- Backfill requirements for departures
- Budget implications with loaded salary costs

### 4. Gap Analysis & Prioritization

Identify critical gaps and hiring priorities:

**Capacity Gaps:**
- Teams significantly under target headcount
- Critical skills shortages blocking strategic initiatives
- Span of control issues requiring management additions
- Geographic expansion requirements

**Prioritization Framework:**
- Critical (blocks revenue/product): Hire immediately
- High (capacity constraint): Hire within quarter
- Medium (efficiency/optimization): Hire as budget allows
- Low (nice-to-have): Defer or reallocate

**Risk Assessment:**
- Time-to-fill assumptions by role difficulty
- Market availability and competition for talent
- Budget constraints and approval timelines
- Organizational capacity to onboard and ramp

## Output Format

Generate comprehensive workforce plan including:

### Executive Summary (1 page)
- Current state snapshot (total HC, key metrics)
- Recommended headcount plan (target HC by end of period)
- Net hiring needs and phasing by quarter
- Budget implications (total compensation cost)
- Key assumptions and risks
- Comparison of scenarios (conservative/base/aggressive)

### Detailed Headcount Forecast
- Function-by-function headcount plan with monthly detail
- Breakdown by department, role type, and level
- Hiring needs vs. backfills vs. net new growth
- Start dates and expected hire dates
- Fully loaded cost per hire and total budget impact

### Capacity Analysis
- Available capacity (FTEs) by team with utilization assumptions
- Demand forecast (person-months) by initiative/project
- Capacity surplus/deficit heatmap (team × quarter)
- Recommended actions (hire, defer, reallocate)

### Scenario Comparison
Table comparing conservative, base, and aggressive scenarios:
- Total headcount by scenario
- Hiring needs by scenario
- Budget implications by scenario
- Risk profile by scenario

### Implementation Roadmap
- Hiring priorities by quarter (role, org, criticality)
- Recruiting capacity assessment (can we hire this many?)
- Organizational design recommendations (new teams, reorgs)
- Key milestones and decision points

## Success Criteria

- Headcount plan aligned with business growth targets
- Scenarios provide range of outcomes for planning flexibility
- Capacity gaps identified and prioritized
- Hiring needs phased quarterly with realistic timelines
- Budget implications clearly quantified
- Plan accounts for attrition and internal mobility
- Stakeholder alignment on priorities and trade-offs

## Related Plugins

- **Skills**: workforce-planning-models, attrition-analysis
- **Agents**: workforce-planner, compensation-analyst
- **Commands**: /attrition-analysis, /skills-gap-analysis, /talent-pipeline
