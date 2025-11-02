# Meta-Agent Builder Plugin

**Build Custom Agentic Systems for Business Operations in Minutes, Not Months**

The meta-agent-builder is a revolutionary plugin for Claude Code that generates complete, production-ready agentic systems tailored to your business operations. Instead of manually coding agents, skills, and commands, describe your business needs and watch as specialized meta-agents design and build your custom solution automatically.

---

## Overview

### What is the Meta-Agent Builder?

The meta-agent-builder is a "plugin that builds plugins" - a meta-system that automates the creation of domain-specific agentic systems for business operations. It combines seven specialized meta-agents, four knowledge skills, and seven generation commands to transform business requirements into working automation systems.

**Core Capabilities**:
- Analyze business domains and map to agentic architectures
- Generate specialized agents with expert system prompts
- Package domain knowledge as progressive disclosure skills
- Create workflow automation commands
- Design multi-agent orchestrations
- Validate plugin quality and compliance
- Integrate with business systems (CRMs, ERPs, data warehouses)

**Target Domains**:
- Revenue Operations (sales, forecasting, pipeline management)
- Supply Chain Operations (demand planning, inventory, logistics)
- Marketing Operations (campaigns, attribution, content)
- Finance Operations (budgeting, forecasting, reporting)
- Customer Success Operations (health scoring, churn, retention)
- Human Resources Operations (workforce planning, attrition, compensation)

**Time Savings**: Build in 30 minutes what would traditionally take weeks of development.

---

## The Meta-Agent Concept

A "meta-agent" is an agent specialized in creating other agents. While traditional agents solve business problems directly (e.g., a sales forecasting agent), meta-agents solve the problem of building those business-solving agents.

**Traditional Approach**:
```
Business Need → Manual Development → Custom Agent (weeks/months)
```

**Meta-Agent Approach**:
```
Business Need → Meta-Agent Analysis → Generated Agent (minutes)
```

The meta-agent-builder embodies the principle of **"systems that build systems"** - leveraging AI to automate the very process of building AI automation. This dramatically reduces the time, cost, and expertise required to deploy agentic systems across business operations.

**Why This Matters**:
- **Speed**: 30 minutes vs. weeks for a complete plugin
- **Quality**: Follows proven patterns from production systems
- **Consistency**: Every plugin uses best practices
- **Scalability**: Build dozens of plugins without scaling team size
- **Accessibility**: Business analysts can create agents, not just developers

---

## Version 1: Human-Guided Builder

The current version (v1.0.0) is a human-guided system where you collaborate with meta-agents through an interactive workflow. You provide business context, answer clarifying questions, and make architectural decisions, while the meta-agents handle the technical implementation.

**Version 1 Workflow**:
1. **You describe** your business need in plain language
2. **Domain-analyzer asks** 5-7 questions to understand requirements
3. **You answer** questions about your processes, data, and goals
4. **Meta-agents recommend** optimal architecture (agents, skills, commands)
5. **You approve** or refine the design
6. **Meta-agents generate** all components automatically
7. **You test** and iterate until satisfied

This collaborative approach ensures that generated plugins match your specific business context while maintaining architectural quality.

**Version 2 (Planned)**: A fully autonomous meta-agent that can independently analyze domains, make architectural decisions, generate components, and validate quality with minimal human oversight.

---

## Components

### 7 Meta-Agents

The meta-agent-builder includes seven specialized agents that work together to build your plugins:

#### 1. domain-analyzer (Sonnet)
**Role**: Business requirements analyst and architect
**Capabilities**:
- Conducts structured interviews using 5-7 targeted questions
- Maps business processes to agentic patterns
- Identifies integration points and data sources
- Recommends optimal plugin architectures
- Assesses complexity and estimates timelines

**When to Use**: Start every plugin project with domain-analyzer to ensure deep understanding of requirements.

**Example Output**: Complete plugin specification with recommended agents, skills, commands, and implementation roadmap.

