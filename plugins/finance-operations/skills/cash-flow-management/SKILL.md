# Cash Flow Management Skill

## Overview
This skill provides comprehensive techniques for cash forecasting, working capital optimization, liquidity analysis, and cash management best practices.

## Core Concepts

### Cash Flow vs. Profit
```
Key Difference:
Profit (Accrual) = Revenue - Expenses (when earned/incurred)
Cash Flow = Cash In - Cash Out (when received/paid)

Example:
Sale: $100K invoice in January (Revenue recognized)
Collection: Received in March (Cash flow occurs)

Profit impact: January
Cash impact: March (2-month lag)
```

### Cash Flow Components

**Operating Cash Flow:**
- Collections from customers
- Payments to suppliers
- Payroll and benefits
- Operating expenses
- Taxes and interest

**Investing Cash Flow:**
- Capital expenditures (CapEx)
- Asset purchases/sales
- Acquisitions and divestitures

**Financing Cash Flow:**
- Debt borrowings and repayments
- Equity raises
- Dividends/distributions
- Share buybacks

## Cash Forecasting Methods

### 1. Direct Method (Receipts and Disbursements)
```
Weekly/Monthly Cash Forecast:

BEGINNING CASH                    $1,000,000

CASH RECEIPTS:
Customer collections               $500,000
Other income                        $20,000
Total Receipts                     $520,000

CASH DISBURSEMENTS:
Vendor payments                   ($250,000)
Payroll                           ($180,000)
Rent                               ($30,000)
Debt service                       ($40,000)
Taxes                              ($15,000)
Other                              ($25,000)
Total Disbursements               ($540,000)

NET CASH FLOW                      ($20,000)
ENDING CASH                        $980,000

Minimum required                   $500,000
Excess/(Deficit)                   $480,000
```

**Advantages:**
- Detailed visibility into cash timing
- Useful for short-term (weekly, daily) forecasting
- Identifies specific cash needs

**Best for:** 13-week rolling forecasts, daily cash positioning

### 2. Indirect Method (From Net Income)
```
Starting with P&L:

NET INCOME                         $100,000

Non-cash adjustments:
+ Depreciation                      $50,000
+ Amortization                      $20,000
- Gain on asset sale                ($5,000)

Working capital changes:
- Increase in A/R                  ($30,000)
- Decrease in inventory             $15,000
- Increase in A/P                   $25,000
- Increase in accrued expenses      $10,000

OPERATING CASH FLOW                $185,000

INVESTING CASH FLOW:
- Capital expenditures             ($75,000)

FINANCING CASH FLOW:
+ Debt proceeds                     $50,000
- Debt repayment                   ($20,000)

NET CASH FLOW                      $140,000
```

**Advantages:**
- Ties to financial statements
- Shows cash conversion from profit
- Good for monthly/quarterly forecasts

**Best for:** Management reporting, annual forecasts

### 3. Rolling 13-Week Cash Forecast
```
Purpose: Maintain constant 13-week forward visibility

Process:
Week 1: Each Monday, update forecast
- Replace Week 1 forecast with actuals
- Add new Week 13 at end
- Revise assumptions for Weeks 2-12 based on latest info

Example structure:
        W1    W2    W3    W4    W5-13
Begin   $1.0M $1.1M $0.9M $1.2M ...
+ Coll  $0.5M $0.6M $0.4M $0.7M ...
- Disb  $0.4M $0.8M $0.1M $0.6M ...
= End   $1.1M $0.9M $1.2M $1.3M ...

Min Req $0.5M $0.5M $0.5M $0.5M ...
Surplus $0.6M $0.4M $0.7M $0.8M ...

Flag: Any week with deficit triggers action plan
```

## Working Capital Management

### Key Metrics

**Days Sales Outstanding (DSO):**
```
DSO = (Accounts Receivable / Revenue) × 365

Example:
A/R: $2,000,000
Annual Revenue: $24,000,000
DSO: ($2M / $24M) × 365 = 30.4 days

Interpretation:
- Average time to collect after sale
- Lower is better (faster collection)
- Compare to payment terms (Net 30, Net 60)

Improvement actions:
- Invoice promptly
- Send payment reminders
- Offer early payment discounts (2/10 Net 30)
- Automate collections process
```

