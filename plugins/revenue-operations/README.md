# Revenue Operations Plugin

Comprehensive revenue operations plugin providing AI-powered sales pipeline analysis, revenue forecasting, deal risk management, quota tracking, territory optimization, and sales operations automation.

## Overview

The Revenue Operations plugin enables sales leaders, RevOps teams, and executives to make data-driven decisions about pipeline health, forecast accuracy, deal risks, quota attainment, and territory design. It combines six specialized agents, eight skill modules, and ten command workflows to cover the complete revenue operations lifecycle.

### Key Capabilities

- **Pipeline Analysis**: Health scoring, coverage tracking, velocity analysis, bottleneck identification
- **Revenue Forecasting**: Multi-methodology forecasting, scenario planning, accuracy improvement
- **Deal Risk Management**: Risk scoring, at-risk deal identification, mitigation strategies
- **Quota Tracking**: Real-time attainment monitoring, pacing analysis, performance projection
- **Territory Optimization**: Data-driven territory design, workload balancing, coverage optimization
- **Sales Automation**: CRM workflow automation, data hygiene, reporting, lead routing

## Components

### Agents (6)

1. **sales-pipeline-analyst** (Sonnet)
   - Pipeline health analysis and deal progression insights
   - Coverage ratio calculation and trending
   - Stage velocity and bottleneck identification
   - At-risk deal detection with mitigation recommendations

2. **revenue-forecaster** (Sonnet)
   - Multi-methodology revenue forecasting
   - Forecast accuracy measurement and improvement
   - Scenario planning (conservative/base/upside)
   - Variance analysis and assumption testing

3. **deal-risk-analyzer** (Sonnet)
   - Multi-dimensional deal risk scoring
   - Competitive threat assessment
   - Stakeholder and engagement risk analysis
   - Mitigation strategy development

4. **sales-ops-automator** (Haiku)
   - CRM workflow and automation design
   - Data hygiene and validation rules
   - Automated reporting and dashboards
   - Lead routing and assignment logic

5. **quota-performance-tracker** (Haiku)
   - Real-time quota attainment tracking
   - Rep performance scorecards
   - Pacing analysis and projection
   - At-risk rep identification

6. **territory-planning-advisor** (Sonnet)
   - Territory design and optimization
   - Workload balance analysis
   - Account assignment strategies
   - New hire territory carve-outs

### Skills (8)

Progressive disclosure knowledge modules with deep expertise:

1. **pipeline-health-analysis** - Pipeline health scoring frameworks and methodologies
2. **revenue-forecasting-methods** - Multiple forecasting techniques (pipeline-based, historical, statistical)
3. **deal-scoring-models** - MEDDIC, BANT, and propensity-to-close scoring frameworks
4. **sales-forecasting** - Forecast submission workflows and category management
5. **crm-integration-patterns** - CRM to data warehouse integration architectures
6. **commission-calculations** - Compensation models and commission calculation methods
7. **territory-optimization** - Territory design principles and balancing techniques
8. **win-loss-analysis** - Win/loss interview frameworks and pattern identification

### Commands (10)

Reusable workflows for common revenue operations tasks:

1. **/pipeline-review** - Comprehensive pipeline health review
2. **/revenue-forecast** - Multi-methodology forecast generation
3. **/deal-risk-analysis** - Individual deal risk assessment
4. **/quota-status** - Quota attainment status report
5. **/territory-analysis** - Territory balance and optimization analysis
6. **/commission-calc** - Sales commission calculation
7. **/win-loss-analysis** - Win/loss pattern analysis
8. **/forecast-accuracy** - Forecast accuracy measurement
9. **/rep-performance** - Individual rep performance analysis
10. **/pipeline-cleanup** - Pipeline hygiene issue identification

### Orchestrations (4)

Multi-agent workflows for complex revenue operations processes:

1. **monthly-revenue-review** - Monthly business review combining forecast, pipeline, and quota analysis
2. **quarterly-planning** - Comprehensive quarterly planning with territory, quota, and forecast modeling
3. **deal-desk-review** - Structured deal approval workflow for non-standard deals
4. **sales-kickoff-prep** - Annual sales kickoff planning and execution

## Installation

### Prerequisites

- Claude Code CLI installed
- Access to CRM system (Salesforce, HubSpot, or similar)
- Sales and revenue data available for analysis

### Setup

1. Clone or copy the `revenue-operations` plugin to your Claude plugins directory:
   ```bash
   cp -r revenue-operations ~/.claude/plugins/
   ```

2. Verify plugin installation:
   ```bash
   claude plugins list
   ```

3. Activate the plugin (if not auto-loaded):
   ```bash
   claude plugins enable revenue-operations
   ```

## Quick Start

### Example 1: Pipeline Health Review

```bash
# Run comprehensive pipeline review for Q4 West region team
/pipeline-review Q4 West-Region

# Claude will:
# - Calculate coverage ratio and stage distribution
# - Analyze deal velocity and identify bottlenecks
# - Score at-risk deals and provide mitigation actions
# - Generate actionable recommendations
```

### Example 2: Revenue Forecast

```bash
# Generate Q4 revenue forecast with scenarios
/revenue-forecast Q4 monthly

# Claude will:
# - Apply multiple forecasting methodologies
# - Create conservative/base/upside scenarios
# - Provide confidence intervals
# - Explain variance from prior forecast
```

### Example 3: Deal Risk Analysis

```bash
# Analyze risk for specific opportunity
/deal-risk-analysis 006ABC123

# Claude will:
# - Score deal across engagement, competitive, timeline dimensions
# - Identify top risk factors with evidence
# - Recommend specific mitigation actions
# - Update win probability and forecast category
```

### Example 4: Interactive Agent Use

