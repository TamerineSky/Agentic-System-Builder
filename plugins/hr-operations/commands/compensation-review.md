---
description: Compensation benchmarking analysis with market comparisons and recommendations
argument-hint: [org] [roles]
version: "1.0.0"
tags: [compensation, benchmarking, market-data, compa-ratio]
tool_access: [Read, Write, Bash]
model: sonnet
---

# Compensation Benchmarking & Review

Analyze compensation competitiveness, benchmark against market data, identify pay equity issues, and recommend adjustments.

## Context
Market-competitive compensation is critical for attraction and retention. Regular benchmarking ensures pay equity and reduces attrition risk.

## Requirements
- **Organization**: Department or "all" for company-wide analysis
- **Roles**: Specific roles or "all" for comprehensive review
- **Market Data**: Access to salary surveys (Radford, Mercer, Payscale, Levels.fyi)
- **Current Compensation**: Base salary, bonus, equity for all employees

## Instructions

### 1. Data Collection & Role Matching
- Extract current compensation data by employee
- Match internal roles to market survey job codes
- Adjust for location (geographic pay differentials)
- Gather performance ratings and compa-ratios

### 2. Market Benchmarking
For each role/level combination:
- Market P25, P50, P75, P90 (base and total cash)
- Current employee positioning vs. market
- Compa-ratio calculation (salary/midpoint)
- Competitive assessment (below/at/above market)

### 3. Competitiveness Analysis
Identify risks:
- Employees below P25 (critical flight risk)
- Roles consistently below market (systemic issue)
- Compression cases (new hires > tenured employees)
- Inversion cases (IC > manager, junior > senior)

### 4. Pay Equity Analysis
Statistical regression controlling for:
- Job level and function
- Tenure and experience
- Performance rating
- Location
Flag significant pay gaps by gender, race, age

### 5. Recommendations
- Priority adjustments (high flight risk, critical roles)
- Market adjustment budget estimate
- Phasing strategy (immediate vs. next cycle)
- Salary band refinement if needed

## Output Format
- Executive summary with overall competitiveness assessment
- Role-by-role benchmarking table (internal vs. market)
- Compa-ratio distribution analysis
- At-risk employee list (below market, high performers)
- Pay equity findings and remediation plan
- Budget impact by scenario (bring to P50, P60, P75)
- Implementation recommendations

## Success Criteria
- All roles matched to market data accurately
- Competitive gaps quantified by role and individual
- Pay equity assessed statistically
- Prioritized adjustment recommendations with budget
- Clear action plan for implementation

## Related Plugins
**Skills**: compensation-benchmarking, attrition-analysis
**Agents**: compensation-analyst, attrition-predictor
**Commands**: /retention-analysis, /performance-distribution
