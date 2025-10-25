---
name: engagement-scoring
description: Frameworks for measuring customer engagement through activity tracking, interaction quality, and behavioral pattern analysis. Use when building engagement models, scoring customer interactions, or identifying disengagement risks.
---

# Engagement Scoring

Systematic methodology for quantifying customer engagement to predict retention, identify at-risk accounts, and optimize CSM resource allocation.

## When to Use This Skill

- Building customer engagement scoring models
- Tracking CSM and customer interaction patterns
- Identifying disengagement early warning signals
- Optimizing engagement cadence and touchpoint mix
- Measuring engagement program effectiveness
- Correlating engagement with retention/expansion outcomes
- Designing scalable engagement models (high-touch to tech-touch)

## Core Framework

### Engagement Dimensions

**Dimension 1: Interaction Frequency** (Weight: 30%)
- CSM touchpoints (calls, meetings, emails)
- User logins and session frequency
- Community participation (forums, events)
- Support interactions (tickets, chat)
- Training and certification activity

**Dimension 2: Interaction Quality** (Weight: 35%)
- Response rates to CSM outreach
- Meeting attendance and participation
- QBR engagement and follow-through
- Depth of conversations (strategic vs. tactical)
- Executive sponsor involvement

**Dimension 3: Breadth of Engagement** (Weight: 20%)
- Number of engaged stakeholders
- Departmental reach across organization
- User role diversity (executives, managers, end-users)
- Multi-threading effectiveness
- Champion development

**Dimension 4: Product Engagement** (Weight: 15%)
- Feature adoption and exploration
- In-app behavior (clicks, actions, workflows)
- Power user emergence
- Integration usage
- Content consumption (help docs, videos)

### Engagement Score Formula

```
Engagement Score = (Frequency × 30%) + (Quality × 35%) + (Breadth × 20%) + (Product × 15%)

Scale: 0-100
- 80-100: Highly engaged (green)
- 60-79: Moderately engaged (yellow)
- 40-59: Low engagement (orange)
- 0-39: Disengaged (red)
```

## Scoring Methodology

### Frequency Scoring

**Activity Count (30-Day Window)**:
```
Points:
- CSM calls/meetings: 5 points each (max 40 points)
- Email exchanges: 2 points each (max 20 points)
- Product logins: 1 point per 5 logins (max 20 points)
- Support interactions: 3 points each (max 15 points)
- Training/events: 10 points each (max 20 points)

Total possible: 115 points → Normalize to 0-100
```

**Engagement Velocity**:
```
Velocity = (Current Activity - Previous Period Activity) / Previous Period

Positive velocity: Engagement increasing (good)
Negative velocity: Engagement declining (warning signal)

Example:
Previous 30 days: 12 touchpoints
Current 30 days: 8 touchpoints
Velocity: -33% (declining engagement, red flag)
```

### Quality Scoring

**Response Rate**:
```
CSM Outreach Response Rate = Responses / Total Outreach × 100

100% response: 100 points
75-99% response: 80 points
50-74% response: 60 points
25-49% response: 40 points
<25% response: 20 points
```

**Meeting Quality**:
```
Quality Indicators:
- On-time attendance: +20 points
- Active participation (questions, discussion): +20 points
- Executive attendees: +25 points
- Follow-through on action items: +25 points
- Strategic (vs. tactical) topics: +10 points

Total possible: 100 points
```

### Breadth Scoring

**Stakeholder Engagement**:
```
Points by role:
- Executive sponsor: 30 points
- Department champions: 15 points each (max 45 points)
- Power users: 5 points each (max 25 points)

Multi-department bonus: +20 points if 3+ departments

Total possible: 120 points → Normalize to 0-100
```

### Product Engagement Scoring

**Feature Usage**:
```
Adoption Score = (Features Used / Total Features) × 100

Weight by feature importance:
- Core features (must-have): 2x weight
- Advanced features (differentiation): 1.5x weight
- Basic features: 1x weight
```

## Engagement Patterns

### High-Engagement Pattern (Green)
- Characteristics: Multiple touchpoints, high response rates, executive involvement
- Behavior: Proactive communication, feature exploration, community participation
- Outcome: 95%+ retention, 40%+ expansion rate
- CSM Action: Focus on expansion, advocacy development

### Moderate-Engagement Pattern (Yellow)
- Characteristics: Regular but not enthusiastic, mostly tactical interactions
- Behavior: Responsive when reached out to, limited proactivity
- Outcome: 85-90% retention, 15-20% expansion rate
- CSM Action: Increase value demonstration, identify engagement gaps

