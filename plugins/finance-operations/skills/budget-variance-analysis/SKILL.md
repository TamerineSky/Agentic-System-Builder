# Budget Variance Analysis Skill

## Overview
This skill provides comprehensive methods and techniques for performing budget variance analysis, identifying root causes, and generating actionable insights for financial performance management.

## Core Concepts

### What is Variance Analysis?
Variance analysis is the systematic investigation of differences between planned (budget) and actual financial performance. It helps organizations:
- Understand financial performance drivers
- Identify areas requiring management attention
- Improve future forecasting accuracy
- Support accountability and performance management

### Types of Variances

**Favorable vs. Unfavorable:**
- **Favorable**: Actual performance better than budget (higher revenue, lower costs)
- **Unfavorable**: Actual performance worse than budget (lower revenue, higher costs)

**Permanent vs. Temporary:**
- **Permanent**: Impact full-year forecast (market shift, pricing change)
- **Temporary**: Timing difference that will reverse (revenue recognition timing, delayed expense)

**Controllable vs. Uncontrollable:**
- **Controllable**: Within management's influence (discretionary spend, headcount)
- **Uncontrollable**: External factors (FX rates, commodity prices, regulation)

## Variance Calculation Methods

### Basic Variance Formula
```
Variance ($) = Actual - Budget
Variance (%) = (Actual - Budget) / Budget × 100%

Example:
Budget Revenue: $1,000,000
Actual Revenue: $1,150,000
Variance: $150,000 favorable (15% favorable)
```

### Volume vs. Price Variance
```
Volume Variance = (Actual Volume - Budget Volume) × Budget Price
Price Variance = (Actual Price - Budget Price) × Actual Volume
Mix Variance = Impact of product/service mix change on results

Example - Product Sales:
Budget: 10,000 units @ $100 = $1,000,000
Actual: 9,500 units @ $110 = $1,045,000

Volume Variance: (9,500 - 10,000) × $100 = ($50,000) unfavorable
Price Variance: ($110 - $100) × 9,500 = $95,000 favorable
Total Variance: ($50,000) + $95,000 = $45,000 favorable
```

### Headcount Variance (Labor)
```
Headcount Variance = (Actual FTE - Budget FTE) × Budget Rate
Rate Variance = (Actual Rate - Budget Rate) × Actual FTE

Example - Department Payroll:
Budget: 50 FTE @ $100K avg = $5,000,000
Actual: 48 FTE @ $105K avg = $5,040,000

Headcount Variance: (48 - 50) × $100K = ($200,000) favorable
Rate Variance: ($105K - $100K) × 48 = $240,000 unfavorable
Total Variance: ($200,000) + $240,000 = $40,000 unfavorable
```

## Materiality Thresholds

### Setting Appropriate Thresholds
```
Typical Materiality Standards:
- Dollar threshold: $50K, $100K, $500K (based on company size)
- Percentage threshold: 5%, 10%, 15% (based on predictability)
- Combined: $50K AND 10% (both must be met)

Example Application:
Account: Marketing Expense
Budget: $500,000
Actual: $540,000
Variance: $40,000 (8%)

If threshold is $50K: Not material (below threshold)
If threshold is 10%: Not material (below threshold)
If threshold is $50K OR 10%: Not material
If threshold is $25K OR 5%: Material (exceeds both)
```

### Account-Specific Thresholds
Different accounts may warrant different thresholds:
- **Revenue**: Lower threshold (5%) due to strategic importance
- **COGS**: Medium threshold (10%) based on volume sensitivity
- **Fixed G&A**: Higher threshold (15%) due to predictability
- **One-time items**: Always investigate regardless of threshold

## Root Cause Identification Framework

### The "5 Whys" Technique
```
Example: Marketing expense $100K over budget

Why #1: Why is marketing over budget?
→ Digital advertising spend higher than planned

Why #2: Why was digital advertising higher?
→ Cost per click increased 40% during the quarter

Why #3: Why did cost per click increase?
→ Competitive bidding intensified for key search terms

Why #4: Why did competitive bidding intensify?
→ Three new competitors entered market with aggressive marketing

Why #5: Why didn't we adjust strategy when CPC increased?
→ Lack of real-time monitoring and spending controls

Root Cause: Need real-time spend monitoring and dynamic budget reallocation
```

