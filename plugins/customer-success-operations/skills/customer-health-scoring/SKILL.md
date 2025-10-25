---
name: customer-health-scoring
description: Comprehensive framework for multi-dimensional customer health assessment using product usage, engagement, sentiment, and financial indicators. Use when building health score models, identifying risk factors, or establishing health benchmarks.
---

# Customer Health Scoring

A systematic methodology for quantifying customer health across multiple dimensions to enable proactive intervention, resource prioritization, and outcome prediction.

## When to Use This Skill

- Designing or refining customer health score models
- Identifying leading indicators of churn or expansion
- Benchmarking health scores across segments or cohorts
- Building early warning systems for at-risk accounts
- Prioritizing CSM portfolios and resource allocation
- Measuring effectiveness of health improvement initiatives
- Creating automated health scoring in CS platforms

## Core Principles

### 1. Multi-Dimensional Assessment

Health is not a single metric - it's a composite of multiple dimensions:

**Product Usage (Typical Weight: 30-35%)**
- Daily/Weekly Active Users (DAU/WAU)
- Feature adoption breadth and depth
- Login frequency and session duration
- Power user engagement
- Stickiness and habit formation

**Engagement (Typical Weight: 25-30%)**
- CSM touchpoint frequency and quality
- Executive sponsor involvement
- Training and certification completion
- QBR participation and outcomes
- Community and support engagement

**Sentiment (Typical Weight: 20-25%)**
- NPS and CSAT scores
- Support ticket patterns and escalations
- Survey feedback and verbatims
- Renewal conversation tone
- Reference-ability and advocacy

**Financial (Typical Weight: 15-20%)**
- ARR/MRR growth or contraction
- Payment timeliness
- Contract utilization (seats, features)
- Expansion revenue history
- Budget allocation signals

### 2. Health Score Formula

```
Health Score = (Usage × 35%) + (Engagement × 25%) + (Sentiment × 25%) + (Financial × 15%)

Scale: 0-100
- 80-100: Green (Healthy)
- 60-79: Yellow (At-Risk)
- 0-59: Red (Critical)
```

**Dimension Scoring (Each 0-100):**

**Usage Score:**
```
Usage = (DAU% × 40) + (Feature Adoption% × 30) + (Frequency Score × 20) + (Depth Score × 10)

DAU%: Active users / Total seats
Feature Adoption%: Features used / Features available
Frequency: Logins per week vs. benchmark
Depth: Advanced feature usage vs. basic
```

**Engagement Score:**
```
Engagement = (Touchpoint Quality × 35) + (Executive Involvement × 25) + (Training × 20) + (Community × 20)

Touchpoint Quality: Meaningful interactions per month
Executive Involvement: Sponsor engagement level
Training: Certification completion rate
Community: Forum posts, event attendance
```

**Sentiment Score:**
```
Sentiment = (NPS Normalized × 40) + (CSAT × 30) + (Support Health × 20) + (Advocacy × 10)

NPS: Convert -100 to +100 scale to 0-100
CSAT: Convert 1-5 scale to 0-100
Support Health: Inverse of escalations + ticket sentiment
Advocacy: Reference calls, case studies, reviews
```

**Financial Score:**
```
Financial = (ARR Trend × 40) + (Payment Health × 30) + (Utilization × 20) + (Expansion × 10)

ARR Trend: Growth rate past 12 months
Payment: On-time payment record
Utilization: % of contracted value being used
Expansion: Historical upsell/cross-sell activity
```

### 3. Leading vs. Lagging Indicators

**Leading Indicators (Predict Future State):**
- Usage decline (predicts churn 60-90 days ahead)
- Engagement drop-off (predicts churn 45-60 days ahead)
- Support ticket spike (predicts dissatisfaction 30-45 days ahead)
- Champion departure (predicts risk 30-90 days ahead)

**Lagging Indicators (Reflect Current State):**
- NPS score (reflects past experience)
- Renewal outcome (final result)
- Financial metrics (trailing indicators)

**Balance**: Weight leading indicators more heavily (70-80%) for predictive power.

### 4. Trending and Velocity

Single snapshot scores are less valuable than trends:

```
Health Velocity = (Current Score - Score 30 Days Ago) / 30 Days

Declining Fast: -0.5 points/day or more (alarm)
Declining: -0.2 to -0.5 points/day (concern)
Stable: -0.2 to +0.2 points/day (monitor)
Improving: +0.2 to +0.5 points/day (positive)
Improving Fast: +0.5 points/day or more (excellent)
```

**Risk Assessment:**
- Red account improving fast: Recovery possible
- Yellow account declining fast: Urgent intervention needed
- Green account declining: Early warning, proactive outreach

## Implementation Framework

### Step 1: Define Dimensions and Weights

**Segment-Specific Weights** (adjust by customer type):

**Enterprise Customers:**
- Usage: 30% (complex, multi-department)
- Engagement: 30% (relationship-driven)
- Sentiment: 25% (strategic importance)
- Financial: 15% (stable contracts)

**SMB Customers:**
- Usage: 40% (product-driven adoption)
- Engagement: 20% (lower touch)
- Sentiment: 25% (vocal feedback)
- Financial: 15% (price-sensitive)