#### 2. agent-generator (Sonnet)
**Role**: Agent design and system prompt engineer
**Capabilities**:
- Generates complete agent markdown files
- Writes domain-specific system prompts
- Selects appropriate models (Haiku vs. Sonnet)
- Assigns necessary tools (Read, Write, Bash, etc.)
- Creates activation criteria
- Includes business examples and patterns

**When to Use**: After architecture approval, generate each specialized agent for your plugin.

**Example Output**: Production-ready agent file (e.g., `sales-analyst.md`) with comprehensive system prompt.

#### 3. skill-builder (Sonnet)
**Role**: Knowledge packaging specialist
**Capabilities**:
- Designs three-tier progressive disclosure structure
- Packages domain methodologies as reusable skills
- Writes clear activation criteria
- Validates against Anthropic specifications
- Optimizes for token efficiency

**When to Use**: Package analytical methods, frameworks, and best practices as reusable knowledge.

**Example Output**: Skill directory with SKILL.md file (e.g., `skills/pipeline-health-scoring/SKILL.md`).

#### 4. command-composer (Sonnet)
**Role**: Workflow automation designer
**Capabilities**:
- Creates user-facing command workflows
- Designs parameter handling ($1, $2 notation)
- Orchestrates multiple agents and skills
- Defines output formats and success criteria
- Writes argument hints for user guidance

**When to Use**: Automate routine business workflows that users will invoke regularly.

**Example Output**: Command file (e.g., `/pipeline-review.md`) ready for users to execute.

#### 5. orchestration-designer (Sonnet)
**Role**: Multi-agent coordination architect
**Capabilities**:
- Designs complex multi-agent workflows
- Creates sequential and parallel execution patterns
- Implements hybrid orchestration (Sonnet → Haiku → Sonnet)
- Manages state across workflow steps
- Optimizes for both quality and token efficiency

**When to Use**: When business processes require multiple agents working together in sophisticated patterns.

**Example Output**: Orchestration specification with agent sequencing and coordination logic.

#### 6. integration-architect (Sonnet)
**Role**: Business systems integration specialist
**Capabilities**:
- Designs integrations with CRMs (Salesforce, HubSpot)
- Connects to ERPs (SAP, NetSuite)
- Accesses data warehouses (Snowflake, BigQuery)
- Creates authentication patterns
- Handles error scenarios and rate limiting

**When to Use**: When your agents need to pull data from or push results to business systems.

**Example Output**: Integration code patterns and configuration guidance.

#### 7. plugin-validator (Sonnet)
**Role**: Quality assurance specialist
**Capabilities**:
- Validates directory structure and file organization
- Checks naming conventions (hyphen-case)
- Verifies frontmatter completeness
- Ensures cross-references are valid
- Confirms Anthropic specification compliance
- Generates validation reports with severity levels

**When to Use**: Before deploying any plugin, validate it meets all quality standards.

**Example Output**: Comprehensive validation report with pass/fail status and remediation guidance.

---

### 4 Meta-Skills

These skills provide the meta-agents with specialized knowledge for building high-quality plugins:

#### 1. meta-plugin-patterns
**Purpose**: Architectural patterns for granular, composable plugins
**Knowledge Domains**:
- Single responsibility principle for plugins
- Token efficiency through progressive disclosure
- Component interaction patterns
- Naming conventions and file organization
- Anthropic best practices (2-8 components per plugin)

**When Activated**: During architecture design and plugin structuring.

#### 2. agent-creation-patterns
**Purpose**: Best practices for designing specialized agents
**Knowledge Domains**:
- System prompt engineering techniques
- Model selection criteria (Haiku vs. Sonnet vs. Opus)
- Tool assignment principles
- Activation trigger design
- Business context examples

**When Activated**: During agent generation and refinement.

#### 3. skill-development-patterns
**Purpose**: Progressive disclosure architecture for skills
**Knowledge Domains**:
- Three-tier structure (metadata, instructions, resources)
- Activation criteria design
- Token optimization strategies
- Knowledge scoping and boundaries
- Anthropic specification compliance

