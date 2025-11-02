---
description: Comprehensive attrition trend analysis with driver identification and predictions
argument-hint: [period] [segment]
version: "1.0.0"
tags: [attrition, retention, turnover, predictive-analytics]
tool_access: [Read, Write, Bash]
model: sonnet
---

# Attrition Analysis & Prediction

Analyze attrition patterns, identify root causes, build predictive models, and develop targeted retention strategies.

## Context
Understanding and reducing regrettable attrition is critical for talent retention and cost management. Turnover costs 1.5-2x annual salary per departure.

## Requirements
- **Period**: Analysis timeframe (e.g., "last 12 months", "2024", "Q1-Q4")
- **Segment**: Specific cohort or "all" (department, level, tenure, manager)
- **Data Access**: HRIS data with departures, demographics, performance, compensation

## Instructions

### 1. Attrition Rate Calculation
- Overall attrition rate (monthly and annualized)
- Voluntary vs. involuntary segmentation
- Regrettable vs. non-regrettable classification
- Benchmark comparison (industry, company historical)

### 2. Cohort Analysis
Segment attrition by:
- Department and function
- Job level (IC, Manager, Director, VP)
- Tenure buckets (0-1yr, 1-3yr, 3-5yr, 5+yr)
- Manager (identify high-attrition teams)
- Demographics (gender, race, age) for fairness
- Performance rating (are we losing top performers?)

### 3. Survival Analysis
- Time-to-attrition curves by cohort
- Critical retention windows (0-6mo, 12-18mo, 3-5yr)
- Median tenure by segment
- Early warning indicators

### 4. Root Cause Analysis
Analyze exit interview data:
- Top 3-5 departure reasons (career growth, compensation, manager, work-life balance)
- Sentiment analysis and theme extraction
- Comparison across high vs. low attrition cohorts

### 5. Predictive Modeling
Build flight risk model with leading indicators:
- Compensation (compa-ratio <0.95)
- Performance trend (declining ratings)
- Engagement scores (<3.5/5)
- Tenure (3-5 year window)
- Manager changes
- Promotion/raise timing
- Generate risk scores for current employees

## Output Format
- Executive summary with key findings and attrition rate trends
- Cohort analysis table with attrition rates by segment
- Exit reason breakdown with percentages
- Flight risk report: Top 20 high-risk employees with scores
- Retention strategy recommendations by cohort
- ROI analysis of proposed retention programs

## Success Criteria
- Attrition rates calculated accurately across cohorts
- Root causes identified from exit data
- High-risk employees flagged with scores
- Targeted retention recommendations provided
- Expected impact quantified (attrition reduction, cost savings)

## Related Plugins
**Skills**: attrition-analysis, workforce-planning-models
**Agents**: attrition-predictor, compensation-analyst
**Commands**: /retention-analysis, /compensation-review
