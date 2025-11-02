---
name: recruiting-analytics
description: Recruiting funnel metrics, source effectiveness analysis, time-to-fill optimization, quality of hire measurement, and recruiting efficiency improvement. Use when analyzing recruiting performance, optimizing hiring funnels, or evaluating sourcing channels.
---

# Recruiting Analytics

Framework for recruiting funnel optimization, source effectiveness, time-to-fill reduction, and quality of hire measurement.

## When to Use This Skill

- Analyzing recruiting funnel conversion rates
- Reducing time-to-fill and improving hiring velocity
- Evaluating source of hire effectiveness and ROI
- Measuring quality of hire and new hire performance
- Optimizing cost-per-hire and recruiting efficiency
- Forecasting hiring capacity and pipeline needs

## Core Concepts

### 1. Recruiting Funnel Stages
Standard funnel progression:
```
Sourced → Applied → Screened → Interviewed → Offered → Accepted → Hired

Conversion Rate = (Candidates at Next Stage / Candidates at Current Stage) × 100
```

### 2. Key Recruiting Metrics
- **Time-to-Fill**: Days from requisition open to offer acceptance (benchmark: 35-45 days)
- **Time-to-Hire**: Days from first candidate contact to offer acceptance
- **Cost-per-Hire**: Total recruiting costs / number of hires
- **Offer Acceptance Rate**: Offers accepted / offers extended (target: 85-90%)
- **Quality of Hire**: New hire performance, retention, hiring manager satisfaction

### 3. Source of Hire
Tracking where candidates originate:
- Employee Referrals (highest quality, 35-40% typical)
- LinkedIn/Professional Networks (high volume, 25-30%)
- Job Boards (high volume, lower quality, 15-20%)
- Recruiting Agencies (high cost, quality varies, 10-15%)
- Career Site/Direct Apply (10-15%)

## Quick Start

```python
def funnel_conversion_rates(funnel_data):
    """
    Calculate conversion rates at each funnel stage
    """
    stages = ['Applied', 'Screened', 'Interviewed', 'Offered', 'Accepted']

    conversions = {}
    for i in range(len(stages) - 1):
        current_stage = funnel_data[stages[i]]
        next_stage = funnel_data[stages[i + 1]]
        conversion = (next_stage / current_stage) * 100 if current_stage > 0 else 0

        conversions[f"{stages[i]}_to_{stages[i+1]}"] = round(conversion, 1)

    return conversions

# Example
funnel = {
    'Applied': 1000,
    'Screened': 250,
    'Interviewed': 125,
    'Offered': 35,
    'Accepted': 30
}

rates = funnel_conversion_rates(funnel)
# Output: {'Applied_to_Screened': 25%, 'Screened_to_Interviewed': 50%, ...}
```

## Recruiting Analytics Methodologies

### Pattern 1: Time-to-Fill Analysis

```python
def time_to_fill_analysis(req_data):
    """
    Analyze time-to-fill by various segments
    """
    import pandas as pd

    df = pd.DataFrame(req_data)

    # Overall metrics
    overall = {
        'mean_ttf': round(df['time_to_fill'].mean(), 1),
        'median_ttf': round(df['time_to_fill'].median(), 1),
        'p90_ttf': round(df['time_to_fill'].quantile(0.9), 1)
    }

    # By function
    by_function = df.groupby('function')['time_to_fill'].agg(['mean', 'median', 'count'])

    # By level
    by_level = df.groupby('level')['time_to_fill'].agg(['mean', 'median', 'count'])

    return {
        'overall': overall,
        'by_function': by_function.to_dict('index'),
        'by_level': by_level.to_dict('index')
    }

# Identifies slowest segments for optimization
```

**Benchmarks**:
- Overall: 35-45 days
- Engineering: 45-55 days
- Sales: 30-40 days
- Senior/Leadership: 60-90 days

**Stage-Level Breakdown**:
```
Sourcing: 8-12 days
Screening: 3-5 days
Interviewing: 10-15 days
Offer Prep/Approval: 3-5 days
Offer to Accept: 7-10 days
```

### Pattern 2: Source Effectiveness Analysis

```python
def source_effectiveness(hire_data):
    """
    Analyze effectiveness of recruiting sources
    """
    sources = {}

    for source_name in hire_data['source'].unique():
        source_hires = hire_data[hire_data['source'] == source_name]

        sources[source_name] = {
            'hires': len(source_hires),
            'avg_time_to_fill': round(source_hires['time_to_fill'].mean(), 1),
            'cost_per_hire': round(source_hires['cost'].sum() / len(source_hires), 0),
            'avg_quality_score': round(source_hires['quality_score'].mean(), 2),
            '90day_retention': round((source_hires['retained_90d'].mean() * 100), 1)
        }

    # Calculate efficiency score (quality / cost)
    for source, metrics in sources.items():
        efficiency = (metrics['avg_quality_score'] * metrics['90day_retention']) / metrics['cost_per_hire']
        metrics['efficiency_score'] = round(efficiency * 1000, 1)  # Scale for readability

    return sources

# Identifies best ROI sources for optimization
```

