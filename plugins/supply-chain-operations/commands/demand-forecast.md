---
description: Generate comprehensive demand forecast for specified product line and time horizon using appropriate statistical methods and business intelligence.
argument-hint: [product-line] [forecast-horizon]
model: sonnet
version: 1.0.0
tags: [demand, forecasting, planning]
---

# Demand Forecast Generation

Generate accurate demand forecasts combining statistical methods, historical patterns, and business judgment for inventory and production planning.

## Context

Demand forecasting drives inventory positioning, production scheduling, and supply chain resource allocation. Accurate forecasts reduce stockouts and excess inventory while improving customer service.

## Requirements
$ARGUMENTS

## Instructions

### 1. Data Collection and Preparation

Gather historical demand data for $1 (product line):
- At least 24 months of sales/shipment history
- Identify and adjust for promotions, stockouts, and anomalies
- Collect causal data: pricing, promotions, seasonality, economic indicators
- Separate constrained sales from true demand
- Validate data quality and completeness

Access data from ERP, data warehouse, or sales systems. Clean outliers and fill gaps using interpolation or domain knowledge.

### 2. Demand Pattern Analysis

Analyze historical demand characteristics:
- Calculate average demand and coefficient of variation
- Identify trend (growing, declining, or stable)
- Detect seasonality (monthly, quarterly, weekly patterns)
- Classify demand pattern (level, trend, seasonal, intermittent)
- Perform ABC/XYZ segmentation if multiple SKUs

Use time series decomposition to separate trend, seasonality, and randomness. Plot demand history to visualize patterns.

### 3. Forecast Method Selection and Application

Select appropriate forecasting method(s) for $2 (forecast horizon):
- **Short-term (1-12 weeks)**: Exponential smoothing, ARIMA
- **Medium-term (3-12 months)**: Holt-Winters, SARIMA, regression with causal factors
- **Long-term (1-2 years)**: Trend projection, scenario planning

Apply selected methods:
- Configure parameters (smoothing constants, ARIMA orders)
- Incorporate seasonality and trend components
- Include causal variables (price, promotions, external factors)
- Generate baseline statistical forecast

### 4. Forecast Validation and Adjustment

Validate forecast accuracy:
- Backtest on historical data (last 6 months holdout)
- Calculate MAPE, MAE, RMSE, and bias (MPE)
- Compare multiple methods if applicable
- Select best-performing method or create ensemble

Apply business judgment:
- Incorporate known future events (promotions, product launches, market changes)
- Adjust for one-time events not reflected in history
- Obtain sales team input for consensus forecasting
- Create optimistic, base, and pessimistic scenarios if high uncertainty

### 5. Generate Forecast Outputs

Produce comprehensive forecast deliverables:
- **Forecast table**: Period-by-period demand forecast for $2
- **Confidence intervals**: 80% and 95% prediction intervals
- **Accuracy metrics**: MAPE, bias, comparison to benchmark
- **Assumptions document**: Key assumptions, risks, and sensitivity
- **Visualizations**: Forecast vs. history charts with confidence bands
- **Recommendation**: Suggested inventory and production implications

## Output Format

1. **Executive Summary**: Forecast overview, key insights, and recommendations (1 page)
2. **Forecast Table**: Detailed period-by-period forecast with confidence intervals
3. **Accuracy Analysis**: Backtest results, error metrics, model selection rationale
4. **Methodology Documentation**: Methods used, parameters, assumptions
5. **Visualizations**: Charts showing forecast vs. history, seasonality, trend
6. **Action Items**: Inventory positioning, production planning, procurement recommendations

## Success Criteria

- Forecast generated for full $2 horizon
- Accuracy metrics calculated (MAPE, bias) with backtest validation
- Business judgment incorporated (not pure statistical forecast)
- Clear documentation of assumptions and methodology
- Actionable recommendations for supply chain planning
- Forecast ready for S&OP process or system upload
