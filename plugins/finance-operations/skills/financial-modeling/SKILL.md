# Financial Modeling Skill

## Overview
This skill covers financial modeling best practices, three-statement model design, scenario analysis, and techniques for building robust, flexible, and auditable financial models.

## Core Principles

### What is Financial Modeling?
Financial modeling is the process of building mathematical representations of a company's financial performance to support decision-making. Models typically project future financial statements based on historical performance, business drivers, and assumptions.

### Model Design Principles

**1. Separation of Concerns:**
```
INPUTS (Blue) → CALCULATIONS (Black) → OUTPUTS (Green)

- Inputs: All assumptions in dedicated area (color-coded blue)
- Calculations: Formulas referencing inputs (black font)
- Outputs: Final results and summaries (green font)
- Never hardcode numbers in formulas
```

**2. Transparency and Auditability:**
- Clear labeling and structure
- One formula per row (consistent across columns)
- Show work (intermediate calculations visible)
- Avoid complex nested formulas
- Include data validation and error checks

**3. Flexibility:**
- Easy to update assumptions
- Supports scenario analysis (base, upside, downside)
- Sensitivity analysis capability
- Modular structure (add/remove sections)

**4. Accuracy:**
- Balance checks (assets = liabilities + equity)
- Cash flow reconciliation
- P&L ties to balance sheet and cash flow
- Error flags for broken links

## Three-Statement Model Structure

### 1. Income Statement (P&L)
```
REVENUE
  Product Revenue
  Service Revenue
  Other Revenue
Total Revenue

COST OF REVENUE
  Direct Labor
  Direct Materials
  Other COGS
Gross Profit
Gross Margin %

OPERATING EXPENSES
  Sales & Marketing
  Research & Development
  General & Administrative
Total Operating Expenses

EBITDA
EBITDA Margin %

Depreciation & Amortization
EBIT

Interest Expense
Interest Income
EBT (Earnings Before Tax)

Income Tax Expense
Tax Rate %

NET INCOME
Net Margin %
```

### 2. Balance Sheet
```
ASSETS
Current Assets:
  Cash & Equivalents
  Accounts Receivable
  Inventory
  Prepaid Expenses
  Other Current Assets
Total Current Assets

Non-Current Assets:
  Property, Plant & Equipment (gross)
  Less: Accumulated Depreciation
  PP&E (net)
  Intangible Assets
  Goodwill
  Other Long-Term Assets
Total Non-Current Assets

TOTAL ASSETS

LIABILITIES & EQUITY
Current Liabilities:
  Accounts Payable
  Accrued Expenses
  Deferred Revenue (current)
  Short-Term Debt
  Other Current Liabilities
Total Current Liabilities

Non-Current Liabilities:
  Long-Term Debt
  Deferred Revenue (long-term)
  Other Long-Term Liabilities
Total Non-Current Liabilities

Shareholders' Equity:
  Common Stock
  Retained Earnings
Total Shareholders' Equity

TOTAL LIABILITIES & EQUITY

CHECK: Assets = Liabilities + Equity (should be $0)
```

### 3. Cash Flow Statement
```
OPERATING ACTIVITIES
Net Income
Adjustments for non-cash items:
  + Depreciation & Amortization
  + Stock-based compensation
  - Gain on asset sale (or + Loss)
Changes in working capital:
  - Increase in A/R (or + Decrease)
  + Increase in A/P (or - Decrease)
  - Increase in Inventory (or + Decrease)
  + Increase in Accrued Expenses
  + Increase in Deferred Revenue
Cash Flow from Operations

INVESTING ACTIVITIES
  Capital Expenditures (CapEx)
  Acquisitions
  Asset sales
  Investment purchases/sales
Cash Flow from Investing

FINANCING ACTIVITIES
  Debt proceeds
  Debt repayment
  Equity raised
  Dividends paid
  Share buybacks
Cash Flow from Financing

NET CHANGE IN CASH
Beginning Cash
Ending Cash

CHECK: Ending Cash = Balance Sheet Cash
```

## Model Linkages

### Income Statement to Balance Sheet
```
Net Income → Retained Earnings
Depreciation → Accumulated Depreciation (reduction)
Revenue → Deferred Revenue (if applicable)
COGS → Inventory (indirect through production)
```

### Balance Sheet to Cash Flow
```
Change in A/R → Operating Cash Flow
Change in Inventory → Operating Cash Flow
Change in A/P → Operating Cash Flow
CapEx → Investing Cash Flow
Debt issuance/repayment → Financing Cash Flow
```

### Cash Flow to Balance Sheet
```
Net Cash Flow → Change in Cash Balance
Ending Cash → Balance Sheet Cash
```

## Supporting Schedules

