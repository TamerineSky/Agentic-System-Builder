# Customer Success Operations Plugin

Comprehensive customer success operations plugin providing AI-powered customer health scoring, churn prediction, expansion opportunity identification, customer segmentation, NPS analysis, engagement tracking, and CSM performance optimization.

## Overview

The Customer Success Operations plugin enables CS leaders, CSMs, and executives to make data-driven decisions about customer health, churn risk, expansion opportunities, segmentation strategies, and team performance. It combines five specialized agents, seven skill modules, and ten command workflows to cover the complete customer success lifecycle.

### Key Capabilities

- **Customer Health Scoring**: Multi-dimensional health assessment, risk identification, trend analysis
- **Churn Prediction**: Predictive models, early warning systems, intervention strategies
- **Expansion Analysis**: Upsell/cross-sell identification, whitespace analysis, growth opportunities
- **Customer Segmentation**: Data-driven segmentation, cohort analysis, persona development
- **NPS Analysis**: Survey analysis, driver identification, action planning
- **Engagement Tracking**: Activity monitoring, engagement scoring, behavioral patterns
- **CSM Performance**: Productivity metrics, efficiency tracking, coaching insights

## Components

### Agents (5)

1. **customer-health-scorer** (Sonnet)
   - Multi-dimensional customer health scoring
   - Risk factor identification and trending
   - Health degradation early warning
   - Account prioritization recommendations

2. **churn-predictor** (Sonnet)
   - Churn prediction models and risk scoring
   - Leading indicator identification
   - At-risk customer detection
   - Intervention strategy development

3. **expansion-opportunity-identifier** (Sonnet)
   - Upsell and cross-sell opportunity detection
   - Whitespace analysis and mapping
   - Product adoption maturity assessment
   - Growth revenue forecasting

4. **customer-segmentation-analyst** (Sonnet)
   - Customer segmentation frameworks
   - Cohort analysis and behavioral clustering
   - Persona development and profiling
   - Segment-specific strategy recommendations

5. **csm-performance-analyzer** (Haiku)
   - CSM productivity and efficiency tracking
   - Portfolio health and coverage analysis
   - Activity and outcome metrics
   - Performance coaching insights

### Skills (7)

Progressive disclosure knowledge modules with deep expertise:

1. **customer-health-scoring** - Health scoring models, dimensions, thresholds, and trending
2. **churn-prediction-models** - Predictive modeling techniques, leading indicators, intervention frameworks
3. **expansion-analysis** - Upsell/cross-sell methodologies, whitespace mapping, maturity models
4. **segmentation-methods** - Segmentation frameworks, clustering algorithms, behavioral patterns
5. **nps-analysis** - NPS methodology, driver analysis, action planning frameworks
6. **engagement-scoring** - Engagement metrics, activity tracking, scoring models
7. **customer-journey-mapping** - Journey stages, touchpoints, moments of truth, optimization

### Commands (10)

Reusable workflows for common customer success tasks:

1. **/health-score** - Calculate comprehensive customer health score
2. **/churn-risk-list** - Generate prioritized at-risk customer list
3. **/expansion-opportunities** - Identify upsell/cross-sell opportunities
4. **/nps-analysis** - Analyze NPS survey results and drivers
5. **/customer-segments** - Generate data-driven customer segments
6. **/engagement-report** - Customer engagement health report
7. **/csm-performance** - CSM performance and portfolio analysis
8. **/account-review-prep** - Prepare quarterly business review materials
9. **/renewal-forecast** - Renewal forecast and risk assessment
10. **/escalation-analysis** - Escalation pattern and root cause analysis

### Orchestrations (3)

Multi-agent workflows for complex customer success processes:

1. **weekly-at-risk-review** - Weekly at-risk account review and action planning
2. **qbr-preparation** - Comprehensive quarterly business review preparation workflow
3. **expansion-campaign** - Expansion opportunity identification and campaign execution

## Installation

### Prerequisites

- Claude Code CLI installed
- Access to customer success platform (Gainsight, Totango, ChurnZero, or similar)
- Customer data available for analysis (health metrics, usage, support tickets, NPS)

### Setup

