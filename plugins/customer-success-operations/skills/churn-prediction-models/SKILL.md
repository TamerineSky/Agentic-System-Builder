---
name: churn-prediction-models
description: Predictive modeling techniques and frameworks for churn forecasting using leading indicators, statistical models, and intervention strategies. Use when building churn prediction algorithms, identifying at-risk customers, or designing retention programs.
---

# Churn Prediction Models

Advanced methodologies for predicting customer churn before it occurs, enabling proactive intervention and retention strategy development.

## When to Use This Skill

- Building or refining churn prediction models
- Identifying leading indicators of attrition
- Quantifying churn risk for individual accounts
- Forecasting portfolio-level churn rates
- Designing early warning systems
- Validating model accuracy and calibration
- Developing risk-specific intervention playbooks

## Core Methodologies

### 1. Logistic Regression Model

**Approach**: Statistical model predicting churn probability based on historical patterns

**Formula**:
```
P(churn) = 1 / (1 + e^-(β₀ + β₁X₁ + β₂X₂ + ... + βₙXₙ))

Where:
- P(churn) = Probability of churn (0-1)
- β = Coefficients (learned from historical data)
- X = Predictor variables (usage, engagement, sentiment)
```

**Key Predictors** (with typical coefficients):
- Usage decline %: -0.85 (strongest predictor)
- Support escalations: +0.62
- NPS score: -0.54
- Engagement frequency: -0.48
- Payment delays: +0.38
- Champion departure: +0.72

**Model Output**: 0-100 churn risk score

### 2. Leading Indicator Framework

**Tiered Indicator System**:

**Tier 1 - Critical Indicators (70-90% churn correlation):**
- Usage drop >40% in 30 days
- Executive sponsor departure
- 3+ escalated support tickets
- Competitive evaluation mentions
- "Pause" or "cancel" discussions

**Tier 2 - Warning Indicators (40-70% correlation):**
- NPS decline >2 points
- Missed 2+ scheduled meetings
- Login frequency drop >25%
- Feature adoption plateau
- Budget scrutiny comments

**Tier 3 - Watch Indicators (20-40% correlation):**
- Support ticket increase
- Response time degradation
- Single-user dependency
- Contract utilization <50%

**Scoring**:
```
Risk Score = (Tier 1 count × 30) + (Tier 2 count × 15) + (Tier 3 count × 5)

0-30: Low risk
31-60: Medium risk
61-85: High risk
86-100: Critical risk
```

### 3. Time-to-Churn Prediction

**Survival Analysis Approach**:

Estimate time until churn event based on current state and velocity:

```
Time-to-Churn = f(current_health, health_velocity, renewal_date)

Example:
- Health score: 55/100
- Velocity: -1.2 points/day
- Renewal: 90 days

Projection:
- 30-day score: 55 - (1.2 × 30) = 19 (critical)
- 60-day score: Below zero (churn likely)
- Time-to-churn estimate: 45 days
```

**Urgency Classification**:
- Immediate (<30 days): Emergency intervention
- Near-term (30-60 days): Standard save play
- Future (60-90 days): Proactive improvement
- Monitoring (>90 days): Regular cadence

## Model Building Process

### Step 1: Historical Data Analysis

**Collect Churned Customer Data** (last 12-24 months):
- Final 90 days of activity before churn
- Health scores, usage patterns, support tickets
- Sentiment indicators, engagement metrics
- Stakeholder changes, competitive signals

**Identify Patterns**:
```sql
-- Example: Average metrics 30 days before churn
SELECT
  AVG(health_score) AS avg_health,
  AVG(usage_score) AS avg_usage,
  AVG(nps) AS avg_nps,
  COUNT(*) FILTER (WHERE escalations > 0) AS pct_with_escalations
FROM churned_customers
WHERE days_before_churn BETWEEN 0 AND 30
```

### Step 2: Feature Engineering

**Create Predictive Features**:
- **Velocity features**: Rate of change (usage_30day_delta, health_velocity)
- **Trend features**: Improving vs. declining patterns
- **Event features**: Binary flags (champion_departed, escalation_exists)
- **Ratio features**: Engagement_rate, utilization_percentage
- **Time features**: Days_since_last_login, days_to_renewal

### Step 3: Model Training and Validation

**Split Data**:
- Training set: 70% of historical churns
- Validation set: 15% for tuning
- Test set: 15% for final accuracy measurement

**Measure Accuracy**:
```
Precision: Of customers predicted to churn, % who actually churned
Recall: Of customers who churned, % we predicted

F1 Score = 2 × (Precision × Recall) / (Precision + Recall)

Target: F1 Score > 0.75 (industry benchmark)
```

**Confusion Matrix Analysis**:
```
                Predicted Churn    Predicted Retain
Actual Churn         TP (78%)         FN (22%)
Actual Retain        FP (18%)         TN (82%)

True Positive: Correctly identified churn (save opportunity)
False Negative: Missed churn (lost customer)
False Positive: False alarm (wasted resources)
True Negative: Correctly identified healthy (efficient)
```

### Step 4: Calibration and Refinement

**Probability Calibration**:
- Model says 70% churn risk → Validate 70% actually churn
- Adjust thresholds if model over/under-predicts

**Continuous Improvement**:
- Monthly: Review false positives/negatives
- Quarterly: Retrain model with new data
- Annually: Reassess feature importance

## Intervention Strategies

### Risk-Specific Playbooks

**Critical Risk (85-100 score):**
- **Action**: Executive escalation, emergency save play
- **Investment**: $15K-30K per account
- **Success Rate**: 35-45% (challenging)
- **Timeline**: Immediate (48-72 hours)

**High Risk (65-84 score):**
- **Action**: Intensive CSM engagement, issue resolution
- **Investment**: $5K-15K per account
- **Success Rate**: 55-65%
- **Timeline**: 1-2 weeks

**Medium Risk (45-64 score):**
- **Action**: Proactive outreach, health improvement plan
- **Investment**: $2K-5K per account
- **Success Rate**: 70-80%
- **Timeline**: 30-45 days

**Low Risk (0-44 score):**
- **Action**: Monitor, standard engagement
- **Investment**: Minimal
- **Success Rate**: 90%+ (mostly false alarms)
- **Timeline**: Regular cadence

### Save Play Economics

**ROI Calculation**:
```
Expected Value = (Account ARR × LTV Multiplier × Save Probability) - Save Investment

Example:
Account ARR: $50,000
LTV: 2.5 years = $125,000
Save Probability: 55%
Save Investment: $10,000

EV = ($125,000 × 0.55) - $10,000 = $68,750 - $10,000 = $58,750 ROI

Proceed if EV > 0 (positive ROI)
```

## Best Practices

1. **Balance False Positives and Negatives**: Missing churn worse than false alarms, but too many alerts cause fatigue
2. **Update Model Frequently**: Customer behavior changes, retrain quarterly
3. **Explain Predictions**: Show CSMs why model flagged account (build trust)
4. **Combine Model + Human Judgment**: Model provides score, CSM validates context
5. **Track Intervention Outcomes**: Did save play work? Improve playbooks based on results
6. **Segment-Specific Models**: Enterprise vs. SMB churn differently, build separate models
7. **Early Action Wins**: Intervene at medium risk (70% save rate) vs. critical risk (40%)

## Resources

- SciKit-Learn documentation (Python ML library for logistic regression)
- Customer churn prediction research papers (academic models)
- CS platform ML features (Gainsight Einstein, Totango Zoe AI)
- Churn benchmarking reports (SaaS metrics standards)
