---
description: Analyze NPS survey results with driver analysis, segment breakdown, and action planning for promoters, passives, and detractors
argument-hint: [survey-period] [segment]
version: "1.0.0"
tags: [nps, satisfaction, feedback]
model: sonnet
---

# NPS Analysis Command

Comprehensive NPS analysis with actionable insights and closed-loop follow-up plan.

## Context
NPS predicts loyalty, churn, and expansion. Promoters expand 38% vs. detractors 2%, and detractors churn at 45% vs. promoters 3%.

## Requirements
$ARGUMENTS

## Instructions

### 1. Calculate NPS Score
For $2 segment in $1 period: Segment responses (Promoters 9-10, Passives 7-8, Detractors 0-6), calculate NPS (% Promoters - % Detractors), compare to previous period and benchmark (SaaS B2B: 30-50 good, 50-70 excellent).

### 2. Analyze Open-Ended Feedback
Categorize detractor comments into themes: Product quality/bugs, missing features, poor support, pricing concerns, usability issues, competitive alternatives. Categorize promoter comments: Product excellence, support quality, ease of use, value/ROI, CSM relationship.

### 3. Identify Drivers
Correlate NPS with: Product usage (feature adoption, frequency), engagement (CSM touches, training), support metrics (ticket volume, CSAT), customer characteristics (segment, tenure, ARR). Determine top positive and negative drivers.

### 4. Segment Analysis
Break down NPS by: Customer segment (Enterprise, Mid-Market, SMB), tenure cohort (0-6 months, 6-12, 12+), product tier, geography, CSM assignment. Identify segments with highest/lowest NPS.

### 5. Plan Closed-Loop Follow-Up
Detractors: Immediate outreach (24h), root cause analysis, service recovery plan, re-survey in 60 days. Passives: Check-in call (1 week), identify path to promoter status, improvement opportunities. Promoters: Request reference/review (48h), case study opportunity, advocacy program invitation.

## Output Format
- Overall NPS score and trend (vs. previous period, vs. benchmark)
- Promoter/Passive/Detractor distribution and changes
- Top 5 detractor themes with specific quotes
- Top 5 promoter themes with specific quotes
- Driver analysis (correlation with metrics)
- Segment breakdown and insights
- Closed-loop follow-up plan (who, what, when)
- Action items for product, support, CS teams
- Target NPS improvement (30/60/90 days)

## Success Criteria
- Analysis completed within 2-3 hours
- All responses categorized by theme
- Drivers identified with statistical correlation
- Segment insights actionable
- Follow-up plan with clear ownership
- Product/support action items specific and prioritized