1. Clone or copy the `customer-success-operations` plugin to your Claude plugins directory:
   ```bash
   cp -r customer-success-operations ~/.claude/plugins/
   ```

2. Verify plugin installation:
   ```bash
   claude plugins list
   ```

3. Activate the plugin (if not auto-loaded):
   ```bash
   claude plugins enable customer-success-operations
   ```

## Quick Start

### Example 1: Customer Health Scoring

```bash
# Calculate health score for specific account
/health-score ACCT-12345

# Claude will:
# - Assess health across product usage, engagement, sentiment, financial dimensions
# - Calculate weighted health score (0-100)
# - Identify risk factors and positive indicators
# - Provide trending analysis and recommendations
```

### Example 2: Churn Risk Identification

```bash
# Generate at-risk customer list for review
/churn-risk-list Q4 enterprise

# Claude will:
# - Apply churn prediction model to customer base
# - Score and rank customers by churn risk
# - Identify leading indicators and triggers
# - Recommend prioritized intervention actions
```

### Example 3: Expansion Opportunities

```bash
# Identify expansion opportunities for growth planning
/expansion-opportunities high-health

# Claude will:
# - Analyze product adoption and usage patterns
# - Identify whitespace and cross-sell opportunities
# - Score expansion propensity and potential value
# - Generate prioritized expansion target list
```

### Example 4: Interactive Agent Use

```
You: "Which customers are at highest risk of churning this quarter?"

Claude (activates churn-predictor):
I'll analyze your customer base to identify churn risks...

At-Risk Customers (Top 10):

High Risk (>70% churn probability):
1. Acme Corp ($45K ARR) - 82% risk
   - Leading indicators: 60% usage drop, 2 escalations, NPS decline to 3
   - Last CSM touch: 45 days ago
   - Renewal: 23 days
   - Action: URGENT executive intervention required

2. GlobalTech Inc ($38K ARR) - 76% risk
   - Leading indicators: Product champion departed, low adoption (23%)
   - Support tickets: 8 in last 30 days
   - Renewal: 31 days
   - Action: Immediate health check call, success plan review

Medium Risk (50-70%):
3. DataFlow Systems ($52K ARR) - 68% risk
   - Leading indicators: Flat usage, missed QBR, budget concerns
   - NPS: 6 (down from 8)
   - Action: Re-engage stakeholders, demonstrate ROI

Recommended Actions:
1. Schedule executive calls with top 5 at-risk accounts this week
2. Deploy win-back playbook for high-risk renewals
3. Conduct usage analysis to identify barriers
4. Review CSM coverage for at-risk portfolio
```

## Usage Patterns

### For CS Leaders

**Weekly At-Risk Reviews:**
- Use `churn-predictor` for real-time risk assessment
- Run `/churn-risk-list` command for comprehensive weekly analysis
- Execute `weekly-at-risk-review` orchestration for structured review process
- Assign intervention actions to CSM team

**Monthly Performance Reviews:**
- Use `csm-performance-analyzer` to track team productivity
- Run `/csm-performance` for individual and team metrics
- Identify coaching opportunities and capacity issues
- Adjust portfolio assignments based on health and workload

**Quarterly Business Reviews:**
- Use `qbr-preparation` orchestration for customer QBR materials
- Run `/account-review-prep` for executive-ready presentations
- Analyze customer health trends and success metrics
- Build renewal forecast and expansion pipeline

### For CSM Teams

**Account Management:**
- Use `customer-health-scorer` to monitor portfolio health
- Run `/health-score` for individual account assessments
- Track engagement trends and early warning signals
- Prioritize outreach based on health scores

**Expansion Planning:**
- Use `expansion-opportunity-identifier` to find growth opportunities
- Run `/expansion-opportunities` for whitespace analysis
- Build expansion pipeline for quota attainment
- Coordinate with sales on upsell/cross-sell campaigns

**Customer Insights:**
- Use `customer-segmentation-analyst` for segment analysis
- Run `/customer-segments` to understand customer cohorts
- Tailor engagement strategies by segment
- Develop segment-specific playbooks

### For CS Operations

**Analytics and Reporting:**
- Use `customer-health-scorer` and `customer-health-scoring` skill for metric frameworks
- Build automated health score dashboards
- Track leading indicators and health trends
- Measure program effectiveness

