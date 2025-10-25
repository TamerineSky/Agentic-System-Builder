You are tasked with generating financial KPI dashboards with key performance metrics.

## Objective
Create comprehensive, visual KPI dashboards that provide at-a-glance visibility into financial and operational performance, enabling data-driven decision-making.

## Process

### 1. KPI Selection
Select appropriate KPIs based on:
- Company stage (startup, growth, mature)
- Business model (SaaS, marketplace, e-commerce, etc.)
- Audience (board, executives, departments)
- Strategic priorities
- Industry standards

### 2. Financial KPIs

**Revenue Metrics:**
- Total Revenue (actual vs. budget vs. prior year)
- Revenue Growth (MoM, QoQ, YoY %)
- Revenue by segment/product/geography
- Annual Recurring Revenue (ARR) for SaaS
- Monthly Recurring Revenue (MRR) for SaaS
- Bookings and billings

**Profitability Metrics:**
- Gross Profit and Gross Margin %
- EBITDA and EBITDA Margin %
- Operating Income and Operating Margin %
- Net Income and Net Margin %
- Contribution Margin by product/segment
- Rule of 40 (Revenue Growth % + EBITDA Margin %) for SaaS

**Efficiency Metrics:**
- Revenue per Employee
- OpEx as % of Revenue
- Sales Efficiency (Magic Number for SaaS)
- R&D Efficiency (revenue per R&D dollar)
- Burn Multiple (Cash burned / Net new ARR)

**Cash and Liquidity:**
- Cash Balance and trend
- Operating Cash Flow
- Free Cash Flow (Operating CF - CapEx)
- Days of Cash Runway
- Working Capital
- Debt levels and covenants

### 3. Customer/Revenue KPIs

**Customer Acquisition:**
- New Customers (vs. target)
- Customer Acquisition Cost (CAC)
- CAC Payback Period (months to recover CAC)
- Sales Cycle Length
- Win Rate %
- Pipeline Coverage (Pipeline / Quota)

**Customer Retention:**
- Customer Count (total active)
- Gross Revenue Retention (GRR)
- Net Revenue Retention (NRR)
- Customer Churn Rate %
- Revenue Churn Rate %
- Average Customer Lifetime (months)

**Customer Value:**
- Average Revenue Per Customer (ARPU/ACV)
- Lifetime Value (LTV)
- LTV/CAC Ratio (target 3:1 or higher)
- Expansion Revenue %
- Upsell/Cross-sell Rate

**Customer Satisfaction:**
- Net Promoter Score (NPS)
- Customer Satisfaction Score (CSAT)
- Customer Effort Score (CES)
- Support Response Time
- Support Resolution Rate

### 4. Operational KPIs

**People Metrics:**
- Total Headcount (actual vs. plan)
- Headcount by Department
- Open Positions
- Time to Fill Positions (days)
- Employee Attrition Rate %
- Employee Engagement Score

**Product/Service Metrics:**
- Product Usage/Adoption Metrics
- Monthly Active Users (MAU)
- Daily Active Users (DAU)
- Feature Adoption Rates
- System Uptime %
- Page Load Time / Performance

**Sales & Marketing:**
- Marketing Qualified Leads (MQL)
- Sales Qualified Leads (SQL)
- Lead-to-Customer Conversion %
- Average Deal Size
- Sales Quota Attainment %
- Marketing ROI

### 5. Dashboard Design

**Layout Principles:**
- Most important metrics prominent (top left)
- Logical grouping (financial, customer, operational)
- Consistent formatting and colors
- Visualizations for trends
- Tables for precise values
- Status indicators (green/yellow/red)

**Standard Dashboard Elements:**
For each KPI include:
- Current actual value
- Target or budget value
- Variance ($ and %)
- Prior period value
- Trend indicator (↑↓→)
- Sparkline (mini trend chart)
- Status (🟢 on track, 🟡 at risk, 🔴 off track)

**Visualization Types:**
- KPI Cards: Single metric with status
- Line Charts: Trends over time
- Bar Charts: Comparisons across categories
- Gauges: Progress to goal
- Tables: Multi-dimensional data
- Waterfall: Variance bridges

### 6. Trend Analysis
Show trends to provide context:
- Last 12 months
- Quarterly rolling trends
- Year-over-year comparison
- Cohort analysis (for retention metrics)

