You are tasked with generating comprehensive board reporting packages with executive summaries.

## Objective
Create professional, strategic board reporting packages that provide directors with financial performance visibility, key metrics, strategic updates, and decision support materials.

## Process

### 1. Content Planning
Determine board package scope based on:
- Meeting type (monthly, quarterly, annual)
- Company stage (startup, growth, mature)
- Board composition and preferences
- Key topics or decisions this meeting
- Regulatory requirements (if public)

### 2. Financial Results Compilation

**Financial Statements:**
- Income Statement (actual, budget, variance, prior year)
- Balance Sheet (current period, prior period, prior year)
- Cash Flow Statement (current period, YTD)
- Key financial metrics dashboard

**Variance Analysis:**
- Revenue variance breakdown and explanation
- Expense variance analysis by department
- EBITDA variance and margin analysis
- Cash and working capital changes

**Financial Metrics:**
- Revenue growth (MoM, QoQ, YoY)
- Gross margin and trends
- EBITDA and EBITDA margin
- Operating cash flow and burn rate
- Days of cash runway
- Rule of 40 (for SaaS): Growth% + EBITDA margin%

### 3. Operational Metrics

**Customer Metrics:**
- Customer count (total, new, churned)
- Customer Acquisition Cost (CAC)
- CAC payback period
- Lifetime Value (LTV)
- LTV/CAC ratio
- Net Revenue Retention (NRR)
- Gross Revenue Retention (GRR)
- Net Promoter Score (NPS)

**Product & Performance:**
- Key product metrics (usage, adoption, engagement)
- Product development milestones
- Service levels and uptime
- Quality metrics

**People Metrics:**
- Total headcount (actual vs. plan)
- Headcount by department
- Open positions and hiring pipeline
- Attrition rate
- Employee engagement scores

### 4. Strategic Update

**Business Highlights:**
- Major customer wins or expansions
- New product launches or features
- Strategic partnerships or alliances
- Market expansion activities
- Awards or recognition

**Challenges and Issues:**
- Significant customer losses or risks
- Competitive threats
- Operational challenges
- Regulatory or legal issues
- Resource constraints

**Strategic Initiatives Progress:**
- Status of major initiatives and projects
- Milestones achieved or missed
- Budget and timeline status
- Dependencies and risks

### 5. Forward-Looking Section

**Forecast Update:**
- Updated financial forecast (if material changes)
- Revised guidance (revenue, EBITDA, cash)
- Key assumption changes
- Scenario analysis (base, upside, downside)

**Strategic Priorities:**
- Next quarter priorities
- Investment areas and rationale
- Strategic decisions needed
- Resource allocation

**Risks and Mitigation:**
- Top 5 risks to achieving plan
- Mitigation strategies
- Contingency plans
- Early warning indicators

### 6. Executive Summary
Create compelling 1-2 page executive summary:
- Overall assessment (on track / ahead / behind plan)
- Key financial and operational highlights
- Major accomplishments this period
- Critical challenges and mitigation plans
- Strategic decisions requiring board input
- Recommended actions

### 7. Board Materials Assembly
Organize complete package:
1. Executive Summary (2-3 pages)
2. Financial Dashboard (1 page)
3. Financial Statements (3-4 pages)
4. Variance Analysis (2 pages)
5. Operational Metrics (2-3 pages)
6. Business Highlights (2-3 pages)
7. Strategic Initiatives Update (2-3 pages)
8. Forward Look and Forecast (2-3 pages)
9. Appendix: Supporting schedules and detail

## Required Inputs
- **Period**: Month, quarter, or annual (e.g., "Q1 2024", "March 2024")
- **Meeting Date**: When board meeting occurs
- **Meeting Type**: "monthly", "quarterly", "annual", "special"
- **Focus Topics**: Specific topics requiring emphasis (optional)
- **Prior Package**: Previous board package for comparison
- **Distribution**: Board members and recipients

## Output Format

1. **PDF Board Package**: Complete formatted package (15-25 pages typical)
2. **PowerPoint Deck**: Presentation version with same content
3. **Executive Summary**: Standalone 2-page summary
4. **Supporting Materials**: Detailed appendices and schedules
5. **Board Portal Upload**: Formatted for board portal if applicable

## Package Components

### Executive Summary Template
```
[Company Name] Board of Directors Meeting
[Date]

EXECUTIVE SUMMARY

FINANCIAL PERFORMANCE
We [beat/met/missed] Q[X] targets with revenue of $X.XM ([Y]% growth)
and EBITDA of $X.XM ([Y]% margin). [Key drivers explanation].

KEY METRICS
Revenue:        $X.XM ([Y]% vs. plan, [Z]% YoY)
EBITDA:         $X.XM ([Y]% margin)
Customers:      X,XXX (net adds: +XXX, NRR: XXX%)
Cash:           $X.XM ([Y] months runway)
Headcount:      XXX FTE

HIGHLIGHTS
• [Major achievement 1 with business impact]
• [Major achievement 2 with business impact]
• [Major achievement 3 with business impact]

CHALLENGES
• [Challenge 1 with mitigation plan]
• [Challenge 2 with mitigation plan]

STRATEGIC UPDATE
[Summary of strategic initiative progress, market position, competitive
landscape updates]

FORWARD LOOK
We are [maintaining/raising/lowering] full-year guidance to $XXM revenue
([Y]% growth) and $XM EBITDA ([Z]% margin) based on [rationale]. Key
assumptions include [assumption 1] and [assumption 2].

DECISIONS REQUIRED
1. [Decision 1]: [Recommendation and rationale]
2. [Decision 2]: [Recommendation and rationale]
```

## Usage Examples

### Quarterly Board Package
```
/board-package-generate --period "Q1-2024" --meeting-date "2024-04-15" --type "quarterly"
```

### Monthly Board Package with Focus
```
/board-package-generate --period "March-2024" --meeting-date "2024-04-10" --type "monthly" --focus "fundraising,M&A-opportunity"
```

### Annual Board Package
```
/board-package-generate --period "FY2024" --meeting-date "2025-02-20" --type "annual" --include "audited-financials"
```

## Best Practices
- Distribute 3-5 days before meeting (allow review time)
- Lead with insights, not just data
- Use consistent format month-to-month
- Tailor depth to board's sophistication
- Focus on strategic vs. operational detail
- Include forward-looking content
- Highlight decisions clearly
- Use visualizations for complex data
- Keep main deck to 15-20 pages, detail in appendix
- Proofread carefully (board scrutiny high)

## Board Communication Tips
- Be transparent about challenges
- Provide context for variances
- Show trends over time
- Benchmark against plan and industry
- Anticipate board questions
- Prepare backup materials
- Include action items from prior meeting
- Document decisions and approvals

---

**Skills Utilized:** management-reporting, budget-variance-analysis, financial-forecasting-methods, gaap-ifrs-compliance
**Agent:** financial-reporter
