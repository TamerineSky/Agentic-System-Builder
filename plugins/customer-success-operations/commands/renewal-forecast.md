---
description: Generate renewal forecast with risk assessment, revenue projections, and retention strategy for upcoming renewal cohort
argument-hint: [cohort/period] [segment]
version: "1.0.0"
tags: [renewal, retention, forecast]
model: sonnet
---

# Renewal Forecast Command

Comprehensive renewal forecast with risk-adjusted projections and retention planning.

## Context
Accurate renewal forecasting enables resource planning, revenue prediction, and proactive risk mitigation. Early renewal outreach (T-90 days) improves retention 18-25%.

## Requirements
$ARGUMENTS

## Instructions

### 1. Define Renewal Cohort
Identify customers renewing in $1 period within $2 segment (e.g., Q4 2024 renewals, Enterprise segment, December renewals).

### 2. Assess Renewal Risk
For each renewing customer: Calculate renewal probability (0-100%) based on health score, engagement levels, sentiment (NPS, CSAT), stakeholder stability (champion status), competitive activity, budget signals, expansion/contraction indicators. Classify risk tier (High confidence 90-100%, Likely 75-89%, At-risk 50-74%, High risk <50%).

### 3. Project Renewal Outcomes
For each customer: Forecast scenario (renew at current ARR, expand, flat, contract, churn), revenue projection (expected ARR post-renewal), confidence level (probability-weighted), timing estimate (early/on-time/late renewal).

### 4. Calculate Portfolio Metrics
Aggregate forecast: Total renewing ARR, Expected retained ARR (probability-weighted), Gross Revenue Retention (GRR) forecast, Logo retention rate forecast, At-risk ARR requiring intervention, Expansion ARR opportunity within cohort.

### 5. Identify Intervention Priorities
Stratify actions: High-risk renewals (executive escalation, save plays, concessions), At-risk renewals (proactive engagement, issue resolution), Likely renewals (secure early commitment, explore expansion), Expansion opportunities (whitespace analysis, upsell campaigns).

### 6. Develop Retention Strategy
Create action plan: T-90 days: Renewal outreach begins, health check, stakeholder engagement, T-60 days: Renewal proposal delivered, ROI review, expansion discussion, T-30 days: Negotiation, contracting, commitment secured, T-0: Renewal closed, celebrate, post-renewal success plan.

## Output Format
- Executive summary (total renewing ARR, GRR forecast, logo retention forecast, at-risk ARR)
- Renewal cohort breakdown (high confidence, likely, at-risk, high risk)
- Account-by-account forecast (renewal probability, expected ARR, risk factors)
- Revenue waterfall (starting ARR, churn, contraction, flat, expansion, ending ARR)
- Risk mitigation plan (high-priority accounts, intervention strategies, resource requirements)
- Expansion opportunities (upsell/cross-sell within renewal cohort)
- Renewal timeline and milestones (T-90/T-60/T-30 activities)
- Resource allocation (CSM focus areas, executive involvement, save play budget)
- Expected outcomes (best/base/worst case scenarios)

## Success Criteria
- Forecast completed 90+ days before renewal period
- All renewing customers assessed and risk-tiered
- Revenue projections probability-weighted (not overly optimistic)
- High-risk accounts detailed with specific intervention plans
- Resource requirements quantified (CSM time, budget)
- Timeline established with clear milestones and ownership
- Scenarios modeled (best/base/worst case GRR and logo retention)
