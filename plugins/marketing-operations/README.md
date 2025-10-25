# Marketing Operations Plugin

Comprehensive marketing operations plugin providing specialized agents, skills, commands, and orchestrations for campaign analysis, content performance, lead scoring, funnel optimization, attribution modeling, and budget allocation.

## Overview

The Marketing Operations Plugin enables data-driven marketing decision-making through AI-powered analysis of campaigns, content, leads, funnels, attribution, and budgets. It integrates with major marketing platforms (Google Ads, Meta, LinkedIn, HubSpot, Marketo, Salesforce) to provide actionable insights and optimization recommendations.

## Components

### Agents (6)

1. **campaign-roi-analyzer** (Sonnet)
   - Campaign ROI analysis and performance tracking
   - Multi-channel campaign attribution
   - Budget pacing and utilization monitoring
   - Optimization opportunity identification

2. **content-performance-analyst** (Sonnet)
   - Content analytics and engagement measurement
   - SEO performance tracking (rankings, traffic, backlinks)
   - Content audit and gap analysis
   - Content optimization recommendations

3. **lead-scoring-engine** (Sonnet)
   - Lead scoring model development and calibration
   - MQL/SQL threshold optimization
   - Predictive lead scoring using ML
   - Sales feedback integration

4. **marketing-funnel-optimizer** (Sonnet)
   - Full-funnel performance analysis
   - Drop-off point identification
   - Conversion rate optimization (CRO)
   - Funnel velocity improvement

5. **attribution-analyst** (Sonnet)
   - Multi-touch attribution modeling
   - Channel contribution analysis
   - Customer journey mapping
   - Attribution model comparison

6. **marketing-budget-optimizer** (Sonnet)
   - Budget allocation optimization
   - Channel ROI and marginal ROI analysis
   - Spend efficiency identification
   - Budget scenario planning

### Skills (8)

1. **attribution-modeling** - Multi-touch, first/last, custom attribution models
2. **campaign-performance-analysis** - Campaign metrics, A/B testing, optimization
3. **content-analytics** - Content performance, engagement, SEO metrics
4. **lead-scoring-models** - Scoring frameworks, predictive models, calibration
5. **funnel-optimization** - Funnel analysis, CRO, drop-off mitigation
6. **budget-allocation** - Budget optimization, channel mix, ROI maximization
7. **ab-testing-methodology** - Test design, statistical significance, analysis
8. **marketing-mix-modeling** - MMM techniques, media impact, optimization

### Commands (10)

- `/campaign-performance` - Campaign performance analysis
- `/content-analysis` - Content performance and engagement analysis
- `/lead-scoring-update` - Update lead scoring criteria/models
- `/funnel-analysis` - Marketing funnel performance analysis
- `/attribution-report` - Attribution analysis report
- `/budget-optimization` - Budget allocation optimization
- `/channel-performance` - Channel performance analysis
- `/cac-analysis` - Customer acquisition cost analysis
- `/marketing-roi` - Marketing ROI by campaign/channel
- `/mql-analysis` - MQL generation and conversion analysis

### Orchestrations (4)

1. **campaign-launch.md** - Campaign planning to execution workflow
2. **monthly-marketing-review.md** - Monthly performance review process
3. **lead-handoff-process.md** - Lead scoring to sales handoff workflow
4. **quarterly-planning.md** - Quarterly marketing planning process

## Key Features

### Campaign Analysis
- Multi-channel performance tracking (paid search, social, display, email)
- ROI, ROAS, CPA, and efficiency metrics
- A/B test analysis and optimization recommendations
- Budget pacing and utilization monitoring

### Content Performance
- Content engagement and conversion metrics
- SEO performance (organic traffic, rankings, backlinks)
- Content audit with top/bottom performers
- Content gap identification and recommendations

### Lead Management
- Rule-based and predictive lead scoring
- MQL/SQL conversion tracking
- Lead quality assessment
- Scoring model calibration

### Funnel Optimization
- Stage-by-stage conversion analysis
- Drop-off point identification
- CRO recommendations
- Funnel velocity tracking

### Attribution Analysis
- Multiple attribution models (first-touch, last-touch, linear, time-decay, position-based, data-driven)
- Channel contribution analysis
- Customer journey mapping
- Budget reallocation recommendations

### Budget Optimization
- ROI-based budget allocation
- Marginal ROI analysis
- Spend efficiency identification
- Scenario planning and forecasting

## Integration Points

### Marketing Platforms
- **Google Ads** - Campaign performance, spend data
- **Meta Ads Manager** - Facebook/Instagram advertising data
- **LinkedIn Campaign Manager** - B2B advertising data
- **Twitter/X Ads** - Social advertising data
- **Microsoft Advertising** - Bing ads data

### Analytics Platforms
- **Google Analytics 4** - Web analytics, conversion tracking
- **Adobe Analytics** - Enterprise analytics, attribution
- **Mixpanel** - Product analytics, funnel analysis
- **Amplitude** - User journey analysis

### Marketing Automation & CRM
- **HubSpot** - Marketing automation, lead tracking, attribution
- **Marketo** - Enterprise marketing automation, ROI reporting
- **Pardot (Salesforce)** - B2B marketing automation
- **Salesforce** - CRM, opportunity tracking, revenue data

