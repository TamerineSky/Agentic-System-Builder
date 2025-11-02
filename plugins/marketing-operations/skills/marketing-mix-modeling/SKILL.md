# Marketing Mix Modeling Skill

## Overview
Master Marketing Mix Modeling (MMM) to measure incremental impact of marketing activities and optimize channel investment across online and offline channels.

## Skill Objectives
- Build marketing mix models to quantify channel impact
- Measure incrementality and true causal effects
- Optimize marketing spend across all channels (online + offline)
- Account for factors like seasonality, promotions, and external events
- Forecast performance at different spend levels

## When to Use This Skill
- Measuring impact of channels without digital tracking (TV, radio, print)
- Understanding incremental lift vs. baseline sales
- Optimizing budget allocation across all marketing channels
- Dealing with attribution limitations (privacy, walled gardens)
- Planning annual marketing strategy and budget

## MMM vs. Digital Attribution

### Key Differences
```
Digital Attribution:
- User-level tracking (cookies, device IDs)
- Touchpoint-level data
- Real-time or near-real-time
- Good for digital channels
- Struggles with offline channels, TV, cross-device

Marketing Mix Modeling:
- Aggregate-level data (weekly or monthly)
- Channel-level analysis
- Periodic (weekly/monthly updates)
- Works for all channels (online + offline)
- Statistical modeling, not tracking

Ideal Approach: Use Both
- MMM for offline channels + incrementality validation
- Attribution for digital channel optimization
- Compare models to triangulate truth
```

## MMM Fundamentals

### Core Concept
```
Sales = f(Marketing, Price, Distribution, Product, Seasonality, Economic Factors, Noise)

Marketing Variables:
- TV advertising (GRPs, impressions, spend)
- Radio (GRPs, spend)
- Print (circulation, spend)
- Digital (impressions, clicks, spend)
- Social media (spend, impressions)
- Search (spend, impressions)
- Promotions (depth, frequency)
- Events, sponsorships

Non-Marketing Variables:
- Seasonality (holidays, time of year)
- Trend (long-term growth/decline)
- Price (average price, discounts)
- Distribution (store count, availability)
- Competitive activity
- Economic indicators (GDP, unemployment, consumer confidence)
- External shocks (weather, news events)
```

### Statistical Model
```
Common MMM Model: Multiple Linear Regression

Y = β0 + β1×TV + β2×Digital + β3×Radio + ... + βn×Seasonality + ε

Where:
- Y = Sales (revenue or units)
- β0 = Baseline (sales with zero marketing)
- β1, β2, β3 = Coefficients (incremental impact of each channel)
- ε = Error term

Transformations Often Applied:
- Adstock: Carryover effect (ad impact persists over time)
- Saturation: Diminishing returns (each incremental dollar less effective)
- Lag: Delayed effect (impact occurs after spend)

Enhanced Model:
Y = β0 + Σ[βi × Adstock(Saturation(Marketing_i))] + Controls + ε
```

## Building an MMM Model

### Step 1: Data Collection
```
Required Data (Weekly or Monthly):

Dependent Variable (Y):
- Sales revenue or units sold
- Granularity: Weekly or monthly for past 2-3 years

Independent Variables (X):

Marketing Spend/Activity:
- TV: Spend, GRPs, impressions (by network/daypart if possible)
- Radio: Spend, GRPs
- Print: Spend, circulation
- Digital: Spend by channel (search, social, display)
- Search: Paid search spend
- Social: Spend by platform
- Email: Number of emails sent (often free)
- Events: Spend, number of events

Control Variables:
- Price: Average selling price
- Distribution: Number of stores, % distribution
- Promotions: Promotional spend, discount depth
- Seasonality: Holiday indicators, month dummies
- Trend: Time index
- Competitors: Competitor ad spend (if available)
- External: Weather, economic indicators

Minimum Data: 2 years (104 weeks or 24 months)
Ideal: 3+ years for robust modeling
```

### Step 2: Data Transformation

#### Adstock Transformation
```
Concept: Advertising effect persists beyond the week it aired

Adstock Formula (Geometric decay):
Adstock_t = Spend_t + λ × Adstock_(t-1)

Where:
- λ = decay rate (0 to 1)
- λ = 0.5 → Half-life of 1 week
- λ = 0.7 → Longer carryover (3-4 weeks)
- λ = 0.3 → Short-lived effect

Example:
Week 1: $100K TV spend
Week 2: $0 TV spend
Week 3: $0 TV spend

With λ = 0.5:
Week 1 adstock: $100K
Week 2 adstock: $0 + 0.5×$100K = $50K (residual effect)
Week 3 adstock: $0 + 0.5×$50K = $25K (further decay)

TV continues driving sales for weeks after airing
```

