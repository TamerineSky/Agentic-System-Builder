# Agentic System Builder

> A comprehensive meta-framework for building business operations agentic systems using Claude Code, adapted from software development patterns to general-purpose business operations including RevOps, SupplyOps, Marketing Operations, and more.

## 🎯 Purpose

This repository provides a systematic approach to building specialized AI agent systems for business operations using Claude Code's architecture. While most Claude Code examples focus on software development, this framework adapts those patterns for business operations teams who need:

- **Revenue Operations (RevOps)** - Sales pipeline optimization, forecasting, customer analytics
- **Supply Chain Operations (SupplyOps)** - Inventory management, demand forecasting, logistics optimization
- **Marketing Operations (MarketingOps)** - Campaign management, content workflows, attribution modeling
- **Finance Operations (FinanceOps)** - Budget analysis, financial reporting, expense optimization
- **Human Resources Operations (HROps)** - Talent analytics, performance management, workflow automation
- **Customer Success Operations (CS Ops)** - Health scoring, retention analysis, escalation workflows

## 🏗️ Framework Overview

### The Three-Layer Architecture

This framework is built on three fundamental layers that work together:

```
┌─────────────────────────────────────────────────────────────┐
│  LAYER 3: Workflow Orchestration                             │
│  Multi-agent coordination for complex business processes     │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│  LAYER 2: Specialized Agents & Skills                        │
│  Domain experts with modular knowledge packages              │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│  LAYER 1: Plugin Architecture & Commands                     │
│  Organizational structure and reusable tools                 │
└─────────────────────────────────────────────────────────────┘
```

### Key Components

1. **Plugins** - Modular packages that organize agents, skills, and commands by business domain
2. **Agents** - Specialized AI assistants with domain expertise (e.g., sales-analyst, supply-chain-optimizer)
3. **Skills** - Reusable knowledge packages that agents can invoke automatically
4. **Commands** - User-invoked workflows and templates for common operations
5. **Orchestrators** - Multi-agent workflows that coordinate complex business processes

## 📚 Core Concepts

### Plugin Architecture

**What**: Self-contained packages that bundle related agents, skills, and commands for a specific business domain.

**Why**: Enables modular installation, minimal token usage, and clear organizational boundaries.

**Structure**:
```
revenue-operations-plugin/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── agents/
│   ├── sales-analyst.md         # Sales pipeline expert
│   ├── revenue-forecaster.md    # Revenue prediction specialist
│   └── deal-optimizer.md        # Deal scoring and optimization
├── skills/
│   ├── crm-integration/         # Salesforce/HubSpot patterns
│   ├── pipeline-analysis/       # Pipeline health metrics
│   └── revenue-modeling/        # Financial forecasting
└── commands/
    ├── pipeline-review.md       # Weekly pipeline analysis
    ├── forecast-update.md       # Revenue forecast generation
    └── deal-risk-analysis.md    # Deal health assessment
```

**Key Principles**:
- Single Responsibility: One domain per plugin
- Composability: Mix and match plugins for complex needs
- Token Efficiency: Load only what you need
- Team Sharing: Version control plugins for consistency

### Specialized Agents

**What**: AI assistants with focused expertise in specific business domains, each with custom system prompts and tool access.

**Why**: Provides deep domain knowledge, maintains context isolation, and enables reusable expertise across projects.

**Anatomy**:
```markdown
---
name: sales-analyst
description: Expert in sales pipeline analysis, deal scoring, and revenue forecasting. Use PROACTIVELY for sales analytics or pipeline reviews.
model: sonnet
tools: Read, Bash, Grep
---

You are an expert sales analyst specializing in...

## Capabilities
- Pipeline health assessment and bottleneck identification
- Deal scoring based on historical win/loss patterns
- Revenue forecasting with confidence intervals
...

## Response Approach
1. Assess data quality and completeness
2. Perform statistical analysis
3. Generate actionable insights
4. Recommend specific next actions
...
```

**Agent Types by Business Function**:

- **Analytics Agents**: Data analysis, reporting, trend identification
- **Operations Agents**: Process optimization, workflow automation, resource allocation
- **Strategy Agents**: Planning, forecasting, decision support
- **Compliance Agents**: Policy enforcement, risk assessment, audit support

**Model Selection Guide**:

| Use Case | Model | Why |
|----------|-------|-----|
| Strategic planning, complex analysis | Sonnet/Opus | Deep reasoning required |
| Data processing, report generation | Haiku | Deterministic, fast execution |
| Multi-step workflows | Hybrid | Planning (Sonnet) → Execution (Haiku) |

### Agent Skills

**What**: Modular knowledge packages that agents automatically invoke based on context, using progressive disclosure to manage token efficiency.

**Why**: Provides specialized expertise without always loading everything, enabling Claude to discover and use capabilities contextually.

**Structure**:
```
skills/revenue-modeling/
└── SKILL.md
```

