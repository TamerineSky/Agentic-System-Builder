---
name: compensation-benchmarking
description: Compensation benchmarking methodologies, market pricing, compa-ratio analysis, pay equity modeling, and salary band development. Use when benchmarking salaries, conducting pay equity studies, or designing compensation structures.
---

# Compensation Benchmarking

Framework for market-competitive compensation analysis, pay equity assessment, and total rewards strategy development.

## When to Use This Skill

- Benchmarking salaries against market data
- Developing salary bands and compensation structures
- Conducting pay equity analysis (gender, race, age)
- Planning merit increases and promotion adjustments
- Analyzing compensation competitiveness and retention risk
- Designing total rewards packages (base, bonus, equity, benefits)

## Core Concepts

### 1. Compa-Ratio
Measure of individual salary vs. midpoint of salary range:
```
Compa-Ratio = Actual Salary / Salary Range Midpoint

Interpretation:
- 0.80-0.90: Below range (new hire, development)
- 0.90-1.00: Below midpoint (growth opportunity)
- 1.00-1.10: At midpoint (market competitive)
- 1.10-1.20: Above midpoint (experienced, high performer)
- >1.20: Premium pay (retention risk if leave)
```

### 2. Market Percentiles
Positioning strategy vs. market:
- **P25**: Below market (cost-focused, high turnover risk)
- **P50 (Median)**: Market competitive (most common target)
- **P75**: Above market (attraction/retention focus)
- **P90**: Premium market (high-demand roles, retention)

### 3. Total Rewards Mix
Complete compensation package:
```
Total Cash Compensation = Base Salary + Target Bonus
Total Direct Compensation = Total Cash + Equity Value
Total Rewards = Total Direct Comp + Benefits + Perks
```

## Quick Start

```python
def compa_ratio(actual_salary, range_midpoint):
    return round(actual_salary / range_midpoint, 2)

def market_position(actual_salary, market_data):
    """
    Determine salary position vs. market percentiles
    """
    p25 = market_data['p25']
    p50 = market_data['p50']
    p75 = market_data['p75']
    p90 = market_data['p90']

    if actual_salary < p25:
        return "Below P25 (High Risk)"
    elif actual_salary < p50:
        return "P25-P50 (Below Market)"
    elif actual_salary < p75:
        return "P50-P75 (Competitive)"
    elif actual_salary < p90:
        return "P75-P90 (Above Market)"
    else:
        return "Above P90 (Premium)"

# Example
salary = 120000
midpoint = 125000
market = {'p25': 100000, 'p50': 115000, 'p75': 130000, 'p90': 145000}

print(f"Compa-ratio: {compa_ratio(salary, midpoint)}")
print(f"Market position: {market_position(salary, market)}")
```

## Benchmarking Methodologies

### Pattern 1: Role Matching & Market Pricing

```python
def match_to_market(internal_role, market_surveys):
    """
    Match internal roles to market survey data

    Sources: Radford, Mercer, Payscale, Levels.fyi, Option Impact
    """
    matched_data = {
        'role_title': internal_role['title'],
        'level': internal_role['level'],
        'function': internal_role['function'],
        'market_data': {
            'p25_base': 0,
            'p50_base': 0,
            'p75_base': 0,
            'p50_total_cash': 0,
            'p50_total_comp': 0
        }
    }

    # Match role to survey job codes
    # Adjust for location, company size, industry
    # Return market percentiles

    return matched_data
```

**Market Data Sources**:
- **Radford**: Tech-focused, comprehensive
- **Mercer/Willis Towers Watson**: Cross-industry
- **Payscale/Salary.com**: Broad market data
- **Levels.fyi**: Tech, crowdsourced, real-time
- **Option Impact**: Startup equity data

### Pattern 2: Pay Equity Analysis

Statistical regression to identify pay gaps:

```python
import statsmodels.api as sm

def pay_equity_regression(employee_data):
    """
    Regression analysis to identify unexplained pay gaps

    Model: Log(Salary) = β0 + β1(Gender) + β2(Level) + β3(Tenure) + ...
    """
    # Prepare features
    X = employee_data[['gender_female', 'level', 'tenure_years',
                       'performance_rating', 'location']]
    X = sm.add_constant(X)  # Add intercept

    # Log-transform salary for % interpretation
    y = np.log(employee_data['base_salary'])

    # Fit model
    model = sm.OLS(y, X).fit()

    # Interpret gender coefficient
    gender_coef = model.params['gender_female']
    gender_pvalue = model.pvalues['gender_female']

    # Convert to % difference
    pct_difference = (np.exp(gender_coef) - 1) * 100

    result = {
        'gender_gap_pct': round(pct_difference, 2),
        'statistically_significant': gender_pvalue < 0.05,
        'p_value': round(gender_pvalue, 4),
        'interpretation': 'Women paid less' if pct_difference < 0 else 'Women paid more'
    }

    return result, model

# Example interpretation:
# gender_gap_pct = -3.2% → Women paid 3.2% less than men, controlling for level, tenure, performance
# If p_value < 0.05 → Statistically significant gap (requires remediation)
```