#### Saturation Transformation
```
Concept: Diminishing returns - first dollar more effective than last

S-Curve (Hill) Function:
Saturated_Spend = (Spend^α) / (Spend^α + K^α)

Where:
- α = shape parameter (typically 1-3)
- K = half-saturation point (spend at 50% of max effect)

Example:
First $10K: 100 sales (+10 sales per $1K)
Next $10K: 150 sales (+5 sales per $1K)
Next $10K: 180 sales (+3 sales per $1K)

Returns diminish as spend increases
```

### Step 3: Model Estimation
```python
# Example Python code for MMM

import pandas as pd
import numpy as np
from sklearn.linear_model import Ridge
from sklearn.preprocessing import StandardScaler

# 1. Load data
data = pd.read_csv('mmm_data.csv')

# 2. Apply adstock transformation
def adstock(x, decay=0.5):
    adstocked = np.zeros_like(x)
    adstocked[0] = x[0]
    for i in range(1, len(x)):
        adstocked[i] = x[i] + decay * adstocked[i-1]
    return adstocked

data['tv_adstock'] = adstock(data['tv_spend'], decay=0.6)
data['digital_adstock'] = adstock(data['digital_spend'], decay=0.3)

# 3. Apply saturation (simplified)
def saturation(x, alpha=2, k=100000):
    return (x**alpha) / (x**alpha + k**alpha)

data['tv_saturated'] = saturation(data['tv_adstock'])
data['digital_saturated'] = saturation(data['digital_adstock'])

# 4. Prepare features and target
features = ['tv_saturated', 'digital_saturated', 'radio_spend',
            'price', 'promotion', 'seasonality_index']
X = data[features]
y = data['sales']

# 5. Standardize
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# 6. Fit model (Ridge regression to handle multicollinearity)
model = Ridge(alpha=1.0)
model.fit(X_scaled, y)

# 7. Extract coefficients (impact of each variable)
coefficients = pd.DataFrame({
    'Variable': features,
    'Coefficient': model.coef_,
    'Impact': model.coef_ * X.std()  # Scaled impact
})

print(coefficients.sort_values('Impact', ascending=False))
```

### Step 4: Model Validation
```
Model Quality Checks:

1. R-squared:
   - Measures % of sales variance explained by model
   - Target: >0.75 (75%+ explained)
   - Lower R² → missing important variables

2. Coefficient Signs:
   - All marketing variables should be positive
   - Price coefficient likely negative (higher price → lower sales)
   - Check logical consistency

3. Statistical Significance:
   - P-values < 0.05 for key variables
   - Confidence intervals don't include zero

4. Multicollinearity:
   - VIF (Variance Inflation Factor) < 10
   - High VIF → variables too correlated (TV and Radio often move together)
   - Solution: Ridge regression or combine variables

5. Holdout Validation:
   - Train on first 80% of data
   - Test on last 20%
   - MAPE (Mean Absolute Percentage Error) < 10% on holdout

6. Residual Analysis:
   - Residuals should be random (white noise)
   - No patterns in residual plot
   - Shapiro-Wilk test for normality
```

## Insights from MMM

### Channel Contribution & ROI
```
ROI Calculation from MMM:

For each channel:
1. Calculate total impact:
   Impact = Coefficient × Sum(Transformed_Spend)

2. Express as sales:
   Incremental_Sales = Impact (in same units as Y)

3. Calculate ROI:
   ROI = Incremental_Sales / Total_Spend

Example:
TV Coefficient: 0.0015 (per adstocked, saturated dollar)
Total TV Impact: 1,500 units sold
TV Spend: $500,000
Unit Price: $100

Incremental Revenue = 1,500 × $100 = $150,000
ROI = $150,000 / $500,000 = 0.30 → 30% return (or -70% loss)
Interpretation: TV not profitable at current spend level

Digital Coefficient: 0.0080
Total Digital Impact: 4,000 units sold
Digital Spend: $200,000

Incremental Revenue = 4,000 × $100 = $400,000
ROI = $400,000 / $200,000 = 2.00 → 200% return (3:1 ROAS)
Interpretation: Digital highly profitable, consider increasing
```

### Response Curves
```
Marginal ROI Analysis:

For each channel, plot response curve:
X-axis: Spend levels ($0 to max)
Y-axis: Incremental sales

Identify:
- Current spend point
- Saturation point (where curve flattens)
- Optimal spend (where marginal ROI = threshold)

Decision Rules:
- If current spend < saturation: Increase budget
- If current spend > saturation: Decrease budget
- If marginal ROI < cost of capital: Reduce spend
```

### Scenario Planning
```
Budget Optimization Scenarios:

Scenario 1: 20% Budget Increase
- Allocate increase to channels with highest marginal ROI
- Forecast: Sales increase by X%, ROI decreases to Y%

Scenario 2: 20% Budget Decrease
- Cut channels with lowest marginal ROI
- Forecast: Sales decrease by X%, ROI increases to Y%

Scenario 3: Rebalance at Same Budget
- Shift $100K from TV to Digital
- Forecast: Sales increase by 5%, ROI increases from 1.5:1 to 2.0:1
```