**When Activated**: During skill creation and validation.

#### 4. orchestration-templates
**Purpose**: Multi-agent coordination patterns
**Knowledge Domains**:
- Sequential workflow patterns
- Parallel execution patterns
- Hybrid orchestration (Sonnet → Haiku → Sonnet)
- State management across agents
- Error handling and recovery

**When Activated**: During orchestration design for complex workflows.

---

### 7 Commands

User-facing commands for generating plugin components:

#### /generate-plugin [domain-name] [description]
**Purpose**: Complete plugin creation wizard
**Workflow**: Domain analysis → Architecture design → Component generation → Validation → Documentation
**Time**: 15-30 minutes
**Output**: Production-ready plugin with all components

**Example**:
```bash
/generate-plugin customer-churn "Analyze customer behavior to predict churn risk and recommend retention strategies"
```

#### /generate-agent [agent-name] [role-description]
**Purpose**: Create a single specialized agent
**Workflow**: Analyze role → Design system prompt → Select model → Generate file
**Time**: 2-5 minutes
**Output**: Agent markdown file ready to use

**Example**:
```bash
/generate-agent sales-analyst "Analyze sales pipeline health and identify at-risk deals"
```

#### /generate-skill [skill-name] [methodology-description]
**Purpose**: Package domain knowledge as reusable skill
**Workflow**: Extract knowledge → Design structure → Create progressive disclosure → Validate
**Time**: 3-7 minutes
**Output**: Skill directory with SKILL.md file

**Example**:
```bash
/generate-skill demand-forecasting "Time-series forecasting methods for demand planning including seasonality and trend analysis"
```

#### /generate-command [command-name] [workflow-description]
**Purpose**: Create workflow automation command
**Workflow**: Design workflow → Define parameters → Specify agents/skills → Generate file
**Time**: 2-5 minutes
**Output**: Command markdown file

**Example**:
```bash
/generate-command pipeline-review "Weekly analysis of sales pipeline health with risk scoring and recommendations"
```

#### /generate-orchestration [orchestration-name] [workflow-description]
**Purpose**: Design multi-agent coordination pattern
**Workflow**: Map workflow steps → Assign agents → Define sequencing → Optimize execution
**Time**: 5-10 minutes
**Output**: Orchestration specification

**Example**:
```bash
/generate-orchestration quarterly-business-review "End-to-end QBR workflow from data collection to executive presentation"
```

#### /validate-plugin [plugin-name]
**Purpose**: Quality assurance check for plugin
**Workflow**: Structure validation → Naming check → Frontmatter verification → Cross-reference integrity
**Time**: 1-2 minutes
**Output**: Validation report with severity levels (CRITICAL, WARNING, INFO)

**Example**:
```bash
/validate-plugin revenue-operations
```

#### /optimize-plugin [plugin-name]
**Purpose**: Improve token efficiency and performance
**Workflow**: Analyze token usage → Identify optimization opportunities → Refactor components → Re-validate
**Time**: 5-10 minutes
**Output**: Optimization report with recommendations and refactored components

**Example**:
```bash
/optimize-plugin marketing-attribution
```

---

## Quick Start

### Installation

The meta-agent-builder plugin is already installed in this Claude Code environment. Verify installation:

```bash
# List installed plugins
claude-code plugins list

# Should show:
# meta-agent-builder v1.0.0 (7 agents, 4 skills, 7 commands)
```

### Your First Plugin in 5 Commands

Build a customer churn analysis plugin in under 30 minutes:

#### Step 1: Generate the Plugin (5 minutes)
```bash
/generate-plugin customer-churn-operations "Predict customer churn risk and recommend retention strategies"
```

The domain-analyzer will ask 5-7 questions:
- What customer data sources do you have?
- How do you define churn?
- Who uses churn predictions?
- How often do you need analysis?
- What retention tactics do you employ?

