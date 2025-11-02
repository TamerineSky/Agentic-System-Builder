# Your First Plugin in 30 Minutes
## Build a Customer Churn Analysis Plugin from Scratch

> **What You'll Build**: A complete customer-churn-operations plugin with 2 agents, 1 skill, and 2 commands that can predict churn risk and recommend retention strategies.

> **Time Required**: 30 minutes
> **Difficulty**: Beginner
> **Prerequisites**: Meta-agent-builder plugin installed

---

## What You'll Learn

By the end of this guide, you'll know how to:
- Use the domain-analyzer to understand business requirements
- Generate specialized agents for your domain
- Create skills that package your expertise
- Build commands that automate workflows
- Validate your plugin for quality

---

## The Challenge We're Solving

Customer churn is expensive. Identifying at-risk customers early and taking action can save 10-30% of annual revenue for SaaS and subscription businesses.

But manual churn analysis is:
- **Time-consuming**: Analysts spend hours each week reviewing customer data
- **Inconsistent**: Different analysts use different criteria
- **Reactive**: By the time patterns are noticed, it's often too late

**The Solution**: An automated churn analysis plugin that runs continuously, applies consistent criteria, and alerts you to at-risk customers before they leave.

---

## Minutes 0-5: Environment Setup & Overview

### Verify Installation

```bash
# Check that meta-agent-builder is installed
ls -la /plugins/meta-agent-builder
```

**Expected Output**:
```
7 agents, 4 skills, 7 commands
```

### Quick Tour

The meta-agent-builder includes 7 specialized agents that work together:

- **domain-analyzer**: Interviews you about your business needs
- **agent-generator**: Creates specialized AI agents
- **skill-builder**: Packages domain knowledge
- **command-composer**: Builds workflow automation
- **orchestration-designer**: Coordinates multi-agent workflows
- **integration-architect**: Connects to your systems
- **plugin-validator**: Ensures quality

You'll use 4 of these in the next 25 minutes.

---

## Minutes 5-10: Analyze Your Domain

### Start with Domain Analysis

The domain-analyzer agent interviews you to understand your business domain.

**Command**:
```bash
/generate-plugin customer-churn-operations "Analyze customer behavior to predict churn risk and recommend retention strategies"
```

**What Happens**:
The domain-analyzer asks you 5-7 questions about your business. Here's what the interview looks like:

**Question 1**: "What customer data sources do you have?"
**Your Answer**: "Salesforce CRM, product usage data, support tickets"

**Question 2**: "What defines churn in your business?"
**Your Answer**: "No login for 30 days or cancellation request"

**Question 3**: "Who uses churn predictions?"
**Your Answer**: "Customer success managers and retention team"

**Question 4**: "How often do you need churn analysis?"
**Your Answer**: "Weekly for high-risk accounts, monthly for all customers"

**Question 5**: "What retention tactics do you use?"
**Your Answer**: "Personalized outreach, product training, special offers"

### Domain Analyzer Output

After the interview, domain-analyzer recommends:

```markdown
## Recommended Plugin Architecture

**Plugin Name**: customer-churn-operations

**Agents** (2):
1. churn-predictor (Sonnet) - Analyze behavior patterns and predict risk
2. retention-strategist (Sonnet) - Recommend personalized retention tactics

**Skills** (1):
1. churn-prediction-models - Methods: usage decline, support signals, payment issues

**Commands** (2):
1. /analyze-churn-risk [segment] - Weekly risk assessment
2. /retention-plan [account-id] - Generate retention strategy

**Complexity**: Moderate (2-3 weeks with integrations)
**Integration**: Salesforce, product analytics, support system
```

**✓ Checkpoint**: You now have a complete plugin specification!

---

## Minutes 10-15: Generate Your First Agent

### Create the Churn Predictor Agent

Now use agent-generator to create your first agent:

**Command**:
```bash
/generate-agent churn-predictor "Analyze customer behavior patterns to predict churn risk using usage data, support interactions, and payment history"
```

**What Happens**:
The agent-generator:
1. Analyzes the role description
2. Identifies required capabilities (behavioral analysis, pattern recognition, risk scoring)
3. Selects Sonnet model (complex reasoning required)
4. Generates comprehensive system prompt
5. Creates activation criteria
6. Generates business examples
7. Saves to `plugins/customer-churn-operations/agents/churn-predictor.md`

### Review the Generated Agent

**File Created**: `plugins/customer-churn-operations/agents/churn-predictor.md`

**Contents Preview**:
```markdown
---
name: churn-predictor
description: Analyze customer behavior patterns to predict churn risk. Use PROACTIVELY when analyzing customer health, usage trends, or retention opportunities.
model: sonnet
tools: Read, Bash, Grep
---

You are an expert customer success analyst specializing in churn prediction...

## Capabilities
- Behavioral pattern analysis (usage decline, engagement drop-off)
- Multi-signal churn detection (support, payment, usage)
- Risk scoring and prioritization
- Early warning signal identification

## Response Approach
1. Gather customer behavioral data
2. Analyze patterns across multiple signals
3. Calculate risk scores (0-100 scale)
4. Identify contributing factors
5. Generate actionable insights
...
```

**✓ Checkpoint**: You have a specialized agent ready to predict churn!

---

## Minutes 15-20: Package Your Expertise as a Skill

### Create the Churn Prediction Models Skill

Skills package domain knowledge using progressive disclosure:

**Command**:
```bash
/generate-skill churn-prediction-models "Methods for predicting customer churn including usage decline analysis, support signal detection, and payment issue patterns"
```

**What Happens**:
The skill-builder:
1. Extracts domain knowledge from description
2. Designs 3-tier progressive disclosure structure
3. Creates activation criteria
4. Writes methodology documentation
5. Adds concrete examples
6. Validates against Anthropic spec (< 1024 char description)
7. Saves to `plugins/customer-churn-operations/skills/churn-prediction-models/SKILL.md`

### Review the Generated Skill

**File Created**: `plugins/customer-churn-operations/skills/churn-prediction-models/SKILL.md`

**Contents Preview**:
```yaml
---
name: churn-prediction-models
description: Methods for predicting customer churn including usage decline analysis, support signal detection, and payment issue patterns. Use when analyzing churn risk or building retention strategies.
---

# Churn Prediction Models

## When to Use This Skill
- Analyzing customer health scores
- Predicting churn risk
- Building early warning systems
- Identifying at-risk customer segments
- Designing retention interventions

## Core Methodologies

### 1. Usage Decline Analysis

**Purpose**: Detect decreasing product engagement as early churn indicator

**Key Metrics**:
- Login frequency (daily/weekly/monthly)
- Feature adoption depth
- Session duration trends
- Active user percentage

**Scoring Approach**:
- Baseline: Compare current vs. historical averages
- Velocity: Rate of decline (gradual vs. sharp drop)
- Absolute threshold: Below minimum engagement level
- Composite score: Weighted combination

**Example**:
```
Customer: Acme Corp
Baseline login: 45 times/month
Current month: 12 times/month
Decline: 73% reduction
Velocity: Sharp (occurred over 2 weeks)
Risk Score: 85/100 (High Risk)
```

### 2. Support Signal Detection

**Purpose**: Identify negative experiences indicating dissatisfaction

**Key Signals**:
- Ticket volume increase (quantity)
- Escalation frequency (severity)
- Response satisfaction (sentiment)
- Unresolved issue aging (time)

**Risk Indicators**:
- 3+ tickets in 30 days: Yellow flag
- Executive escalation: Orange flag
- Unresolved critical issue >14 days: Red flag
- Net Promoter Score decline >20 points: Red flag

### 3. Payment Issue Patterns

**Purpose**: Track payment reliability as churn predictor

**Warning Signs**:
- Failed payment attempts
- Payment method expiration
- Downgrade requests
- Discount/pricing inquiries
- Contract renewal delays

**Risk Timing**:
- 30 days before renewal: Critical monitoring period
- Failed payment + usage decline: 90% churn probability
- Downgrade + support issues: 75% churn probability

---

## Implementation Guidance

### Data Requirements
- 90 days minimum historical usage data
- Support ticket database access
- Payment/billing system integration
- Customer contract and renewal dates

### Scoring Framework
1. Calculate individual signal scores (0-100)
2. Apply domain-specific weights
3. Combine into composite risk score
4. Segment by customer tier/value
5. Prioritize by revenue at risk

### Action Thresholds
- **Score 0-30 (Low Risk)**: Standard engagement
- **Score 31-60 (Medium Risk)**: Proactive check-in
- **Score 61-80 (High Risk)**: CSM intervention
- **Score 81-100 (Critical Risk)**: Executive engagement

---

## Resources

### Sample Data Format
```json
{
  "customer_id": "ACME-001",
  "usage_metrics": {
    "logins_30d": 12,
    "logins_baseline": 45,
    "active_users": 3,
    "active_users_baseline": 15
  },
  "support_metrics": {
    "tickets_30d": 5,
    "escalations": 1,
    "unresolved_critical": 1
  },
  "payment_metrics": {
    "failed_payments": 1,
    "days_to_renewal": 45
  }
}
```

### Calculation Example
```python
# Usage decline score (40% weight)
usage_decline = (baseline - current) / baseline
usage_score = min(usage_decline * 100, 100)

