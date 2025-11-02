You are tasked with creating detailed cash flow projections and working capital analysis.

## Objective
Develop accurate cash flow forecasts to ensure adequate liquidity, optimize working capital, and support financial planning and decision-making.

## Process

### 1. Historical Cash Flow Analysis
- Analyze 12-24 months of historical cash flows
- Calculate average monthly burn rate (for growth companies)
- Identify seasonality and patterns in collections/disbursements
- Calculate working capital metrics (DSO, DPO, DIO, CCC)
- Review historical forecast accuracy

### 2. Cash Receipt Forecasting
Build detailed collection forecast:

**A/R Collections:**
- Beginning A/R balance by aging bucket
- New billings/revenue (from revenue forecast)
- Collection pattern by aging (current month, 30 days, 60 days, 90+ days)
- Estimated bad debt write-offs
- Customer-specific payment terms and history

**Other Receipts:**
- Debt or equity proceeds
- Asset sales
- Tax refunds
- Other income

### 3. Cash Disbursement Forecasting
Build detailed payment forecast:

**Operating Disbursements:**
- Vendor payments (by payment terms and A/P aging)
- Payroll (bi-weekly or semi-monthly schedule)
- Payroll taxes and benefits
- Rent and facilities
- Software and subscriptions
- Marketing and advertising
- Professional services
- Other operating expenses

**Non-Operating Disbursements:**
- Capital expenditures (by project schedule)
- Debt service (principal and interest)
- Tax payments (quarterly estimated or annual)
- Dividends or distributions

### 4. Working Capital Analysis
Analyze and forecast key metrics:
- Days Sales Outstanding (DSO): Target and actual
- Days Payable Outstanding (DPO): Target and actual
- Days Inventory Outstanding (DIO): If applicable
- Cash Conversion Cycle: DSO + DIO - DPO
- Working capital optimization opportunities

### 5. Scenario Development
Create multiple cash flow scenarios:

**Base Case**: Most likely collections and payments based on historical patterns

**Stressed Case**:
- Slower collections (DSO +15 days)
- Accelerated payments (vendor pressures)
- Lower revenue/delayed deals
- Contingency planning

**Optimistic Case**:
- Faster collections (improved processes)
- Extended payment terms
- Revenue upside

### 6. Liquidity Analysis
Assess liquidity position:
- Ending cash balance by period
- Minimum cash required (covenants, operations)
- Months of runway at current burn rate
- Debt covenant compliance
- Credit availability (revolvers, lines of credit)
- Liquidity ratios (current, quick, cash)

### 7. Action Planning
Based on projections:
- Identify potential cash shortfalls
- Recommend working capital improvements
- Suggest financing needs and timing
- Propose cost reduction if needed
- Accelerate collections strategies
- Optimize payment timing

## Required Inputs
- **Horizon**: "13-weeks" (rolling), "monthly" (12 months), "quarterly"
- **Start Date**: Beginning of forecast period
- **Scenarios**: "base-only" or "base,stressed,optimistic"
- **Current Cash**: Beginning cash balance
- **Revenue Forecast**: Link to revenue projection or provide assumptions
- **Key Assumptions**: DSO, DPO, burn rate, major cash events

## Output Format

1. **Cash Flow Summary**:
   - Weekly (13-week) or monthly cash flow projection
   - Beginning cash, receipts, disbursements, ending cash
   - Minimum required cash and surplus/deficit

2. **Working Capital Analysis**:
   - Current metrics vs. targets
   - Improvement opportunities with $ impact
   - Optimization recommendations

3. **Liquidity Assessment**:
   - Runway calculation (months of cash)
   - Covenant compliance forecast
   - Funding need analysis

4. **Scenario Comparison**:
   - Base vs. stressed vs. optimistic
   - Key assumption differences
   - Risk mitigation strategies

5. **Action Plan**:
   - Specific recommendations to improve cash position
   - Timeline and ownership
   - Expected impact

## Usage Examples

### 13-Week Rolling Cash Forecast
```
/cash-flow-projection --horizon "13-weeks" --start-date "2024-04-01" --scenarios "base,stressed"
```

### Annual Cash Planning
```
/cash-flow-projection --horizon "monthly" --start-date "2024-01-01" --scenarios "base,optimistic"
```

### Fundraising Analysis
```
/cash-flow-projection --horizon "quarterly" --start-date "2024-Q2" --scenarios "base,stressed" --purpose "fundraising"
```

## Best Practices
- Update weekly for 13-week forecast, monthly for annual forecast
- Track actual vs. forecast to refine assumptions
- Include all cash items (not just P&L-related)
- Model working capital changes explicitly
- Flag covenant violations or cash shortfalls early
- Maintain scenario analysis for risk planning

---

**Skills Utilized:** cash-flow-management, financial-forecasting-methods, financial-modeling, scenario-planning
**Agent:** cash-flow-analyst