**Days Payable Outstanding (DPO):**
```
DPO = (Accounts Payable / COGS) × 365

Example:
A/P: $1,500,000
Annual COGS: $18,000,000
DPO: ($1.5M / $18M) × 365 = 30.4 days

Interpretation:
- Average time to pay suppliers
- Higher is better for cash (retain cash longer)
- But maintain good supplier relationships

Optimization actions:
- Use full payment terms (pay on day 30, not day 10)
- Negotiate extended terms (Net 60 vs Net 30)
- Take early payment discounts only if attractive (>18% ROI)
```

**Days Inventory Outstanding (DIO):**
```
DIO = (Inventory / COGS) × 365

Example:
Inventory: $1,000,000
Annual COGS: $18,000,000
DIO: ($1M / $18M) × 365 = 20.3 days

Interpretation:
- Average time inventory held before sale
- Lower is better (less cash tied up)
- Balance with stockout risk

Improvement actions:
- Just-in-time inventory management
- Demand forecasting to reduce safety stock
- Faster inventory turnover
- Consignment arrangements
```

**Cash Conversion Cycle (CCC):**
```
CCC = DSO + DIO - DPO

Example:
DSO: 30 days
DIO: 20 days
DPO: 30 days
CCC: 30 + 20 - 30 = 20 days

Interpretation:
- Time from cash out (pay supplier) to cash in (customer pays)
- Lower is better
- Negative CCC is ideal (collect before paying)

SaaS Company Example:
DSO: 30 days (Net 30 terms)
DIO: 0 days (no inventory)
DPO: 45 days (extended vendor terms)
CCC: 30 + 0 - 45 = -15 days (NEGATIVE - very cash efficient!)
```

## Liquidity Ratios

### Current Ratio
```
Current Ratio = Current Assets / Current Liabilities

Example:
Current Assets: $5,000,000
Current Liabilities: $2,500,000
Current Ratio: 2.0

Interpretation:
- >1.0: Can cover short-term obligations
- 1.5-2.0: Healthy liquidity
- <1.0: Potential liquidity issues
- >3.0: Inefficient (too much working capital)
```

### Quick Ratio (Acid Test)
```
Quick Ratio = (Current Assets - Inventory) / Current Liabilities

Example:
Current Assets: $5,000,000
Inventory: $1,000,000
Current Liabilities: $2,500,000
Quick Ratio: ($5M - $1M) / $2.5M = 1.6

Interpretation:
- More conservative than current ratio
- >1.0: Strong immediate liquidity
- Excludes inventory (less liquid)
```

### Cash Ratio
```
Cash Ratio = Cash & Equivalents / Current Liabilities

Example:
Cash: $1,500,000
Current Liabilities: $2,500,000
Cash Ratio: 0.6

Interpretation:
- Most conservative liquidity measure
- Shows ability to pay with cash only
- >0.5: Strong cash position
```

## Cash Optimization Strategies

### Accelerate Collections
```
1. Invoice Immediately
   - Bill upon delivery, not end of month
   - Electronic invoicing for speed

2. Shorten Payment Terms
   - Net 30 instead of Net 60
   - Due upon receipt for small amounts

3. Early Payment Discounts
   - 2/10 Net 30 (2% discount if paid in 10 days)
   - Customer benefit: 36% annual return
   - Your cost: 2% of invoice

4. Automated Reminders
   - Day 15: Friendly reminder
   - Day 30: Payment due notice
   - Day 45: Escalation

5. Multiple Payment Methods
   - ACH (fastest, lowest cost)
   - Credit card (fastest, higher cost)
   - Wire transfer (for large amounts)

6. Deposits and Milestones
   - 50% upfront for large projects
   - Progress billing based on milestones
```

