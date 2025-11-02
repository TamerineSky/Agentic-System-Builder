---
name: attrition-analysis
description: Attrition driver identification, predictive modeling, retention strategy development, and turnover cost analysis. Use when analyzing turnover patterns, building flight risk models, or designing retention interventions.
---

# Attrition Analysis

Comprehensive framework for analyzing attrition patterns, predicting flight risk, identifying root causes, and developing evidence-based retention strategies.

## When to Use This Skill

- Analyzing historical attrition trends and patterns
- Building predictive models to identify flight risks
- Investigating root causes of turnover
- Designing targeted retention interventions
- Calculating turnover costs and ROI of retention programs
- Conducting exit interview analysis and sentiment extraction

## Core Concepts

### 1. Attrition Rate Calculation
Standard formula for measuring turnover:
```
Monthly Attrition Rate = (Departures in Month / Average Headcount) × 100
Annual Attrition Rate = (Departures in Year / Average Headcount) × 100

Alternative (Annualized from Monthly):
Annual Rate = (1 - (1 - Monthly Rate)^12) × 100
```

### 2. Voluntary vs. Involuntary Turnover
- **Voluntary**: Employee-initiated departures
- **Involuntary**: Company-initiated terminations
- **Regrettable**: Loss of high-performers (retention focus)
- **Non-Regrettable**: Low performers or poor fits

### 3. Attrition Cost Model
Total cost of turnover per employee:
```
Turnover Cost = Direct Costs + Indirect Costs + Opportunity Costs

Direct: Recruiting, onboarding, training
Indirect: Lost productivity, team disruption
Opportunity: Delayed projects, lost knowledge

Rule of Thumb: 1.5-2.0x annual salary per departure
```

## Quick Start

```python
# Basic Attrition Analysis

def calculate_attrition_rate(departures, avg_headcount, period='monthly'):
    """
    Calculate attrition rate
    """
    rate = (departures / avg_headcount) * 100

    if period == 'annual':
        return rate
    elif period == 'monthly':
        # Return both monthly and annualized
        monthly_rate = rate
        annual_rate = (1 - (1 - monthly_rate/100)**12) * 100
        return {
            'monthly': round(monthly_rate, 2),
            'annualized': round(annual_rate, 2)
        }

def attrition_cost(departures, avg_salary, cost_multiplier=1.5):
    """
    Estimate total cost of attrition
    """
    return departures * avg_salary * cost_multiplier

# Example
rate = calculate_attrition_rate(departures=15, avg_headcount=500, period='monthly')
cost = attrition_cost(departures=15, avg_salary=100000, cost_multiplier=1.5)

print(f"Monthly Attrition: {rate['monthly']}%")
print(f"Annualized: {rate['annualized']}%")
print(f"Total Cost: ${cost:,}")
```

## Attrition Analysis Methodologies

### Pattern 1: Cohort Analysis

Analyze attrition by segments to identify high-risk groups.

```python
def cohort_attrition_analysis(employee_data):
    """
    Segment attrition by cohorts

    Cohorts: Department, Level, Tenure, Manager, Location
    """
    cohorts = {}

    for cohort_type in ['department', 'level', 'tenure_bucket', 'manager']:
        cohort_data = {}

        for employee in employee_data:
            cohort_value = employee[cohort_type]

            if cohort_value not in cohort_data:
                cohort_data[cohort_value] = {'headcount': 0, 'departures': 0}

            cohort_data[cohort_value]['headcount'] += 1
            if employee['departed']:
                cohort_data[cohort_value]['departures'] += 1

        # Calculate rates
        for cohort, data in cohort_data.items():
            data['attrition_rate'] = (data['departures'] / data['headcount']) * 100

        cohorts[cohort_type] = cohort_data

    return cohorts

# Example output:
# {
#   'department': {
#     'Engineering': {'headcount': 100, 'departures': 18, 'attrition_rate': 18%},
#     'Sales': {'headcount': 50, 'departures': 12, 'attrition_rate': 24%}
#   },
#   'tenure_bucket': {
#     '0-1 years': {'headcount': 80, 'departures': 24, 'attrition_rate': 30%},
#     '1-3 years': {'headcount': 120, 'departures': 18, 'attrition_rate': 15%}
#   }
# }
```

**High-Risk Cohorts** (typical patterns):
- **New Hires** (0-12 months): 25-35% attrition common
- **3-5 Year Tenure**: Career growth window, higher attrition
- **Below-Market Compensation**: 2-3x higher attrition
- **Low Engagement Scores**: <3.5/5 correlated with attrition

