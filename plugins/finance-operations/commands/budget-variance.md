You are tasked with performing comprehensive budget variance analysis.

## Objective
Identify, analyze, and explain material variances between budget and actual financial performance, providing actionable insights and root cause explanations.

## Process

### 1. Data Collection
- Extract actual financial results from the specified period
- Retrieve corresponding budget/forecast data
- Include prior year actuals for comparison
- Gather relevant operational metrics (headcount, customers, units, etc.)

### 2. Variance Calculation
- Calculate variances for all P&L line items ($ and %)
- Flag material variances per established thresholds (e.g., $50K and/or 10%)
- Categorize variances by type:
  - Volume variance (quantity-driven)
  - Price/rate variance (price-driven)
  - Mix variance (product/service mix changes)
  - Timing variance (period recognition differences)
  - One-time/non-recurring items

### 3. Root Cause Analysis
For each material variance:
- Investigate underlying business drivers
- Separate operational vs. accounting/timing differences
- Identify controllable vs. uncontrollable factors
- Link to specific business events or decisions
- Determine if temporary (will reverse) or permanent (impacts full-year)

### 4. Reporting
Generate comprehensive variance analysis including:

**Executive Summary:**
- Overall financial performance vs. budget
- Total variance impact on key metrics (Revenue, EBITDA, Net Income)
- Top 3-5 favorable variances with explanations
- Top 3-5 unfavorable variances with explanations
- Key insights and patterns
- Recommended actions

**Detailed Variance Report:**
- Line-by-line variance analysis for material items
- Clear explanations (1-2 sentences per variance)
- Business context and drivers
- Forward-looking implications
- Full-year forecast impact assessment

**Variance Trends:**
- Multi-period variance analysis (last 3-6 months)
- Identify patterns (widening, improving, seasonal)
- Recurring vs. one-time variances

### 5. Forward-Looking Assessment
- Determine if variances require forecast revision
- Estimate full-year impact of variances
- Identify mitigation strategies for unfavorable variances
- Assess opportunities from favorable variances

## Required Inputs
Provide the following information:
- **Period**: Month, quarter, or YTD (e.g., "March 2024", "Q1 2024", "YTD 2024")
- **Departments**: Specific departments or "all" for company-wide analysis
- **Materiality Threshold**: Dollar amount and/or percentage (e.g., "$50K or 10%")
- **Focus Areas**: Specific accounts or areas requiring deep dive (optional)
- **Data Source**: Financial system to extract data from (NetSuite, SAP, etc.)

## Output Format

Provide results in:
1. **Executive summary** (1 page) suitable for leadership review
2. **Detailed variance table** with explanations
3. **Variance trend charts** showing patterns over time
4. **Forecast impact assessment** with recommendations

## Usage Example
```
/budget-variance --period "2024-03" --departments "all" --threshold "50000 or 10%" --focus "revenue,marketing"
```

This command will generate a comprehensive variance analysis for March 2024 across all departments, flagging variances over $50K or 10%, with special attention to revenue and marketing variances.

---

**Skills Utilized:** budget-variance-analysis, financial-forecasting-methods, management-reporting
**Agent:** budget-variance-analyst
