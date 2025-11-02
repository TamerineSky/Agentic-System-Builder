# HR Operations Plugin

> **Comprehensive human resources and people analytics plugin for workforce planning, attrition prediction, compensation analysis, performance management, and recruiting optimization.**

## Overview

The HR Operations Plugin provides AI-powered agents, analytical skills, and workflows to optimize people operations across the talent lifecycle. From strategic workforce planning to tactical recruiting optimization, this plugin helps HR teams make data-driven decisions, improve efficiency, and enhance the employee experience.

## Key Capabilities

### Strategic Workforce Planning
- Headcount forecasting with scenario modeling (conservative/base/aggressive)
- Capacity analysis and organizational design optimization
- Skills gap analysis and build-vs-buy recommendations
- Succession planning and talent pipeline assessment
- Revenue per employee and productivity tracking

### Attrition & Retention
- Predictive attrition modeling with flight risk scoring
- Cohort analysis by department, tenure, manager, demographics
- Root cause analysis from exit interviews
- Retention strategy development with ROI modeling
- Early intervention programs for high-risk employees

### Compensation & Rewards
- Market benchmarking with compa-ratio analysis
- Pay equity analysis using statistical regression
- Merit increase planning with performance differentiation
- Salary band development and geographic pay strategies
- Total rewards optimization (base, bonus, equity, benefits)

### Performance Management
- Rating distribution analysis and calibration support
- Bias detection and demographic fairness validation
- Performance-outcome correlation analysis
- Manager calibration facilitation
- Continuous feedback and goal-setting frameworks

### Recruiting Analytics
- Funnel optimization with stage-by-stage conversion rates
- Time-to-fill analysis and bottleneck identification
- Source effectiveness and ROI analysis
- Offer competitiveness and acceptance rate improvement
- Quality of hire measurement and tracking

### Diversity & Inclusion
- Representation analysis by level and function
- Pay equity studies by protected class
- Hiring, promotion, and attrition flow analysis
- Inclusion measurement through engagement surveys
- Intersectionality analysis for underrepresented groups

## Plugin Components

### Agents (5)

#### 1. **workforce-planner** (Sonnet)
Strategic workforce planning specialist for headcount forecasting, capacity modeling, and organizational design.

**Use when**:
- Planning annual headcount and budgets
- Modeling workforce scenarios
- Optimizing organizational structure
- Analyzing span of control
- Forecasting capacity needs

**Capabilities**:
- Driver-based headcount forecasting
- Scenario modeling (conservative, base, aggressive)
- Capacity gap analysis
- Organizational design recommendations
- Span of control optimization

#### 2. **attrition-predictor** (Sonnet)
Attrition analysis and retention strategy expert using predictive modeling and data-driven interventions.

**Use when**:
- Analyzing turnover trends
- Predicting flight risks
- Investigating attrition drivers
- Developing retention strategies
- Calculating attrition costs and ROI

**Capabilities**:
- Predictive flight risk scoring
- Cohort and survival analysis
- Exit interview theme extraction
- Retention program ROI modeling
- Early warning signal identification

#### 3. **compensation-analyst** (Sonnet)
Compensation benchmarking and pay equity specialist for market-competitive and equitable compensation strategies.

**Use when**:
- Benchmarking salaries against market
- Conducting pay equity studies
- Planning merit increases
- Developing salary bands
- Assessing compensation competitiveness

**Capabilities**:
- Market data matching and benchmarking
- Compa-ratio calculation and analysis
- Statistical pay equity regression
- Merit increase matrix design
- Geographic pay differential modeling

#### 4. **performance-analytics-agent** (Sonnet)
Performance distribution analyst and calibration facilitator for fair and consistent performance management.

**Use when**:
- Analyzing rating distributions
- Supporting calibration sessions
- Detecting rating bias
- Validating performance-pay linkage
- Assessing manager rating tendencies

**Capabilities**:
- Distribution analysis vs. guidelines
- Calibration prep and facilitation
- Demographic fairness testing
- Performance-outcome correlation
- Manager outlier identification