### Step 2: Establish Benchmarks

**Data Collection (Historical Analysis):**
- Churned customers: What were their average scores 30/60/90 days before churn?
- Expanded customers: What scores preceded expansion?
- Healthy customers: What's the baseline healthy score?

**Benchmark Thresholds:**
```
Churn Risk Analysis:
- Customers with score <60: 78% churn within 90 days
- Customers with score 60-69: 34% churn within 90 days
- Customers with score 70-79: 12% churn within 90 days
- Customers with score 80+: 3% churn within 90 days

Set Yellow threshold: 60 (where churn risk accelerates)
Set Green threshold: 80 (where churn risk minimal)
```

### Step 3: Build Scoring Logic

**Data Sources:**
- Product analytics: Usage metrics (Amplitude, Mixpanel, Pendo)
- CS platform: Engagement data (Gainsight, Totango, ChurnZero)
- CRM: Financial data (Salesforce, HubSpot)
- Survey tools: NPS/CSAT (Delighted, Qualtrics)
- Support: Tickets and sentiment (Zendesk, Intercom)

**Calculation Frequency:**
- Real-time: Usage metrics (daily updates)
- Weekly: Engagement and sentiment
- Monthly: Financial metrics
- Overall score: Recalculated daily with latest data

### Step 4: Automate and Alert

**Automated Triggers:**
- Score drops below 60: Alert CSM immediately
- Score drops 10+ points in 7 days: Alert CSM
- Score <70 with renewal in 90 days: Alert manager
- Usage dimension <40: Trigger adoption playbook

**Dashboard Views:**
- Portfolio health distribution (red/yellow/green counts)
- Health trending (improving/declining accounts)
- Risk concentration (% of ARR in red/yellow)
- Dimension breakdown (identify systematic issues)

## Common Patterns and Insights

### Pattern 1: Usage Leading Indicator

**Observation**: Usage decline precedes all other dimensions
- 85% of churned customers showed usage decline 60-90 days before churn
- Engagement/sentiment decline followed 30-45 days later

**Action**: Weight usage heavily, trigger proactive outreach at usage <60

### Pattern 2: Champion Departure Impact

**Observation**: Stakeholder changes cause 30-40 point health drops
- Usage typically drops 40% when champion leaves
- Re-engagement takes 45-60 days on average

**Action**: Track stakeholder changes, immediate re-onboarding playbook

### Pattern 3: Support Ticket Sentiment

**Observation**: Support ticket tone predicts satisfaction decline
- 3+ frustrated tickets in 30 days = 65% NPS drop probability
- Escalations correlate with 45% higher churn risk

**Action**: Sentiment analysis on tickets, proactive intervention

### Pattern 4: Financial Metrics Lag

**Observation**: Financial indicators lag by 60-90 days
- Payment issues appear after disengagement begins
- ARR contraction occurs after usage/sentiment decline

**Action**: Don't rely on financial metrics for early warning

## Best Practices

1. **Validate with Outcomes**: Compare scores to actual churn/expansion to refine model
2. **Segment-Specific Models**: Enterprise vs. SMB require different weights
3. **Lifecycle Adjustments**: Onboarding customers scored differently (ramp curve)
4. **Manager Review**: Human review of score changes, not pure automation
5. **Continuous Calibration**: Revisit weights quarterly based on outcome data
6. **Transparency**: Share scores with customers (when helpful), build trust
7. **Action-Oriented**: Every score should drive specific CSM actions
8. **Avoid Gaming**: Don't incentivize CSMs purely on scores (behaviors distort)

## Tools and Templates

**CS Platform Health Score Setup:**
- Gainsight: Scorecard configuration with rules engine
- Totango: SuccessScore with custom dimensions
- ChurnZero: ChurnScore with API integrations

**SQL Query Template:**
```sql
-- Usage Score Calculation Example
WITH usage_metrics AS (
  SELECT
    account_id,
    AVG(dau / total_seats) * 40 AS dau_score,
    (COUNT(DISTINCT features_used) / 12) * 30 AS adoption_score,
    (logins_per_week / 4.5) * 20 AS frequency_score,
    (advanced_features_used / basic_features_used) * 10 AS depth_score
  FROM product_analytics
  WHERE date >= CURRENT_DATE - 30
  GROUP BY account_id
)
SELECT
  account_id,
  (dau_score + adoption_score + frequency_score + depth_score) AS usage_score
FROM usage_metrics
```

## Troubleshooting

**Issue**: Scores not correlating with outcomes
- **Solution**: Analyze false positives/negatives, adjust dimension weights

**Issue**: Too many accounts flagged as at-risk
- **Solution**: Recalibrate thresholds based on actual churn rates

**Issue**: Usage data incomplete or inaccurate
- **Solution**: Improve product instrumentation, fill data gaps

**Issue**: CSMs not acting on health scores
- **Solution**: Simplify presentation, connect scores to quota/comp, provide playbooks

## Resources

- Customer health score benchmark reports (Gainsight, TSIA)
- SaaS metrics guides (ChartMogul, ProfitWell)
- Statistical modeling tutorials (logistic regression for churn prediction)
