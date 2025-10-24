---
description: Analyze forecast accuracy calculating MAPE, bias, and variance patterns with recommendations for forecast improvement
argument-hint: [lookback-period] [granularity]
version: "1.0.0"
tags: [forecast, accuracy, improvement]
model: sonnet
---

# Forecast Accuracy Analysis Command

Systematic forecast accuracy measurement and improvement recommendations.

## Context
Measuring forecast accuracy enables continuous improvement and builds credibility with stakeholders.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Historical Data
For $1 lookback period at $2 granularity: All forecasts submitted (weekly/monthly/quarterly), actual outcomes, forecast categories used, methodologies applied.

### 2. Calculate Accuracy Metrics
- MAPE (Mean Absolute Percentage Error): Average |Forecast - Actual| / Actual
- Forecast Bias: Average (Forecast - Actual) / Actual (positive = over-forecast)
- Hit Rate: % of periods within ±X% of actual
- By rep, by methodology, by time horizon

### 3. Identify Patterns
- Accuracy by forecast horizon (30/60/90 days out)
- Accuracy by rep or team
- Accuracy by segment or deal size
- Consistent over/under-forecasting (bias)
- Forecast volatility (changes week to week)

### 4. Root Cause Analysis
Common causes: Deal slippage patterns, rep optimism/sandbagging, methodology weaknesses, external factors

### 5. Improvement Recommendations
Methodology refinements, probability calibration, process changes, training needs, incentive alignment.

## Output Format
- Executive summary: Overall MAPE, bias, trend vs. prior periods
- Accuracy metrics dashboard by dimension
- Forecast variance waterfall (actual vs. forecast bridge)
- Rep-level accuracy scores with outliers flagged
- Pattern analysis: When/where forecasts are most/least accurate
- Root cause findings
- Prioritized improvement recommendations
- Target accuracy goals for next period

## Success Criteria
- Analysis completed within 1 week of period close
- MAPE calculated for all forecast horizons
- Rep-level and methodology-level accuracy quantified
- Patterns identified and explained
- Specific improvement recommendations with expected impact
- Action plan with owners and timeline
- Goals set for next period
