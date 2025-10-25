---
name: demand-forecasting-methods
description: Comprehensive demand forecasting methodologies including time series analysis, causal modeling, and machine learning techniques for accurate demand prediction. Use when building demand forecasts, selecting forecasting methods, or improving forecast accuracy.
---

# Demand Forecasting Methods

Master the art and science of demand forecasting through statistical time series methods, causal regression models, and modern machine learning approaches to predict future product demand with accuracy and reliability.

## When to Use This Skill

- Building demand forecasts for inventory planning, production scheduling, or capacity planning
- Selecting appropriate forecasting techniques based on demand patterns and data characteristics
- Improving forecast accuracy through better methods or parameter tuning
- Implementing new product forecasting with limited historical data
- Handling seasonal, promotional, or intermittent demand patterns
- Combining statistical forecasts with business judgment in S&OP processes
- Evaluating forecast performance and identifying improvement opportunities
- Addressing demand uncertainty through scenario planning and probabilistic forecasting

## Core Forecasting Principles

### 1. Forecast Accuracy vs. Utility

Forecasting is not about perfection but about providing actionable insights that improve decisions. A forecast's value lies in reducing uncertainty enough to make better inventory, production, and supply chain decisions.

**Key Trade-offs**:
- Simple methods often outperform complex ones (principle of parsimony)
- Accuracy at aggregate levels typically exceeds item-level accuracy
- Short-term forecasts more accurate than long-term forecasts
- Combining methods (ensemble forecasting) often beats single best method

### 2. Demand Patterns and Method Selection

Different demand patterns require different forecasting approaches:

**Level (Stationary)**: Demand fluctuates around constant mean
- Methods: Moving Average, Simple Exponential Smoothing

**Trend**: Demand shows consistent upward or downward movement
- Methods: Holt's Linear Trend, Regression

**Seasonality**: Regular periodic fluctuations (monthly, quarterly, weekly)
- Methods: Seasonal Decomposition, Holt-Winters, SARIMA

**Intermittent/Lumpy**: Sporadic demand with many zero periods
- Methods: Croston, TSB, Syntetos-Boylan Approximation

### 3. Forecast Horizon and Granularity

Match forecast horizon to planning purpose:
- **Short-term (1-4 weeks)**: Replenishment and short-cycle production
- **Medium-term (1-6 months)**: S&OP, capacity planning, supplier commitments
- **Long-term (6-24 months)**: Strategic planning, facility decisions, network design

Hierarchical forecasting levels:
- **SKU-location**: Most granular, for store replenishment
- **SKU-region or product family**: For distribution planning
- **Total business**: For financial planning and capacity allocation

## Time Series Forecasting Methods

### Method 1: Moving Average and Exponential Smoothing

**Moving Average (MA)**: Average of last N periods
```
Forecast[t+1] = (Demand[t] + Demand[t-1] + ... + Demand[t-N+1]) / N
```

**Advantages**: Simple, smooths random variation
**Disadvantages**: Lags trends, requires storing N periods of data, equal weighting

**Simple Exponential Smoothing (SES)**: Weighted average with exponential decay
```
Forecast[t+1] = α × Demand[t] + (1-α) × Forecast[t]
```

Where α (alpha) is smoothing constant (0 < α < 1)

**Advantages**: Simple, efficient, more weight on recent data
**Disadvantages**: Lags trends and seasonality, requires alpha tuning

**When to use**: Level demand patterns with no trend or seasonality

**Example**: Forecasting steady-state spare parts demand
- Historical demand: [100, 105, 98, 102, 99]
- α = 0.3 (moderate smoothing)
- Forecast = 0.3 × 99 + 0.7 × previous_forecast

### Method 2: Holt-Winters Seasonal Method

Extends exponential smoothing to handle trend and seasonality.

**Additive Seasonality** (constant seasonal amplitude):
```
Level[t] = α × (Demand[t] - Season[t-p]) + (1-α) × (Level[t-1] + Trend[t-1])
Trend[t] = β × (Level[t] - Level[t-1]) + (1-β) × Trend[t-1]
Season[t] = γ × (Demand[t] - Level[t]) + (1-γ) × Season[t-p]
Forecast[t+h] = Level[t] + h × Trend[t] + Season[t+h-p]
```

**Multiplicative Seasonality** (seasonal amplitude proportional to level):
```
Level[t] = α × (Demand[t] / Season[t-p]) + (1-α) × (Level[t-1] + Trend[t-1])
Forecast[t+h] = (Level[t] + h × Trend[t]) × Season[t+h-p]
```

Where:
- α (alpha): Level smoothing constant
- β (beta): Trend smoothing constant
- γ (gamma): Seasonal smoothing constant
- p: Seasonal period (12 for monthly data with yearly seasonality)

**When to use**: Seasonal demand with trend (common for consumer products)

**Example**: Forecasting monthly ice cream sales
- Seasonal pattern repeats yearly (p=12)
- Growing trend (increasing baseline sales)
- Use multiplicative model if seasonal peaks grow with baseline

