# Financial Forecasting Methods Skill

## Overview
This skill covers comprehensive forecasting techniques, driver-based modeling, and projection methodologies for accurate financial planning and prediction.

## Core Forecasting Methods

### 1. Time-Series Forecasting

**Moving Average:**
```
Forecast = Average of last N periods

Example (3-period moving average):
Jan: $100K, Feb: $110K, Mar: $120K
Apr forecast: ($100K + $110K + $120K) / 3 = $110K

Use cases: Smooth out random fluctuations
Limitations: Lags behind trends, equal weight to all periods
```

**Exponential Smoothing:**
```
Forecast(t+1) = α × Actual(t) + (1-α) × Forecast(t)

Where α = smoothing constant (0 to 1)

Example (α = 0.3):
Mar Actual: $120K, Mar Forecast: $105K
Apr Forecast: 0.3 × $120K + 0.7 × $105K = $109.5K

Use cases: More recent data weighted higher
Advantages: Responsive to trends, simple calculation
```

**Trend Analysis:**
```
Linear trend: Y = a + b×X
Where: a = intercept, b = slope, X = time period

Example:
Use Excel LINEST or regression to fit historical data
Project trend line forward

Use cases: Clear upward/downward trends
Limitations: Assumes linear continuation
```

**Seasonal Decomposition:**
```
Identify and separate:
- Trend component (long-term direction)
- Seasonal component (quarterly/monthly patterns)
- Cyclical component (business cycle effects)
- Irregular component (random variation)

Seasonal Index Example:
Q1 index: 0.85 (15% below average)
Q2 index: 1.05 (5% above average)
Q3 index: 0.95 (5% below average)
Q4 index: 1.15 (15% above average)

Apply to forecast: Base forecast × Seasonal index
```

### 2. Driver-Based Forecasting

**Revenue Drivers:**
```
SaaS Model:
Revenue = Customers × ARPU

Forecast customers:
Beginning customers: 1,000
+ New customers: 150 (from sales pipeline)
- Churned customers: 50 (5% churn rate)
= Ending customers: 1,100

Forecast ARPU: $10,000 (2% price increase)
Monthly Revenue: 1,100 × $10,000 = $11M

E-commerce Model:
Revenue = Visitors × Conversion Rate × Average Order Value

Forecast:
Visitors: 100,000 (20% growth from marketing)
Conversion: 3% (improving from optimization)
AOV: $150 (slight increase from mix)
Revenue: 100,000 × 3% × $150 = $450K
```

**Expense Drivers:**
```
Headcount-Driven:
Department Expense = FTE × (Salary + Benefits) + Non-personnel

Forecast:
Beginning FTE: 50
+ Hires: 10
- Attrition: 3
= Ending FTE: 57
Average FTE in period: 53.5

Personnel: 53.5 × $120K × 1.3 (benefits) = $8.3M
Non-personnel: $500K (software, T&E, etc.)
Total: $8.8M

Volume-Driven:
Support Cost = Tickets × Cost per Ticket

Forecast:
Customers: 1,100 (from revenue model)
Tickets per customer: 2 per quarter
Total tickets: 2,200
Cost per ticket: $50 (includes labor, tools)
Support cost: 2,200 × $50 = $110K
```

### 3. Regression Analysis

**Simple Linear Regression:**
```
Forecast Y (revenue) based on X (marketing spend)

Y = a + b×X

Example:
Historical data shows: $1M marketing → $5M revenue
Regression: Revenue = $2M + 3 × Marketing spend

Forecast:
If marketing = $1.2M
Revenue = $2M + 3 × $1.2M = $5.6M

R-squared: 0.85 (85% of variance explained)
```

**Multiple Regression:**
```
Revenue = a + b1×Marketing + b2×Sales_FTE + b3×Seasonality

Example model:
Revenue = $1M + 2.5×Marketing + $500K×Sales_FTE + Seasonal factors

Forecast Q3:
Marketing: $800K
Sales FTE: 15
Seasonal factor: 0.95 (5% below average)

Base forecast: $1M + 2.5×$800K + $500K×15 = $10.5M
Adjusted: $10.5M × 0.95 = $10M
```

### 4. Statistical Methods

**ARIMA (AutoRegressive Integrated Moving Average):**
```
Components:
- AR (AutoRegressive): Use past values to predict future
- I (Integrated): Differencing to make series stationary
- MA (Moving Average): Use past errors to predict

Use cases: Complex time series with trends and seasonality
Tools: Python statsmodels, R forecast package
Best for: Advanced forecasting with sufficient historical data
```

**Monte Carlo Simulation:**
```
Steps:
1. Identify key uncertain variables (growth rate, churn, etc.)
2. Assign probability distributions (normal, uniform, etc.)
3. Run 10,000+ simulations
4. Analyze distribution of outcomes

Example Output:
P90 (pessimistic): $8M revenue
P50 (median): $12M revenue
P10 (optimistic): $16M revenue

Use cases: Risk assessment, scenario planning
```

