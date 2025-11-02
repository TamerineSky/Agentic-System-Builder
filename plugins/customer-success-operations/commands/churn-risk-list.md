---
description: Generate prioritized list of at-risk customers with churn probability, leading indicators, and intervention recommendations
argument-hint: [timeframe] [segment]
version: "1.0.0"
tags: [churn, risk, retention]
model: sonnet
---

# Churn Risk List Command

Identify and prioritize at-risk customers for proactive retention efforts.

## Context
Early identification of churn risk enables timely intervention with higher save rates (70% at medium risk vs. 35% at critical risk).

## Requirements
$ARGUMENTS

## Instructions

### 1. Define Scope
Generate churn risk list for $2 segment over $1 timeframe (e.g., Q4, next 90 days, December renewals).

### 2. Apply Churn Prediction Model
For each customer: Calculate churn risk score (0-100) using leading indicators (usage decline, engagement drop, support escalations, sentiment deterioration, stakeholder changes, competitive signals).

### 3. Segment by Risk Tier
- Critical Risk (85-100): 75%+ churn probability, immediate action
- High Risk (65-84): 55-75% churn probability, urgent intervention
- Medium Risk (45-64): 35-55% churn probability, proactive outreach
- Low Risk (0-44): <35% churn probability, monitor

### 4. Prioritize by Impact
Sort within risk tiers by: Account ARR (revenue at risk), strategic value (enterprise/reference customers), time to renewal (urgency), save probability (realistic recovery chance).

### 5. Identify Risk Drivers
For each at-risk account: List top 3 leading indicators triggering risk, provide specific evidence (metrics, events, behavior changes), estimate time-to-churn if no intervention.

### 6. Recommend Interventions
Match risk tier to playbook: Critical = Executive escalation + emergency save play, High = Intensive CSM engagement + issue resolution, Medium = Proactive improvement plan + stakeholder engagement.

## Output Format
- Executive summary (total at-risk ARR, count by tier, estimated churn impact)
- Critical risk accounts (top 10, immediate action required)
- High risk accounts (next 15-20, urgent intervention)
- Medium risk accounts (monitoring list)
- Risk driver analysis (patterns across portfolio)
- Intervention plan with resource requirements
- Expected outcomes (save rate projections, investment ROI)

## Success Criteria
- Analysis completed in 30-45 minutes
- All customers scored and risk-tiered
- Top 25 at-risk accounts detailed with specific interventions
- Resource allocation plan provided (CSM time, save play budget)
- Expected save rate and revenue impact quantified