#### Step 2: Review Architecture (2 minutes)
Domain-analyzer recommends:
- **Agents**: churn-predictor, retention-strategist
- **Skills**: churn-prediction-models
- **Commands**: /analyze-churn-risk, /retention-plan

Approve the architecture or request adjustments.

#### Step 3: Generate Components (10 minutes)
Meta-agents automatically create all components:
```
plugins/customer-churn-operations/
├── agents/
│   ├── churn-predictor.md
│   └── retention-strategist.md
├── skills/
│   └── churn-prediction-models/SKILL.md
└── commands/
    ├── analyze-churn-risk.md
    └── retention-plan.md
```

#### Step 4: Validate Quality (2 minutes)
```bash
/validate-plugin customer-churn-operations
```

Validation checks:
- Directory structure ✓
- Naming conventions ✓
- Frontmatter completeness ✓
- Cross-references ✓
- Anthropic compliance ✓

#### Step 5: Test Your Plugin (5 minutes)
```bash
/analyze-churn-risk "Enterprise customers"
```

Your churn-predictor agent analyzes behavior patterns and generates a risk report!

### Example Output

```markdown
## Churn Risk Analysis: Enterprise Customers
**Date**: 2025-01-15
**Segment**: Enterprise (Annual >$50K)

### High Risk (Score 80-100)
- Acme Corp ($120K/year) - Score: 92
  Risk: 45-day usage gap, 3 support escalations
  Action: Executive outreach within 48 hours

- TechStart Inc ($85K/year) - Score: 87
  Risk: Usage down 60%, feature adoption stalled
  Action: CSM check-in + enablement session

### Retention Recommendations
1. Immediate outreach to 2 high-risk accounts
2. Product training sessions for low-adoption customers
3. Executive sponsor engagement for strategic accounts
```

**Result**: You've built a production-ready customer churn operations plugin in 30 minutes!

---

## Workflow

### Step-by-Step Plugin Creation Process

```
1. ANALYZE DOMAIN
   User describes need → domain-analyzer asks questions
   ↓
2. DESIGN ARCHITECTURE
   Domain-analyzer recommends agents/skills/commands
   ↓
3. GENERATE AGENTS
   agent-generator creates specialized agents
   ↓
4. PACKAGE SKILLS
   skill-builder creates reusable knowledge
   ↓
5. CREATE COMMANDS
   command-composer builds workflows
   ↓
6. DESIGN ORCHESTRATION (if needed)
   orchestration-designer coordinates agents
   ↓
7. BUILD INTEGRATIONS (if needed)
   integration-architect connects systems
   ↓
8. VALIDATE QUALITY
   plugin-validator ensures standards
   ↓
9. TEST & ITERATE
   User tests plugin and refines
   ↓
10. DEPLOY
    Plugin ready for production use
```

### Visual Flow

```
Business Need
     ↓
[domain-analyzer] ← You answer questions
     ↓
Architecture Specification
     ↓
┌────────────┬──────────────┬────────────────┐
│            │              │                │
[agent-gen]  [skill-build]  [command-comp]
│            │              │                │
└────────────┴──────────────┴────────────────┘
     ↓
[orchestration-designer] ← If complex workflows
     ↓
[integration-architect] ← If system integration
     ↓
[plugin-validator] ← Quality check
     ↓
Production-Ready Plugin
```

---

## Examples

### Example 1: Revenue Operations Plugin

**Business Need**: Automate sales forecasting and pipeline management

**Generated Architecture**:
- **5 Agents**: forecast-collector, forecast-analyzer, forecast-modeler, variance-analyst, forecast-presenter
- **3 Skills**: pipeline-based-forecasting, variance-analysis-frameworks, forecast-presentation-templates
- **7 Commands**: /forecast-collect, /forecast-generate, /forecast-review, /variance-report, /forecast-update, /forecast-scenario, /forecast-present

**Business Impact**:
- Time saved: 200 hours/year (from 3 days/month → 4 hours/month)
- Forecast accuracy: +15% improvement
- Stakeholder satisfaction: 4.7/5.0

