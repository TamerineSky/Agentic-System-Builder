You are tasked with reviewing and validating accruals for accuracy and completeness.

## Objective
Ensure all accruals are properly recorded, accurately calculated, complete, and compliant with GAAP/IFRS standards to support clean month-end/quarter-end close and audit readiness.

## Process

### 1. Accrual Identification
Review all categories of accruals:

**Operating Expense Accruals:**
- Payroll and wages (earned but not yet paid)
- Payroll taxes and benefits
- Bonuses and commissions
- Professional fees (legal, accounting, consulting)
- Marketing and advertising
- Utilities
- Rent and facilities
- Insurance
- Software and subscriptions
- Travel and entertainment (incurred but not yet invoiced)

**Revenue-Related Accruals:**
- Accrued revenue (services delivered, not yet invoiced)
- Deferred revenue (cash received, services not yet delivered)
- Customer credits and refunds
- Sales returns and allowances
- Warranty reserves

**COGS/Inventory Accruals:**
- Inventory received but not invoiced
- Freight and shipping costs
- Manufacturing overhead
- Inventory reserves (obsolescence, shrinkage)

**Other Accruals:**
- Interest expense/income
- Tax accruals (income tax, sales tax, property tax)
- Contingent liabilities
- Restructuring charges
- Legal settlements

### 2. Accrual Calculation Review
For each accrual, validate:

**Payroll Accrual:**
```
Calculation:
- Days in pay period after month-end: X days
- Total monthly payroll: $Y
- Daily rate: $Y / days in month
- Accrual: Daily rate × X days in following month

Example:
Pay period: 16th to 15th
Month-end: March 31 (Friday)
Payroll for March 16-31: 16 days
Monthly payroll: $1,000,000
Daily rate: $1M / 31 days = $32,258
Accrual: $32,258 × 16 days = $516,129

Validation:
- Matches payroll schedule
- Includes all employees
- Includes salary + hourly
- Excludes benefits (separate accrual)
```

**Bonus Accrual:**
```
Calculation:
- Annual bonus target: % of salary
- YTD accrual: (Annual target / 12) × Months elapsed
- Expected payout %: Based on performance to date
- Adjusted accrual: YTD accrual × Expected payout %

Example:
Employee annual salary: $120,000
Target bonus: 20% = $24,000
Q1 accrual (3 months): ($24,000 / 12) × 3 = $6,000
Performance tracking: 110% of target
Adjusted accrual: $6,000 × 110% = $6,600

Validation:
- All bonus-eligible employees included
- Performance adjustment reasonable
- Prior period accruals reviewed for accuracy
- Matches bonus plan terms
```

**Professional Fees Accrual:**
```
Calculation:
- Identify services received but not invoiced
- Estimate based on:
  * Statements of Work (SOWs) and milestones
  * Hourly rates × estimated hours
  * Prior month actuals
  * Vendor communication

Example:
Legal services received in March:
- M&A transaction support: Estimate $150K based on SOW
- General corporate: $25K based on typical monthly
- Total accrual: $175K

Validation:
- All active projects included
- Reasonable estimates (not understated)
- Communication with vendors for large items
- Supporting documentation on file
```

### 3. Completeness Check
Ensure no accruals are missing:

**Review Checklist:**
- [ ] Compare to prior period accrual listing
- [ ] Review all purchase orders and contracts for deliveries/services in period
- [ ] Scan AP aging for invoices dated prior period, received after close
- [ ] Review employee expense reports for prior period expenses
- [ ] Confirm with department heads on outstanding items
- [ ] Review project status reports for milestone completion
- [ ] Check for known liabilities (legal matters, settlements)
- [ ] Validate tax accruals (income, sales, payroll, property)

### 4. Accuracy Validation
For each accrual:

**Documentation Review:**
- Supporting calculations clearly documented
- Assumptions and estimates reasonable
- Source data validated
- Preparer and reviewer sign-off

**Rollforward Analysis:**
```
Beginning accrual balance
+ New accruals this period
- Reversals of prior period accruals
- Payments against accruals
= Ending accrual balance

Check:
- Prior period accruals reversed or paid
- No stale accruals (>90 days without activity)
- Ending balance reasonable
```