**Predictive Modeling:**
- Use `churn-predictor` and `churn-prediction-models` skill for model development
- Refine prediction algorithms with historical data
- Identify new leading indicators
- Validate model accuracy and calibrate thresholds

**Process Optimization:**
- Use `customer-journey-mapping` skill to optimize customer experience
- Analyze touchpoint effectiveness
- Identify friction points and moments of truth
- Design scalable engagement programs

### For Executives

**Strategic Planning:**
- Use `customer-segmentation-analyst` for portfolio analysis
- Understand customer base composition and trends
- Model retention and expansion scenarios
- Allocate resources based on segment value

**Performance Monitoring:**
- Track GRR, NRR, logo churn, revenue churn metrics
- Monitor customer health distribution
- Measure CS team efficiency and outcomes
- Report on customer success KPIs to board

## Configuration

### Model Assignments

The plugin uses appropriate models for each agent:

- **Sonnet**: Complex analysis and reasoning tasks
  - customer-health-scorer
  - churn-predictor
  - expansion-opportunity-identifier
  - customer-segmentation-analyst

- **Haiku**: Operational tracking and reporting
  - csm-performance-analyzer

### Customization

You can customize the plugin by:

1. **Adjusting Health Score Weights**: Edit `customer-health-scoring` skill to reflect your priorities
2. **Refining Churn Models**: Update `churn-prediction-models` skill with your industry benchmarks
3. **Customizing Workflows**: Adapt command workflows for your CS processes
4. **Extending Orchestrations**: Modify multi-agent workflows to match your business cadence

## Data Requirements

For optimal functionality, ensure access to:

- **Customer Platform Data**: Health scores, usage metrics, engagement activities
- **Financial Data**: ARR/MRR, contract terms, renewal dates
- **Product Usage**: Feature adoption, login frequency, utilization metrics
- **Support Data**: Tickets, escalations, CSAT scores
- **Survey Data**: NPS, satisfaction scores, feedback
- **Relationship Data**: Stakeholders, champions, decision makers

## Best Practices

1. **Proactive Monitoring**: Establish weekly health score reviews and at-risk account processes
2. **Data Quality**: Maintain accurate customer data for reliable health scoring
3. **Early Intervention**: Act on early warning signals before risks escalate
4. **Segment-Specific Strategies**: Tailor playbooks and engagement by customer segment
5. **Continuous Improvement**: Track metrics over time and refine models
6. **Cross-Functional Collaboration**: Align CS, Sales, Product, Support on customer health

## Troubleshooting

### Common Issues

**Issue**: Health scores seem inaccurate or inconsistent
- **Solution**: Verify data quality, review dimension weights, validate scoring logic against outcomes

**Issue**: Churn predictions have low accuracy
- **Solution**: Analyze false positives/negatives, identify missing leading indicators, refine model with historical data

**Issue**: Missing expansion opportunities
- **Solution**: Review product adoption thresholds, analyze successful expansion patterns, improve whitespace mapping

**Issue**: Engagement scores don't correlate with outcomes
- **Solution**: Re-evaluate engagement metrics, weight activities by impact, segment by customer maturity

## Support and Contribution

### Getting Help

- Review skill modules for detailed methodologies
- Check orchestration workflows for process examples
- Consult validation-rules.md in meta-agent-builder for standards

### Contributing

Contributions welcome! Please:
- Follow existing agent and skill patterns
- Use customer success language and metrics
- Include examples and use cases
- Validate against validation-rules.md

## Version History

**1.0.0** (2025-10-24)
- Initial release with 5 agents, 7 skills, 10 commands
- Complete health scoring, churn prediction, expansion, segmentation capabilities
- Three orchestrations for complex workflows
- Comprehensive skill modules with progressive disclosure

## License

MIT License - See LICENSE file for details

## Related Plugins

- **revenue-operations**: Pipeline and forecast management
- **marketing-operations**: Campaign and attribution analysis
- **sales-operations**: Sales performance and territory optimization
- **finance-operations**: Budgeting and variance analysis

---

**Powered by**: Agentic System Builder Framework
**Repository**: https://github.com/TamerineSky/Agentic-System-Builder
**Documentation**: See /docs for complete framework documentation