### Method 3: ARIMA and SARIMA

**ARIMA (AutoRegressive Integrated Moving Average)**: General purpose time series method

ARIMA(p,d,q) components:
- **p**: AutoRegressive terms (past values predict current)
- **d**: Differencing order (to achieve stationarity)
- **q**: Moving Average terms (past errors predict current)

**SARIMA**: ARIMA with seasonal components ARIMA(p,d,q)(P,D,Q)[s]

**Model Selection Process**:
1. Check stationarity (ADF test, KPSS test)
2. Difference if needed to achieve stationarity (d parameter)
3. Examine ACF (autocorrelation) and PACF (partial autocorrelation) plots
4. Identify p and q from plot patterns
5. Fit model and validate residuals (white noise test)

**When to use**: Complex demand patterns requiring sophisticated modeling

**Example**: Forecasting airline passenger demand
- Monthly data with yearly seasonality
- Growing trend over time
- SARIMA(1,1,1)(1,1,1)[12] - seasonal differencing and AR/MA components

## Causal and Regression Forecasting

### Method 4: Multiple Regression with External Variables

Forecast demand as function of explanatory variables (price, promotions, weather, economic indicators).

```
Demand[t] = β0 + β1×Price[t] + β2×Promo[t] + β3×GDP[t] + ε[t]
```

**Common Causal Variables**:
- **Price and promotion**: Promotional flag, discount percentage, display
- **Economic**: GDP growth, unemployment, consumer confidence, housing starts
- **Competitive**: Competitor pricing and promotions
- **External**: Weather (temperature, precipitation), holidays, events

**Price Elasticity**:
```
Elasticity = (% Change in Demand) / (% Change in Price)
```

Typical elasticity: -1.5 to -2.5 (1% price increase → 1.5-2.5% demand decrease)

**Promotional Lift Modeling**:
```
Promotional Lift = (Promoted Demand - Baseline Demand) / Baseline Demand
```

Account for pull-forward and cannibalization effects.

**When to use**: Demand significantly influenced by controllable or observable factors

**Example**: Forecasting beverage sales
- Temperature impact: +2% sales per 1°F increase above 75°F
- Promotion lift: 30% increase during promotional weeks
- Holiday spike: +50% for Memorial Day, July 4th, Labor Day weekends

### Method 5: New Product Forecasting

Forecasting without historical demand data.

**Analogous Product Method**:
1. Identify similar historical products (substitute-in-class)
2. Adjust for differences (price point, features, market size)
3. Apply historical launch curve to new product

**Bass Diffusion Model**:
```
Adopters[t] = p×M + (q-p)×Cumulative[t-1] - (q/M)×Cumulative[t-1]²
```

Where:
- M: Market potential (total eventual adopters)
- p: Coefficient of innovation (early adopters)
- q: Coefficient of imitation (mainstream adoption)

Typical values: p = 0.01-0.03, q = 0.3-0.5

**Market Research and Test Markets**:
- Conduct conjoint analysis to estimate demand at different price points
- Use test market results to calibrate national forecast
- Apply purchase intent survey data with adjustment factors

**When to use**: New product launches, market entries, product line extensions

**Example**: New smartphone launch
- Analogous product: Previous model launch curve
- Adjustment factors: Better camera (+10%), higher price (-5%), larger market (+15%)
- Bass model to shape launch trajectory over 12 months

## Machine Learning Approaches

### Method 6: Gradient Boosting and Random Forest

Ensemble tree-based methods for complex nonlinear relationships.

**Random Forest**: Aggregates predictions from many decision trees
**Gradient Boosting (XGBoost, LightGBM)**: Sequentially builds trees to correct errors

**Feature Engineering**:
- Lag features: Demand[t-1], Demand[t-7], Demand[t-52]
- Rolling statistics: Moving averages, standard deviations
- Calendar features: Month, week of year, day of week, holiday flags
- Trend and seasonality decomposition components
- External variables: Price, promotion, weather, economic indicators

**Training Approach**:
- Time series cross-validation (walk-forward validation)
- Separate train/validation/test sets chronologically
- Hyperparameter tuning (tree depth, learning rate, number of trees)

**When to use**: Large datasets with many features, highly nonlinear relationships

**Example**: Retail demand forecasting with hundreds of SKUs
- Features: Price, promotion, holiday, weather, day-of-week, historical lags
- XGBoost model trained on 2 years of data
- Achieve 15-20% accuracy improvement over simple time series methods

### Method 7: Ensemble Forecasting

Combine multiple forecast methods to improve accuracy and robustness.

**Simple Average**:
```
Ensemble Forecast = (Forecast1 + Forecast2 + Forecast3) / 3
```

**Weighted Average** (weights sum to 1):
```
Ensemble Forecast = w1×Forecast1 + w2×Forecast2 + w3×Forecast3
```

Determine weights from historical accuracy (inverse of forecast error).

**Stacking**: Use machine learning to learn optimal combination
- Train models: Time series, regression, ML
- Use predictions as features for meta-model
- Meta-model learns best combination for different scenarios