### Low-Engagement Pattern (Orange)
- Characteristics: Declining responsiveness, missed meetings
- Behavior: Reactive only, decreasing product usage
- Outcome: 60-75% retention, <5% expansion rate
- CSM Action: Re-engagement campaign, root cause analysis

### Disengaged Pattern (Red)
- Characteristics: No response to outreach, dormant usage
- Behavior: Avoiding CSM, silent treatment
- Outcome: 30-45% retention (high churn risk)
- CSM Action: Executive escalation, save play, or graceful offboarding

## Early Warning Signals

### Disengagement Triggers

**Red Flags** (Immediate action required):
- 3+ consecutive unanswered emails/calls
- 2+ canceled meetings without reschedule
- QBR declined or no-showed
- Executive sponsor stops responding
- Product usage drop >50% in 30 days

**Yellow Flags** (Monitor closely):
- Response time increasing (24h → 72h+)
- Meeting participation declining (active → passive)
- Email tone changing (warm → formal/terse)
- Single-threaded relationship (champion only)
- Tactical-only conversations (no strategic dialogue)

## Engagement Optimization

### Ideal Engagement Cadence

**Strategic Accounts (High-Touch)**:
- CSM touchpoints: Weekly (calls/emails)
- Business reviews: Quarterly (QBRs)
- Executive check-ins: Monthly or quarterly
- Training/enablement: Ongoing, as-needed
- Total engagement score target: 85+

**Growth Accounts (Standard-Touch)**:
- CSM touchpoints: Bi-weekly
- Business reviews: Quarterly or semi-annual
- Executive check-ins: Semi-annual
- Training/enablement: Scheduled, cohort-based
- Total engagement score target: 75+

**Core Accounts (Low-Touch)**:
- CSM touchpoints: Monthly or as-needed
- Business reviews: Annual or trigger-based
- Executive check-ins: Renewal-based
- Training/enablement: Self-serve
- Total engagement score target: 65+

**Nurture Accounts (Tech-Touch)**:
- CSM touchpoints: None (automated campaigns only)
- Business reviews: None
- Executive check-ins: None
- Training/enablement: Automated, in-app
- Total engagement score target: 55+ (product-led)

### Engagement Program Design

**High-Value Activities** (Highest impact per hour):
1. Executive QBRs (strategic alignment)
2. Use case workshops (adoption acceleration)
3. Champion enablement (internal advocacy)
4. Success plan reviews (outcome tracking)
5. Product roadmap previews (future value)

**Moderate-Value Activities**:
1. Regular check-in calls (relationship maintenance)
2. Training sessions (skill development)
3. Support escalation resolution (issue mitigation)
4. Newsletter/content sharing (passive engagement)

**Lower-Value Activities** (Automate or minimize):
1. Administrative tasks (CRM updates)
2. Generic communications (not personalized)
3. Low-impact meetings (no clear agenda/outcome)

## Measurement & Analysis

### Engagement-to-Outcome Correlation

**Retention Correlation**:
```
Engagement Score 80+: 97% retention
Engagement Score 60-79: 88% retention
Engagement Score 40-59: 68% retention
Engagement Score <40: 42% retention

Correlation coefficient: 0.82 (strong positive)
```

**Expansion Correlation**:
```
Engagement Score 80+: 45% expansion rate
Engagement Score 60-79: 22% expansion rate
Engagement Score 40-59: 8% expansion rate
Engagement Score <40: 2% expansion rate

High engagement predicts expansion
```

### A/B Testing Engagement Models

**Test Different Approaches**:
- Engagement frequency (weekly vs. monthly touchpoints)
- Channel mix (calls vs. emails vs. in-app)
- Content types (educational vs. business-focused)
- Proactive vs. reactive outreach

**Measure**:
- Engagement score changes
- Customer satisfaction (NPS)
- Retention and expansion outcomes
- CSM efficiency (time invested vs. results)

## Best Practices

1. **Quality Over Quantity**: One strategic QBR > Five tactical calls
2. **Personalize**: Tailor engagement to customer preferences
3. **Be Proactive**: Don't wait for customers to reach out
4. **Multi-Thread**: Engage multiple stakeholders, not just one champion
5. **Track Trends**: Declining engagement > Absolute score
6. **Close Feedback Loop**: Ask customers about engagement preferences
7. **Automate Low-Touch**: Use tech for scaled, lower-tier accounts
8. **Link to Outcomes**: Prove engagement drives retention/expansion

## Resources

- Customer engagement platform features (Gainsight, Totango engagement tracking)
- Engagement model design frameworks (TSIA, Gainsight benchmarks)
- Digital engagement best practices (in-app messaging, automated campaigns)
- CSM productivity tools (calendaring, email tracking, automation)
