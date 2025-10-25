---
name: segmentation-methods
description: Customer segmentation frameworks using firmographic, behavioral, and value-based clustering to enable personalized engagement and resource optimization. Use when designing segmentation strategies, building cohorts, or developing segment-specific playbooks.
---

# Segmentation Methods

Comprehensive methodologies for dividing customer base into meaningful, actionable segments that drive personalized engagement and operational efficiency.

## When to Use This Skill

- Designing customer segmentation frameworks
- Building engagement models and service tiers
- Allocating CSM resources and portfolios
- Developing segment-specific playbooks
- Analyzing cohort retention and behavior
- Optimizing pricing and packaging strategies
- Forecasting segment-level metrics (churn, NRR, LTV)

## Core Segmentation Approaches

### 1. Value-Based Segmentation

**ARR Tiers** (Most common SaaS approach):

**Strategic/Enterprise (>$50K ARR)**
- % of Customer Base: 15-20%
- % of ARR: 50-60%
- Service Model: High-touch, dedicated CSM
- CSM Ratio: 1:8-15 accounts
- NRR Target: 125-140%

**Growth/Mid-Market ($15K-50K ARR)**
- % of Customer Base: 30-40%
- % of ARR: 30-35%
- Service Model: Standard CSM coverage
- CSM Ratio: 1:25-40 accounts
- NRR Target: 110-120%

**Core/SMB ($5K-15K ARR)**
- % of Customer Base: 30-40%
- % of ARR: 10-15%
- Service Model: Pooled CSM, digital-first
- CSM Ratio: 1:50-80 accounts
- NRR Target: 100-110%

**Starter (<$5K ARR)**
- % of Customer Base: 10-20%
- % of ARR: 2-5%
- Service Model: Tech-touch only
- CSM Ratio: No dedicated CSM
- NRR Target: 95-105%

### 2. Behavioral Segmentation

**Usage Patterns**:

**Power Users** (High engagement, high value)
- Characteristics: >80% feature adoption, daily usage
- Opportunity: Expansion, advocacy, case studies
- Risk: Low churn risk
- Engagement: Leverage for community, beta testing

**Standard Users** (Moderate engagement, stable)
- Characteristics: 40-70% adoption, weekly usage
- Opportunity: Adoption acceleration, tier upgrades
- Risk: Medium churn risk if stagnant
- Engagement: Use case expansion, training

**At-Risk Users** (Low engagement, declining)
- Characteristics: <30% adoption, infrequent usage
- Opportunity: Reactivation, value rediscovery
- Risk: High churn risk
- Engagement: Intensive re-onboarding, executive intervention

**Dormant Users** (No usage)
- Characteristics: No logins in 30+ days
- Opportunity: Win-back programs
- Risk: Very high churn risk
- Engagement: Save play or graceful offboarding

### 3. Lifecycle Stage Segmentation

**Onboarding (0-90 days)**
- Focus: Activation, first value, training
- Health Target: 75+ by Day 90
- Churn Risk: 15-20% (highest early-stage churn)
- CSM Activity: Intensive, structured onboarding

**Growth (91 days - 2 years)**
- Focus: Expansion, advocacy development
- Health Target: 80+
- Churn Risk: 5-8%
- CSM Activity: Proactive expansion, QBRs

**Mature (2-5 years)**
- Focus: Retention, sustained value, renewal
- Health Target: 75+
- Churn Risk: 3-5%
- CSM Activity: Business reviews, relationship deepening

**Late Stage (5+ years)**
- Focus: Retention, potential refresh/migration
- Health Target: 70+
- Churn Risk: 5-7% (can increase if product ages)
- CSM Activity: Innovation discussions, modernization

### 4. Health & Risk Segmentation

**Champions** (Green health, expanding)
- % of Base: 30-35%
- Characteristics: Health 80+, NPS 8+, expanding
- Strategy: Harvest advocacy, expand further, reduce touch
- CSM Time: 15% of portfolio time

**Stable** (Green health, flat)
- % of Base: 25-30%
- Characteristics: Health 75-85, satisfied but not growing
- Strategy: Identify expansion opportunities, maintain
- CSM Time: 20% of portfolio time

**At-Risk** (Yellow health)
- % of Base: 25-30%
- Characteristics: Health 60-75, some concerns
- Strategy: Proactive improvement, prevent decline
- CSM Time: 35% of portfolio time

