You are tasked with analyzing cost structures and identifying optimization opportunities.

## Objective
Perform comprehensive cost analysis to identify spending patterns, inefficiencies, and actionable cost reduction opportunities while maintaining business effectiveness.

## Process

### 1. Cost Data Collection
- Extract 12-24 months of expense data by account, department, vendor
- Gather headcount and compensation data
- Collect contract terms and renewal dates
- Obtain volume/activity metrics for cost allocation
- Benchmark data against industry standards

### 2. Cost Categorization
Classify all costs by:
- **Type**: Personnel, software, facilities, marketing, professional services, etc.
- **Behavior**: Fixed, variable, semi-variable
- **Controllability**: Controllable, semi-controllable, non-controllable
- **Strategic Importance**: Critical, important, nice-to-have
- **Department**: Sales, Marketing, R&D, G&A, COGS

### 3. Cost Analysis
Perform multi-dimensional analysis:

**Trend Analysis:**
- Cost growth rates vs. revenue growth
- YoY and MoM comparisons
- Identify accelerating cost areas

**Benchmark Analysis:**
- Costs as % of revenue vs. industry standards
- Cost per employee by department
- Efficiency ratios (revenue per employee, CAC, etc.)

**Vendor Analysis:**
- Top vendors by spend
- Vendor concentration risk
- Contract renewal schedule
- Rate comparison vs. market

**Unit Cost Analysis:**
- Cost per customer
- Cost per transaction
- Cost per employee supported
- Cost per unit produced

### 4. Opportunity Identification
Identify cost reduction opportunities:

**Quick Wins** (low effort, high impact):
- Unused software licenses
- Redundant subscriptions
- Vendor consolidation
- Process automation

**Strategic Initiatives** (higher effort, high impact):
- Headcount optimization
- Real estate rightsizing
- Offshore/nearshore opportunities
- Vendor renegotiation
- Technology modernization

### 5. Impact Assessment
For each opportunity:
- Annual savings potential ($ amount)
- Implementation difficulty (low/medium/high)
- Business impact/risk (low/medium/high)
- Timeline to realize savings
- One-time implementation costs
- ROI and payback period

### 6. Prioritization and Roadmap
- Prioritize by impact, effort, risk
- Develop implementation roadmap (quarters)
- Assign ownership
- Set targets and milestones

## Required Inputs
- **Period**: Time range to analyze (e.g., "last 12 months", "YTD 2024")
- **Focus Areas**: Specific categories or "all" (e.g., "OpEx", "personnel", "software")
- **Target**: Savings target if applicable (e.g., "reduce OpEx by 10%")
- **Constraints**: Areas off-limits (e.g., "protect R&D headcount")
- **Data Source**: Financial system (NetSuite, SAP, Workday, etc.)

## Output Format

1. **Executive Summary**: Total opportunity, top recommendations, implementation roadmap
2. **Cost Structure Analysis**: Current spending breakdown with trends and benchmarks
3. **Opportunity Detail**: Prioritized list with savings, effort, risk, timeline
4. **Implementation Plan**: Phased approach with quick wins and strategic initiatives
5. **Financial Impact Model**: P&L impact by quarter and annually

## Usage Examples

```
/cost-analysis --period "last-12-months" --focus "all" --target "reduce OpEx by 15%"
```

```
/cost-analysis --period "YTD-2024" --focus "software,professional-services" --constraints "protect customer-facing teams"
```

---

**Skills Utilized:** cost-allocation, budget-variance-analysis, financial-modeling, scenario-planning
**Agent:** cost-optimizer
