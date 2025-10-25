---
name: nps-analysis
description: Net Promoter Score methodology, driver analysis, and action planning frameworks for measuring and improving customer loyalty. Use when analyzing NPS surveys, identifying satisfaction drivers, or developing improvement programs.
---

# NPS Analysis

Comprehensive framework for measuring, analyzing, and acting on Net Promoter Score data to drive customer loyalty and retention.

## When to Use This Skill

- Designing NPS survey programs
- Analyzing NPS results and trends
- Identifying drivers of promoter/detractor behavior
- Developing action plans from NPS feedback
- Benchmarking NPS across segments and cohorts
- Correlating NPS with churn and expansion outcomes
- Building closed-loop feedback systems

## Core Methodology

### NPS Calculation

**Survey Question**: "How likely are you to recommend [Product] to a friend or colleague?"
**Scale**: 0-10 (0 = Not at all likely, 10 = Extremely likely)

**Segmentation**:
- **Promoters** (9-10): Loyal enthusiasts, growth drivers
- **Passives** (7-8): Satisfied but unenthusiastic
- **Detractors** (0-6): Unhappy customers, churn/negative WOM risk

**Formula**:
```
NPS = % Promoters - % Detractors
Range: -100 to +100

Example:
60% Promoters - 15% Detractors = NPS of 45
```

### Benchmarks

**SaaS B2B NPS Benchmarks**:
- Excellent: 50-70
- Good: 30-50
- Acceptable: 10-30
- Poor: <10
- Critical: Negative

**Segment Benchmarks**:
- Enterprise: Typically 10-15 points lower (higher expectations)
- SMB: Typically 5-10 points higher (lower complexity)

## Driver Analysis

### Open-Ended Feedback Categorization

**Promoter Themes** (Why they recommend):
- Product quality and reliability
- Ease of use and user experience
- Customer support responsiveness
- Value for money / ROI
- Innovation and feature velocity
- Relationship with CSM

