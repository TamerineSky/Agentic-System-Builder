# Monthly Marketing Review Orchestration

## Overview
Comprehensive monthly review of marketing performance across all channels, campaigns, and initiatives.

## Workflow Stages

### Stage 1: Campaign Performance Review
**Agent**: campaign-roi-analyzer  
**Tasks**:
- Analyze all campaign performance for the month
- Calculate ROI, ROAS, CAC by campaign and channel
- Identify top and bottom performers
- Compare actual vs. target performance
- Trend analysis vs. prior months

**Inputs**: Month-end data from all campaigns  
**Outputs**: Campaign performance report, top/bottom performers

---

### Stage 2: Funnel Health Analysis
**Agent**: marketing-funnel-optimizer  
**Tasks**:
- Full funnel analysis (visitor → customer)
- Identify bottlenecks and drop-off points
- Calculate stage conversion rates and velocity
- Compare to prior month and targets
- Segment analysis by channel/source

**Inputs**: Funnel data from analytics and CRM  
**Outputs**: Funnel health report, bottleneck identification

---

### Stage 3: Attribution & Channel Contribution
**Agent**: attribution-analyst  
**Tasks**:
- Multi-touch attribution analysis
- Channel contribution assessment (direct + assisted)
- Customer journey analysis
- Path length and time-to-conversion trends
- Channel interaction insights

**Inputs**: Customer journey data, conversion data  
**Outputs**: Attribution report, channel contribution analysis

---

### Stage 4: Content Performance Review
**Agent**: content-performance-analyst  
**Tasks**:
- Analyze content published/promoted in month
- Top performing content identification
- SEO performance (rankings, traffic)
- Engagement metrics and conversion impact
- Content gap identification

**Inputs**: Content analytics data  
**Outputs**: Content performance report, optimization recommendations

---

### Stage 5: Lead Quality & MQL Analysis
**Agent**: lead-scoring-engine  
**Tasks**:
- MQL volume and quality assessment
- Lead scoring model performance
- MQL to SQL conversion analysis
- Sales feedback review
- Scoring calibration recommendations

**Inputs**: Lead and MQL data, sales feedback  
**Outputs**: MQL quality report, scoring adjustments

---

### Stage 6: Budget Performance & Reallocation
**Agent**: marketing-budget-optimizer  
**Tasks**:
- Budget utilization review
- Spend pacing analysis
- Channel ROI comparison
- Identify budget waste and reallocation opportunities
- Forecast impact of budget changes

**Inputs**: Spend data, performance data  
**Outputs**: Budget performance report, reallocation recommendations

---

### Stage 7: Executive Summary & Recommendations
**Agent**: campaign-roi-analyzer (synthesis)  
**Tasks**:
- Synthesize insights from all analyses
- Create executive dashboard
- Prioritize top 5 action items
- Quantify expected impact of recommendations
- Create next month's focus areas

**Inputs**: All prior stage outputs  
**Outputs**: Executive summary, prioritized action plan

## Orchestration Flow

```
Month-End Trigger
    ↓
[campaign-roi-analyzer] → Campaign performance analysis
    ↓
[marketing-funnel-optimizer] → Funnel health check
    ↓
[attribution-analyst] → Attribution & channel contribution
    ↓
[content-performance-analyst] → Content performance review
    ↓
[lead-scoring-engine] → MQL quality assessment
    ↓
[marketing-budget-optimizer] → Budget optimization
    ↓
[campaign-roi-analyzer] → Executive synthesis
    ↓
Monthly Review Report + Action Plan
```

## Deliverables

### Executive Dashboard
- Overall marketing metrics (spend, revenue, ROI, CAC)
- Performance vs. targets
- Month-over-month trends
- Key insights (3-5 bullets)

### Detailed Analysis
- Campaign performance breakdown
- Funnel analysis with bottlenecks
- Attribution insights
- Content performance
- MQL quality assessment
- Budget optimization recommendations

### Action Plan
- Top 5 priorities for next month
- Expected impact of each action
- Owner and timeline for each
- Resources required

## Meeting Preparation

Share report 24 hours before monthly review meeting with:
- Marketing leadership
- Demand generation team
- Content team
- Marketing ops

## Success Metrics

- Report completed within 3 business days of month-end
- All key stakeholders reviewed report before meeting
- At least 3 actionable recommendations implemented
- Performance trending positively quarter-over-quarter