#### 5. **recruiting-efficiency-analyst** (Haiku)
Recruiting metrics and funnel optimization specialist for efficient, high-quality hiring.

**Use when**:
- Analyzing recruiting funnel performance
- Reducing time-to-fill
- Evaluating source effectiveness
- Improving offer acceptance rates
- Optimizing cost-per-hire

**Capabilities**:
- Funnel conversion rate analysis
- Time-to-fill decomposition by stage
- Source ROI and effectiveness scoring
- Offer competitiveness assessment
- Quality of hire measurement

### Skills (7)

#### 1. **workforce-planning-models**
Methodologies for strategic headcount planning, capacity modeling, and scenario analysis. Includes driver-based forecasting, span of control analysis, and organizational design principles.

#### 2. **attrition-analysis**
Techniques for attrition driver identification, predictive modeling, and retention strategy development. Covers cohort analysis, survival curves, and flight risk scoring.

#### 3. **compensation-benchmarking**
Methods for market pricing, compa-ratio analysis, pay equity studies, and total rewards strategy. Includes statistical regression for pay equity and merit matrix design.

#### 4. **performance-management**
Frameworks for performance rating systems, calibration processes, and feedback systems. Covers distribution analysis, bias detection, and performance-outcome validation.

#### 5. **recruiting-analytics**
Metrics for funnel optimization, source effectiveness, and quality of hire measurement. Includes time-to-fill analysis, cost-per-hire calculation, and hiring velocity forecasting.

#### 6. **diversity-inclusion-metrics**
Approaches for measuring workforce diversity, representation analysis, and inclusion assessment. Covers pay equity studies, flow analysis, and intersectionality.

#### 7. **skills-gap-analysis**
Methodologies for skills inventory assessment, gap identification, and workforce development planning. Includes build-vs-buy analysis and skills decay forecasting.

### Commands (10)

#### Workforce Planning
- **/headcount-plan** - Generate headcount forecast with scenario modeling
- **/skills-gap-analysis** - Identify skills gaps and development needs
- **/talent-pipeline** - Assess succession readiness and pipeline health

#### Retention & Attrition
- **/attrition-analysis** - Comprehensive attrition trend and driver analysis
- **/retention-analysis** - Retention analysis by cohort with risk identification

#### Compensation
- **/compensation-review** - Market benchmarking and competitiveness analysis
- **/offer-analysis** - Offer acceptance and competitiveness assessment

#### Performance
- **/performance-distribution** - Rating distribution and calibration analysis

#### Recruiting
- **/recruiting-metrics** - Funnel analysis and efficiency optimization

#### Diversity
- **/diversity-report** - Comprehensive D&I metrics and reporting

### Orchestrations (3)

#### 1. **annual-planning.md**
14-week annual workforce planning process integrating headcount forecasting, budget development, organizational design, and talent strategy. Coordinates workforce-planner, attrition-predictor, and compensation-analyst agents.

**Key Phases**:
- Business strategy alignment
- Current state assessment
- Demand forecasting with scenarios
- Organizational design
- Budget development
- Stakeholder review
- Quarterly tracking

#### 2. **performance-review-cycle.md**
14-week performance review and calibration cycle including self-assessments, manager reviews, calibration sessions, and linkage to compensation. Orchestrates performance-analytics-agent and compensation-analyst.

**Key Phases**:
- Cycle launch and training
- Employee self-assessments
- Manager reviews
- Pre-calibration analysis
- Calibration sessions
- Performance conversations
- Merit planning integration

#### 3. **compensation-planning.md**
14-week annual compensation planning process with market benchmarking, pay equity analysis, merit increase planning, and total rewards strategy. Coordinates compensation-analyst, performance-analytics-agent, and attrition-predictor.

**Key Phases**:
- Market benchmarking
- Pay equity analysis
- Merit matrix design
- Budget approval
- Manager allocation
- Equity validation
- Communication and delivery

## Quick Start

### 1. Install the Plugin