**Source ROI Ranking** (typical):
1. **Employee Referrals**: Highest quality, moderate cost, best ROI
2. **LinkedIn**: Good quality, moderate cost, strong ROI
3. **Job Boards**: High volume, low quality, moderate ROI
4. **Agencies**: Variable quality, very high cost, lowest ROI

### Pattern 3: Quality of Hire Measurement

```python
def quality_of_hire(new_hire_data, weights=None):
    """
    Composite quality of hire score

    Factors: Performance rating, retention, time to productivity, hiring manager satisfaction
    """
    if weights is None:
        weights = {'performance': 0.35, 'retention': 0.25, 'time_to_productivity': 0.20, 'manager_satisfaction': 0.20}

    qoh_scores = []

    for hire in new_hire_data:
        # Normalize each factor to 0-100 scale
        perf_score = (hire['performance_rating'] / 5.0) * 100  # Assuming 5-point scale
        retention_score = 100 if hire['retained_12mo'] else 0
        ttp_score = max(0, 100 - (hire['time_to_productivity_days'] / 180 * 100))  # 180 days = 0 score
        mgr_score = (hire['manager_satisfaction'] / 5.0) * 100  # 5-point scale

        # Weighted average
        qoh = (
            weights['performance'] * perf_score +
            weights['retention'] * retention_score +
            weights['time_to_productivity'] * ttp_score +
            weights['manager_satisfaction'] * mgr_score
        )

        qoh_scores.append(round(qoh, 1))

    return {
        'mean_qoh': round(sum(qoh_scores) / len(qoh_scores), 1),
        'distribution': qoh_scores
    }

# Benchmark: >70 = good, >80 = excellent
```

## Advanced Topics

### Hiring Velocity Forecasting

```python
def forecast_hiring_capacity(current_pipeline, conversion_rates, recruiter_capacity):
    """
    Forecast hires based on pipeline and conversion rates
    """
    # Pipeline stages
    screened = current_pipeline['screened']
    interviewing = current_pipeline['interviewing']

    # Conversion rates
    screen_to_offer = conversion_rates['screen_to_offer']  # e.g., 0.12 (12%)
    offer_to_accept = conversion_rates['offer_to_accept']  # e.g., 0.85 (85%)

    # Forecast hires
    forecast_hires = screened * screen_to_offer * offer_to_accept

    return {
        'forecast_hires_30d': round(forecast_hires),
        'capacity_utilization': round((forecast_hires / recruiter_capacity) * 100, 1)
    }
```

### Offer Acceptance Optimization

**Factors Affecting Acceptance**:
- **Compensation Competitiveness**: Market-rate offers (target: 90% acceptance)
- **Time-to-Offer**: Faster offers increase acceptance (target: <3 days post-final interview)
- **Candidate Experience**: Positive interview experience critical
- **Competing Offers**: Multiple offers reduce acceptance rate

### Recruiting ROI Analysis

```python
def recruiting_roi(costs, benefits):
    """
    Calculate recruiting function ROI

    Benefits: Reduced attrition (retention of high performers), faster time-to-productivity
    """
    total_cost = sum(costs.values())  # Recruiters, tools, agencies, etc.
    total_benefit = sum(benefits.values())  # Attrition savings, productivity gains

    roi = ((total_benefit - total_cost) / total_cost) * 100

    return {
        'total_cost': total_cost,
        'total_benefit': total_benefit,
        'roi_pct': round(roi, 1)
    }
```

## Resources

- **ATS Platforms**: Greenhouse, Lever, Workable, iCIMS, Workday Recruiting
- **Sourcing Tools**: LinkedIn Recruiter, Indeed, ZipRecruiter, Hired
- **Benchmarks**:
  - Time-to-fill: 35-45 days
  - Offer acceptance: 85-90%
  - Cost-per-hire: $4-12K (varies by role/industry)
  - Quality of hire: >70/100
- **Analytics Tools**: ATS reporting, Tableau, Excel, Python/pandas

## Best Practices

1. **Track Full Funnel**: Monitor all stages from source to hire
2. **Benchmark by Segment**: Different benchmarks for role type, level, function
3. **Source Analysis**: Regularly evaluate source effectiveness and ROI
4. **Quality Over Speed**: Balance time-to-fill with quality of hire
5. **Candidate Experience**: Survey candidates to identify friction points
6. **Continuous Improvement**: Monthly review of metrics and bottlenecks
7. **Hiring Manager Accountability**: Include managers in time-to-fill metrics
8. **Pipeline Management**: Proactive sourcing to maintain healthy pipelines

## Common Pitfalls

1. **Ignoring Quality**: Optimizing for speed without quality measurement
2. **Single Metric Focus**: Time-to-fill only (missing conversion rates, quality)
3. **Poor Source Tracking**: Inaccurate attribution of source of hire
4. **No Benchmarking**: Not comparing to industry standards or internal trends
5. **Reactive Sourcing**: Waiting for requisition to start sourcing
6. **Bottleneck Blindness**: Not identifying stage-level delays
7. **Agency Over-Reliance**: High cost-per-hire without optimization
8. **No Quality Follow-Up**: Not tracking new hire performance and retention
