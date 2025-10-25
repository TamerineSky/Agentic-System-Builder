---
name: workforce-planning-models
description: Workforce planning methodologies, capacity modeling techniques, and scenario analysis for strategic headcount planning. Use when forecasting headcount needs, modeling capacity scenarios, or planning organizational structure.
---

# Workforce Planning Models

Comprehensive framework for strategic workforce planning, capacity modeling, and headcount forecasting to align workforce with business objectives.

## When to Use This Skill

- Forecasting headcount needs for next 12-18 months
- Planning organizational structure and reporting relationships
- Modeling capacity and utilization by team
- Analyzing span of control and organizational health
- Scenario planning for different growth trajectories
- Budget planning with headcount constraints

## Core Concepts

### 1. Demand-Supply-Gap Analysis
The foundational framework for workforce planning:
- **Demand**: Future workforce needs based on business goals
- **Supply**: Current workforce adjusted for attrition and internal movement
- **Gap**: Difference between demand and supply (hiring needs or surplus)

### 2. Capacity Modeling
Quantitative approach to workforce capacity:
- **Available Capacity**: FTEs × Utilization Rate × Working Days
- **Demand Forecast**: Projects/initiatives estimated effort
- **Capacity Gap**: Demand - Available Capacity

### 3. Span of Control
Manager-to-direct report ratios for organizational design:
- **Typical Ranges**: 5-10 direct reports
- **Factors**: Complexity, autonomy, manager experience
- **Health Indicators**: Too high (burnout), too low (inefficiency)

## Quick Start

```python
# Simple Headcount Forecast Model
def forecast_headcount(current_hc, growth_rate, attrition_rate, months=12):
    """
    Basic headcount forecasting formula

    current_hc: Current headcount
    growth_rate: Monthly business growth rate (e.g., 0.05 for 5%)
    attrition_rate: Monthly attrition rate (e.g., 0.02 for 2%)
    """
    forecast = []
    hc = current_hc

    for month in range(months):
        # Attrition reduces headcount
        departures = hc * attrition_rate

        # Growth drives hiring needs
        hiring_need = hc * growth_rate

        # Net change
        hc = hc - departures + hiring_need
        forecast.append({
            'month': month + 1,
            'headcount': round(hc),
            'departures': round(departures),
            'hires_needed': round(hiring_need)
        })

    return forecast

# Example usage
forecast = forecast_headcount(
    current_hc=100,
    growth_rate=0.04,  # 4% monthly growth
    attrition_rate=0.015,  # 1.5% monthly attrition
    months=12
)
```

## Workforce Planning Methodologies

### Pattern 1: Driver-Based Headcount Forecasting

Model headcount based on business drivers rather than simple growth percentages.

```python
# Driver-Based Forecasting Example

def sales_team_forecast(revenue_target, avg_rep_quota, ramp_months=6):
    """
    Sales headcount based on revenue targets

    Formula: Required Reps = Revenue Target / (Avg Quota × Productivity Factor)
    """
    # Account for ramp time (partial productivity)
    productivity_factor = 0.7  # Accounts for ramping reps

    fully_productive_reps_needed = revenue_target / avg_rep_quota
    total_reps_needed = fully_productive_reps_needed / productivity_factor

    return {
        'fully_productive_reps': round(fully_productive_reps_needed),
        'total_reps_needed': round(total_reps_needed),
        'buffer_for_ramp': round(total_reps_needed - fully_productive_reps_needed)
    }

def customer_success_forecast(customers, csm_capacity=50):
    """
    CS headcount based on customer count

    Formula: Required CSMs = Total Customers / Customers per CSM
    """
    csm_needed = customers / csm_capacity
    return round(csm_needed)

def engineering_forecast(product_roadmap_capacity, team_productivity=2.5):
    """
    Engineering headcount based on roadmap capacity needs

    Formula: Required Engineers = Roadmap Effort (person-months) / (Team Size × Productivity)
    """
    # product_roadmap_capacity in person-months
    # team_productivity in story points or projects per engineer per month
    engineers_needed = product_roadmap_capacity / team_productivity
    return round(engineers_needed)

# Example: Sales team sizing
result = sales_team_forecast(
    revenue_target=10_000_000,  # $10M ARR target
    avg_rep_quota=500_000,       # $500K per rep
    ramp_months=6
)
print(f"Need {result['total_reps_needed']} reps ({result['fully_productive_reps']} fully productive)")
```