```bash
# From your Claude Code workspace
cd .claude/plugins
git clone <plugin-repo-url> hr-operations
```

### 2. Enable in Claude Code

Add to your `.claude/config.json`:

```json
{
  "plugins": [
    "hr-operations"
  ]
}
```

### 3. First Analysis

```bash
# Analyze attrition trends
/attrition-analysis --period "last 12 months" --segment "all"

# Review compensation competitiveness
/compensation-review --org "Engineering" --roles "all"

# Generate headcount plan
/headcount-plan --timeframe "FY2025" --org "all" --growth-rate "50% ARR growth"
```

## Common Use Cases

### Use Case 1: Annual Workforce Planning

**Objective**: Develop strategic workforce plan for next fiscal year.

**Workflow**:
1. Run `/headcount-plan` with business growth assumptions
2. Use `workforce-planner` agent for scenario modeling
3. Run `/skills-gap-analysis` for capability assessment
4. Use `attrition-predictor` for turnover forecasting
5. Integrate with budget planning and organizational design
6. Follow **annual-planning** orchestration for full cycle

**Expected Outcome**: Comprehensive workforce plan with headcount targets, hiring priorities, budget, and organizational design recommendations.

### Use Case 2: Reducing Engineering Attrition

**Objective**: Identify and address engineering attrition drivers.

**Workflow**:
1. Run `/attrition-analysis --period "last 24 months" --segment "engineering"`
2. Use `attrition-predictor` to build flight risk model
3. Run `/compensation-review --org "engineering"` to assess pay competitiveness
4. Run `/retention-analysis --cohort "engineering"` for targeted strategies
5. Develop retention programs based on root causes
6. Measure ROI of interventions

**Expected Outcome**: Data-driven retention strategy with targeted interventions, flight risk scores, and expected attrition reduction (3-5 percentage points).

### Use Case 3: Merit Increase Planning

**Objective**: Plan fair, competitive merit increases within budget.

**Workflow**:
1. Run `/compensation-review --org "all"` for market benchmarking
2. Run `/performance-distribution --cycle "2024 Annual"` for performance data
3. Use `compensation-analyst` to design merit matrix
4. Model budget scenarios (3%, 3.5%, 4%)
5. Validate pay equity post-merit
6. Follow **compensation-planning** orchestration for full cycle

**Expected Outcome**: Performance-differentiated merit plan within budget, market-competitive, pay equity validated.

### Use Case 4: Performance Calibration

**Objective**: Ensure fair, consistent performance ratings across organization.

**Workflow**:
1. Managers submit initial ratings
2. Run `/performance-distribution --cycle "current" --org "all"` for pre-calibration analysis
3. Use `performance-analytics-agent` to identify outliers
4. Facilitate calibration sessions with peer comparisons
5. Validate post-calibration distribution and fairness
6. Follow **performance-review-cycle** orchestration

**Expected Outcome**: Calibrated ratings aligned with guidelines, no demographic disparities, consistent standards across teams.

### Use Case 5: Recruiting Funnel Optimization

**Objective**: Reduce time-to-fill and improve recruiting efficiency.

**Workflow**:
1. Run `/recruiting-metrics --period "last 6 months" --function "all"`
2. Use `recruiting-efficiency-analyst` to identify bottlenecks
3. Run `/offer-analysis` to assess acceptance rates
4. Analyze source effectiveness and ROI
5. Implement optimization recommendations
6. Track improvement metrics quarterly

**Expected Outcome**: 10-15 day reduction in time-to-fill, improved source mix, higher offer acceptance (85-90%), lower cost-per-hire.

## Integration Points

### HRIS Systems
- **Workday**: Headcount, org structure, compensation, performance data
- **BambooHR**: Employee data, attrition tracking, reporting
- **ADP**: Payroll integration, compensation administration
- **SuccessFactors**: Performance management, talent review

### Applicant Tracking Systems (ATS)
- **Greenhouse**: Recruiting funnel data, source tracking, hiring metrics
- **Lever**: Candidate pipeline, interview feedback, offer management
- **Workable**: Job postings, applicant screening, hiring workflows