### Pattern 2: Survival Analysis

Model time-to-attrition and identify critical retention windows.

```python
import numpy as np

def survival_curve(tenure_at_departure, total_population):
    """
    Calculate survival curve (Kaplan-Meier estimator)

    Shows % of employees remaining at each tenure milestone
    """
    # Group by tenure milestones
    milestones = [3, 6, 12, 18, 24, 36, 48, 60]  # months
    survival_rates = []

    for milestone in milestones:
        departed_before = sum(1 for t in tenure_at_departure if t <= milestone)
        surviving = total_population - departed_before
        survival_rate = (surviving / total_population) * 100
        survival_rates.append({
            'month': milestone,
            'survival_rate': round(survival_rate, 1),
            'attrition_rate': round(100 - survival_rate, 1)
        })

    return survival_rates

# Example
tenure_at_departure = [2, 4, 8, 11, 14, 18, 22, 28, 36, 42]  # months
total_pop = 100

curve = survival_curve(tenure_at_departure, total_pop)
# Output: At 12 months, 90% survival rate (10% have left)
```

**Critical Retention Windows**:
- **0-6 months**: Onboarding quality critical
- **12-18 months**: First performance review, compensation cycle
- **24-36 months**: Career growth expectations, promotion cycle
- **3-5 years**: Vesting milestones, external market opportunities

### Pattern 3: Predictive Modeling (Flight Risk Scoring)

Build logistic regression model to predict attrition probability.

```python
from sklearn.linear_model import LogisticRegression
import pandas as pd

def build_flight_risk_model(historical_data):
    """
    Build predictive model for attrition risk

    Features: Tenure, Performance, Compensation, Engagement, Manager Tenure
    Target: Departed in next 90 days (0 or 1)
    """
    # Prepare features
    features = [
        'tenure_months',
        'performance_rating',       # 1-5 scale
        'compa_ratio',             # Salary vs market (0.8-1.2)
        'engagement_score',         # 1-5 scale
        'manager_tenure_months',
        'time_since_promotion',     # months
        'time_since_raise'          # months
    ]

    X = historical_data[features]
    y = historical_data['departed_90_days']

    # Train model
    model = LogisticRegression()
    model.fit(X, y)

    # Feature importance (coefficients)
    importance = pd.DataFrame({
        'feature': features,
        'coefficient': model.coef_[0],
        'impact': ['Increase' if c < 0 else 'Decrease' for c in model.coef_[0]]
    }).sort_values('coefficient')

    return model, importance

def score_flight_risk(model, employee_data):
    """
    Score current employees for flight risk
    """
    # Predict probability of attrition
    risk_scores = model.predict_proba(employee_data)[:, 1] * 100

    # Categorize risk
    def risk_category(score):
        if score >= 70:
            return 'Critical'
        elif score >= 50:
            return 'High'
        elif score >= 30:
            return 'Medium'
        else:
            return 'Low'

    results = []
    for idx, score in enumerate(risk_scores):
        results.append({
            'employee_id': employee_data.iloc[idx]['employee_id'],
            'risk_score': round(score, 1),
            'risk_category': risk_category(score)
        })

    return results
```

**Leading Indicators** (typical model features):
1. **Compensation**: Compa-ratio < 0.95 (below market)
2. **Performance**: Recent decline in performance rating
3. **Engagement**: Low survey scores (<3.5/5)
4. **Tenure**: 3-5 years (common departure window)
5. **Manager Change**: Recent manager change (3-6 months)
6. **Promotion**: Missed promotion cycle or long time since last promotion
7. **Workload**: Utilization >90% (burnout indicator)

## Advanced Topics

### Exit Interview Analysis

Extract themes and sentiment from exit interviews:

```python
def exit_interview_analysis(exit_data):
    """
    Categorize and analyze exit reasons
    """
    # Common exit reason categories
    categories = {
        'compensation': ['salary', 'pay', 'bonus', 'equity', 'compensation'],
        'career_growth': ['promotion', 'growth', 'career', 'development', 'learning'],
        'manager': ['manager', 'leadership', 'management', 'supervisor'],
        'work_life_balance': ['hours', 'balance', 'workload', 'burnout', 'flexibility'],
        'culture': ['culture', 'values', 'environment', 'fit'],
        'commute': ['commute', 'remote', 'location', 'relocation']
    }

    reason_counts = {cat: 0 for cat in categories}
    total_exits = len(exit_data)

    for exit_record in exit_data:
        reason_text = exit_record['reason_for_leaving'].lower()

        for category, keywords in categories.items():
            if any(keyword in reason_text for keyword in keywords):
                reason_counts[category] += 1

    # Calculate percentages
    reason_pcts = {
        cat: (count / total_exits) * 100
        for cat, count in reason_counts.items()
    }

    return sorted(reason_pcts.items(), key=lambda x: x[1], reverse=True)

# Example output:
# [
#   ('career_growth', 35%),
#   ('compensation', 28%),
#   ('manager', 18%),
#   ('work_life_balance', 12%),
#   ('culture', 7%)
# ]
```

