---
name: performance-management
description: Performance management frameworks, rating calibration processes, feedback systems, and performance distribution analysis. Use when designing performance systems, facilitating calibration, or analyzing rating patterns.
---

# Performance Management

Comprehensive framework for performance rating systems, calibration processes, distribution analysis, and effective performance management practices.

## When to Use This Skill

- Designing or refining performance rating systems
- Facilitating performance calibration sessions
- Analyzing rating distributions for fairness and consistency
- Investigating rating bias and manager tendencies
- Linking performance to compensation and promotion decisions
- Developing feedback and goal-setting frameworks

## Core Concepts

### 1. Performance Rating Systems
Common approaches:
- **5-Point Scale**: (1) Below Expectations, (2) Partially Meets, (3) Meets, (4) Exceeds, (5) Exceptional
- **3-Point Scale**: Below/Meets/Exceeds (simpler, less differentiation)
- **Forced Rankings**: Stack rank employees (controversial, less common now)
- **OKR-Based**: Objectives and Key Results scoring (0.0-1.0)

### 2. Rating Distributions
Target vs. actual distribution:
```
Common Guideline Distribution (5-point scale):
- Exceptional (5): 10%
- Exceeds (4): 30%
- Meets (3): 50%
- Partially Meets (2): 8%
- Below (1): 2%

Forced vs. Guideline: Guideline = recommendation, Forced = requirement
```

### 3. Calibration Process
Multi-manager review to ensure rating consistency:
- **Purpose**: Align standards across teams
- **Approach**: Peer comparison and discussion
- **Outcome**: Fair, consistent ratings across organization

## Quick Start

```python
def rating_distribution(ratings, guidelines):
    """
    Compare actual vs. target rating distribution
    """
    from collections import Counter

    actual = Counter(ratings)
    total = len(ratings)

    results = {}
    for rating, guideline_pct in guidelines.items():
        actual_count = actual.get(rating, 0)
        actual_pct = (actual_count / total) * 100
        variance = actual_pct - guideline_pct

        results[rating] = {
            'actual_count': actual_count,
            'actual_pct': round(actual_pct, 1),
            'guideline_pct': guideline_pct,
            'variance': round(variance, 1),
            'status': '⚠' if abs(variance) > 5 else '✓'
        }

    return results

# Example
ratings = [5, 4, 4, 4, 3, 3, 3, 3, 3, 3, 3, 3, 2, 1]
guidelines = {5: 10, 4: 30, 3: 50, 2: 8, 1: 2}

distribution = rating_distribution(ratings, guidelines)
```

## Performance Management Methodologies

### Pattern 1: Calibration Facilitation

```python
def calibration_prep_analysis(team_ratings):
    """
    Pre-calibration analysis to identify outliers
    """
    results = {}

    for manager, ratings in team_ratings.items():
        total = len(ratings)
        top_ratings = sum(1 for r in ratings if r >= 4)
        top_pct = (top_ratings / total) * 100

        results[manager] = {
            'team_size': total,
            'top_rating_pct': round(top_pct, 1),
            'status': 'High' if top_pct > 45 else 'Low' if top_pct < 35 else 'OK'
        }

    return sorted(results.items(), key=lambda x: x[1]['top_rating_pct'], reverse=True)

# Identifies managers with rating inflation/deflation for discussion
```

**Calibration Best Practices**:
1. Start with teams furthest from guidelines
2. Use peer comparisons (similar roles across teams)
3. Focus on top and bottom ratings (require evidence)
4. Document rationale for outliers
5. Iterate until distribution meets guidelines

### Pattern 2: Rating Bias Detection

```python
def detect_rating_bias(ratings_by_demographics):
    """
    Identify potential bias in rating distribution
    """
    from scipy.stats import chi2_contingency

    # Chi-square test for independence
    # Null hypothesis: Ratings independent of demographic group
    chi2, p_value, dof, expected = chi2_contingency(ratings_by_demographics)

    significant = p_value < 0.05

    return {
        'chi_square': round(chi2, 2),
        'p_value': round(p_value, 4),
        'significant_bias': significant,
        'interpretation': 'Bias detected' if significant else 'No bias detected'
    }

# Example: Test if gender affects rating distribution
# If significant → deeper investigation required
```

