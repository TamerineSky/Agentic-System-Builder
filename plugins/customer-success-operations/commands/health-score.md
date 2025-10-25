---
description: Calculate comprehensive customer health score with dimension breakdown, trending analysis, and risk assessment
argument-hint: [account-id] [timeframe]
version: "1.0.0"
tags: [health, scoring, risk]
model: sonnet
---

# Health Score Command

Calculate multi-dimensional health score for customer account with actionable recommendations.

## Context
Customer health scores predict churn risk and expansion potential through usage, engagement, sentiment, and financial indicators.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Health Data
For account $1 over $2 timeframe: Product usage metrics (DAU, feature adoption), engagement data (CSM touches, QBRs), sentiment indicators (NPS, CSAT, support tickets), financial metrics (ARR, payment status, utilization).

### 2. Calculate Dimension Scores
- Usage Score (0-100): DAU%, feature adoption%, login frequency, power user activity
- Engagement Score (0-100): Touchpoint frequency, response rates, QBR participation, executive involvement
- Sentiment Score (0-100): NPS, CSAT, support health, advocacy signals
- Financial Score (0-100): ARR growth, payment timeliness, contract utilization, expansion history

### 3. Compute Overall Health Score
Weighted average: (Usage × 35%) + (Engagement × 25%) + (Sentiment × 25%) + (Financial × 15%) = Overall Score (0-100)

### 4. Analyze Trends
Compare current score to 30/60/90 days ago. Calculate health velocity (points/day change). Identify improving vs. declining dimensions.

### 5. Identify Risks
Flag red indicators: Usage <40, engagement <50, sentiment <40, declining velocity >-0.5 points/day. List specific risk factors with evidence.

## Output Format
- Overall health score and color status (Green 80+, Yellow 60-79, Red <60)
- Dimension scores with benchmarks
- 30/60/90 day trend analysis and velocity
- Key risk factors prioritized by severity
- Positive indicators and strengths
- Recommended actions (next 7/30/90 days)
- Target health score and improvement plan

## Success Criteria
- Analysis completed in 10-15 minutes
- All four dimensions scored with supporting data
- Trends identified with specific evidence
- 3-5 prioritized action items provided
- Clear health trajectory and forecast