# Support signal score (30% weight)
support_score = (tickets * 10) + (escalations * 20)

# Payment issue score (30% weight)
payment_score = (failed_payments * 40)

# Composite risk score
risk_score = (usage_score * 0.4) +
             (support_score * 0.3) +
             (payment_score * 0.3)
```
```

**✓ Checkpoint**: Your churn expertise is now packaged and reusable!

---

## Minutes 20-25: Create Automation Commands

### Build the Churn Risk Analysis Command

Commands automate routine workflows:

**Command**:
```bash
/generate-command analyze-churn-risk "Weekly analysis of customer segment to identify high-risk accounts"
```

**What Happens**:
The command-composer:
1. Analyzes workflow description
2. Identifies parameter (segment)
3. Designs workflow steps
4. References churn-predictor agent and churn-prediction-models skill
5. Defines output format
6. Saves to `plugins/customer-churn-operations/commands/analyze-churn-risk.md`

### Review the Generated Command

**File Created**: `plugins/customer-churn-operations/commands/analyze-churn-risk.md`

**Usage**:
```bash
/analyze-churn-risk "Enterprise customers"
```

**What It Does**:
1. Load customer data for specified segment
2. Apply churn prediction models (usage, support, payment)
3. Calculate risk scores (0-100)
4. Prioritize by impact (revenue at risk)
5. Generate retention recommendations
6. Output actionable report