### Compensation Platforms
- **Pave**: Market data, compensation benchmarking, merit planning
- **Carta**: Equity management, cap table, equity compensation
- **Salary.com**: Salary surveys, job matching, market pricing

### Performance & Engagement
- **Lattice**: Performance reviews, goal tracking, 1:1 management
- **15Five**: Continuous feedback, engagement surveys, OKRs
- **Culture Amp**: Employee engagement, pulse surveys, analytics

### Data Warehouses
- **Snowflake**: Centralized people data, advanced analytics
- **BigQuery**: People analytics, custom reporting, dashboards
- **Redshift**: Data consolidation, reporting, visualization

## Best Practices

### Data Quality
- Ensure HRIS data accuracy (headcount, roles, comp, demographics)
- Validate data before analysis (missing values, outliers, inconsistencies)
- Maintain consistent role taxonomies and leveling
- Regular data audits (quarterly)

### Privacy & Confidentiality
- Limit access to compensation data (role-based permissions)
- Anonymize data for demographic analysis when possible
- Comply with data privacy regulations (GDPR, CCPA)
- Store sensitive data securely

### Stakeholder Engagement
- Involve business leaders in workforce planning
- Train managers on compensation and performance tools
- Communicate methodology and rationale transparently
- Set clear expectations on timelines and outcomes

### Continuous Improvement
- Track metrics over time (trends matter more than snapshots)
- Benchmark externally (industry, stage, size)
- Conduct post-cycle retrospectives
- Iterate on processes based on feedback

### Model Validation
- Test predictive models on historical data (accuracy, recall, precision)
- Monitor model drift over time
- Update models annually with new data
- Document assumptions and limitations clearly

## Metrics & Benchmarks

### Workforce Planning
- **Revenue per Employee**: $200K-$350K (SaaS), $400K-$600K (mature tech)
- **Span of Control**: 5-10 direct reports typical, 5-8 for engineering managers
- **Forecast Accuracy**: Actual within 10% of planned headcount

### Attrition & Retention
- **Attrition Rate**: 10-15% annually overall, 18-22% engineering (tech industry)
- **New Hire Attrition** (0-12 months): 25-35% typical (high-risk cohort)
- **Turnover Cost**: 1.5-2.0x annual salary per departure

### Compensation
- **Compa-Ratio**: 0.95-1.05 target for most employees (market competitive)
- **Merit Budget**: 3-4% of payroll typical
- **Pay Equity**: <2% adjusted gender pay gap acceptable, 0% goal

### Performance
- **Rating Distribution**: Follow guidelines (e.g., 10/30/50/10 for 5-point scale)
- **Performance-Merit Correlation**: >0.6 (strong linkage)
- **Calibration**: ±2% tolerance from guidelines acceptable

### Recruiting
- **Time-to-Fill**: 35-45 days overall, 45-55 days engineering
- **Offer Acceptance Rate**: 85-90% target
- **Cost-per-Hire**: $4-12K varies by role/industry
- **Quality of Hire**: >70/100 good, >80/100 excellent

### Diversity & Inclusion
- **Representation**: Track overall, by level, by function
- **Pay Equity**: No statistically significant gaps (p-value >0.05)
- **Inclusion Index**: >4.0/5.0 strong inclusion

## Troubleshooting

### Issue: Attrition forecast inaccurate
- **Cause**: Historical data not representative or external factors changed
- **Solution**: Use shorter lookback window (12 months), adjust for known changes, segment by cohort rather than overall

### Issue: Pay equity regression shows gaps
- **Cause**: Missing legitimate factors, small sample size, or actual inequity
- **Solution**: Include all relevant factors (level, tenure, performance, location, function), increase sample size, plan remediation if true gap

### Issue: Performance ratings inflated vs. guidelines
- **Cause**: Manager leniency, lack of calibration, unclear rating definitions
- **Solution**: Conduct calibration sessions, train managers on standards, require evidence for top ratings