**Remediation Approach**:
1. Identify individuals >2 standard deviations below expected
2. Quantify adjustment needed to reach expected salary
3. Phase remediation over 1-2 compensation cycles
4. Establish review process for new hires and promotions

### Pattern 3: Salary Band Development

Create salary ranges by role and level:

```python
def create_salary_bands(market_data, spread=0.20):
    """
    Develop salary bands using market data

    spread: Range spread (0.20 = 20% above/below midpoint)
    """
    bands = {}

    for role, market in market_data.items():
        midpoint = market['p50_base']  # Use market 50th percentile as midpoint

        min_salary = midpoint * (1 - spread)
        max_salary = midpoint * (1 + spread)

        bands[role] = {
            'minimum': round(min_salary, -3),  # Round to nearest $1000
            'midpoint': round(midpoint, -3),
            'maximum': round(max_salary, -3),
            'range_spread': f"{spread*100}% above/below midpoint"
        }

    return bands

# Example output:
# {
#   'Senior Software Engineer': {
#     'minimum': 120000,
#     'midpoint': 150000,
#     'maximum': 180000,
#     'range_spread': '20% above/below midpoint'
#   }
# }
```

**Band Design Principles**:
- **Spread**: 40-50% total range (±20-25% from midpoint)
- **Midpoint**: Target P50-P60 of market for most roles
- **Quartiles**:
  - 1st: New to role, learning (80-90% of midpoint)
  - 2nd-3rd: Proficient, meeting expectations (90-110%)
  - 4th: Experienced, high performer (110-120%)

## Advanced Topics

### Merit Increase Matrix

Performance and position-based merit allocation:

```python
def merit_matrix(performance_rating, compa_ratio, budget_factor=1.0):
    """
    Determine merit increase % based on performance and compa-ratio

    Logic: Larger increases for high performers below market
    """
    matrix = {
        'Exceptional': {
            'low': 7.0,    # <0.95 compa-ratio
            'mid': 5.5,    # 0.95-1.05
            'high': 4.0    # >1.05
        },
        'Exceeds': {
            'low': 5.5,
            'mid': 4.5,
            'high': 3.5
        },
        'Meets': {
            'low': 3.5,
            'mid': 2.5,
            'high': 1.5
        },
        'Developing': {
            'low': 1.5,
            'mid': 0.5,
            'high': 0.0
        }
    }

    # Determine compa-ratio bucket
    if compa_ratio < 0.95:
        cr_bucket = 'low'
    elif compa_ratio <= 1.05:
        cr_bucket = 'mid'
    else:
        cr_bucket = 'high'

    base_increase = matrix[performance_rating][cr_bucket]
    adjusted_increase = base_increase * budget_factor

    return round(adjusted_increase, 1)
```

### Geographic Pay Differentials

Location-based salary adjustments:

```python
def geo_differential(base_salary, from_location, to_location, differentials):
    """
    Calculate salary adjustment for location

    differentials: Dict of location cost-of-living multipliers
    """
    from_multiplier = differentials.get(from_location, 1.0)
    to_multiplier = differentials.get(to_location, 1.0)

    adjusted_salary = base_salary * (to_multiplier / from_multiplier)

    return round(adjusted_salary, -3)

# Example differentials:
geo_diffs = {
    'San Francisco': 1.25,
    'New York': 1.20,
    'Seattle': 1.15,
    'Austin': 1.05,
    'Remote US': 1.00
}
```

## Resources

- **Benchmarking Sources**: Radford, Mercer, Payscale, Levels.fyi
- **Statistical Tools**: Python (statsmodels), R, Excel (regression analysis)
- **Regulations**: California SB 1162, Colorado Equal Pay Act, EU Pay Transparency
- **HRIS Platforms**: Workday, ADP, Pave, Carta
- **Benchmarks**:
  - Typical merit budget: 3-4% of payroll
  - Promotion increases: 8-15%
  - Compa-ratio target: 0.95-1.05 for most employees

## Best Practices

1. **Multiple Data Sources**: Use 2-3 market surveys for validation
2. **Role Matching Rigor**: Ensure accurate job matching to market data
3. **Regular Updates**: Refresh market data annually
4. **Pay Equity Audits**: Conduct regression analysis annually
5. **Total Rewards View**: Benchmark total compensation, not just base
6. **Document Methodology**: Clear documentation for legal defensibility
7. **Location Strategy**: Define geographic pay philosophy (location-based vs. role-based)
8. **Internal Equity**: Balance external competitiveness with internal fairness

## Common Pitfalls

1. **Single Data Source**: Overreliance on one survey (use multiple)
2. **Poor Role Matching**: Mismatched job levels lead to bad benchmarks
3. **Ignoring Total Comp**: Benchmarking base only misses equity/bonus
4. **Static Data**: Using outdated market data (refresh annually)
5. **No Pay Equity Analysis**: Legal and fairness risk
6. **Compression**: New hires paid more than tenured employees
7. **One-Size-Fits-All**: Same approach for all roles (high-demand roles need premium)
8. **No Communication**: Employees don't understand comp philosophy
