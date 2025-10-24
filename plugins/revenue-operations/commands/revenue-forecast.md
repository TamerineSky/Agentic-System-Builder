---
description: Generate comprehensive revenue forecast using multiple methodologies with confidence intervals, scenario analysis, and variance explanations
argument-hint: [forecast-period] [granularity]
version: "1.0.0"
tags: [forecasting, revenue, planning]
model: sonnet
---

# Revenue Forecast Command

Build multi-methodology revenue forecast with scenarios and confidence levels.

## Context
Accurate forecasts enable resource planning, investor communications, and proactive gap-closing actions.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Historical Context
- Last 4-6 quarters actuals and forecasts
- Historical win rates, deal cycles, seasonality
- Current pipeline snapshot
- Team capacity and changes
- Known market/business changes for $1

### 2. Apply Multiple Forecasting Methods

**Pipeline-Based:** Weight current pipeline by stage probabilities
**Historical Trend:** Apply growth rates and seasonal adjustments
**Capacity Model:** Calculate team productivity × headcount
**Statistical:** Run regression on leading indicators

### 3. Create Ensemble Forecast
- Combine methods with appropriate weights (pipeline 40%, historical 30%, capacity 20%, statistical 10%)
- Generate base case, conservative (P90), and upside (P10) scenarios
- Document assumptions and sensitivities

### 4. Variance Analysis
Compare to previous forecast, explain changes in deal-specific and trend factors.

## Output Format
- Executive Summary with forecast range and confidence
- Methodology details and weights
- Scenario waterfall showing conservative/base/upside
- Top 10 deals analysis
- Variance bridge from prior forecast
- Risks and opportunities identified

## Success Criteria
- Forecast completed within 4 hours
- All methodologies applied and documented
- Scenarios clearly differentiated
- Assumptions explicitly stated
- Variance to prior forecast explained
- Confidence levels assigned (P10/P50/P90)
