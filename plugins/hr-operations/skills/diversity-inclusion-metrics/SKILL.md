---
name: diversity-inclusion-metrics
description: D&I metrics, representation analysis, pay equity studies, inclusion measurement, and diversity reporting. Use when analyzing workforce diversity, conducting pay equity studies, measuring inclusion, or developing D&I strategies.
---

# Diversity & Inclusion Metrics

Framework for measuring workforce diversity, analyzing representation, conducting pay equity studies, and assessing inclusion effectiveness.

## When to Use This Skill

- Measuring workforce diversity and representation
- Conducting demographic analysis of hiring, promotion, attrition
- Pay equity analysis by protected class
- Inclusion measurement through surveys and engagement
- D&I goal setting and progress tracking
- Regulatory compliance and reporting (EEO-1, etc.)

## Core Concepts

### 1. Representation Metrics
Workforce composition by demographics:
```
Representation = (Count of Group / Total Population) × 100

Analyze at multiple levels:
- Overall company
- By level (IC, Manager, Director, VP, Executive)
- By function (Engineering, Sales, Operations)
- By location/region
```

### 2. Diversity Index
Measure heterogeneity of workforce:
```
Simpson's Diversity Index = 1 - Σ(ni/N)²

Where:
- ni = count of individuals in group i
- N = total population

Range: 0 (no diversity) to 1 (maximum diversity)
```

### 3. Pay Equity
Equal pay for equal work analysis:
```
Regression-based analysis controlling for legitimate factors
(Level, Tenure, Performance, Location, Function)

Unadjusted Gap = Simple average difference
Adjusted Gap = Difference after controlling for factors
```

## Quick Start

```python
def representation_analysis(employee_data, demographic_field):
    """
    Calculate representation by demographic group
    """
    from collections import Counter

    total = len(employee_data)
    counts = Counter(employee_data[demographic_field])

    representation = {}
    for group, count in counts.items():
        representation[group] = {
            'count': count,
            'percentage': round((count / total) * 100, 1)
        }

    return representation

def diversity_index(demographics):
    """
    Calculate Simpson's Diversity Index
    """
    total = sum(demographics.values())
    proportions_squared = sum((count / total) ** 2 for count in demographics.values())

    diversity_index = 1 - proportions_squared

    return round(diversity_index, 3)

# Example
employees = {'gender': ['M', 'M', 'F', 'M', 'F', 'F', 'M', 'M', 'F', 'M']}
representation = representation_analysis(employees, 'gender')
# Output: {'M': {'count': 6, 'percentage': 60%}, 'F': {'count': 4, 'percentage': 40%}}
```

## D&I Analytics Methodologies

### Pattern 1: Representation by Level (Pipeline Analysis)

```python
def representation_by_level(employee_data):
    """
    Analyze representation across organizational levels

    Identifies where underrepresentation is most acute
    """
    levels = ['IC', 'Manager', 'Director', 'VP', 'Executive']

    representation_pipeline = {}

    for level in levels:
        level_data = [emp for emp in employee_data if emp['level'] == level]
        total = len(level_data)

        demographics = {}
        for demo_field in ['gender', 'race_ethnicity', 'age_group']:
            counts = Counter(emp[demo_field] for emp in level_data)
            demographics[demo_field] = {
                group: round((count / total) * 100, 1)
                for group, count in counts.items()
            }

        representation_pipeline[level] = {
            'headcount': total,
            'demographics': demographics
        }

    return representation_pipeline

# Typical finding: Underrepresentation increases at senior levels
# Example: Women 45% IC → 35% Manager → 25% Director → 15% VP
```

**Key Questions**:
- Where does representation drop most significantly?
- Is there a "broken rung" in management promotion?
- Are senior levels less diverse than IC levels?

### Pattern 2: Flow Analysis (Hiring, Promotion, Attrition)

```python
def diversity_flow_analysis(flow_data, demographic_group):
    """
    Analyze hiring, promotion, and attrition rates by demographic

    Identifies where disparities occur in talent lifecycle
    """
    flows = {}

    # Hiring
    total_hires = len([e for e in flow_data if e['event_type'] == 'hire'])
    group_hires = len([e for e in flow_data
                       if e['event_type'] == 'hire' and e['demographic'] == demographic_group])
    hire_rate = (group_hires / total_hires) * 100 if total_hires > 0 else 0

    # Promotions
    total_promotions = len([e for e in flow_data if e['event_type'] == 'promotion'])
    group_promotions = len([e for e in flow_data
                            if e['event_type'] == 'promotion' and e['demographic'] == demographic_group])
    promo_rate = (group_promotions / total_promotions) * 100 if total_promotions > 0 else 0

    # Attrition
    total_attrition = len([e for e in flow_data if e['event_type'] == 'attrition'])
    group_attrition = len([e for e in flow_data
                           if e['event_type'] == 'attrition' and e['demographic'] == demographic_group])
    attrition_rate = (group_attrition / total_attrition) * 100 if total_attrition > 0 else 0

    return {
        'hiring_representation': round(hire_rate, 1),
        'promotion_representation': round(promo_rate, 1),
        'attrition_representation': round(attrition_rate, 1)
    }

# Benchmark against current workforce representation
# Example: If women are 40% of workforce but only 25% of promotions → disparity
```

### Pattern 3: Pay Equity by Protected Class