### Optimize Disbursements
```
1. Use Full Payment Terms
   - If Net 30, pay on day 30 (not day 5)
   - Retain cash as long as possible

2. Negotiate Extended Terms
   - Request Net 60 or Net 90
   - Especially for large vendors

3. Take Early Payment Discounts Strategically
   - 2/10 Net 30 = 36.7% annual return
   - Formula: (Discount % / (100% - Discount%)) × (365 / (Full terms - Discount period))
   - 2/10 Net 30: (2/98) × (365/20) = 37.2%
   - Take discount if return > your cost of capital

4. Batch Payments
   - Reduce transaction fees
   - Minimize banking time
   - Weekly payment runs

5. Use Credit Cards for Float
   - Extra 30-day float if no fees
   - Useful for recurring expenses
```

### Reduce Working Capital
```
1. Inventory Optimization
   - Lower safety stock levels
   - Improve demand forecasting
   - Just-in-time ordering
   - Drop-shipping (no inventory)

2. A/R Management
   - Tighter credit policies
   - Earlier escalation on aging
   - Collections incentives

3. A/P Optimization
   - Negotiate better terms
   - Consolidate vendors for leverage
   - Use procurement cards

4. Cash Management
   - Sweep accounts (automatically move excess)
   - Interest-bearing accounts
   - Short-term investments for excess cash
```

## Scenario Planning

### Base, Stressed, Optimistic Scenarios
```
BASE CASE:
- Collections: 70% in month, 28% in month+1, 2% uncollectible
- Revenue growth: 20% annually
- Payment terms: Pay vendors Net 30

STRESSED CASE:
- Collections: 50% in month, 40% in month+1, 10% uncollectible
- Revenue growth: 0% (flat)
- Payment terms: Vendors demand Net 15
- Impact: $500K cash deficit, need funding

OPTIMISTIC CASE:
- Collections: 80% in month, 19% in month+1, 1% uncollectible
- Revenue growth: 40% annually
- Payment terms: Extended to Net 45
- Impact: $300K cash surplus, opportunity for investment
```

## Best Practices

### 1. Maintain Rolling Forecasts
- 13-week cash forecast updated weekly
- Monthly forecast for 12 months updated monthly
- Track actuals vs. forecast, refine assumptions

### 2. Monitor Key Metrics
- Days of cash on hand (runway)
- Working capital metrics (DSO, DPO, CCC)
- Liquidity ratios
- Burn rate (for growth companies)

### 3. Establish Cash Reserves
```
Recommended reserves:
- Startups: 12-18 months of burn
- Growth companies: 6-12 months
- Mature companies: 3-6 months
- Cyclical businesses: Higher reserves for downturns
```

### 4. Automate Where Possible
- Automated A/R collection reminders
- Automated payment processing
- Cash position reporting dashboards
- Bank feed integration

### 5. Communicate Proactively
- Weekly cash report to CFO/CEO
- Alert stakeholders to potential shortfalls early
- Provide recommended actions
- Maintain transparency on assumptions

## Integration with Other Skills

- **financial-forecasting-methods**: Forecast revenue and expenses for cash planning
- **budget-variance-analysis**: Understand variances impacting cash
- **financial-modeling**: Build integrated cash flow models
- **scenario-planning**: Develop cash scenarios
- **gaap-ifrs-compliance**: Proper cash flow statement presentation

## Key Terminology

- **Operating Cash Flow**: Cash from core business operations
- **Free Cash Flow**: Operating cash flow minus CapEx
- **DSO**: Days Sales Outstanding (collection period)
- **DPO**: Days Payable Outstanding (payment period)
- **DIO**: Days Inventory Outstanding (inventory holding period)
- **Cash Conversion Cycle**: DSO + DIO - DPO
- **Burn Rate**: Monthly cash consumption
- **Runway**: Months of cash remaining at current burn
- **Working Capital**: Current assets minus current liabilities
- **Liquidity**: Ability to meet short-term obligations

---

**Skill Type**: Financial management
**Difficulty**: Intermediate
**Prerequisites**: Basic accounting, financial statements
**Related Skills**: financial-forecasting-methods, financial-modeling, budget-variance-analysis
