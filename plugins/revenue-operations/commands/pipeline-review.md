---
description: Conduct comprehensive pipeline health review analyzing coverage, velocity, stage distribution, and deal risks with actionable recommendations
argument-hint: [period] [team-name]
version: "1.0.0"
tags: [pipeline, analysis, health, review]
tool_access: [Read, Write, Grep]
model: sonnet
---

# Pipeline Review Command

Perform systematic pipeline health assessment for a specified period and team, identifying strengths, risks, and improvement opportunities.

## Context

Sales leaders need regular pipeline reviews to ensure adequate coverage, identify bottlenecks, spot at-risk deals, and take corrective action before quota attainment is jeopardized.

## Requirements
$ARGUMENTS

## Instructions

### 1. Data Collection

Gather pipeline data for $1 (period) and $2 (team):
- All open opportunities with stages, values, close dates, probabilities
- Historical stage progression data
- Activity levels (calls, meetings, emails)
- Win/loss data from comparable periods
- Quota targets and current attainment

Sources: CRM (Salesforce/HubSpot), sales dashboards, historical reports

### 2. Pipeline Health Analysis

**Coverage Ratio:**
- Calculate: Total Pipeline Value / Remaining Quota
- Benchmark: 3-4x for new business, 2-3x late quarter
- Status: Green (3-4x), Yellow (2-3x), Red (<2x)

**Stage Distribution:**
- Early (Discovery/Qual): Target 40-50%
- Mid (Proposal/Negotiation): Target 35-45%
- Late (Verbal/Contract): Target 10-20%
- Identify imbalances (too front/back loaded)

**Velocity Metrics:**
- Average days in each stage vs. benchmark
- Deals >90 days old (zombie deals)
- Stage progression rate (% advancing vs. stalling)

**Deal Quality Scoring:**
- MEDDIC/BANT qualification scores
- Engagement levels (activity frequency, stakeholder breadth)
- Risk indicators (competitive presence, champion changes)

### 3. Risk Identification

Identify at-risk deals:
- High-value deals (>$250K) with low activity (<5 touches in 14 days)
- Deals overdue for stage progression (>1.5x benchmark time)
- Close dates pushed repeatedly
- Competitive threats identified
- Stakeholder changes (champion departure)

Calculate risk-adjusted forecast:
- Weighted pipeline using stage probabilities
- Apply risk penalties to at-risk deals
- Generate expected value forecast

### 4. Generate Insights and Recommendations

**Strengths to Leverage:**
- High-performing reps or segments
- Effective sales motions
- Strong pipeline generation sources

**Issues to Address:**
- Bottleneck stages
- Coverage gaps
- Deal quality concerns
- Rep-specific challenges

**Prioritized Actions:**
1. Deal-Specific Actions (Top 10 at-risk deals)
2. Process Improvements (systematic issues)
3. Pipeline Generation Needs (coverage gaps)
4. Coaching/Enablement (rep skill gaps)

## Output Format

**Executive Summary (1 page):**
- Overall pipeline health score (0-100)
- Coverage status and forecast
- Top 3 risks and mitigation actions
- Pipeline generation requirements

**Detailed Analysis:**
1. Pipeline health scorecard with all metrics
2. Stage distribution and velocity analysis
3. At-risk deal register with mitigation plans
4. Rep-level performance breakdown
5. Week-by-week action plan

**Visualizations:**
- Pipeline funnel by stage
- Coverage trend over time
- Deal age histogram
- Risk heatmap by rep/deal

## Success Criteria

- Pipeline review completed within 2 hours
- All key metrics calculated and benchmarked
- Top 10 at-risk deals have specific action plans
- Rep-level insights and coaching priorities identified
- Forecast updated with risk adjustments
- Action items assigned with owners and deadlines
- Follow-up review scheduled for next period
