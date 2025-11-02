You are tasked with tracking and reporting month-end close progress and outstanding items.

## Objective
Monitor month-end close activities, identify bottlenecks, ensure timely completion, and provide status visibility to stakeholders.

## Process

### 1. Close Checklist Review
Review standard month-end close checklist including:

**Subledger Activities:**
- A/R aging and reconciliation
- A/P aging and reconciliation
- Inventory reconciliation (if applicable)
- Fixed asset additions and depreciation
- Payroll reconciliation

**Balance Sheet Reconciliations:**
- Cash and bank accounts
- Intercompany accounts
- Prepaid expenses and accruals
- Deferred revenue
- Debt and interest

**Journal Entries:**
- Standard recurring entries posted
- Accrual entries (payroll, benefits, bonuses, commissions)
- Depreciation and amortization
- Revenue recognition adjustments
- Reclassifications and adjustments
- Intercompany eliminations

**Review and Analysis:**
- Variance analysis (actual vs. budget)
- Account analysis for unusual balances
- Management review and sign-off
- Supporting documentation filed

### 2. Status Tracking
For each close activity, track:
- Task description
- Owner (person responsible)
- Due date
- Status (Not Started, In Progress, Pending Review, Complete, Blocked)
- % complete
- Outstanding items or issues
- Dependencies

### 3. Progress Reporting
Generate daily close status reports showing:
- Overall close % complete
- Tasks completed vs. total tasks
- On-time vs. late completions
- Open items requiring attention
- Blocked items needing escalation
- Projected close completion date

### 4. Issue Identification
Flag issues requiring attention:
- Late or at-risk tasks
- Reconciliation differences needing investigation
- Missing documentation or approvals
- System or data issues
- Resource constraints or bottlenecks
- Significant variances requiring explanation

### 5. Close Metrics
Track and report close performance metrics:
- Days to close (target vs. actual)
- Number of post-close adjustments
- Reconciliation timeliness
- Variance analysis completion rate
- Journal entry error rate
- Resource hours required

### 6. Recommendations
Provide recommendations for:
- Accelerating completion of late tasks
- Process improvements for future closes
- Automation opportunities
- Resource reallocation
- Escalations needed

## Required Inputs
- **Close Period**: Month and year (e.g., "March 2024", "2024-03")
- **Close Day**: Current business day in close process (e.g., "Day 3", "2024-04-03")
- **Target Close Date**: When close should be completed (e.g., "5 business days")
- **Data Source**: Accounting system (NetSuite, SAP, etc.)
- **Checklist Template**: Standard close checklist or use default

## Output Format

1. **Executive Dashboard** (1 page):
   - Overall close status (% complete, on track / at risk)
   - Days to target close completion
   - Critical items requiring attention
   - Escalations needed

2. **Detailed Status Report**:
   - Task-by-task status table
   - Completed, in progress, not started
   - Owners and due dates
   - Issues and blockers

3. **Reconciliation Status**:
   - All balance sheet accounts
   - Reconciliation complete vs. pending
   - Differences requiring resolution

4. **Outstanding Items List**:
   - Prioritized list of open items
   - Required actions and owners
   - Target completion dates

5. **Metrics and Trends**:
   - Close performance metrics
   - Comparison to prior months
   - Trend analysis

6. **Process Improvement Recommendations**:
   - Bottlenecks identified
   - Automation opportunities
   - Best practices from prior closes

## Usage Examples

### Daily Close Status During Close
```
/month-end-close-status --period "2024-03" --close-day "Day 3" --target "5 business days"
```

### Post-Close Performance Analysis
```
/month-end-close-status --period "2024-03" --view "post-close-analysis" --compare-to "last-3-months"
```

### Automated Daily Email
```
/month-end-close-status --period "2024-03" --format "email" --recipients "finance-team,cfo"
```

## Best Practices
- Establish clear close calendar and communicate to all stakeholders
- Assign clear ownership for each close task
- Use checklist consistently every month
- Track metrics to drive continuous improvement
- Implement daily close processes where possible
- Automate recurring journal entries
- Pre-close activities (accrual estimates, draft variance analysis)
- Post-close debrief to identify improvements

## Close Acceleration Strategies
- **Soft close**: Preliminary close before final
- **Daily close**: Routine activities done daily, not monthly
- **Automation**: Recurring entries, reconciliations, reports
- **Pre-close**: Accruals estimated before month-end
- **Continuous close**: Spread activities throughout month

---

**Skills Utilized:** management-reporting, budget-variance-analysis, gaap-ifrs-compliance
**Agent:** financial-reporter