**Critical** (Red health)
- % of Base: 10-15%
- Characteristics: Health <60, high churn risk
- Strategy: Save plays, triage, intensive intervention
- CSM Time: 30% of portfolio time

## Advanced Segmentation Techniques

### RFM Analysis (Recency, Frequency, Monetary)

**Recency**: How recently did customer engage?
- R5: Engaged in last 7 days (high)
- R1: No engagement in 90+ days (low)

**Frequency**: How often do they use product?
- F5: Daily usage (high)
- F1: Monthly or less (low)

**Monetary**: How much revenue do they generate?
- M5: Top 20% by ARR (high)
- M1: Bottom 20% by ARR (low)

**Combined Score**: R + F + M (scale 3-15)
- 13-15: VIP segment (retain, expand)
- 10-12: Solid customers (maintain, grow)
- 7-9: At-risk (improve engagement)
- 3-6: Likely to churn (save or let go)

### Persona-Based Segmentation

**Technical Buyer Persona**
- Characteristics: Engineering-led, values integrations, API usage
- Engagement: Technical workshops, developer resources
- Expansion: API tiers, integration packages

**Business Buyer Persona**
- Characteristics: ROI-focused, exec sponsor, business outcomes
- Engagement: Executive QBRs, ROI reports
- Expansion: User seats, enterprise features

**Champion-Led Persona**
- Characteristics: Internal advocate, drives adoption
- Engagement: Empower champion, co-marketing
- Expansion: Department expansion, advocacy programs

## Implementation Framework

### Step 1: Segment Definition

**Criteria for Good Segments**:
1. **Measurable**: Can be quantified with available data
2. **Substantial**: Large enough to justify different treatment
3. **Accessible**: Can be reached through different channels
4. **Differentiable**: Respond differently to strategies
5. **Actionable**: Can execute distinct playbooks

### Step 2: Segment Assignment Logic

**Multi-Dimensional Segmentation**:
```
Primary: Value tier (ARR-based)
Secondary: Health/risk status
Tertiary: Lifecycle stage
Quaternary: Behavioral pattern

Example:
"Strategic + At-Risk + Mature + Declining Usage"
= High-priority save play candidate
```

### Step 3: Segment-Specific Strategies

**Strategic + Healthy**:
- Engagement: Quarterly exec QBRs, dedicated CSM
- Cadence: Weekly touchpoints, monthly check-ins
- Focus: Expansion, advocacy, innovation partnership
- Metrics: 130% NRR, <2% churn, 90% reference-able

**Core + At-Risk**:
- Engagement: Pooled CSM, automated health campaigns
- Cadence: As-needed touchpoints, triggered outreach
- Focus: Stabilization, value reinforcement
- Metrics: 100% retention, break-even NRR

### Step 4: Dynamic Segmentation

**Segment Migration Rules**:
- **Upward**: ARR growth >20%, health improvement to green
- **Downward**: ARR contraction, health decline to red
- **Review Frequency**: Quarterly segment review and reassignment

**Transition Management**:
- Communicate segment changes to customers (when beneficial)
- Warm handoffs between CSMs if reassigned
- Maintain continuity during transitions

## Best Practices

1. **Start Simple**: Begin with 3-4 segments, add complexity as needed
2. **Validate with Data**: Ensure segments have distinct outcomes (churn, NRR)
3. **Align Resources**: Match CSM skills and capacity to segment needs
4. **Measure Performance**: Track metrics by segment, refine strategies
5. **Avoid Over-Segmentation**: Too many segments = operational complexity
6. **Dynamic, Not Static**: Allow segment migration as customers evolve
7. **Transparent Criteria**: Clear rules for segment assignment (avoid bias)

## Common Pitfalls

- **ARR-Only Segmentation**: Ignores high-potential small accounts
- **Static Segments**: Customers evolve, segments should too
- **Operational Disconnect**: Segments defined but not operationalized
- **Inconsistent Application**: Segment rules applied inconsistently
- **No Validation**: Segments not validated against actual outcomes

## Resources

- Customer segmentation case studies (SaaS companies)
- Statistical clustering techniques (k-means, hierarchical)
- CS platform segmentation features (Gainsight, Totango rules engines)
- Engagement model design frameworks