**Comparison to Actual:**
```
When invoice arrives, compare to accrual:
- Accrual: $10,000
- Actual invoice: $11,500
- Variance: $1,500 (13% under-accrued)

If material variance:
- Investigate cause
- Adjust estimate methodology
- Consider prior period adjustment if material
```

### 5. GAAP/IFRS Compliance
Ensure accruals meet accounting standards:

**Accrual Requirements:**
- Matching principle: Expense matched to period when incurred
- Probable: More likely than not the liability exists
- Estimable: Can reasonably estimate the amount
- Documentation: Sufficient support for accrual

**Revenue Accrual (ASC 606):**
- Performance obligation substantially complete
- Collection is probable
- Price is determinable
- Supporting documentation (delivery confirmation, milestone acceptance)

### 6. Reversal Planning
Document accrual reversal approach:
- **Auto-Reverse**: Accrual reverses first day of new period (most accruals)
- **Manual Reverse**: Reverse when paid or adjust (specific accruals)
- **Cumulative**: Adjust to correct balance each period (bonus, tax accruals)

### 7. Reporting
Generate accrual review summary:

**Accrual Summary Report:**
| Category | Current Period | Prior Period | Change | % Change | Notes |
|----------|---------------|--------------|--------|----------|-------|
| Payroll | $500K | $480K | $20K | 4% | Extra payroll days |
| Bonus | $150K | $100K | $50K | 50% | Q1 performance strong |
| Professional Fees | $175K | $200K | ($25K) | -13% | Lower legal this month |

**Key Items Requiring Attention:**
- Material new accruals (>$X)
- Significant variances vs. prior period
- Stale accruals requiring review
- Estimates with high uncertainty

**Recommendations:**
- Adjustments needed
- Documentation to improve
- Process improvements
- Follow-up required

## Required Inputs
- **Period**: Month-end or quarter-end (e.g., "March 2024", "Q1 2024")
- **Materiality Threshold**: Accruals above threshold require extra scrutiny (e.g., "$50K")
- **Focus Areas**: Specific accrual categories to emphasize (optional)
- **Prior Period Accruals**: List for rollforward analysis
- **Data Source**: Accounting system (NetSuite, SAP, etc.)

## Output Format

1. **Accrual Summary**:
   - Total accruals by category
   - Period-over-period comparison
   - Significant changes explained

2. **Detailed Accrual Listing**:
   - Line-by-line accrual detail
   - Calculation methodology
   - Supporting documentation reference
   - Preparer and reviewer

3. **Rollforward Analysis**:
   - Beginning balance
   - Additions, reversals, payments
   - Ending balance
   - Stale accrual identification

4. **Variance Analysis**:
   - Accrual vs. actual when invoiced
   - Accuracy tracking
   - Methodology refinement recommendations

5. **Compliance Checklist**:
   - GAAP/IFRS requirements met
   - Documentation adequate
   - Approval obtained

6. **Action Items**:
   - Adjustments needed
   - Missing accruals to record
   - Documentation to collect
   - Process improvements

## Usage Examples

### Month-End Accrual Review
```
/accrual-review --period "March-2024" --threshold "50000" --focus "payroll,bonuses,professional-fees"
```

### Quarter-End Comprehensive Review
```
/accrual-review --period "Q1-2024" --threshold "25000" --focus "all" --include-variance-analysis
```

### Audit Preparation
```
/accrual-review --period "December-2024" --threshold "10000" --purpose "audit-prep" --include-documentation-checklist
```

## Best Practices
- Maintain standardized accrual templates and calculations
- Document methodology and assumptions clearly
- Review prior period accrual accuracy (actual vs. estimate)
- Involve department heads for large estimates
- Track accrual accuracy metrics over time
- Reverse accruals promptly in new period
- Flag and research stale accruals (>90 days)
- Maintain audit trail of calculations and approvals
- Automate recurring accrual calculations where possible
- Quarterly review of accrual methodologies for refinement

## Common Accrual Errors to Avoid
- Under-accruing expenses (conservative bias)
- Forgetting to accrue known liabilities
- Not reversing prior period accruals
- Using incorrect calculation methodology
- Missing approval or documentation
- Accruing items that should be prepaid expenses
- Not adjusting cumulative accruals (bonus, taxes)

---

**Skills Utilized:** gaap-ifrs-compliance, management-reporting, budget-variance-analysis
**Agent:** financial-reporter