```python
def pay_equity_by_demographic(salary_data, demographic_field):
    """
    Statistical analysis of pay equity

    Uses regression to control for legitimate factors
    """
    import statsmodels.api as sm
    import numpy as np

    # Create dummy variables for demographic groups
    salary_data_encoded = pd.get_dummies(salary_data, columns=[demographic_field])

    # Features: Demographics + legitimate factors
    legitimate_factors = ['level', 'tenure_years', 'performance_rating', 'location']
    demographic_columns = [col for col in salary_data_encoded.columns
                           if col.startswith(demographic_field)]

    X = salary_data_encoded[legitimate_factors + demographic_columns]
    X = sm.add_constant(X)

    # Log-transform salary for % interpretation
    y = np.log(salary_data['base_salary'])

    # Regression model
    model = sm.OLS(y, X).fit()

    # Extract demographic coefficients
    gaps = {}
    for demo_col in demographic_columns:
        coef = model.params.get(demo_col, 0)
        pval = model.pvalues.get(demo_col, 1.0)
        pct_diff = (np.exp(coef) - 1) * 100

        gaps[demo_col] = {
            'pay_gap_pct': round(pct_diff, 2),
            'p_value': round(pval, 4),
            'significant': pval < 0.05
        }

    return gaps

# Example output:
# {'gender_Female': {'pay_gap_pct': -2.8%, 'p_value': 0.032, 'significant': True}}
# Interpretation: Women paid 2.8% less than men, controlling for level/tenure/performance
```

## Advanced Topics

### Inclusion Measurement

Beyond representation, measure belonging and inclusion:

**Inclusion Index Components**:
1. **Belonging**: "I feel I belong at this company" (survey question)
2. **Voice**: "My opinions are valued and heard"
3. **Authenticity**: "I can be my authentic self at work"
4. **Growth**: "I have equal access to growth opportunities"
5. **Respect**: "I'm treated with respect by colleagues"

**Calculation**:
```python
def inclusion_index(survey_responses):
    """
    Calculate inclusion index from survey responses (1-5 scale)
    """
    inclusion_questions = [
        'belonging', 'voice', 'authenticity', 'growth', 'respect'
    ]

    scores = {}
    for demo_group in survey_responses.keys():
        group_scores = survey_responses[demo_group]
        avg_score = sum(group_scores[q] for q in inclusion_questions) / len(inclusion_questions)
        scores[demo_group] = round(avg_score, 2)

    return scores

# Benchmark: >4.0 = strong inclusion, <3.5 = concern
# Compare across demographic groups to identify disparities
```

### Intersectionality Analysis

Analyze representation at intersections (e.g., women of color, LGBTQ+ veterans):

```python
def intersectional_analysis(employee_data, dimensions):
    """
    Analyze representation at intersection of multiple dimensions

    Example: dimensions = ['gender', 'race_ethnicity']
    """
    from collections import Counter

    # Create intersectional groups
    intersectional_groups = []
    for emp in employee_data:
        group = tuple(emp[dim] for dim in dimensions)
        intersectional_groups.append(group)

    counts = Counter(intersectional_groups)
    total = len(intersectional_groups)

    representation = {
        group: {
            'count': count,
            'percentage': round((count / total) * 100, 2)
        }
        for group, count in counts.items()
    }

    return representation

# Example output:
# {('Female', 'Asian'): {'count': 15, 'percentage': 7.5%},
#  ('Female', 'Black'): {'count': 8, 'percentage': 4.0%}, ...}
```

### D&I Goal Setting

**SMART D&I Goals**:
- **Specific**: "Increase women in engineering leadership from 20% to 30%"
- **Measurable**: Quantified target with baseline
- **Achievable**: Based on pipeline and hiring/promotion rates
- **Relevant**: Aligned with business priorities
- **Time-bound**: "Within 24 months"

## Resources

- **Regulations**: EEO-1 reporting, OFCCP compliance, pay transparency laws
- **Benchmarks**:
  - Tech industry: ~30% women overall, ~20% women in technical roles
  - Leadership diversity often lags IC diversity by 10-20 percentage points
  - Pay gaps: 2-5% adjusted gap common (should trend toward 0%)
- **Tools**: Workday, Culture Amp, Lattice, Namely, ADP Diversity Analytics
- **Frameworks**: McKinsey Diversity Wins, Deloitte Inclusion Index

## Best Practices

1. **Representation at All Levels**: Don't just measure overall; analyze by level and function
2. **Flow Analysis**: Track hiring, promotion, attrition by demographic
3. **Pay Equity Annually**: Conduct regression-based pay equity analysis yearly
4. **Inclusion Measurement**: Supplement representation with inclusion survey data
5. **Intersectionality**: Analyze multiple dimensions simultaneously
6. **Transparent Goals**: Public D&I goals create accountability
7. **Manager Training**: Bias training and inclusive leadership development
8. **Regular Reporting**: Quarterly D&I metrics to leadership, annual public reporting

## Common Pitfalls

1. **Representation Only**: Measuring diversity without inclusion (incomplete picture)
2. **No Baseline**: Setting goals without measuring starting point
3. **Vanity Metrics**: Focusing on easy wins vs. senior leadership diversity
4. **Ignoring Intersectionality**: Missing underrepresentation at intersections
5. **No Pay Equity Analysis**: Legal and ethical risk
6. **One-Time Measurement**: D&I requires continuous tracking and improvement
7. **No Accountability**: Goals without owner or consequences
8. **Aggregate Reporting Only**: Missing disparities at team/function level