**SKILL.md Format**:
```yaml
---
name: revenue-modeling
description: Build revenue forecast models with cohort analysis, seasonality adjustment, and scenario planning. Use when forecasting revenue, analyzing growth trends, or creating financial projections.
---

# Revenue Modeling

Comprehensive guidance for revenue forecasting and financial modeling.

## When to Use This Skill
- Creating quarterly or annual revenue forecasts
- Analyzing revenue trends and growth patterns
- Building scenario-based financial projections
...

## Core Methodologies
### 1. Cohort-Based Forecasting
[Detailed methodology]

### 2. Time Series Analysis
[Detailed methodology]
...

## Examples
[Real-world examples with code snippets]
```

**Progressive Disclosure Architecture**:
1. **Metadata** (Frontmatter): Always loaded - name + activation criteria
2. **Instructions**: Loaded when skill is activated by Claude
3. **Resources**: Loaded on-demand when needed

**Activation Pattern**:
```
User: "Create Q4 revenue forecast for SaaS business"
  ↓
Claude recognizes keywords: "revenue forecast"
  ↓
Activates: revenue-modeling skill
  ↓
Uses skill instructions to generate forecast
```

### Slash Commands

**What**: User-invoked reusable prompts and workflows with parameter support, stored as markdown files.

**Why**: Codifies best practices, accelerates routine tasks, ensures consistency across team.

**Structure**:
```markdown
---
description: Analyze sales pipeline health and identify bottlenecks
argument-hint: [time-period] [team-name]
model: sonnet
---

Perform comprehensive pipeline analysis for $1 covering $2 team:

1. Pipeline Stage Distribution
   - Calculate deal count and value at each stage
   - Compare to historical benchmarks
   - Identify unusual concentrations

2. Velocity Analysis
   - Measure average days in each stage
   - Calculate stage-to-stage conversion rates
   - Identify bottlenecks (>2 standard deviations from mean)

3. Win/Loss Analysis
   - Analyze closed deals in the period
   - Identify patterns in won vs lost deals
   - Generate recommendations

4. Forecast Accuracy
   - Compare forecasted vs actual closed revenue
   - Calculate forecast accuracy percentage
   - Adjust forecast model if needed

Provide actionable recommendations with specific next steps for sales leadership.
```

**Usage**:
```bash
/pipeline-review "Q3 2024" "Enterprise Sales"
```

**Command Types**:

- **Analysis Commands**: Data analysis and reporting workflows
- **Planning Commands**: Strategic planning and forecasting
- **Automation Commands**: Routine task automation
- **Review Commands**: Periodic business reviews

### Workflow Orchestration

**What**: Multi-agent coordination systems that break complex business processes into phases handled by specialized agents.

**Why**: Manages complexity, ensures quality, maintains context across long-running processes.

**Pattern**:
```markdown
# Quarterly Business Review Orchestrator

## Phase 1: Data Collection & Validation
1. **Data Gathering Agent**
   - Prompt: "Collect Q3 data from [sources]..."
   - Output: Validated dataset

2. **Data Quality Agent**
   - Prompt: "Validate data completeness using [dataset from step 1]..."
   - Output: Quality report

## Phase 2: Analysis & Insights
3. **Revenue Analyst Agent**
   - Prompt: "Analyze revenue trends using [validated data]..."
   - Output: Revenue analysis

4. **Customer Analytics Agent**
   - Prompt: "Analyze customer metrics using [validated data]..."
   - Output: Customer insights

## Phase 3: Strategic Recommendations
5. **Strategy Agent**
   - Prompt: "Synthesize findings from [steps 3-4] and generate recommendations..."
   - Output: Strategic recommendations

## Phase 4: Presentation & Documentation
6. **Presentation Agent**
   - Prompt: "Create executive presentation from [all previous outputs]..."
   - Output: Final QBR deck
```

**Orchestration Patterns**:

| Pattern | Use Case | Example |
|---------|----------|---------|
| Sequential | Each phase depends on previous | Month-end close process |
| Parallel | Independent analyses combined | Multi-channel marketing analysis |
| Iterative | Refinement through feedback | Budget planning with revisions |
| Conditional | Different paths based on results | Deal escalation workflows |

## 🚀 Getting Started

### 1. Understand the Foundation

Start by reading these core concept documents:

- [Foundation Concepts](docs/01-foundation-concepts.md) - Core architecture and design principles
- [Plugin Architecture](docs/02-plugin-architecture.md) - How to structure and organize plugins
- [Specialized Agents](docs/03-specialized-agents.md) - Building domain-expert agents

### 2. Explore Business Domain Examples

Review example implementations for your domain:

- [Revenue Operations Example](examples/revenue-operations/) - Sales, forecasting, pipeline
- [Supply Chain Operations Example](examples/supply-operations/) - Inventory, logistics, demand
- [Marketing Operations Example](examples/marketing-operations/) - Campaigns, content, attribution

### 3. Build Your First Plugin

Follow the step-by-step guide:
- [Building Your First Business Operations Plugin](docs/tutorials/first-plugin.md)

### 4. Deep Dive Into Advanced Topics

