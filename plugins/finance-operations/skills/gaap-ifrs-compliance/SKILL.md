# GAAP/IFRS Compliance Skill

## Overview
This skill covers accounting standards, compliance requirements, financial statement preparation, and key differences between US GAAP and IFRS for proper financial reporting.

## Core Concepts

### What are GAAP and IFRS?

**GAAP (Generally Accepted Accounting Principles):**
- US accounting standards
- Rules-based approach (detailed, specific guidance)
- Set by FASB (Financial Accounting Standards Board)
- Required for US public companies
- Many private companies also follow GAAP

**IFRS (International Financial Reporting Standards):**
- International accounting standards
- Principles-based approach (broader guidance, more judgment)
- Set by IASB (International Accounting Standards Board)
- Used in 140+ countries
- Required in EU, many other jurisdictions

**Why Compliance Matters:**
- Legal requirement for public companies
- Audit requirements
- Investor and lender expectations
- Comparability across companies and periods
- Credibility of financial reporting

## Key GAAP Standards and Concepts

### Revenue Recognition (ASC 606)

**Five-Step Model:**
```
Step 1: Identify the contract with customer
Step 2: Identify performance obligations
Step 3: Determine transaction price
Step 4: Allocate transaction price to performance obligations
Step 5: Recognize revenue when (or as) performance obligations satisfied

Example - SaaS Company:
Contract: $100K annual subscription + $20K implementation

Performance Obligations:
1. Implementation (satisfied at point in time)
2. Subscription (satisfied over time)

Transaction Price: $120K total

Allocation:
- Implementation: $20K (standalone selling price)
- Subscription: $100K (standalone selling price)

Recognition:
- Implementation: $20K recognized upon go-live
- Subscription: $100K / 12 = $8.3K per month over 12 months
```

**Key Concepts:**
```
Point in time revenue:
- Control transfers at specific moment
- Examples: Product sale, implementation service, license

Over time revenue:
- Control transfers continuously
- Examples: Subscription, maintenance, managed services

Variable consideration:
- Estimate expected value or most likely amount
- Constrain estimate to avoid reversal
- Examples: Volume discounts, rebates, performance bonuses
```

### Lease Accounting (ASC 842)

**Lessee Accounting:**
```
All leases (>12 months) go on balance sheet

Operating Lease:
- Right-of-use (ROU) asset
- Lease liability
- Straight-line expense recognition

Finance Lease (formerly capital lease):
- ROU asset (depreciated)
- Lease liability
- Interest expense + depreciation

Example - Office Lease:
Term: 5 years
Annual payment: $100K
Discount rate: 6%

PV of lease payments: $421K

Balance Sheet:
- ROU asset: $421K (asset)
- Lease liability: $421K (liability)

P&L (Year 1):
- Lease expense: $100K (operating lease)
  OR
- Interest: $25K + Depreciation: $84K = $109K (finance lease)
```

### Financial Statement Presentation

**Balance Sheet Classification:**
```
Current vs. Non-Current:
- Current: Due within 12 months or operating cycle
- Non-Current: Beyond 12 months

Example:
Deferred Revenue (SaaS company):
- $10M total deferred revenue
- $8M expected to be recognized in next 12 months = Current
- $2M beyond 12 months = Non-current
```

**Income Statement:**
```
Required elements:
- Revenue
- Cost of revenue (COGS)
- Gross profit
- Operating expenses
- Operating income
- Other income/expense
- Income tax expense
- Net income
- Earnings per share (if public)

Non-GAAP metrics (allowed but must reconcile):
- EBITDA
- Adjusted EBITDA
- Non-GAAP net income
- Free cash flow
```

**Cash Flow Statement:**
```
Three sections:
1. Operating Activities
   - Indirect method (start with net income) most common
   - Direct method (show cash receipts/payments) allowed

2. Investing Activities
   - CapEx
   - Acquisitions/divestitures
   - Investment purchases/sales

3. Financing Activities
   - Debt proceeds/repayments
   - Equity transactions
   - Dividends
```

## Key GAAP vs. IFRS Differences

### Revenue Recognition
```
GAAP (ASC 606) vs. IFRS (IFRS 15):
- Largely converged (similar 5-step model)
- Minor differences in implementation guidance
- IFRS slightly more principles-based

Practical impact: Minimal for most companies
```