## Incrementality Testing

### Purpose
```
Incrementality Test = Controlled Experiment

Goal: Measure TRUE causal impact, not just correlation

Method:
1. Select test markets and control markets (similar characteristics)
2. Increase spend in test markets, hold constant in control
3. Measure sales lift in test vs. control
4. Calculate incremental ROI = Lift / Additional Spend

Why It's Important:
- MMM shows correlation, not causation
- Incrementality test validates MMM findings
- Identifies baseline (sales that would happen anyway)

Example:
Test markets: Increase Facebook spend 50%
Control markets: Hold Facebook spend constant

Results:
- Test markets: +10% sales
- Control markets: +2% sales (organic growth)
- True lift: 10% - 2% = 8% incremental

Incremental ROI: (8% lift × sales) / (50% increase in FB spend)
```

### Incrementality Test Design
```
Geo-Based Testing:

1. Market Selection:
   - Need 10-20 test markets, 10-20 control markets
   - Match on: Population, demographics, historical sales
   - Random assignment to test/control

2. Test Duration:
   - Minimum 4-8 weeks
   - Long enough to see effect, not so long that external factors confound

3. Holdout Testing:
   - Stop spending in channel in test markets
   - Measure sales decline vs. control markets
   - Pure incrementality measure

4. Ramp Testing:
   - Gradually increase spend in test markets
   - Measure sales response at each level
   - Build response curve
```

## Advanced MMM Techniques

### Hierarchical Bayes
```
Why:
- Standard MMM = one model for all markets
- Hierarchical Bayes = separate model per market, with shared priors
- Accounts for market-level differences while pooling information

Benefits:
- More accurate market-level predictions
- Better handling of sparse data
- Uncertainty quantification (credible intervals)

Tools: PyMC3, Stan, Facebook Robyn
```

### Bayesian MMM (Facebook Robyn)
```
Robyn Open-Source MMM Tool:

Features:
- Automated hyperparameter tuning (adstock, saturation)
- Bayesian model averaging (combines multiple models)
- Budget allocator (optimization tool)
- Ridge regression with Bayesian priors

Workflow:
1. Load data
2. Define variables and hyperparameter ranges
3. Run model calibration (tests many combinations)
4. Select best models based on fit
5. Extract channel ROI and response curves
6. Use budget allocator for optimization

Advantage: Less manual tuning, more robust results
```

## MMM Limitations & Solutions

### Limitations
```
1. Aggregate Data:
   - Can't analyze individual customer journeys
   - Solution: Combine with attribution for digital channels

2. Multicollinearity:
   - Marketing channels often correlated (campaigns launch together)
   - Solution: Ridge regression, longer time series, test markets

3. Historical Bias:
   - Model based on past spend levels
   - Extrapolation to very different levels risky
   - Solution: Incrementality tests at different levels

4. External Validity:
   - Model fit to historical period may not apply to future
   - Solution: Regular retraining, scenario planning

5. Delayed Effects:
   - Some channels have long lag (brand building)
   - Solution: Model with longer adstock decay, analyze long-term effects
```

## Tools & Platforms

**Open-Source:**
- Facebook Robyn (R package)
- PyMC-Marketing (Python)
- LightweightMMM (Google, Python)

**Commercial:**
- Nielsen Marketing Mix Modeling
- Analytic Partners
- Neustar MarketShare
- IRI

**Analysis:**
- Python (statsmodels, scikit-learn)
- R (lm, glm packages)

## Best Practices

1. **Sufficient Data**: 2-3 years weekly/monthly data minimum
2. **Include Control Variables**: Price, seasonality, trend, promotions
3. **Transform Variables**: Use adstock and saturation
4. **Validate Rigorously**: Holdout test, coefficient signs, R²
5. **Test Incrementality**: Validate MMM with experiments
6. **Update Regularly**: Retrain model quarterly or semi-annually
7. **Combine with Attribution**: Use both MMM and digital attribution
8. **Scenario Plan**: Model different budget allocations
9. **Communicate Uncertainty**: MMM is model-based, show confidence intervals

## Success Metrics

- **Model Fit**: R² > 0.75, MAPE < 10%
- **Incrementality Validation**: MMM ROI within 20% of test ROI
- **Actionable Insights**: Clear budget reallocation recommendations
- **ROI Improvement**: Optimized budget outperforms status quo
- **Forecast Accuracy**: Predictions within 10% of actuals

Remember: MMM is most powerful when combined with other measurement approaches (attribution, incrementality tests, brand studies). Use each method's strengths to build a comprehensive view of marketing effectiveness.
