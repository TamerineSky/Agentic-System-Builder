---
description: Analyze customer escalation patterns, root causes, resolution effectiveness, and process improvement recommendations
argument-hint: [period] [segment]
version: "1.0.0"
tags: [escalations, support, quality]
model: sonnet
---

# Escalation Analysis Command

Comprehensive escalation pattern analysis with root cause identification and prevention strategies.

## Context
Escalations are high-risk events (62% higher churn risk) and indicators of systemic issues. Understanding patterns enables prevention and process improvement.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Escalation Data
For $2 segment in $1 period: All escalations (count, affected customers, ARR at risk), escalation details (issue type, severity, duration), resolution outcomes (resolved, partially resolved, unresolved, churned), customer impact (health score changes, NPS impact, churn outcomes).

### 2. Analyze Escalation Patterns
Calculate metrics: Escalation rate (escalations per 100 customers), Escalation concentration (% of customers with multiple escalations), Average time-to-resolution, Resolution effectiveness (% fully resolved), Customer outcome (churn rate for escalated vs. non-escalated). Identify trends over time (increasing/decreasing, seasonal patterns).

### 3. Categorize Root Causes
Group escalations by: Product issues (bugs, performance, integration failures), Feature gaps (missing functionality, competitive limitations), Service issues (support quality, CSM responsiveness), Onboarding failures (poor implementation, inadequate training), Pricing/commercial (billing disputes, contract issues), Expectation misalignment (sales overpromise, use case mismatch).

### 4. Assess Customer Impact
Measure escalation effects: Average health score drop (typically -30 to -40 points), NPS deterioration (typically -15 to -25 points), Churn rate impact (45-65% higher for escalated customers), Expansion impact (expansion rate drops from 30% to <5%), Time to recovery (avg 45-60 days to restore pre-escalation health).

### 5. Evaluate Response Effectiveness
Analyze resolution quality: Time-to-acknowledgment (< 4 hour SLA?), Time-to-resolution (by severity tier), Executive involvement rate, Service recovery actions (credits, apologies, remediation), Post-escalation follow-up (closed-loop confirmation), Customer satisfaction with resolution.

### 6. Develop Prevention Strategies
Identify improvements: Product (prioritize bugs/features causing escalations), Onboarding (prevent early-stage escalations 40% of total), Support (training, process, tools, staffing), Sales (qualification, expectation setting), Early warning (detect escalation triggers before they blow up), Service recovery (improve resolution process, reduce time-to-fix).

## Output Format
- Escalation summary (total count, rate, affected ARR, trend vs. prior period)
- Root cause breakdown (% by category, top 10 specific issues)
- Customer segment analysis (escalation rates by segment, ARR, tenure)
- Resolution effectiveness (time-to-resolution, outcome rates)
- Customer impact analysis (health, NPS, churn correlation)
- High-impact escalations (critical accounts, repeat escalators, revenue at risk)
- Prevention recommendations (by category: product, support, onboarding, sales)
- Process improvement plan (response protocols, service recovery, monitoring)
- Expected impact (reduced escalations, improved outcomes, churn prevention)

## Success Criteria
- Analysis completed in 2-3 hours
- All escalations categorized by root cause
- Patterns identified (not just individual cases)
- Customer impact quantified (health, churn, revenue)
- Resolution effectiveness measured objectively
- Prevention strategies specific and actionable
- Cross-functional action items (Product, Support, CS, Sales)
- Expected ROI quantified (reduction targets, churn prevention value)