**Common Biases**:
- **Leniency**: Manager rates everyone high
- **Severity**: Manager rates everyone low
- **Central Tendency**: Manager avoids extremes (too many 3s)
- **Halo Effect**: One trait influences overall rating
- **Recency**: Focus on recent performance, not full year

### Pattern 3: Performance-Outcome Correlation

```python
def performance_outcome_correlation(performance_data):
    """
    Validate performance system by correlating ratings with outcomes
    """
    from scipy.stats import pearsonr

    # Correlation between performance and merit increases
    perf_merit_corr, p_val_merit = pearsonr(
        performance_data['performance_rating'],
        performance_data['merit_increase_pct']
    )

    # Correlation between performance and promotions
    avg_promo_by_rating = {}
    for rating in [1, 2, 3, 4, 5]:
        subset = performance_data[performance_data['performance_rating'] == rating]
        promo_rate = subset['promoted'].mean() * 100
        avg_promo_by_rating[rating] = round(promo_rate, 1)

    return {
        'merit_correlation': round(perf_merit_corr, 2),
        'merit_significant': p_val_merit < 0.05,
        'promotion_rates': avg_promo_by_rating
    }

# Strong correlation (>0.6) indicates effective performance system
```

## Advanced Topics

### Goal Setting & OKRs

**OKR Framework**:
```
Objective: Qualitative, inspirational goal
Key Results: Quantitative, measurable outcomes (3-5 per objective)

Scoring: 0.0-1.0
- 0.0-0.3: Significant shortfall
- 0.4-0.6: On track (typical target: 0.7)
- 0.7-1.0: Exceeded expectations
```

**SMART Goals**: Specific, Measurable, Achievable, Relevant, Time-bound

### Continuous Feedback Models

Shift from annual reviews to ongoing feedback:
- **Weekly 1:1s**: Manager-employee check-ins
- **Quarterly Reviews**: Progress on goals, course correction
- **Annual Summary**: Compilation of year's feedback
- **360-Degree Feedback**: Multi-source feedback (peers, manager, direct reports)

### Performance Improvement Plans (PIPs)

Structured approach for underperformers:
```
PIP Components:
1. Clear performance gaps documented
2. Specific improvement goals (SMART)
3. Timeline (typically 30-90 days)
4. Support/resources provided
5. Check-in frequency (weekly)
6. Success criteria defined
7. Consequences if not met
```

## Resources

- **Rating Systems**: 5-point scale, 3-point scale, OKRs, continuous feedback
- **Calibration**: Multi-manager review, peer comparison, evidence-based discussion
- **Tools**: Workday, Lattice, 15Five, Culture Amp, Betterworks (OKRs)
- **Benchmarks**:
  - Top ratings (4-5): 35-45% typical
  - Forced curves declining (trend toward guideline distributions)
  - Annual review supplemented with continuous feedback

## Best Practices

1. **Clear Definitions**: Document what each rating level means (with examples)
2. **Calibration Required**: Multi-manager review for consistency
3. **Evidence-Based**: Ratings supported by documented examples
4. **Timely Feedback**: Ongoing feedback, not just annual
5. **Link to Outcomes**: Clear connection between performance, pay, promotions
6. **Manager Training**: Train managers on rating standards and bias
7. **Demographic Analysis**: Annual check for rating bias by gender, race, tenure
8. **Communication**: Transparent process and criteria to employees

## Common Pitfalls

1. **Rating Inflation**: Too many high ratings (dilutes meaning)
2. **Central Tendency**: Everyone rated "Meets" (no differentiation)
3. **Recency Bias**: Focus on recent months, not full year
4. **No Calibration**: Inconsistent standards across managers
5. **Weak Documentation**: Insufficient evidence to support ratings
6. **Pay Disconnect**: Performance ratings not reflected in compensation
7. **Annual Only**: No ongoing feedback, just once-a-year review
8. **Manager Avoidance**: Managers avoid difficult conversations