**When to Use**:
- Clear business driver relationships (revenue per sales rep, customers per CSM)
- Planning for significant growth or new team buildout
- Justifying headcount requests with quantitative rationale

### Pattern 2: Scenario-Based Planning

Model multiple scenarios to understand range of outcomes and plan for uncertainty.

```python
def scenario_planning(base_assumptions):
    """
    Generate conservative, base, and aggressive scenarios
    """
    scenarios = {
        'conservative': {
            'growth_rate': base_assumptions['growth_rate'] * 0.7,
            'attrition_rate': base_assumptions['attrition_rate'] * 1.2,
            'productivity': base_assumptions['productivity'] * 0.9
        },
        'base': base_assumptions,
        'aggressive': {
            'growth_rate': base_assumptions['growth_rate'] * 1.3,
            'attrition_rate': base_assumptions['attrition_rate'] * 0.8,
            'productivity': base_assumptions['productivity'] * 1.1
        }
    }

    results = {}
    for scenario_name, assumptions in scenarios.items():
        results[scenario_name] = forecast_headcount(
            current_hc=base_assumptions['current_hc'],
            growth_rate=assumptions['growth_rate'],
            attrition_rate=assumptions['attrition_rate'],
            months=12
        )

    return results

# Example usage
base = {
    'current_hc': 150,
    'growth_rate': 0.03,      # 3% monthly
    'attrition_rate': 0.015,  # 1.5% monthly
    'productivity': 1.0
}

scenarios = scenario_planning(base)
```

**Output Interpretation**:
- **Conservative**: Plan for this scenario (hiring budget, timeline)
- **Base**: Most likely outcome based on current trends
- **Aggressive**: Upside case if everything goes well (capacity planning)

### Pattern 3: Capacity Modeling

Quantify available capacity vs. demand to identify gaps and optimization opportunities.

```python
def capacity_analysis(team_data, utilization_target=0.75):
    """
    Analyze capacity vs. demand

    team_data: List of teams with headcount, workload, productivity
    utilization_target: Target utilization rate (e.g., 0.75 = 75%)
    """
    results = []

    for team in team_data:
        # Available capacity (FTE-months)
        available_capacity = (
            team['headcount'] *
            utilization_target *
            team['working_months']
        )

        # Demand (estimated effort for projects)
        demand = team['projects_effort']  # in person-months

        # Gap analysis
        gap = demand - available_capacity
        gap_pct = (gap / available_capacity) * 100 if available_capacity > 0 else 0

        results.append({
            'team': team['name'],
            'headcount': team['headcount'],
            'available_capacity': round(available_capacity, 1),
            'demand': demand,
            'gap': round(gap, 1),
            'gap_pct': round(gap_pct, 1),
            'status': 'Overcapacity' if gap < 0 else 'Undercapacity',
            'hiring_need': max(0, round(gap / utilization_target))
        })

    return results

# Example
teams = [
    {
        'name': 'Backend Engineering',
        'headcount': 20,
        'working_months': 12,
        'projects_effort': 200  # person-months of work planned
    },
    {
        'name': 'Frontend Engineering',
        'headcount': 15,
        'working_months': 12,
        'projects_effort': 120
    }
]

capacity_results = capacity_analysis(teams, utilization_target=0.75)
for team in capacity_results:
    print(f"{team['team']}: {team['gap_pct']}% gap, need {team['hiring_need']} additional hires")
```

**Key Metrics**:
- **Utilization Target**: 70-80% typical for knowledge work (buffer for meetings, admin)
- **Capacity Gap**: Positive = need more capacity, Negative = excess capacity
- **Hiring Need**: Gap divided by utilization to account for realistic productivity

## Advanced Topics

### Organizational Design & Span of Control

**Optimal Span of Control Analysis**:

```python
def analyze_span_of_control(org_data):
    """
    Analyze manager span of control across organization
    """
    benchmarks = {
        'individual_contributor': (5, 8),      # Min, Max
        'first_level_manager': (5, 8),
        'senior_manager': (4, 7),
        'director': (5, 10)
    }

    results = []
    for manager in org_data:
        direct_reports = manager['direct_reports']
        level = manager['level']

        min_span, max_span = benchmarks.get(level, (5, 8))

        status = 'Optimal'
        if direct_reports < min_span:
            status = 'Too Low (Inefficient)'
        elif direct_reports > max_span:
            status = 'Too High (Manager Burnout Risk)'

        results.append({
            'manager': manager['name'],
            'level': level,
            'direct_reports': direct_reports,
            'benchmark_range': f"{min_span}-{max_span}",
            'status': status
        })

    return results
```

**Factors Affecting Optimal Span**:
1. **Team Autonomy**: Senior, autonomous teams can support higher spans (8-10)
2. **Complexity**: High complexity work requires lower spans (5-7)
3. **Manager Experience**: New managers should start with lower spans (4-6)
4. **Geographic Distribution**: Remote/distributed teams may need lower spans
5. **Growth Rate**: Rapidly growing teams need more management capacity

### Revenue per Employee Analysis

Track organizational efficiency over time:

```python
def revenue_per_employee(revenue, headcount):
    """
    Calculate revenue per employee - key efficiency metric
    """
    return revenue / headcount

# Benchmarks by industry:
# - SaaS: $200K-$350K per employee
# - High-growth tech: $150K-$250K per employee
# - Mature tech: $400K-$600K per employee
```

**Improvement Strategies**:
- **Increase Revenue**: Sales effectiveness, pricing, expansion
- **Optimize Headcount**: Automation, process efficiency, role consolidation
- **Strategic Hiring**: Focus on revenue-generating roles vs. support roles

### Attrition Impact on Planning

Account for attrition in workforce forecasts:

```python
def attrition_adjusted_forecast(current_hc, hiring_plan, monthly_attrition_rate, months=12):
    """
    Forecast with attrition factored in
    """
    forecast = []
    hc = current_hc

    for month in range(months):
        # Attrition
        departures = hc * monthly_attrition_rate

        # Planned hiring
        hires = hiring_plan.get(month, 0)

        # Net headcount
        hc = hc - departures + hires

        forecast.append({
            'month': month + 1,
            'beginning_hc': round(hc + departures - hires),
            'departures': round(departures),
            'hires': hires,
            'ending_hc': round(hc)
        })

    return forecast
```

## Resources

- **Frameworks**: Demand-Supply-Gap, Capacity Planning, Scenario Analysis
- **Tools**: Excel/Google Sheets, Workday, BambooHR, Anaplan
- **Benchmarks**:
  - Attrition: 10-15% annually typical, 18-22% in tech
  - Span of Control: 5-8 direct reports typical
  - Revenue per Employee: Varies by industry ($200K-$600K)
- **Data Sources**: HRIS (headcount, attrition), Finance (revenue, budget), Business (roadmaps, capacity needs)

## Best Practices

1. **Use Driver-Based Models**: Tie headcount to business metrics (revenue, customers, products)
2. **Scenario Planning**: Always model 3 scenarios (conservative, base, aggressive)
3. **Account for Ramp Time**: New hires take 3-6 months to reach full productivity
4. **Include Attrition**: Factor in realistic attrition rates (1-2% monthly typical)
5. **Quarterly Reviews**: Update forecasts quarterly as business conditions change
6. **Stakeholder Alignment**: Involve finance, leadership, and department heads in planning
7. **Balance Efficiency and Growth**: Monitor revenue per employee while investing for growth
8. **Document Assumptions**: Clear documentation of growth rates, productivity, and drivers

## Common Pitfalls

1. **Linear Growth Assumptions**: Business growth is rarely linear; use driver-based models
2. **Ignoring Attrition**: Failure to plan for turnover leads to capacity shortfalls
3. **Overly Optimistic Ramp**: New hires need time; don't assume immediate productivity
4. **Neglecting Span of Control**: Poor management ratios lead to burnout or inefficiency
5. **Single Scenario Planning**: Always prepare for upside and downside scenarios
6. **Disconnected from Business**: Workforce plans must align with business strategy
7. **Annual Planning Only**: Quarterly reviews critical in fast-changing environments
8. **Ignoring Internal Mobility**: Factor in promotions and lateral moves in supply planning