```
You: "How does our Q4 pipeline look?"

Claude (activates sales-pipeline-analyst):
I'll analyze your Q4 pipeline health...

Current Pipeline: $12.5M against $8M quota = 1.56x coverage

Key Risks Identified:
1. Stage Distribution Issue: 62% in Stage 1-2 (vs. 40% benchmark)
2. Deal Age Concern: 15 deals >90 days old ($4.2M)
3. Velocity Slowdown: 87 days avg vs. 72 day target

Recommended Actions:
1. Focus on advancing 23 Stage 3+ deals
2. Review/disqualify 15 aged opportunities
3. Generate $5M additional qualified pipeline
```

## Usage Patterns

### For Sales Leaders

**Weekly Pipeline Reviews:**
- Use `sales-pipeline-analyst` for real-time pipeline health insights
- Run `/pipeline-review` command for comprehensive weekly analysis
- Identify at-risk deals and assign mitigation actions

**Monthly Forecasting:**
- Use `revenue-forecaster` to build and validate forecasts
- Run `/revenue-forecast` for multi-methodology projections
- Execute `monthly-revenue-review` orchestration for complete business review

**Quarterly Planning:**
- Use `territory-planning-advisor` for territory optimization
- Run `quarterly-planning` orchestration for comprehensive planning
- Use `/territory-analysis` to model rebalancing scenarios

### For RevOps Teams

**Pipeline Analytics:**
- Use `sales-pipeline-analyst` and `pipeline-health-analysis` skill for deep analytics
- Build automated pipeline health dashboards
- Track pipeline metrics and trends over time

**Process Automation:**
- Use `sales-ops-automator` to design CRM workflows
- Implement automated lead routing and data hygiene
- Build scheduled reporting and alert systems

**Performance Tracking:**
- Use `quota-performance-tracker` for real-time attainment monitoring
- Run `/quota-status` for performance snapshots
- Run `/rep-performance` for individual coaching insights

### For Finance Teams

**Revenue Planning:**
- Use `revenue-forecaster` for annual and quarterly planning
- Validate sales forecasts with multiple methodologies
- Understand forecast assumptions and sensitivities

**Deal Approvals:**
- Use `deal-desk-review` orchestration for structured approvals
- Use `deal-risk-analyzer` for deal economics validation
- Track deal approval patterns and margins

### For Sales Reps

**Deal Management:**
- Use `deal-risk-analyzer` to assess opportunity health
- Get mitigation recommendations for at-risk deals
- Understand win/loss patterns from similar deals

**Performance Tracking:**
- Check quota status and pacing regularly
- Understand pipeline health and coverage requirements
- Access personalized coaching recommendations

## Configuration

### Model Assignments

The plugin uses appropriate models for each agent:

- **Sonnet**: Complex reasoning tasks (forecasting, risk analysis, planning)
  - revenue-forecaster
  - deal-risk-analyzer
  - sales-pipeline-analyst
  - territory-planning-advisor

- **Haiku**: Deterministic operational tasks (tracking, automation)
  - sales-ops-automator
  - quota-performance-tracker

### Customization

You can customize the plugin by:

1. **Adjusting Benchmarks**: Edit skill modules to reflect your industry/segment benchmarks
2. **Modifying Workflows**: Update command workflows for your specific processes
3. **Adding Skills**: Create additional skills for unique methodologies
4. **Extending Orchestrations**: Adapt multi-agent workflows to your business cadence

## Data Requirements

For optimal functionality, ensure access to:

- **CRM Data**: Opportunities, accounts, contacts, activities
- **Historical Performance**: Closed deals, win rates, deal cycles
- **Team Structure**: Territories, quotas, rep assignments
- **Current State**: Pipeline snapshot, forecast submissions

## Best Practices

1. **Regular Cadence**: Establish weekly pipeline reviews and monthly forecast cycles
2. **Data Quality**: Maintain clean CRM data for accurate analysis
3. **Consistent Methodology**: Use same forecasting methods for trend analysis
4. **Action-Oriented**: Always convert insights into specific next steps
5. **Continuous Improvement**: Track metrics over time and refine processes

## Troubleshooting

### Common Issues

**Issue**: Pipeline analysis shows unexpected coverage ratios
- **Solution**: Verify CRM data accuracy, check stage definitions, confirm quota targets

**Issue**: Forecast accuracy is low
- **Solution**: Review rep forecast discipline, calibrate probabilities, use ensemble methods

**Issue**: Territory imbalances identified
- **Solution**: Run territory optimization scenarios, plan gradual rebalancing, communicate changes

**Issue**: Automation workflows not triggering
- **Solution**: Check CRM permissions, validate workflow criteria, test with sample data

## Support and Contribution

### Getting Help

- Review skill modules for detailed methodologies
- Check orchestration workflows for process examples
- Consult validation-rules.md in meta-agent-builder for standards

### Contributing

Contributions welcome! Please:
- Follow existing agent and skill patterns
- Use business operations language (not technical jargon)
- Include examples and use cases
- Validate against validation-rules.md

## Version History

**1.0.0** (2025-10-24)
- Initial release with 6 agents, 8 skills, 10 commands
- Complete pipeline, forecast, deal, quota, territory capabilities
- Four orchestrations for complex workflows
- Comprehensive skill modules with progressive disclosure

## License

MIT License - See LICENSE file for details

## Related Plugins

- **supply-chain-operations**: Inventory and demand planning
- **marketing-operations**: Campaign and attribution analysis
- **customer-success-operations**: Health scoring and churn prevention
- **finance-operations**: Budgeting and variance analysis

---

**Powered by**: Agentic System Builder Framework
**Repository**: https://github.com/TamerineSky/Agentic-System-Builder
**Documentation**: See /docs for complete framework documentation