**When to use**: Improve forecast reliability, reduce method selection risk

**Example**: S&OP consensus forecast
- Statistical forecast (ARIMA): 35% weight
- Sales forecast (judgment): 25% weight
- ML forecast (XGBoost): 40% weight
- Weights based on historical forecast value added (FVA)

## Advanced Topics

### Intermittent Demand Forecasting

For sparse demand with many zero periods (spare parts, slow-movers).

**Croston's Method**:
- Forecast demand size and inter-demand interval separately
- Smooth each with exponential smoothing
- Forecast = Demand Size / Inter-demand Interval

**TSB (Teunter-Syntetos-Babai)**:
- Improved version of Croston addressing bias
- Forecasts probability of demand and demand size

**When to use**: Products with sporadic, intermittent demand patterns

### Hierarchical Reconciliation

Ensure forecasts are coherent across aggregation levels.

**Bottom-up**: Sum item-level forecasts to get totals (preserves detail)
**Top-down**: Disaggregate total forecast using proportions (smooth, less accurate at item level)
**Middle-out**: Forecast at intermediate level, reconcile up and down
**Optimal Reconciliation**: Minimize total forecast error across hierarchy

**Example**: Retail chain
- Total company forecast (top)
- Regional forecasts (middle)
- Store-SKU forecasts (bottom)
- Ensure: Sum(Store-SKU) = Region = Company

### Probabilistic Forecasting

Generate forecast distributions instead of point estimates.

**Quantile Forecasting**:
- Predict 10th, 50th (median), 90th percentiles
- Provides range of possible outcomes
- Use for safety stock and risk assessment

**Scenario Planning**:
- Optimistic scenario (P90)
- Base case (P50)
- Pessimistic scenario (P10)

**When to use**: High uncertainty environments, financial planning, risk analysis

## Forecast Accuracy Metrics

### Accuracy Metrics

**MAPE (Mean Absolute Percentage Error)**:
```
MAPE = (100/n) × Σ|Actual - Forecast| / Actual
```
Scale-independent, but undefined when Actual=0, sensitive to small denominators.

**MAE (Mean Absolute Error)**:
```
MAE = (1/n) × Σ|Actual - Forecast|
```
Scale-dependent, easy to interpret in original units.

**RMSE (Root Mean Squared Error)**:
```
RMSE = √[(1/n) × Σ(Actual - Forecast)²]
```
Penalizes large errors more than MAE.

**WMAPE (Weighted MAPE)**:
```
WMAPE = 100 × Σ|Actual - Forecast| / ΣActual
```
Better for aggregated accuracy, avoids division-by-zero issues.

### Bias Metrics

**MPE (Mean Percentage Error)**:
```
MPE = (100/n) × Σ(Actual - Forecast) / Actual
```
Positive = under-forecasting, Negative = over-forecasting.

**Tracking Signal**:
```
Tracking Signal = Cumulative Forecast Error / MAD
```
Alert if |TS| > 4-6 (systematic bias present).

### Best Practices

- Use multiple metrics (accuracy and bias)
- Calculate at multiple aggregation levels
- Track forecast value added (FVA) - value of each forecasting step
- Perform backtesting on holdout data
- Monitor forecast accuracy trends over time

## Resources

### Statistical Software
- **R**: forecast package (auto.arima, ets, tbats), fable package
- **Python**: statsmodels (ARIMA, SARIMAX), Prophet (Facebook), scikit-learn
- **Commercial**: SAS Forecast Server, IBM SPSS, Autobox

### Supply Chain Planning Systems
- **SAP IBP**: Integrated Business Planning with statistical forecasting
- **Kinaxis RapidResponse**: Scenario-based forecasting and consensus
- **o9 Solutions**: AI-driven demand planning
- **Blue Yonder (formerly JDA)**: Advanced demand forecasting
- **ToolsGroup**: Probabilistic forecasting and inventory optimization

### Learning Resources
- "Forecasting: Principles and Practice" by Hyndman & Athanasopoulos (free online)
- "The Demand Planning Book" by Joannes Vermorel
- "Forecasting and Judgmental Adjustments" by Nikolopoulos & Goodwin
- IBF (Institute of Business Forecasting) certification programs
- ISF (International Institute of Forecasters) resources

## Common Pitfalls

- **Over-complicating methods**: Simple methods often work better (Occam's razor)
- **Ignoring data quality**: Garbage in, garbage out - cleanse outliers and anomalies
- **Forgetting business context**: Blindly applying statistics without supply chain judgment
- **Not adjusting for promotions**: Promotional demand inflates baseline forecast
- **Neglecting new products**: Many businesses have significant new product mix
- **Chasing noise**: Over-reacting to random variation instead of systematic patterns
- **One-size-fits-all**: Different products need different methods (ABC/XYZ segmentation)
- **Ignoring forecast error**: Focus on accuracy metrics and continuous improvement
- **Lack of collaboration**: Statistical forecasts need sales/marketing input for events
- **Static models**: Demand patterns change - retrain and update models regularly