### Issue: Time-to-fill too long
- **Cause**: Funnel bottleneck, slow interviewing, uncompetitive offers
- **Solution**: Run `/recruiting-metrics` to identify bottleneck stage, streamline process, improve compensation competitiveness

### Issue: Headcount plan misaligned with budget
- **Cause**: Unrealistic assumptions, lack of scenario planning, misaligned priorities
- **Solution**: Model multiple scenarios, align with CFO on constraints, prioritize critical hires, phase hiring over time

## Roadmap & Future Enhancements

### Q1 2025
- Integration with Workday API for real-time data sync
- Enhanced predictive models with ML (XGBoost, Random Forest)
- Automated anomaly detection in HR metrics

### Q2 2025
- Skills-based hiring recommendations
- Career pathing and internal mobility optimization
- Total rewards optimization (base, bonus, equity mix)

### Q3 2025
- Organizational network analysis (collaboration patterns)
- Manager effectiveness scoring
- Personalized development plan generation

### Q4 2025
- Real-time dashboards and alerting
- Natural language query interface for HR data
- Automated workflow orchestrations

## Contributing

We welcome contributions to improve the HR Operations Plugin! Please see [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines.

### Areas for Contribution
- Additional skills (e.g., benefits analytics, learning & development)
- New commands (e.g., internal mobility analysis, manager effectiveness)
- Enhanced orchestrations (e.g., onboarding programs, exit processes)
- Integration adapters for additional HRIS/ATS systems
- Improved predictive models and algorithms

## License

MIT License - see [LICENSE](../../LICENSE)

## Support

- **Documentation**: See [docs/domains/hr-operations.md](../../docs/domains/hr-operations.md) (coming)
- **Issues**: Report bugs or request features via GitHub Issues
- **Community**: Join discussions in [GitHub Discussions](https://github.com/TamerineSky/Agentic-System-Builder/discussions)

## Acknowledgments

This plugin adapts proven patterns from:
- **Seth Dobson's agents repository**: Agent architecture and plugin design
- **Anthropic's Agent Skills**: Progressive disclosure and skills framework
- **People Analytics Best Practices**: Industry-standard methodologies and benchmarks

## Related Plugins

- **revenue-operations**: Sales analytics, pipeline health, forecasting
- **finance-operations**: Budget variance, forecasting, cost optimization
- **customer-success-operations**: Health scoring, churn prediction, expansion
- **supply-operations**: Capacity planning, demand forecasting (workforce parallels)

---

**Version**: 1.0.0
**Last Updated**: 2025-10-24
**Maintainer**: Meta Agent Builder
**Category**: Business Operations - Human Resources

---

## Quick Reference

### Most Common Commands
```bash
# Workforce planning
/headcount-plan --timeframe "12 months" --org "all" --growth-rate "50%"

# Attrition analysis
/attrition-analysis --period "last 12 months" --segment "all"

# Compensation review
/compensation-review --org "Engineering" --roles "all"

# Performance distribution
/performance-distribution --cycle "2024 Annual" --org "all"

# Recruiting metrics
/recruiting-metrics --period "last 6 months" --function "all"

# Diversity report
/diversity-report --period "2024 Annual"
```

### Most Used Agents
- `@workforce-planner` - Strategic headcount and capacity planning
- `@attrition-predictor` - Turnover analysis and retention strategies
- `@compensation-analyst` - Pay equity and market benchmarking
- `@performance-analytics-agent` - Performance calibration and analysis
- `@recruiting-efficiency-analyst` - Recruiting funnel optimization

### Key Skills to Reference
- `workforce-planning-models` - Headcount forecasting methodologies
- `attrition-analysis` - Predictive turnover modeling
- `compensation-benchmarking` - Market pricing and pay equity
- `performance-management` - Calibration and distribution analysis
- `recruiting-analytics` - Funnel metrics and optimization

---

**Ready to optimize your HR operations with data-driven insights? Get started with `/attrition-analysis` or `/headcount-plan` today!**