- [Agent Skills Development](docs/04-agent-skills.md) - Progressive disclosure and knowledge packaging
- [Slash Commands Design](docs/05-slash-commands.md) - Creating reusable workflows
- [Workflow Orchestration](docs/06-workflow-orchestration.md) - Multi-agent coordination
- [Business Context Engineering](docs/07-context-engineering.md) - Optimizing prompts for operations

## 📖 Documentation Structure

### Core Guides
1. [Foundation Concepts](docs/01-foundation-concepts.md) - Architecture & principles
2. [Plugin Architecture](docs/02-plugin-architecture.md) - Organizational patterns
3. [Specialized Agents](docs/03-specialized-agents.md) - Building expert agents
4. [Agent Skills](docs/04-agent-skills.md) - Modular knowledge packages
5. [Slash Commands](docs/05-slash-commands.md) - Reusable workflows
6. [Workflow Orchestration](docs/06-workflow-orchestration.md) - Multi-agent coordination
7. [Context Engineering](docs/07-context-engineering.md) - Prompt optimization

### Business Domain Guides
- [Revenue Operations Guide](docs/domains/revenue-operations.md)
- [Supply Chain Operations Guide](docs/domains/supply-operations.md)
- [Marketing Operations Guide](docs/domains/marketing-operations.md)
- [Finance Operations Guide](docs/domains/finance-operations.md)
- [Customer Success Operations Guide](docs/domains/customer-success-operations.md)

### Reference
- [Agent Catalog](docs/reference/agent-catalog.md) - All business operations agents
- [Skills Catalog](docs/reference/skills-catalog.md) - All available skills
- [Command Catalog](docs/reference/command-catalog.md) - All workflow commands
- [Orchestration Patterns](docs/reference/orchestration-patterns.md) - Common workflows

## 🎓 Learning Path

### For Business Analysts
1. Start with Foundation Concepts
2. Explore Specialized Agents for your domain
3. Create your first agent using domain knowledge
4. Build slash commands for routine analyses

### For Operations Managers
1. Review Workflow Orchestration patterns
2. Map your current processes to orchestration templates
3. Identify automation opportunities
4. Create plugin for your team's operations

### For Data Teams
1. Study Agent Skills architecture
2. Package analytical methodologies as skills
3. Build agents that leverage those skills
4. Create reusable analysis commands

## 🏢 Use Cases by Industry

### SaaS & Technology
- Revenue forecasting and ARR analysis
- Customer health scoring and churn prediction
- Product usage analytics and feature adoption
- Go-to-market optimization

### Retail & E-commerce
- Inventory optimization and demand forecasting
- Pricing strategy and promotion effectiveness
- Supply chain visibility and logistics
- Customer lifetime value modeling

### Professional Services
- Resource allocation and utilization
- Project profitability analysis
- Client pipeline management
- Capacity planning

### Manufacturing
- Production planning and scheduling
- Quality control analytics
- Supply chain optimization
- Equipment maintenance prediction

## 🔗 Related Resources

### Official Documentation
- [Claude Code Documentation](https://docs.claude.com/en/docs/claude-code/overview)
- [Plugins Guide](https://docs.claude.com/en/docs/claude-code/plugins)
- [Subagents Guide](https://docs.claude.com/en/docs/claude-code/sub-agents)
- [Agent Skills Guide](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)
- [Slash Commands Reference](https://docs.claude.com/en/docs/claude-code/slash-commands)

### Source Repository
- [wshobson/agents](https://github.com/wshobson/agents) - Original software development-focused repo that inspired this framework

## 📋 Roadmap

### Phase 1: Foundation (Current)
- ✅ Core documentation and meta-framework
- 🚧 Business domain examples
- 🚧 GitHub issues for each concept area

### Phase 2: Domain Examples
- Revenue Operations plugin suite
- Supply Chain Operations plugin suite
- Marketing Operations plugin suite
- Customer Success Operations plugin suite

### Phase 3: Advanced Patterns
- Cross-domain orchestration workflows
- Business intelligence integration patterns
- Real-time operations monitoring
- Automated reporting systems

### Phase 4: Community & Templates
- Template library for common operations
- Community-contributed plugins
- Best practices from production usage
- Integration with business tools (Salesforce, NetSuite, etc.)

## 🤝 Contributing

This is a living framework designed to evolve with community input. We welcome:

- Business domain examples and use cases
- Agent and skill implementations
- Orchestration workflow patterns
- Documentation improvements
- Bug reports and feature requests

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

This framework is built upon patterns and architectures from:
- [wshobson/agents](https://github.com/wshobson/agents) by Seth Hobson
- Anthropic's Claude Code documentation and best practices
- Community contributions and feedback

## 📞 Support & Questions

- **Issues**: Use GitHub Issues for bugs and feature requests
- **Discussions**: Use GitHub Discussions for questions and community support
- **Documentation**: Check the [docs/](docs/) directory for comprehensive guides

---

**Note**: This framework adapts software development patterns from Claude Code to business operations contexts. While the original inspiration focuses on code development, this framework reimagines those patterns for business operations teams including RevOps, SupplyOps, MarketingOps, FinanceOps, and more.