## Best Practices

### 1. Choose the Right Method
```
Short-term (1-3 months):
- Use driver-based models with pipeline/backlog data
- Minimal scenario variation needed
- High accuracy expected (±5%)

Medium-term (4-12 months):
- Combine drivers with time-series methods
- Multiple scenarios (base, upside, downside)
- Moderate accuracy expected (±10-15%)

Long-term (1-5 years):
- Driver-based strategic models
- Heavy reliance on assumptions
- Directional accuracy (±20-30%)
```

### 2. Document Assumptions
```
Assumption Documentation Template:

Assumption: New customer acquisition rate
Value: 150 customers per quarter (growing 5% quarterly)
Basis: Historical average 140/qtr, increased marketing spend
Owner: VP Sales
Sensitivity: High (10% change = $X revenue impact)
Last Updated: 2024-01-15
Review Frequency: Monthly
```

### 3. Track Forecast Accuracy
```
Forecast Accuracy Metrics:

MAPE (Mean Absolute Percentage Error):
MAPE = Average(|Actual - Forecast| / Actual) × 100%

Example:
Q1: Forecast $10M, Actual $11M = 10% error
Q2: Forecast $12M, Actual $11.5M = 4.2% error
Q3: Forecast $13M, Actual $13.5M = 3.8% error
MAPE: (10% + 4.2% + 3.8%) / 3 = 6%

Target accuracy:
- Revenue: <10% MAPE
- Expenses: <5% MAPE (more controllable)
- EBITDA: <15% MAPE (leveraged metric)
```

### 4. Update Regularly
```
Rolling Forecast Process:

Monthly Update:
- Add actual results for completed month
- Remove oldest forecast month
- Add new month at end (maintain 12-month horizon)
- Revise near-term assumptions based on trends

Quarterly Update:
- Comprehensive assumption review
- Update full-year forecast
- Refresh scenarios
- Validate against budget
```

## Common Forecasting Scenarios

### SaaS Revenue Forecast
```
Components:
1. Beginning ARR
2. New ARR (New customers × ACV)
3. Expansion ARR (Upsells, cross-sells)
4. Contraction ARR (Downgrades)
5. Churn ARR (Lost customers)

Formula:
Ending ARR = Beginning ARR + New + Expansion - Contraction - Churn
Revenue (monthly) = Average ARR / 12

Key metrics:
- Net retention: (Beginning + Expansion - Contraction - Churn) / Beginning
- Gross retention: (Beginning - Churn) / Beginning
- Target: >90% gross, >110% net retention
```

### OpEx Forecast by Department
```
Department Budget Template:

Personnel Costs:
- Beginning headcount: X FTE
- Planned hires: Y FTE (by month)
- Attrition: Z% annually
- Average salary: $A
- Benefits load: B%
- Subtotal: (FTE × Salary × (1+Benefits))

Non-Personnel Costs:
- Software/tools: $X (per seat or fixed)
- Travel & entertainment: $Y (% of headcount or fixed)
- Professional services: $Z (by project)
- Other: $A
- Subtotal: Sum of above

Total Department: Personnel + Non-Personnel
```

### Product Revenue Forecast
```
Unit-Based Model:

Units Forecast:
- Historical trend (time-series analysis)
- Market size and penetration
- New product launches
- Competitive dynamics
- Seasonal adjustments

Price Forecast:
- Historical pricing trends
- Planned price increases
- Product mix (shifting to premium)
- Volume discounts
- Competitive pricing

Revenue = Units × Price (adjusted for mix)
```

## Integration with Other Skills

- **budget-variance-analysis**: Use variances to improve forecast accuracy
- **scenario-planning**: Develop multiple forecast scenarios
- **financial-modeling**: Build integrated financial forecast models
- **cash-flow-management**: Translate P&L forecast to cash forecast
- **cost-allocation**: Forecast allocated costs accurately

## Key Terminology

- **Driver-Based Model**: Forecast built from operational drivers (customers, FTE, units)
- **Time-Series**: Historical data points over time
- **Trend**: Long-term direction of data (upward, downward, flat)
- **Seasonality**: Regular, predictable patterns (quarterly, monthly)
- **ARPU**: Average Revenue Per User
- **ARR**: Annual Recurring Revenue
- **MRR**: Monthly Recurring Revenue
- **Churn**: Customer attrition rate
- **Net Retention**: Revenue retention including expansion
- **MAPE**: Mean Absolute Percentage Error (forecast accuracy)
- **Rolling Forecast**: Continuously updated forecast maintaining constant horizon

---

**Skill Type**: Analytical methodology
**Difficulty**: Intermediate to Advanced
**Prerequisites**: Financial modeling basics, Excel proficiency, statistical concepts
**Related Skills**: budget-variance-analysis, scenario-planning, financial-modeling