### Variance Category Framework

**Operating Variances:**
- Volume changes (higher/lower customer activity)
- Price changes (different pricing achieved)
- Efficiency variances (productivity, waste)
- Mix variances (product/customer mix shifts)

**Timing Variances:**
- Revenue recognition timing
- Expense accrual timing
- Seasonal pattern differences
- Project milestone timing

**One-Time/Non-Recurring:**
- Restructuring charges
- Legal settlements
- Asset impairments
- M&A transaction costs

**Accounting/Classification:**
- Reclassifications between accounts
- Accrual vs. cash timing
- Intercompany eliminations
- FX translation impacts

## Best Practices

### 1. Focus on Actionable Insights
```
Poor Variance Explanation:
"Marketing exceeded budget by $100K due to higher digital spend."

Better Variance Explanation:
"Marketing exceeded budget by $100K (15%) due to 40% increase in Google Ads
cost-per-click in competitive enterprise segments. This variance is expected
to persist; recommend shifting $50K/month to lower-cost content marketing
channels or increasing budget for Q3-Q4."
```

### 2. Use Consistent Formats
```
Standard Variance Commentary Template:

Account: [Account Name]
Variance: $[X] ([Y]%) [favorable/unfavorable]

Root Cause:
[1-2 sentence explanation of primary driver]

Business Context:
[Additional detail on why this occurred]

Forward-Looking Impact:
[Will this reverse? Does forecast need adjustment?]

Action Required:
[What should management do? If any]
```

### 3. Trend Analysis
Don't just analyze current period - look at patterns:
```
Revenue Variance Trend (Last 6 Months):
Jan: ($50K)  unfavorable
Feb: ($40K)  unfavorable
Mar: ($60K)  unfavorable
Apr: ($80K)  unfavorable
May: ($90K)  unfavorable
Jun: ($100K) unfavorable

Pattern: Widening unfavorable trend
Implication: Structural issue, not random variation
Action: Revise forecast down, investigate market share loss
```

### 4. Link to Business Drivers
```
Financial Metric           Business Driver
--------------------------------------------
Revenue variance     →     Customer count, ARPU, churn
COGS variance       →     Units sold, material costs, labor rates
Payroll variance    →     Headcount, average salary, overtime
Marketing variance  →     Campaign spend, CAC, channel mix
```

### 5. Separate Timing from True Variances
```
Example - Revenue Variance:

Total Variance: ($200K) unfavorable

Decomposition:
- Timing variance: ($150K) - Revenue delayed to next month
- True variance: ($50K) - Lost customer deal
- FX variance: $0 - No currency impact this period

Forecast Impact:
- Current quarter: ($200K)
- Next quarter: +$150K (timing reversal)
- Full year: ($50K)
- Recommended FY forecast adjustment: ($50K)
```

## Practical Applications

### Monthly Variance Review Process
```
1. Extract Data (Day 1-2 post close)
   - Pull GL actuals
   - Extract budget comparison
   - Generate variance report

2. Calculate Variances (Day 2-3)
   - $ and % variances for all accounts
   - Flag material variances per thresholds
   - Categorize by department/cost center

3. Investigate Material Variances (Day 3-5)
   - Contact department owners
   - Review supporting documentation
   - Identify root causes
   - Assess forward impact

4. Document Explanations (Day 5-6)
   - Write variance commentary
   - Update forecast if needed
   - Prepare executive summary

5. Report and Review (Day 7)
   - Distribute to stakeholders
   - Executive review meeting
   - Track action items
```

### Variance Analysis by Statement Type

**Income Statement Variances:**
```
Focus Areas:
- Revenue by product/segment
- Gross margin %
- Major expense categories (payroll, marketing, R&D)
- EBITDA and operating income

Key Questions:
- Is revenue variance volume or price?
- Is gross margin variance mix or cost?
- Are expense variances controllable?
- What's the EBITDA impact?
```

**Balance Sheet Variances:**
```
Focus Areas:
- Working capital (A/R, inventory, A/P)
- CapEx spending vs. plan
- Debt levels
- Cash balance

Key Questions:
- Is working capital efficient (DSO, DIO, DPO)?
- Is CapEx on track with strategic plan?
- Are we compliant with debt covenants?
- Do we have adequate liquidity?
```