### Revenue Build-Up (Driver-Based)
```
SaaS Revenue Model:

Customers, Beginning of Period
+ New Customers (from sales forecast)
- Churned Customers (beginning × churn rate)
= Customers, End of Period

Average Customers in Period
× ARPU (Average Revenue Per User)
= Monthly Recurring Revenue

× 12 months
= Annual Recurring Revenue (ARR)

Plus: One-time implementation fees
Plus: Professional services
= Total Revenue
```

### Depreciation Schedule
```
For each asset category:

                Year 1  Year 2  Year 3  Year 4  Year 5
Beginning PP&E  $1,000  $1,200  $1,400  $1,400  $1,400
+ CapEx          $500    $500    $300    $200    $200
- Depreciation   ($300)  ($300)  ($300)  ($300)  ($300)
= Ending PP&E   $1,200  $1,400  $1,400  $1,300  $1,300

Depreciation Expense:
Equipment: Straight-line over 5 years
Buildings: Straight-line over 30 years
Software: Straight-line over 3 years

Total Depreciation → Income Statement
Accumulated Depreciation → Balance Sheet
```

### Debt Schedule
```
                Year 1  Year 2  Year 3  Year 4  Year 5
Beginning Debt  $5,000  $6,000  $7,000  $6,500  $6,000
+ New Borrowing $1,500  $1,500  $500    $0      $0
- Repayment     ($500)  ($500)  ($1,000)($500)  ($500)
= Ending Debt   $6,000  $7,000  $6,500  $6,000  $5,500

Interest Expense:
Average Debt Balance × Interest Rate
= ($5,000 + $6,000) / 2 × 5%
= $5,500 × 5% = $275

Interest Expense → Income Statement
Ending Debt → Balance Sheet (current + long-term)
```

### Working Capital Assumptions
```
Days Metrics:
- DSO (Days Sales Outstanding): 45 days
- DIO (Days Inventory Outstanding): 30 days (if applicable)
- DPO (Days Payable Outstanding): 30 days

Calculations:
A/R = Revenue / 365 × DSO
Inventory = COGS / 365 × DIO
A/P = COGS / 365 × DPO

Changes in working capital → Cash Flow Statement
Balances → Balance Sheet
```

## Scenario Analysis

### Base, Upside, Downside Scenarios
```
Scenario Switches:
Create dropdown or toggle to select scenario

Key assumptions that vary:
                Base    Upside  Downside
Revenue growth  20%     30%     10%
Gross margin    75%     78%     70%
Churn rate      5%      3%      8%
New customers   150/q   200/q   100/q
OpEx growth     15%     20%     10%

One model, multiple scenarios
Use IF statements or INDEX/MATCH to pull assumptions
```

### Sensitivity Analysis
```
Data Table (Excel):
Shows how output changes with input variations

Example: NPV sensitivity to revenue growth and discount rate

              Discount Rate
              8%      10%     12%     14%
Revenue
Growth:
15%           $20M    $18M    $16M    $14M
20%           $25M    $23M    $21M    $19M
25%           $30M    $28M    $26M    $24M
30%           $35M    $33M    $31M    $29M

Identifies key value drivers and risks
```

## Best Practices

### 1. Model Structure and Layout
```
Sheet 1: Executive Summary
- Key outputs and metrics
- Scenario selector
- Dashboard charts

Sheet 2: Assumptions
- All model inputs in one place
- Organized by category
- Clearly labeled
- Color-coded (blue background)

Sheet 3: Revenue Model
- Customer or unit-based build-up
- Driver calculations
- Supporting detail

Sheet 4: Expense Model
- Headcount-driven OpEx
- Other operating expenses
- CapEx forecast

Sheet 5: Financial Statements
- Income Statement
- Balance Sheet
- Cash Flow Statement
- Linked to assumptions and drivers

Sheet 6: Supporting Schedules
- Depreciation
- Debt
- Working capital
- Tax calculations

Sheet 7: Checks and Balances
- All error checks in one place
- Balance sheet check
- Cash flow reconciliation
- Formula audits
```

### 2. Formula Best Practices
```
Good Formula:
= assumptions!revenue_growth × prior_year_revenue

Bad Formula:
= 0.20 × 1000000 (hardcoded, not flexible)

Good Formula:
= SUM(B10:B20)

Bad Formula:
= B10 + B11 + B12 + B13... (manual, error-prone)

Good Formula:
= IF(scenario="Base", base_assumptions, IF(scenario="Upside", upside_assumptions, downside_assumptions))

Use named ranges for clarity:
= revenue_per_customer × customer_count
vs.
= B5 × C10
```

### 3. Error Checking
```
Balance Sheet Check:
= Assets - (Liabilities + Equity)
Should always = $0
Use conditional formatting to highlight if not zero

Cash Flow Check:
= Ending_Cash_from_CF_Statement - Cash_on_Balance_Sheet
Should always = $0

Revenue Check:
= SUM(monthly_revenue) - Annual_Revenue
Should always = $0

Circularity Check:
- Avoid circular references (debt interest based on cash,
  cash based on debt)
- Use iteration settings if unavoidable
- Or break circularity with prior period references
```

