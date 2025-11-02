---
description: Retention analysis by cohort and segment with risk identification
argument-hint: [cohort] [period]
version: "1.0.0"
tags: [retention, attrition, cohort, risk]
tool_access: [Read, Write, Bash]
model: sonnet
---

# Retention Analysis by Cohort

Analyze retention rates across cohorts, identify at-risk segments, and develop targeted retention strategies.

## Requirements
- **Cohort**: Segment to analyze (e.g., "2023 new hires", "engineering", "high-performers", "all")
- **Period**: Retention period (e.g., "90-day", "1-year", "2-year", "tenure analysis")
- **Comparison**: Baseline or benchmark for comparison

## Instructions

### 1. Retention Rate Calculation
- Overall retention rate for cohort
- By tenure milestone (30/60/90 days, 6mo, 1yr, 2yr)
- Benchmark comparison (company avg, industry, prior cohorts)
- Attrition cost impact

### 2. Cohort Segmentation
Retention rates by:
- Department and function
- Job level and role type
- Hire source (referral, LinkedIn, agency)
- Manager and team
- Demographics (gender, race, age)
- Performance level (top, average, low performers)

### 3. At-Risk Identification
Identify high-risk cohorts:
- Below benchmark retention (<85% at 1 year)
- Declining retention trends
- Early attrition patterns (high 90-day attrition)
- Critical roles with retention concerns

### 4. Root Cause Analysis
Investigate drivers of attrition:
- Exit interview themes by cohort
- Engagement score differences
- Compensation competitiveness
- Manager effectiveness
- Onboarding quality indicators

### 5. Targeted Interventions
Develop cohort-specific retention strategies:
- New hire onboarding improvements (if 90-day attrition high)
- Compensation adjustments (if pay-related departures)
- Manager coaching (if team-specific attrition)
- Career development programs (if growth-related)
- Estimate ROI and expected retention improvement

## Output Format
- Executive summary with retention rates and trends
- Cohort retention comparison table
- At-risk segment identification with severity
- Root cause analysis by high-attrition cohort
- Targeted retention recommendations
- ROI analysis of interventions
- Implementation timeline

## Related Plugins
**Skills**: attrition-analysis, workforce-planning-models
**Agents**: attrition-predictor, compensation-analyst
**Commands**: /attrition-analysis, /compensation-review