### SEO & Content Tools
- **Google Search Console** - Search performance data
- **SEMrush** - Keyword research, rankings, SEO audits
- **Ahrefs** - Backlink analysis, content performance
- **Moz** - Domain authority, keyword tracking

### Attribution Platforms
- **Bizible (Marketo Measure)** - B2B attribution
- **Rockerbox** - Multi-touch attribution
- **Google Attribution** - Cross-channel attribution

## Usage Examples

### Analyze Campaign Performance
```
User: "Analyze Q4 paid social campaign performance"

Response: campaign-roi-analyzer provides:
- Overall performance metrics (spend, conversions, ROI, ROAS)
- Platform breakdown (Meta vs. LinkedIn)
- Audience segment performance
- Creative variation analysis
- Optimization recommendations with expected impact
```

### Optimize Marketing Funnel
```
User: "Identify why we're losing leads between MQL and SQL stages"

Response: marketing-funnel-optimizer delivers:
- Full funnel analysis with volumes and conversion rates
- Identification of MQL→SQL as primary bottleneck (45% drop-off)
- Segmentation by lead source showing quality gaps
- Root cause diagnosis (scoring criteria, sales capacity, lead quality)
- Specific optimization recommendations
```

### Update Lead Scoring Model
```
User: "Our MQL to SQL conversion is only 30%, expected 45%. Update scoring model."

Response: lead-scoring-engine provides:
- Historical conversion analysis by score tier
- Identification of over-weighted and under-weighted criteria
- Recommended scoring adjustments
- New MQL threshold recommendation
- Expected impact on MQL volume and quality
```

### Optimize Budget Allocation
```
User: "Optimize our $200K/month marketing budget allocation"

Response: marketing-budget-optimizer delivers:
- Current allocation and ROI by channel
- Marginal ROI analysis
- Reallocation recommendations (e.g., shift $30K from display to paid search)
- Expected revenue impact (+$120K)
- Scenario analysis for different budget levels
```

## Metrics & KPIs

### Campaign Metrics
- ROI (Return on Investment)
- ROAS (Return on Ad Spend)
- CPA (Cost Per Acquisition)
- CPL (Cost Per Lead)
- CAC (Customer Acquisition Cost)
- LTV:CAC Ratio
- Conversion Rate
- CTR (Click-Through Rate)

### Content Metrics
- Page Views, Unique Visitors
- Time on Page, Scroll Depth
- Organic Traffic, Keyword Rankings
- Backlinks, Domain Authority
- Social Shares, Engagement Rate
- Content Conversion Rate
- Leads per Content Piece

### Lead Metrics
- MQL Volume and Rate
- MQL to SQL Conversion Rate
- SQL Acceptance Rate
- Lead Score Distribution
- Cost per MQL
- Lead Quality (score correlation with conversion)

### Funnel Metrics
- Stage Conversion Rates
- Drop-off Rates
- Funnel Velocity
- Overall Funnel CVR
- Leakage by Stage

### Attribution Metrics
- Assisted Conversions
- Attribution Credit by Channel
- Path Length
- Time to Conversion
- Channel Overlap

### Budget Metrics
- Budget Utilization
- ROI by Channel
- Marginal ROI
- Spend Efficiency
- Budget Pacing

## Best Practices

### Data Quality
- Ensure UTM parameters are consistently applied
- Verify conversion tracking is working correctly
- Validate data connections to all platforms
- Clean and deduplicate lead data regularly

### Analysis Frequency
- **Daily**: Campaign performance monitoring, budget pacing
- **Weekly**: Funnel analysis, content performance
- **Monthly**: Comprehensive review, budget optimization
- **Quarterly**: Strategic planning, model calibration

### Collaboration
- Share insights with sales team (lead quality feedback)
- Align with finance on budget and ROI expectations
- Coordinate with content team on performance data
- Present executive summaries to leadership

### Continuous Improvement
- A/B test optimization hypotheses
- Calibrate lead scoring models quarterly
- Update attribution models semi-annually
- Iterate on funnel optimization continuously

## Success Criteria

- **Campaign Performance**: ROI improving quarter-over-quarter
- **Content Performance**: Organic traffic growing month-over-month
- **Lead Quality**: MQL to SQL conversion rate >40%
- **Funnel Efficiency**: Stage conversion rates improving
- **Attribution Accuracy**: Multi-touch insights driving better decisions
- **Budget Optimization**: Spend efficiency improving with maintained or increased volume

## Support & Resources

- **Plugin Documentation**: This README
- **Agent Documentation**: See individual agent files
- **Skill Documentation**: See individual SKILL.md files
- **Command Documentation**: See individual command files
- **Orchestration Documentation**: See orchestration workflow files

## Version

**Version**: 1.0.0  
**Last Updated**: 2025-10-24  
**Maintained By**: Agentic System Builder Project

---

## Quick Start

1. **Install Plugin**: Add marketing-operations plugin to your .claude-plugin/marketplace.json
2. **Configure Integrations**: Connect to your marketing platforms (Google Ads, HubSpot, etc.)
3. **Run Analysis**: Use commands like `/campaign-performance` or `/funnel-analysis`
4. **Review Insights**: Act on optimization recommendations
5. **Monitor Results**: Track performance improvements

For detailed guidance, see orchestration workflows for end-to-end processes.