### Lease Accounting
```
GAAP (ASC 842) vs. IFRS (IFRS 16):

GAAP: Operating vs. Finance lease classification
IFRS: Single lessee model (all leases treated like finance leases)

Example impact:
$100K annual lease, 5 years

GAAP (if operating):
- Expense: $100K/year (straight-line)

IFRS:
- Interest + Depreciation (front-loaded expense pattern)
- Year 1: ~$109K, Year 5: ~$92K

Total expense same over lease term, timing differs
```

### Inventory
```
GAAP:
- FIFO, LIFO, or Average cost allowed
- LIFO widely used (tax benefits)

IFRS:
- FIFO or Average cost only
- LIFO prohibited

Impact: US companies may show lower COGS under LIFO in inflationary periods
```

### Development Costs
```
GAAP:
- R&D expensed as incurred
- Software development costs capitalized after technological feasibility

IFRS (IAS 38):
- Research expensed
- Development capitalized if criteria met (technical feasibility, intent to
  complete, ability to use/sell, probable future benefits, ability to measure)

Impact: IFRS companies may capitalize more development costs
```

### Financial Statement Presentation
```
GAAP:
- Specific line items required
- Classified balance sheet (current/non-current)
- Single or multi-step income statement

IFRS:
- More flexibility in presentation
- Minimum line items specified
- Can present by function or nature
- Additional options (e.g., presenting comprehensive income)
```

## Common Compliance Areas

### Accrual Accounting
```
Revenue Recognition:
- Recognize when earned, not when cash received
- Match revenue to period when performance obligation met

Expense Recognition:
- Match expenses to period when incurred
- Recognize when obligation created, not when paid

Example:
December services delivered, invoice sent Jan 5, paid Jan 30

GAAP Treatment:
- Revenue: Recognize in December (when earned)
- A/R: Record in December
- Cash: Increase in January (when paid)
```

### Cut-Off Procedures
```
Month-End/Year-End Cut-Off:

Ensure transactions recorded in correct period:

Revenue:
- Shipped 12/31, received by customer 1/2 → December revenue (if shipped FOB)
- Subscription service for January billed 12/25 → Deferred to January

Expenses:
- Invoice dated 12/28, received 1/5, goods received 12/30 → December expense
- January rent paid 12/20 → Prepaid expense in December, expense in January

Importance: Material cut-off errors can require restatement
```

### Disclosure Requirements

**GAAP Footnote Disclosures:**
```
Required footnotes:
1. Summary of Significant Accounting Policies
   - Revenue recognition policy
   - Inventory valuation
   - Depreciation methods and lives
   - Use of estimates

2. Revenue Recognition
   - Disaggregation by type, geography, timing
   - Contract balances (A/R, deferred revenue)
   - Performance obligations
   - Significant judgments

3. Fair Value Measurements
   - Fair value hierarchy (Level 1, 2, 3)
   - Valuation techniques
   - Assumptions

4. Debt
   - Terms, maturity, interest rates
   - Covenants
   - Fair value
   - Future maturities

5. Leases
   - Lease costs by type
   - Maturity analysis
   - Assumptions (discount rate)

6. Income Taxes
   - Effective tax rate reconciliation
   - Deferred tax assets/liabilities
   - Tax loss carryforwards

7. Stock-Based Compensation
   - Description of plans
   - Valuation methods
   - Expense recognized

8. Commitments and Contingencies
   - Litigation
   - Purchase commitments
   - Guarantees

9. Subsequent Events
   - Material events after balance sheet date
```

## Compliance Best Practices

### 1. Maintain Strong Documentation
```
Required documentation:
- Revenue recognition memos
- Lease classification analyses
- Fair value determinations
- Impairment testing
- Tax provisions
- Journal entry support

Best practices:
- Document judgments and estimates
- Update memos annually or when facts change
- Maintain for audit trail (7+ years)
- Use consistent templates
```

### 2. Implement Internal Controls
```
Key controls:
- Segregation of duties (preparer vs. reviewer)
- Authorization limits
- Reconciliations (bank, A/R, A/P, inventory)
- Cut-off procedures
- Financial close checklist
- Review and approval processes

SOX compliance (if applicable):
- Document key controls
- Test operating effectiveness
- Remediate deficiencies
- Management certification
```