### Retention Intervention ROI

Calculate ROI of retention programs:

```python
def retention_program_roi(program_cost, employees_at_risk,
                          baseline_attrition_rate, expected_reduction,
                          avg_salary, turnover_cost_multiplier=1.5):
    """
    Calculate ROI of retention program
    """
    # Baseline scenario (no program)
    baseline_departures = employees_at_risk * (baseline_attrition_rate / 100)
    baseline_cost = baseline_departures * avg_salary * turnover_cost_multiplier

    # Program scenario (with intervention)
    reduced_attrition_rate = baseline_attrition_rate * (1 - expected_reduction)
    program_departures = employees_at_risk * (reduced_attrition_rate / 100)
    program_cost_total = (program_departures * avg_salary * turnover_cost_multiplier) + program_cost

    # ROI calculation
    savings = baseline_cost - program_cost_total
    roi = (savings / program_cost) * 100

    return {
        'baseline_departures': round(baseline_departures, 1),
        'program_departures': round(program_departures, 1),
        'departures_prevented': round(baseline_departures - program_departures, 1),
        'baseline_cost': round(baseline_cost),
        'program_cost_total': round(program_cost_total),
        'savings': round(savings),
        'roi': round(roi, 1)
    }

# Example: Manager training program
result = retention_program_roi(
    program_cost=50000,           # Manager training cost
    employees_at_risk=200,        # High-risk employees
    baseline_attrition_rate=20,   # 20% annual attrition
    expected_reduction=0.25,      # 25% reduction in attrition
    avg_salary=100000,
    turnover_cost_multiplier=1.5
)

print(f"ROI: {result['roi']}%")
print(f"Savings: ${result['savings']:,}")
```

**Typical Program ROI**:
- **Manager Training**: 3-5x ROI (reduces attrition 20-30%)
- **Compensation Adjustments**: 2-4x ROI (targets below-market employees)
- **Career Development**: 2-3x ROI (reduces growth-related attrition)
- **Stay Interviews**: 4-6x ROI (low cost, high impact)

## Resources

- **Statistical Methods**: Logistic regression, survival analysis, chi-square tests
- **Benchmarks**:
  - Tech industry attrition: 13-15% overall, 18-22% engineering
  - New hire attrition (0-12 months): 25-35%
  - Turnover cost: 1.5-2.0x annual salary
- **Tools**: Workday, Culture Amp, Qualtrics, Python (pandas, scikit-learn)
- **Data Sources**: HRIS, engagement surveys, exit interviews, performance data

## Best Practices

1. **Segment Analysis**: Always analyze attrition by cohorts (don't just look at overall rate)
2. **Voluntary vs. Involuntary**: Separate voluntary (retention focus) from involuntary turnover
3. **Regrettable Focus**: Prioritize retention of high-performers and critical roles
4. **Leading Indicators**: Build predictive models with 90-180 day lead time for intervention
5. **Root Cause Analysis**: Use exit interviews and statistical analysis to identify drivers
6. **Targeted Interventions**: Design retention programs for specific cohorts, not one-size-fits-all
7. **ROI Mindset**: Calculate retention program ROI to justify investments
8. **Early Intervention**: Focus on new hire retention (0-12 months) and critical windows (3-5 years)

## Common Pitfalls

1. **Ignoring Voluntary vs. Involuntary**: Mixing both inflates apparent attrition problem
2. **Overall Rate Only**: Missing high-risk cohorts by only looking at aggregate attrition
3. **Exit Interview Bias**: People may not be honest; supplement with engagement data
4. **Reactive Approach**: Waiting for resignations instead of predicting and preventing
5. **Uniform Interventions**: One-size-fits-all programs miss specific cohort needs
6. **Short-Term Focus**: Retention is long-term; programs take 6-12 months to show impact
7. **No ROI Analysis**: Failing to measure retention program effectiveness
8. **Benchmarking Only**: Industry benchmarks are guides; focus on your trends and drivers