### 4. Documentation
```
Include:
- Model purpose and audience
- Key assumptions and sources
- Version history and change log
- Instructions for use
- Contact info for questions

Assumptions documentation:
Assumption: Revenue growth rate
Value: 20% annually
Source: Historical average (18%), adjusted for market expansion
Sensitivity: High (10% change = $X impact on valuation)
Last reviewed: 2024-01-15
Owner: CFO
```

### 5. Version Control
```
File naming convention:
CompanyName_ModelType_Version_Date.xlsx
Example: Acme_Budget2024_v2.3_2024-01-15.xlsx

Change log (within file):
Version  Date        Author    Changes
2.0      2024-01-01  CFO      Initial 2024 budget
2.1      2024-01-08  Analyst  Updated headcount assumptions
2.2      2024-01-12  CFO      Added scenario analysis
2.3      2024-01-15  CFO      Revised revenue forecast

Save major versions, track changes
```

## Common Model Types

### 1. Budget / Operating Plan Model
- 12-month detail by month
- Department-level expense detail
- Headcount planning
- CapEx plan
- Used for annual budgeting process

### 2. Long-Range Plan (LRP) Model
- 3-5 year annual projections
- Higher-level, strategic drivers
- Multiple scenarios
- Used for strategic planning

### 3. Valuation Model (DCF)
- Detailed financial projections
- Free cash flow calculation
- Terminal value
- Discount rate (WACC)
- Present value and valuation output

### 4. M&A Model
- Standalone target projections
- Acquisition consideration and structure
- Synergies (revenue and cost)
- Pro forma combined financials
- Returns analysis (IRR, NPV, accretion/dilution)

### 5. Project ROI Model
- Project-specific cash flows
- Implementation costs
- Ongoing benefits (revenue or cost savings)
- NPV, IRR, payback period
- Sensitivity analysis

## Advanced Techniques

### Monte Carlo Simulation
```
Process:
1. Identify uncertain variables (revenue growth, churn, etc.)
2. Assign probability distributions (normal, uniform, triangular)
3. Run thousands of simulations
4. Analyze distribution of outcomes

Tools:
- Excel add-ins (@RISK, Crystal Ball)
- Python (NumPy, SciPy)
- R (simulation packages)

Output:
- P10, P50, P90 outcomes
- Probability of achieving targets
- Risk-adjusted expected value
```

### Circular Reference Handling
```
Example: Interest expense depends on debt level, which depends on cash
flow, which depends on interest expense

Solutions:
1. Iteration (Excel setting):
   - Enable iterative calculation
   - Set max iterations and precision

2. Break circularity:
   - Use prior period for one reference
   - Interest based on beginning debt (not average)

3. Goal Seek / Solver:
   - Manually solve for balancing item
```

## Tools and Software

### Spreadsheet-Based
- Excel (most common, powerful with add-ins)
- Google Sheets (collaboration, web-based)
- Formulas: SUMIF, INDEX/MATCH, Data Tables, Scenarios

### Dedicated Software
- Adaptive Insights (planning and budgeting)
- Anaplan (connected planning)
- Host Analytics (CPM software)
- Planful (financial planning platform)

### Programming/Advanced
- Python (pandas, NumPy for modeling)
- R (statistical modeling)
- MATLAB (complex mathematical models)

## Integration with Other Skills

- **financial-forecasting-methods**: Core forecasting inputs to models
- **scenario-planning**: Develop model scenarios
- **budget-variance-analysis**: Track model accuracy
- **cash-flow-management**: Build cash flow projections
- **gaap-ifrs-compliance**: Ensure proper financial statement presentation

## Key Terminology

- **Three-Statement Model**: Integrated P&L, balance sheet, cash flow
- **Driver-Based Model**: Built from operational drivers (customers, FTE, units)
- **Scenario Analysis**: Multiple cases (base, upside, downside)
- **Sensitivity Analysis**: Test impact of changing assumptions
- **DCF**: Discounted Cash Flow valuation model
- **NPV**: Net Present Value
- **IRR**: Internal Rate of Return
- **WACC**: Weighted Average Cost of Capital
- **Terminal Value**: Value beyond explicit forecast period
- **Working Capital**: Current assets minus current liabilities
- **Free Cash Flow**: Operating cash flow minus CapEx

---

**Skill Type**: Technical/Analytical
**Difficulty**: Intermediate to Advanced
**Prerequisites**: Excel proficiency, financial statement knowledge, accounting basics
**Related Skills**: financial-forecasting-methods, scenario-planning, cash-flow-management