**Cash Flow Variances:**
```
Focus Areas:
- Operating cash flow
- Cash conversion vs. P&L income
- CapEx spending
- Cash runway

Key Questions:
- Why is operating CF different from net income?
- Are working capital changes as expected?
- Is CapEx spending creating value?
- How many months of runway remain?
```

## Common Variance Scenarios

### Scenario 1: Revenue Miss
```
Situation: Revenue $500K (10%) below budget

Investigation:
- New customer adds: On track (200 new customers vs. 200 budget)
- Churn: Higher than expected (50 churned vs. 30 budget)
- ARPU: Slightly lower ($10K vs. $10.5K budget)

Root Cause:
- Churn driven by product quality issues in Feb release
- ARPU decline due to competitive pricing pressure

Variance Breakdown:
- Volume (churn): ($10.5K × 20 extra churned) = ($210K)
- Price (ARPU): ($0.5K × 1,150 customers) = ($575K)
- Volume (new customers): $0
Total: ($785K) ... wait, doesn't match!

Refined Analysis:
Need to account for beginning base, not just changes. Use more sophisticated
cohort analysis to fully explain $500K variance.
```

### Scenario 2: Favorable Expense Variance
```
Situation: Engineering expense $300K (15%) below budget

Investigation:
- Headcount: 48 FTE vs. 50 budget (2 open positions)
- Average salary: $120K vs. $125K budget (hired more junior)
- Software spend: $50K vs. $100K budget (negotiated discount)

Root Cause:
- Hiring delays for 2 positions (1 month vacant each)
- Backfilled senior departure with 2 junior engineers
- Renegotiated tooling contract mid-year

Variance Breakdown:
- Headcount variance: (48 - 50) × $125K / 12 months = ($20.8K)
- Rate variance: ($120K - $125K) × 48 / 12 months = ($20K)
- Software: ($100K - $50K) / 12 months × 1 month = ($4.2K)
- Total: ~$45K (need full-year view for $300K)

Forward Impact:
- Headcount variance will reverse when positions filled
- Rate variance permanent (junior hiring strategy)
- Software savings permanent (new contract)
- Forecast adjustment: ($200K) for full year
```

## Tools and Templates

### Variance Analysis Spreadsheet
```
Columns needed:
- Account number and description
- Department/Cost center
- Budget
- Actual
- Variance ($)
- Variance (%)
- Prior year actual (for comparison)
- Variance category (Volume, Price, Timing, etc.)
- Explanation
- Action required
- Owner
- Status
```

### Variance Dashboard Metrics
```
Key metrics to track:
- Total variance as % of budget
- Number of material variances
- % of variances explained
- Revenue variance YTD
- EBITDA variance YTD
- Forecast accuracy (variance trend)
```

### Automation Opportunities
- Automated variance calculation (flag material items)
- Trend charts (variance over time)
- Drill-down to transaction detail
- Variance commentary templates
- Workflow for department review and approval

## Integration with Other Skills

- **financial-forecasting-methods**: Use variance insights to improve forecasts
- **cost-allocation**: Understand cost drivers for expense variances
- **management-reporting**: Include variance analysis in reports
- **scenario-planning**: Model variance scenarios
- **gaap-ifrs-compliance**: Ensure proper accounting for variances

## Key Terminology

- **Variance**: Difference between actual and budget/forecast
- **Material**: Exceeds significance threshold requiring investigation
- **Favorable**: Better than budget (higher revenue, lower cost)
- **Unfavorable**: Worse than budget (lower revenue, higher cost)
- **Volume Variance**: Due to quantity differences
- **Price/Rate Variance**: Due to rate/price differences
- **Mix Variance**: Due to product/customer mix changes
- **Timing Variance**: Due to period recognition differences
- **Permanent Variance**: Impacts full-year forecast
- **Temporary Variance**: Reverses in future periods

---

**Skill Type**: Analytical methodology
**Difficulty**: Intermediate
**Prerequisites**: Basic accounting knowledge, understanding of budgeting
**Related Skills**: financial-forecasting-methods, management-reporting, cost-allocation