### 3. Stay Current with Standards
```
Monitor for updates:
- FASB Accounting Standards Updates (ASUs)
- IASB exposure drafts and standards
- Industry-specific guidance
- SEC rules and regulations (if public)

Recent major standards:
- ASC 606 (Revenue Recognition) - 2018
- ASC 842 (Leases) - 2019
- ASU 2016-13 (CECL - Current Expected Credit Losses) - 2023
```

### 4. Engage Auditors Appropriately
```
Best practices:
- Early consultation on complex transactions
- Pre-implementation review of new standards
- Quarterly reviews (if public)
- Annual audit planning
- Technical accounting questions resolved timely

Areas to consult:
- New revenue contracts with unusual terms
- Complex lease arrangements
- Business combinations
- Restructuring charges
- Fair value measurements
```

## Common Compliance Pitfalls

### Revenue Recognition Errors
```
Common mistakes:
1. Recognizing before performance obligation met
   - Example: SaaS company recognizing annual contract upfront
   - Correct: Recognize ratably over subscription period

2. Improper allocation to performance obligations
   - Example: Not separately pricing implementation
   - Correct: Allocate based on standalone selling prices

3. Incorrect contract modification accounting
   - Example: Treating add-on as separate contract when should be modification
   - Correct: Apply ASC 606 modification guidance

4. Missing variable consideration constraint
   - Example: Recognizing full bonus even if unlikely
   - Correct: Constrain to amount probable not to reverse
```

### Expense Capitalization Errors
```
Common mistakes:
1. Capitalizing expenses that should be expensed
   - Example: Capitalizing internal R&D labor
   - Correct: Expense unless software development post-feasibility

2. Wrong useful life for depreciation
   - Example: 10-year life for computer equipment
   - Correct: 3-5 years more appropriate

3. Not impairing assets when required
   - Example: Continuing to depreciate obsolete equipment at full value
   - Correct: Impair to fair value when indicators present
```

### Classification Errors
```
Common mistakes:
1. Misclassifying current vs. non-current
   - Example: Showing debt due in 6 months as non-current
   - Correct: Classify as current

2. Netting assets and liabilities
   - Example: Showing deferred revenue net of deferred costs
   - Correct: Show gross unless right of offset exists

3. Incorrect cash flow classification
   - Example: Showing debt proceeds as operating cash flow
   - Correct: Financing activity
```

## Tools and Resources

### Accounting Standards Resources
- **FASB Codification**: Official GAAP source (subscription required)
- **IFRS Foundation**: Free IFRS standards
- **SEC Edgar**: Public company filings for reference
- **Big 4 Guides**: Technical guides from accounting firms
- **Industry Groups**: AICPA, state CPA societies

### Technical Tools
- **Accounting software**: NetSuite, SAP, Workday (GAAP compliance features)
- **Revenue recognition**: Zuora RevPro, RevStream (ASC 606 compliance)
- **Lease accounting**: LeaseQuery, Visual Lease (ASC 842 compliance)
- **Excel templates**: Amortization schedules, disclosures

### Getting Help
- **External auditors**: Technical consultations
- **Technical accounting consultants**: Complex transactions
- **CFO networks**: Peer guidance
- **Industry conferences**: Updates and training

## Integration with Other Skills

- **management-reporting**: Apply GAAP in reports
- **financial-modeling**: Ensure models follow GAAP
- **budget-variance-analysis**: Understand accounting impact of variances
- **cash-flow-management**: GAAP cash flow statement
- **financial-forecasting-methods**: Forecast GAAP-compliant financials

## Key Terminology

- **GAAP**: Generally Accepted Accounting Principles (US)
- **IFRS**: International Financial Reporting Standards
- **FASB**: Financial Accounting Standards Board (US standard-setter)
- **IASB**: International Accounting Standards Board
- **ASC**: Accounting Standards Codification (GAAP codification)
- **ASU**: Accounting Standards Update (GAAP amendments)
- **Performance Obligation**: Promise to transfer good/service to customer
- **Right-of-Use Asset**: Lessee's right to use leased asset
- **Deferred Revenue**: Payment received before performance obligation met
- **Accrual**: Recording transactions when incurred, not when cash moves
- **Material**: Significant enough to influence decisions
- **Disclosure**: Footnote information accompanying financial statements

---

**Skill Type**: Technical accounting
**Difficulty**: Intermediate to Advanced
**Prerequisites**: Accounting degree or equivalent, financial statement knowledge
**Related Skills**: management-reporting, financial-modeling, budget-variance-analysis