**Sample Output**:
```markdown
## Churn Risk Analysis: Enterprise Customers
**Date**: 2025-01-15
**Segment**: Enterprise (Annual >$50K)
**Accounts Analyzed**: 47

### High Risk (Score 80-100) - IMMEDIATE ACTION REQUIRED
**2 accounts, $205K annual revenue at risk**

#### 1. Acme Corp - $120K/year - Score: 92
**Risk Factors**:
- Usage gap: 45 days since last login
- Support escalations: 3 in past month (exec involvement)
- Payment: 1 failed attempt, renewal in 30 days

**Recommendation**:
Executive outreach + product training within 48 hours. Assign dedicated CSM. Offer strategic consulting session.

**Priority**: CRITICAL - Schedule intervention today

---

#### 2. TechStart Inc - $85K/year - Score: 87
**Risk Factors**:
- Usage decline: 60% drop from baseline
- Feature adoption: Stalled at basic tier
- Support: Feature request denied

**Recommendation**:
CSM check-in to understand blockers. Arrange feature enablement session. Consider custom solution discussion.

**Priority**: HIGH - Contact within 3 days

---

### Medium Risk (Score 60-79) - PROACTIVE ENGAGEMENT
**5 accounts, $340K annual revenue at risk**

#### 3. GlobalTech Ltd - $95K/year - Score: 74
- Usage decline: 35% drop
- Support: 2 tickets, average satisfaction
- Action: Quarterly business review scheduled + success planning

#### 4. DataFlow Systems - $78K/year - Score: 68
- Usage stable but low depth
- Support: Minimal engagement
- Action: Product training + advanced features demo

[... continued for remaining medium-risk accounts ...]

---

### Low Risk (Score 0-59) - STANDARD ENGAGEMENT
**40 accounts, $2.8M annual revenue - healthy**

Standard quarterly reviews and proactive success management.

---

## Executive Summary

**Total Risk Assessment**:
- Critical: 2 accounts ($205K at risk) - 7.3% of segment revenue
- High: 5 accounts ($340K at risk) - 12.1% of segment revenue
- Low: 40 accounts ($2.8M healthy) - 80.6% of segment revenue

**Recommended Actions**:
1. **Today**: Executive engagement for 2 critical accounts
2. **This Week**: CSM interventions for 5 medium-risk accounts
3. **This Month**: Strategic planning to address root causes

**Potential Save**: If successful interventions reduce churn by 50%, estimated revenue saved: $272K annually
```

**✓ Checkpoint**: You have automated churn analysis!

---

## Minutes 25-28: Validate Your Plugin

### Run Quality Checks

**Command**:
```bash
/validate-plugin customer-churn-operations
```

**What Happens**:
The plugin-validator checks:
- ✓ Plugin structure (directory organization)
- ✓ File naming conventions (hyphen-case)
- ✓ Agent frontmatter (name, description, model)
- ✓ Skill Anthropic spec compliance
- ✓ Command parameter handling
- ✓ Cross-references (agents → skills)

**Validation Report**:
```markdown
## Validation Report: customer-churn-operations

### Summary
- Status: ✓ PASS
- Components: 2 agents, 1 skill, 2 commands
- Issues: 0 CRITICAL, 1 WARNING, 2 INFO

### Component Validation

#### Agents (2)
✓ churn-predictor
  - Frontmatter: PASS
  - Model assignment: sonnet (appropriate for complex analysis)
  - Tools: Read, Bash, Grep (appropriate)
  - System prompt: Comprehensive, business-focused
  - Activation criteria: Clear

✓ retention-strategist
  - Frontmatter: PASS
  - Model assignment: sonnet (appropriate for strategic recommendations)
  - Tools: Read (appropriate)
  - System prompt: Comprehensive, business-focused
  - Activation criteria: Clear

#### Skills (1)
✓ churn-prediction-models
  - Frontmatter: PASS (description 247 chars, under 1024 limit)
  - Structure: 3-tier progressive disclosure
  - Activation criteria: Clear
  - Methodology: Comprehensive
  - Examples: Included

#### Commands (2)
✓ analyze-churn-risk
  - Frontmatter: PASS
  - Parameter handling: Correct ($1 for segment)
  - Workflow: Clear step-by-step
  - Agent references: Valid (churn-predictor)
  - Skill references: Valid (churn-prediction-models)

✓ retention-plan
  - Frontmatter: PASS
  - Parameter handling: Correct ($1 for account-id)
  - Workflow: Clear step-by-step
  - Agent references: Valid (retention-strategist)

### Warnings & Recommendations

⚠ WARNING: Consider adding integration-architect for Salesforce connection
  - Impact: Medium
  - Recommendation: Add Salesforce integration agent for automated data pull

ℹ INFO: Skill could benefit from code examples
  - Impact: Low
  - Recommendation: Add sample Python/SQL code for risk score calculations

ℹ INFO: Consider adding orchestration for end-to-end workflow
  - Impact: Low
  - Recommendation: Create orchestration combining analyze-churn-risk → retention-plan

### Quality Score: 95/100

**Excellent!** Plugin is production-ready. Warnings are suggestions for enhancement, not blockers.
```