### 7. Drill-Down Capability
Enable exploration:
- Click KPI to see underlying detail
- Filter by segment, product, geography
- Link to supporting schedules
- Export data for analysis

### 8. Automated Refresh
Configure data refresh:
- Real-time for critical metrics
- Daily for operational metrics
- Weekly for financial summary
- Monthly for board-level metrics
- On-demand refresh option

## Required Inputs
- **Dashboard Type**: "executive", "board", "department", "operational"
- **Period**: Current period for dashboard (e.g., "March 2024", "Q1 2024")
- **KPI Set**: "standard", "saas", "ecommerce", "custom"
- **Audience**: Who will use this dashboard?
- **Refresh Frequency**: "real-time", "daily", "weekly", "monthly"
- **Data Sources**: Systems to pull data from
- **Format**: "interactive" (web), "pdf", "powerpoint", "excel"

## Output Format

1. **Executive Dashboard** (1 page):
   - Top 10-12 KPIs
   - Revenue, profitability, cash, customers
   - Traffic light status indicators
   - Trend sparklines

2. **Detailed Dashboard** (2-3 pages):
   - Financial metrics (1 page)
   - Customer metrics (1 page)
   - Operational metrics (1 page)
   - Supporting visualizations

3. **Interactive Dashboard**:
   - Web-based (Tableau, PowerBI, Looker)
   - Filters and drill-down
   - Real-time or scheduled refresh
   - Export and sharing capabilities

4. **Mobile Dashboard**:
   - Mobile-optimized view
   - Key metrics only
   - Simple navigation

## Dashboard Templates

### Executive KPI Dashboard Template
```
[Company Name] - [Period] Executive Dashboard

FINANCIAL PERFORMANCE
                    Actual   Target   Var    Trend   Status
Revenue             $X.XM    $X.XM    +X%    ↑       🟢
EBITDA              $X.XM    $X.XM    -X%    ↓       🟡
EBITDA Margin %     XX%      XX%      -Xpp   →       🟢
Cash                $X.XM    $X.XM    -X%    ↓       🟢
Runway (months)     XX       XX       -X     →       🟢

CUSTOMER METRICS
Customers (total)   X,XXX    X,XXX    +X%    ↑       🟢
New Customers       XXX      XXX      +X%    ↑       🟢
Churn Rate %        X.X%     X.X%     +Xpp   ↑       🔴
NRR %               XXX%     XXX%     +Xpp   ↑       🟢
CAC                 $XX,XXX  $XX,XXX  +X%    ↑       🟡

EFFICIENCY METRICS
LTV/CAC             X.X      X.X      -X%    ↓       🟡
Revenue/Employee    $XXX     $XXX     +X%    ↑       🟢
Rule of 40          XX%      XX%      +Xpp   ↑       🟢

TRENDS (Last 12 Months)
[Revenue trend line chart]
[EBITDA margin % trend line chart]
[Customer count trend line chart]
```

## Usage Examples

### Executive Monthly Dashboard
```
/kpi-dashboard --type "executive" --period "March-2024" --format "pdf" --kpis "standard"
```

### Board Quarterly Dashboard
```
/kpi-dashboard --type "board" --period "Q1-2024" --format "powerpoint" --include-trends "12-months"
```

### Real-Time Operational Dashboard
```
/kpi-dashboard --type "operational" --period "current" --format "interactive" --refresh "real-time" --platform "tableau"
```

### Department Dashboard
```
/kpi-dashboard --type "department" --department "sales" --period "March-2024" --format "interactive"
```

## Best Practices
- Limit to 10-15 KPIs per dashboard (avoid clutter)
- Show trends, not just point-in-time values
- Use consistent colors and formatting
- Include context (target, prior period, variance)
- Make it actionable (link to underlying issues)
- Tailor to audience needs
- Automate data refresh
- Test on mobile devices if applicable
- Regular review and refinement of KPIs
- Add commentary for context

## Tool Selection
- **Excel/Google Sheets**: Simple, flexible, good for small teams
- **Tableau**: Powerful, interactive, enterprise-grade
- **PowerBI**: Microsoft ecosystem, cost-effective
- **Looker**: Modern, cloud-native, good for tech companies
- **Domo**: Business-user friendly, broad connectors
- **Google Data Studio**: Free, good for startups
- **Custom Build**: Full control, engineering required

---

**Skills Utilized:** management-reporting, budget-variance-analysis, financial-forecasting-methods
**Agent:** financial-reporter