**Detractor Themes** (Why they don't recommend):
- Product bugs and quality issues
- Missing features / functionality gaps
- Poor onboarding or training
- Support responsiveness issues
- Pricing concerns
- Integration limitations
- Competitive alternatives

**Text Analysis Approach**:
```
1. Categorize responses into themes (manual or NLP)
2. Count mentions by theme
3. Correlate themes with NPS score
4. Identify top drivers (+ and -)

Example:
"Ease of use" mentioned by 72% of promoters
"Missing features" mentioned by 68% of detractors
```

### Statistical Driver Analysis

**Correlation Analysis**:
```
Correlate NPS with potential drivers:
- Product usage metrics (feature adoption, frequency)
- Engagement metrics (CSM touches, QBR attendance)
- Support metrics (ticket volume, resolution time)
- Outcome metrics (time-to-value, ROI realized)

High Correlation = Strong Driver

Example:
Feature adoption >70% → 85% likelihood of Promoter score
Support tickets >5/month → 62% likelihood of Detractor score
```

## Actionable Insights Framework

### Closed-Loop Follow-Up

**Promoters (9-10)**:
- **Action**: Request reference, case study, review
- **Timeline**: Within 48 hours of response
- **Owner**: CSM
- **Goal**: Convert enthusiasm into advocacy

**Passives (7-8)**:
- **Action**: Understand what would make them a promoter
- **Timeline**: Within 1 week
- **Owner**: CSM
- **Goal**: Move to promoter status

**Detractors (0-6)**:
- **Action**: Root cause analysis, service recovery
- **Timeline**: Within 24 hours
- **Owner**: CSM + Manager
- **Goal**: Prevent churn, restore satisfaction

### Action Planning Template

**For Detractors**:
```
1. Immediate outreach (apologize, acknowledge concern)
2. Deep-dive conversation (understand full context)
3. Issue resolution plan (specific actions, timeline)
4. Executive involvement (if strategic account)
5. Follow-up NPS (measure improvement)

Target: Convert 40-50% of detractors to passives/promoters
```

**For Passives**:
```
1. Schedule check-in call (within 1 week)
2. Ask: "What would make you a 9 or 10?"
3. Identify gaps (features, support, engagement)
4. Create improvement plan
5. Re-survey in 60-90 days

Target: Convert 30-40% of passives to promoters
```

## NPS Program Design

### Survey Cadence

**Relationship NPS** (Overall satisfaction):
- Frequency: Quarterly or semi-annually
- Target: All customers or random sample
- Goal: Track overall loyalty trends

**Transactional NPS** (Experience-specific):
- Frequency: After key events (onboarding, QBR, support case)
- Target: 100% of customers experiencing event
- Goal: Improve specific touchpoints

**Best Practice**: Combine both for comprehensive view

### Survey Delivery

**Email Surveys**:
- Pros: High reach, cost-effective
- Cons: Lower response rates (15-25%)
- Best for: Relationship NPS

**In-App Surveys**:
- Pros: Higher response rates (30-40%), contextual
- Cons: Limited to active users
- Best for: Transactional NPS

**Phone/Video Surveys**:
- Pros: Deepest insights, qualitative richness
- Cons: Resource-intensive, low scale
- Best for: Strategic accounts, detractors

### Response Rate Optimization

**Tactics**:
- Personalize from CSM (not generic email)
- Explain impact: "Your feedback shapes our roadmap"
- Keep short: 2-3 questions maximum
- Offer incentive: Gift card, donation to charity
- Mobile-optimize: 60%+ respond on mobile
- Optimal timing: Tuesday-Thursday, 10am-2pm

**Target**: 40-50% response rate (relationship NPS)

## NPS Analysis Techniques

### Trend Analysis

**Time-Series Tracking**:
```
Monitor NPS over time:
- Quarterly trends (improving/declining)
- Seasonal patterns
- Impact of product releases, initiatives
- Segment-specific trends

Example:
Q1: 42 → Q2: 45 → Q3: 48 → Q4: 46
Overall trend: Positive (+4 points annual)
Q4 dip: Investigate (holiday support issues?)
```

### Cohort Analysis

**NPS by Cohort**:
```
Compare NPS across customer cohorts:
- Acquisition cohort (Q1 2024 signups)
- Tenure cohort (0-6 months, 6-12 months, 12+ months)
- Segment cohort (Enterprise, SMB)

Insight: New customers (0-6 months) have higher NPS (52 vs. 42 overall)
Action: Identify what changes as customers mature
```

### Predictive Analysis

**NPS as Churn Predictor**:
```
Correlation with churn outcomes:
- Detractors: 45% churn rate within 12 months
- Passives: 12% churn rate
- Promoters: 3% churn rate

Use NPS as early warning signal
```

**NPS as Expansion Predictor**:
```
Correlation with expansion:
- Promoters: 38% expand within 12 months
- Passives: 12% expand
- Detractors: 2% expand

Prioritize expansion efforts on promoters
```

## Best Practices

1. **Act on Feedback**: Survey without action erodes trust
2. **Close the Loop**: Follow up with every detractor
3. **Share Results**: Communicate NPS to entire company
4. **Segment Analysis**: Don't just look at overall score
5. **Track Drivers**: Understand why, not just what
6. **Benchmark Externally**: Compare to industry, competitors
7. **Link to Outcomes**: Correlate NPS with churn, expansion, LTV
8. **Continuous Improvement**: Use NPS to drive product/service changes

## Common Pitfalls

- **Survey Fatigue**: Over-surveying reduces response rates
- **No Follow-Up**: Surveying without action damages relationships
- **Vanity Metric**: Celebrating high NPS without understanding drivers
- **Gaming**: Incentivizing NPS scores (distorts true sentiment)
- **Ignoring Passives**: Focus only on promoters/detractors, miss largest group

## Resources

- Net Promoter System methodology (Reichheld/Bain)
- NPS benchmarking reports (Retently, Delighted)
- Survey design best practices (Qualtrics, SurveyMonkey)
- Text analytics tools (sentiment analysis, theme extraction)
