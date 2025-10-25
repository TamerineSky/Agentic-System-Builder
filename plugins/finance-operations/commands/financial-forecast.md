You are tasked with generating comprehensive financial forecasts using driver-based models and advanced forecasting techniques.

## Objective
Create accurate, data-driven financial forecasts that support strategic planning, budgeting, and decision-making.

## Process

### 1. Historical Analysis
- Analyze 24-36 months of historical financial performance
- Identify trends, seasonality, and patterns
- Calculate key financial ratios and metrics
- Assess forecast accuracy of prior forecasts (if available)

### 2. Driver Identification
Identify and model key business drivers:

**Revenue Drivers:**
- Customer count (new, existing, churned)
- Average revenue per customer (ARPU/ACV)
- Units sold and average selling price
- Market size and penetration rate
- Seasonality factors

**Expense Drivers:**
- Headcount by department
- Average compensation and benefits
- Revenue-linked expenses (% of revenue)
- Volume-driven costs (per unit, per transaction)
- Fixed costs and commitments

### 3. Forecast Methodology Selection
Choose appropriate method(s):
- **Time-series**: Trend analysis, moving averages, exponential smoothing
- **Driver-based**: Build from operational drivers (customers × ARPU, FTE × salary)
- **Regression**: Statistical relationships between variables
- **Hybrid**: Combine statistical methods with business judgment

### 4. Scenario Development
Create multiple forecast scenarios:

**Base Case** (most likely, 50-60% probability):
- Conservative assumptions where uncertain
- Current trend continuation with known adjustments
- Used for official planning and guidance

**Upside Case** (optimistic, 20-30% probability):
- Favorable market conditions
- Better-than-expected execution
- Used for capacity planning

**Downside Case** (conservative, 20-30% probability):
- Unfavorable conditions
- Execution challenges
- Used for risk planning and contingencies

### 5. Model Construction
Build integrated financial forecast:
- Income Statement (P&L)
- Balance Sheet
- Cash Flow Statement
- Supporting schedules (headcount, CapEx, working capital)
- Key metrics and ratios

### 6. Validation and Refinement
- Sanity check outputs (growth rates, margins, ratios)
- Compare to industry benchmarks
- Validate assumptions with business leaders
- Perform sensitivity analysis on key drivers
- Document all assumptions and sources

### 7. Reporting
Generate forecast package including:
- Executive summary with key takeaways
- Financial statements (all scenarios)
- Driver assumptions and calculations
- Scenario comparison and sensitivities
- Risks and opportunities
- Recommendations

## Required Inputs
Provide the following information:
- **Forecast Type**: "quarterly" (4 quarters), "annual" (12 months), "rolling-4q", "long-range" (3-5 years)
- **Base Period**: Starting point for forecast (e.g., "2024-Q1", "2024-01")
- **Scenarios**: "base-only" or "base,upside,downside"
- **Key Assumptions**: Revenue growth rate, headcount plan, major initiatives (if known)
- **Data Source**: System to extract historical data (NetSuite, SAP, etc.)
- **Output Detail**: "summary" or "detailed"

## Output Format

Provide results in:
1. **Executive summary** with key forecast highlights and assumptions
2. **Financial statements** (P&L, Balance Sheet, Cash Flow) for all scenarios
3. **Driver model** showing customer/headcount/unit build-up
4. **Scenario comparison** table and charts
5. **Sensitivity analysis** showing impact of key assumption changes
6. **Assumption documentation** with sources and rationale

## Usage Examples

### Quarterly Forecast Update
```
/financial-forecast --type "rolling-4q" --base-period "2024-Q1" --scenarios "base,upside,downside"
```

### Annual Budget Preparation
```
/financial-forecast --type "annual" --base-period "2025-01" --scenarios "base" --output "detailed"
```

### Long-Range Strategic Plan
```
/financial-forecast --type "long-range" --base-period "2024" --scenarios "base,upside,downside" --years 5
```

## Best Practices
- Use driver-based models for transparency and flexibility
- Document all assumptions clearly with sources
- Track forecast vs. actual performance to improve accuracy
- Update rolling forecasts monthly or quarterly
- Validate assumptions with department leaders
- Perform sensitivity analysis on critical assumptions

---

**Skills Utilized:** financial-forecasting-methods, financial-modeling, scenario-planning, budget-variance-analysis
**Agent:** financial-forecaster