**✓ Checkpoint**: Your plugin is validated and production-ready!

---

## Minutes 28-30: Test & Celebrate!

### Run Your First Analysis

**Command**:
```bash
/analyze-churn-risk "All customers"
```

**Result**:
Your churn-predictor agent analyzes customer behavior and generates a risk report in seconds!

### What You've Built

In 30 minutes, you created:
- **A complete plugin** for customer churn operations
- **2 specialized agents** that analyze churn and recommend retention strategies
- **1 reusable skill** packaging churn prediction expertise
- **2 automation commands** for routine analysis
- **A validated system** ready for production use

### The Impact

**Before**:
- Manual analysis: 4 hours/week per analyst
- Inconsistent criteria across team
- Reactive approach (notice churn too late)
- Limited coverage (only high-value accounts)

**After**:
- Automated analysis: < 5 minutes/week
- Consistent, data-driven decisions
- Proactive churn prevention
- Complete customer base coverage

**Time Saved**: ~200 hours/year per analyst
**Revenue Protected**: 10-30% reduction in churn (varies by intervention success)
**ROI**: Paying for itself with a single saved customer

---

## Next Steps

### Enhance Your Plugin

#### 1. Add Salesforce Integration
```bash
/generate-agent salesforce-connector "Pull customer data from Salesforce including usage, support, and contract information"
```

This agent will:
- Authenticate to Salesforce
- Query customer data (usage, support, contracts)
- Transform data for churn analysis
- Handle rate limiting and errors

#### 2. Create Orchestration
```bash
/generate-orchestration weekly-churn-review "Automated weekly workflow: pull data → analyze churn → generate report → send alerts"
```

This orchestration will:
- Run every Monday morning
- Pull latest customer data
- Analyze all segments
- Generate executive summary
- Send alerts for critical accounts

#### 3. Add Retention Strategy Agent
```bash
/generate-agent retention-strategist "Recommend personalized retention tactics based on churn risk factors and customer profile"
```

This agent will:
- Analyze risk factors
- Consider customer segment and value
- Recommend specific tactics
- Estimate intervention costs
- Prioritize by ROI

#### 4. Optimize Performance
```bash
/optimize-plugin customer-churn-operations
```

This command will:
- Analyze token usage
- Identify optimization opportunities
- Refactor for efficiency
- Re-validate quality

### Learn More

**Deep Dives**:
- [Ultimate Guide to Business Operations Agents](/docs/guides/ultimate-guide-business-operations-agents.md) - 5,000+ word comprehensive reference
- [50 Business Operations Use Cases Playbook](/docs/playbooks/50-business-operations-use-cases.md) - More plug-and-play examples
- [Integration Cookbook](/docs/cookbooks/business-systems-integration.md) - Connect to Salesforce, HubSpot, and more

**Community**:
- Share your plugin on GitHub
- Get help in our Slack community
- Contribute improvements

### Try Another Use Case

Pick from the 50 use cases playbook:
- **Revenue Operations**: Pipeline health analysis, sales forecasting
- **Supply Chain**: Demand planning, inventory optimization
- **Marketing**: Campaign attribution, content performance
- **Finance**: Budget variance, cash flow forecasting
- **Customer Success**: Health scoring, expansion opportunities
- **HR**: Attrition prediction, workforce planning

---

## Troubleshooting

### "Plugin not found"
**Problem**: Meta-agent-builder isn't installed