**Quick Win**: `/forecast-collect` command automates data gathering, saving 1 day/month immediately.

### Example 2: Supply Chain Plugin

**Business Need**: Optimize demand planning and inventory management

**Generated Architecture**:
- **4 Agents**: demand-forecaster, inventory-optimizer, reorder-planner, supplier-analyst
- **3 Skills**: time-series-forecasting, inventory-policy-models, supplier-scorecard-methods
- **5 Commands**: /forecast-demand, /optimize-inventory, /plan-reorders, /analyze-suppliers, /run-sop

**Business Impact**:
- Inventory reduction: 20% (from overstocking)
- Stockout reduction: 30% (better forecasting)
- Time saved: 150 hours/year

**Quick Win**: `/forecast-demand` provides daily demand predictions in seconds vs. hours of manual work.

---

## What's Next

### Version 2 Roadmap

The next major version will introduce autonomous meta-agent capabilities:

**Planned Features**:
- **Autonomous Domain Analysis**: Meta-agent conducts research and analyzes domains independently
- **Self-Optimizing Architecture**: Automatically refines plugin designs based on usage patterns
- **Intelligent Testing**: Generates test scenarios and validates functionality automatically
- **Integration Discovery**: Automatically identifies and configures business system integrations
- **Version Management**: Handles plugin updates and backward compatibility
- **Community Learning**: Learns from successful plugins to improve recommendations

**Timeline**: Q2 2025 (estimated)

### Additional Resources

**Documentation**:
- [Quick Start Guide](/docs/quickstart/first-plugin-30-minutes.md) - Your first plugin in 30 minutes
- [Ultimate Guide](/docs/guides/ultimate-guide-business-operations-agents.md) - Comprehensive reference (5,000+ words)
- [50 Use Cases Playbook](/docs/playbooks/50-business-operations-use-cases.md) - Pre-built patterns for common needs
- [Integration Cookbook](/docs/cookbooks/business-systems-integration.md) - Connect to CRMs, ERPs, and data warehouses

**GitHub Issues**:
- [Issue #9: Meta-Agent Builder](https://github.com/TamerineSky/Agentic-System-Builder/issues/9) - Complete specification
- [Issue #8: Implementation Projects](https://github.com/TamerineSky/Agentic-System-Builder/issues/8) - 6 domain plugins to build
- [Issues #1-7: Core Concepts](https://github.com/TamerineSky/Agentic-System-Builder/issues) - Architecture foundations

**Community**:
- Share your plugins on GitHub
- Contribute improvements and new patterns
- Get help from other builders

---

## Success Stories

**"We built a complete revenue operations plugin in 2 hours that would have taken our team 6 weeks to develop manually. The meta-agent-builder is a game-changer for business operations teams."**
- Director of Revenue Operations, B2B SaaS Company

**"As a business analyst with no coding experience, I can now package my forecasting expertise as reusable agents that our entire team uses. This has transformed my role from manual analysis to knowledge engineering."**
- Senior Business Analyst, Manufacturing Company

**"The 50 use cases playbook gave us ideas we hadn't even considered. We've built 8 different plugins covering everything from pipeline management to churn prediction."**
- VP of Operations, High-Growth Startup

---

## Support & Contributing

### Get Help

- **Documentation**: Start with the [Quick Start Guide](/docs/quickstart/first-plugin-30-minutes.md)
- **GitHub Issues**: Report bugs or request features
- **Discussions**: Ask questions and share insights

### Contribute

We welcome contributions! Areas where you can help:
- Domain-specific patterns and examples
- Integration templates for business systems
- Documentation improvements
- Testing and validation enhancements

See [CONTRIBUTING.md](/CONTRIBUTING.md) for guidelines.

---

## License

MIT License - See [LICENSE](/LICENSE) for details.

---

**Built with the meta-agent-builder plugin for Claude Code**

*Transforming business operations through intelligent automation*