**Solution**: Verify installation
```bash
ls -la /plugins/meta-agent-builder
```

If missing, check with your administrator.

---

### "Agent generation failed"
**Problem**: Description is too vague or unclear

**Solution**: Provide more detail

❌ **Too vague**:
```bash
/generate-agent analyzer "analyze stuff"
```

✓ **Better**:
```bash
/generate-agent churn-analyzer "Analyze customer usage patterns, support interactions, and payment history to predict churn risk with 0-100 scoring"
```

**Tips**:
- Mention specific data sources
- Describe the analysis approach
- Include output format
- Specify business context

---

### "Validation warnings"
**Problem**: Plugin has warnings in validation report

**Solution**: Understand warning severity

- **CRITICAL**: Must fix before deployment
- **WARNING**: Should fix for optimal quality
- **INFO**: Nice-to-have improvements

Warnings and INFO items are suggestions, not blockers. You can deploy with warnings.

**Example**:
```
⚠ WARNING: Consider adding integration-architect
```

This means the plugin works but would benefit from an integration agent. Add it when ready, not required for initial deployment.

---

### "Command doesn't return expected output"
**Problem**: Command runs but output doesn't match expectations

**Solution**: Check data availability

**Common Issues**:
1. **No data**: Agent can't access customer data
   - Verify data sources are accessible
   - Check permissions
   - Add sample data for testing

2. **Incomplete data**: Missing key fields
   - Review data requirements in skill
   - Add data transformation step
   - Handle missing data gracefully

3. **Format issues**: Output format doesn't match needs
   - Edit command workflow
   - Adjust output template
   - Add formatting step

**Testing Tip**: Start with sample data to verify logic before connecting real systems.

---

### "Too slow / High token usage"
**Problem**: Plugin is slow or uses too many tokens

**Solution**: Optimize for performance

```bash
/optimize-plugin customer-churn-operations
```

The optimizer will:
- Identify token-heavy components
- Suggest Haiku alternatives for simple tasks
- Recommend skill restructuring
- Optimize progressive disclosure

**Quick Wins**:
- Use Haiku for data collection (vs. Sonnet)
- Load skills only when needed
- Reduce system prompt length
- Cache frequently used data

---

## You Did It!

**Congratulations!** You've built your first agentic system plugin in just 30 minutes.

You now know how to:
- ✓ Analyze business domains with domain-analyzer
- ✓ Generate specialized agents with agent-generator
- ✓ Package expertise as skills with skill-builder
- ✓ Automate workflows with command-composer
- ✓ Validate quality with plugin-validator

### What Makes This Powerful

You didn't just follow a tutorial - you built a **real, production-ready system** that:
- Saves hours of manual work every week
- Applies consistent analytical criteria
- Provides actionable recommendations
- Scales across your entire customer base
- Can be enhanced and customized infinitely

### Your New Superpower

You can now build agentic systems for **any business operations domain**:
- Revenue operations
- Supply chain management
- Marketing analytics
- Financial planning
- Customer success
- Human resources
- And more...

**What's next?** Choose another use case from our **[50 Business Operations Use Cases Playbook](/docs/playbooks/50-business-operations-use-cases.md)** and build your second plugin!

---

## Share Your Success

We'd love to hear about your plugin!

- **GitHub**: Share your plugin repository
- **LinkedIn**: Post your experience with #AgenticSystems
- **Twitter**: Tweet @ClaudeCode with your results
- **Community**: Join our Slack and showcase your work

**Tag us and you might be featured in our success stories!**

---

*Built with the meta-agent-builder plugin for Claude Code*

**Ready to transform your business operations with intelligent automation?**

[Download Meta-Agent Builder](https://github.com/TamerineSky/Agentic-System-Builder) | [Read the Ultimate Guide](/docs/guides/ultimate-guide-business-operations-agents.md) | [View 50 Use Cases](/docs/playbooks/50-business-operations-use-cases.md)
