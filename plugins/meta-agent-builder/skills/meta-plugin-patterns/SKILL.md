---
name: meta-plugin-patterns
description: Comprehensive patterns for plugin organization, naming, and structure from the Agentic System Builder framework. Use when generating plugins, validating plugin architecture, or establishing plugin design standards.
---

# Meta-Plugin Patterns

Comprehensive patterns for designing focused, composable business operations plugins following proven architecture principles from the wshobson/agents framework.

## When to Use This Skill

- Generating new business operations plugins
- Validating plugin structure and organization
- Establishing plugin design standards
- Reviewing plugin architecture before implementation
- Adapting software development patterns to business domains
- Ensuring compliance with Anthropic specifications
- Planning plugin componentization strategy
- Refactoring monolithic plugins into granular ones

## Core Concepts

### 1. Granular Plugin Architecture

**Single Responsibility Principle**
- Each plugin does one thing well (Unix philosophy)
- Clear, focused purposes describable in 5-10 words
- Average plugin size: 2-8 components (Anthropic recommendation)
- Zero bloated plugins - all focused and purposeful

**Benefits of Granularity:**
- Faster processing with smaller context windows
- More accurate, focused responses
- Install only what you need
- Easier updates and maintenance
- Clear boundaries between plugins
- Better composability

### 2. Three-Tier Component Structure

Every plugin contains up to three component types:

**agents/** - Specialized AI assistants with domain expertise
- Business role-based naming (sales-analyst, demand-forecaster)
- System prompts define capabilities and behavior
- Model selection based on task complexity (Haiku/Sonnet)
- Activation criteria with "Use PROACTIVELY when..." clauses

**skills/** - Modular knowledge packages with progressive disclosure
- Business methodology naming (pipeline-health-scoring, demand-forecasting-methods)
- Three-tier architecture: Metadata → Instructions → Resources
- Activation with "Use when..." clauses
- Token-efficient loading on demand

**commands/** - User-invoked reusable workflows
- Action-oriented naming (analyze-pipeline, update-forecast)
- Multi-step orchestrated processes
- Argument support for parameterization
- Business process automation

**Minimum Requirement:** At least ONE agent OR command (skills alone insufficient)

### 3. Plugin Structure Template

```
plugins/{domain}-operations/
├── .claude-plugin/
│   └── plugin.json              # REQUIRED: Plugin manifest
├── README.md                     # STRONGLY RECOMMENDED: Documentation
├── agents/                       # Optional: Domain experts
│   ├── {role}-{function}.md
│   └── ...
├── skills/                       # Optional: Knowledge packages
│   ├── {methodology}/
│   │   └── SKILL.md
│   └── ...
└── commands/                     # Optional: Workflows
    ├── {action}.md
    └── ...
```

## Plugin Manifest Format

### plugin.json Structure

```json
{
  "name": "revenue-operations",
  "source": "./plugins/revenue-operations",
  "description": "Comprehensive revenue operations plugin providing sales pipeline analysis, forecasting, deal management, and revenue intelligence capabilities for sales teams.",
  "version": "1.0.0",
  "author": {
    "name": "Your Organization",
    "url": "https://example.com"
  },
  "homepage": "https://github.com/org/revenue-operations",
  "repository": "https://github.com/org/revenue-operations",
  "license": "MIT",
  "keywords": [
    "revenue",
    "sales",
    "forecasting",
    "pipeline",
    "deals"
  ],
  "category": "Business Operations",
  "strict": false,
  "agents": [
    "./agents/sales-analyst",
    "./agents/pipeline-manager",
    "./agents/forecast-optimizer"
  ],
  "skills": [
    "./skills/forecasting-methods",
    "./skills/pipeline-health-scoring"
  ],
  "commands": [
    "./commands/pipeline-review",
    "./commands/forecast-update",
    "./commands/quota-planning"
  ]
}
```

### Required Fields

- **name**: Hyphen-case (e.g., `revenue-operations`, `supply-chain-operations`)
- **version**: Semantic versioning (e.g., `1.0.0`, `0.2.1`)
- **description**: 100-500 characters, clear and comprehensive

### Component Path Formats

- **Agents**: `./agents/{agent-name}` (no .md extension)
- **Skills**: `./skills/{skill-name}` (directory, not file)
- **Commands**: `./commands/{command-name}` (no .md extension)

## Naming Conventions

### Plugin Naming

**Pattern:** `{domain}-operations`

**Examples:**
- `revenue-operations` - Sales, forecasting, pipeline management
- `supply-chain-operations` - Inventory, logistics, demand planning
- `marketing-operations` - Campaigns, attribution, lead management
- `finance-operations` - Budgeting, forecasting, variance analysis
- `customer-success-operations` - Health scoring, churn prediction, expansion

**Requirements:**
- Hyphen-case only (no underscores, spaces, camelCase)
- Pattern: `^[a-z0-9]+(-[a-z0-9]+)*$`
- Clearly indicates business domain
- 3-50 characters in length

### Component Naming

**Agents:** Business role names
- `sales-analyst` (not sales_analyst or SalesAnalyst)
- `demand-forecaster` (not demandForecaster)
- `inventory-optimizer` (not inventory-manager-optimizer)
- `pipeline-manager` (not pipelineManager)
- `churn-predictor` (not churn_predictor)

**Skills:** Methodology names
- `forecasting-methods` (not forecastingMethods)
- `pipeline-health-scoring` (not pipeline_scoring)
- `cohort-retention-analysis` (not cohortAnalysis)
- `demand-planning-models` (not demandPlanning)
- `budget-variance-analysis` (not budgetAnalysis)

**Commands:** Action-oriented names
- `pipeline-review` (not reviewPipeline)
- `forecast-update` (not updateForecast)
- `analyze-churn` (not churn-analysis)
- `quota-planning` (not planQuota)
- `inventory-rebalance` (not rebalanceInventory)

## Complete Plugin Examples

### Example 1: Revenue Operations Plugin

**Purpose:** Sales pipeline analysis, forecasting, and deal management for sales teams

**Structure:**
```
plugins/revenue-operations/
├── .claude-plugin/
│   └── plugin.json
├── README.md
├── agents/
│   ├── sales-analyst.md          # Pipeline analysis and reporting
│   ├── forecast-optimizer.md      # Revenue forecasting
│   └── pipeline-manager.md        # Deal and pipeline management
├── skills/
│   ├── forecasting-methods/
│   │   └── SKILL.md               # Statistical forecasting techniques
│   └── pipeline-health-scoring/
│       └── SKILL.md               # Pipeline quality assessment
└── commands/
    ├── pipeline-review.md         # Monthly/quarterly pipeline review
    ├── forecast-update.md         # Update revenue forecasts
    └── deal-review.md             # Deep dive into specific deals
```

**Components:** 3 agents + 2 skills + 3 commands = 8 components

**Business Focus:**
- Metrics: ARR, MRR, pipeline coverage, win rate, cycle time
- Processes: QBRs, forecast calls, pipeline reviews
- Integrations: Salesforce, HubSpot, data warehouses
- Outcomes: Improved forecast accuracy, faster deal velocity

### Example 2: Supply Chain Operations Plugin

**Purpose:** Inventory optimization, demand planning, and logistics management

**Structure:**
```
plugins/supply-chain-operations/
├── .claude-plugin/
│   └── plugin.json
├── README.md
├── agents/
│   ├── demand-forecaster.md       # Demand prediction and planning
│   ├── inventory-optimizer.md     # Inventory level optimization
│   └── logistics-coordinator.md   # Logistics and fulfillment
├── skills/
│   ├── demand-forecasting-models/
│   │   └── SKILL.md               # Demand forecasting methodologies
│   ├── inventory-optimization/
│   │   └── SKILL.md               # Inventory optimization techniques
│   └── supply-planning-methods/
│       └── SKILL.md               # S&OP and supply planning
└── commands/
    ├── demand-plan.md             # Monthly demand planning cycle
    ├── inventory-rebalance.md     # Inventory rebalancing workflow
    └── sop-review.md              # S&OP monthly review process
```

**Components:** 3 agents + 3 skills + 3 commands = 9 components

**Business Focus:**
- Metrics: Inventory turnover, fill rate, OTIF, COGS
- Processes: S&OP, demand planning, inventory reviews
- Integrations: ERP (SAP, Oracle), WMS, demand planning tools
- Outcomes: Reduced stockouts, optimized inventory levels

### Example 3: Marketing Operations Plugin

**Purpose:** Campaign performance, lead generation, and marketing attribution

**Structure:**
```
plugins/marketing-operations/
├── .claude-plugin/
│   └── plugin.json
├── README.md
├── agents/
│   ├── campaign-analyst.md        # Campaign performance analysis
│   ├── attribution-specialist.md   # Marketing attribution modeling
│   └── content-strategist.md      # Content planning and strategy
├── skills/
│   ├── attribution-modeling/
│   │   └── SKILL.md               # Multi-touch attribution models
│   └── campaign-optimization/
│       └── SKILL.md               # Campaign optimization techniques
└── commands/
    ├── campaign-review.md         # Campaign performance review
    ├── attribution-analysis.md    # Attribution modeling workflow
    └── content-plan.md            # Quarterly content planning
```

**Components:** 3 agents + 2 skills + 3 commands = 8 components

**Business Focus:**
- Metrics: CAC, MQL/SQL conversion, campaign ROI, engagement
- Processes: Campaign reviews, attribution analysis, content planning
- Integrations: Marketing automation (Marketo, HubSpot), analytics
- Outcomes: Improved campaign ROI, better lead quality

### Example 4: Finance Operations Plugin

**Purpose:** Budgeting, forecasting, and financial variance analysis

**Structure:**
```
plugins/finance-operations/
├── .claude-plugin/
│   └── plugin.json
├── README.md
├── agents/
│   ├── budget-analyst.md          # Budget planning and analysis
│   └── variance-analyzer.md       # Variance analysis and reporting
├── skills/
│   ├── budget-planning-methods/
│   │   └── SKILL.md               # Budget planning methodologies
│   └── variance-analysis/
│       └── SKILL.md               # Variance analysis techniques
└── commands/
    ├── budget-plan.md             # Annual budget planning
    ├── variance-review.md         # Monthly variance review
    └── forecast-roll.md           # Rolling forecast updates
```

**Components:** 2 agents + 2 skills + 3 commands = 7 components

**Business Focus:**
- Metrics: Budget variance, gross margin, EBITDA, cash flow
- Processes: Budget planning, monthly close, variance reviews
- Integrations: ERP, BI platforms, financial systems
- Outcomes: Better budget accuracy, faster variance analysis

### Example 5: Customer Success Operations Plugin

**Purpose:** Health scoring, churn prediction, and expansion opportunity identification

**Structure:**
```
plugins/customer-success-operations/
├── .claude-plugin/
│   └── plugin.json
├── README.md
├── agents/
│   ├── health-scorer.md           # Customer health scoring
│   ├── churn-predictor.md         # Churn risk prediction
│   └── expansion-specialist.md    # Expansion opportunity identification
├── skills/
│   ├── health-scoring-models/
│   │   └── SKILL.md               # Health scoring methodologies
│   └── churn-prediction-methods/
│       └── SKILL.md               # Churn prediction techniques
└── commands/
    ├── health-review.md           # Quarterly health review
    ├── churn-analysis.md          # Monthly churn analysis
    └── expansion-planning.md      # Expansion opportunity planning
```

**Components:** 3 agents + 2 skills + 3 commands = 8 components

**Business Focus:**
- Metrics: NRR, GRR, churn rate, health score, CSAT
- Processes: QBRs, health reviews, expansion planning
- Integrations: Customer success platforms (Gainsight, Totango)
- Outcomes: Reduced churn, increased expansion revenue

## Best Practices

### 1. Token Optimization

**Keep Plugins Focused:**
- Average 2-8 components per plugin
- Single domain responsibility
- No "kitchen sink" plugins
- Clear boundaries

**Progressive Disclosure:**
- Skills load knowledge on demand
- Three-tier architecture reduces base context
- Metadata always loaded, content loaded when needed

**Avoid Duplication:**
- Don't replicate patterns across plugins
- Create skills for shared knowledge
- Reference other plugins when appropriate

### 2. Composability Over Bundling

**Design for Composition:**
- Plugins work independently
- Workflows can combine multiple plugins
- Clear interfaces between plugins
- No forced feature bundling

**Example Multi-Plugin Workflow:**
```
Monthly Business Review:
1. revenue-operations:pipeline-review
2. finance-operations:variance-review
3. marketing-operations:campaign-review
4. customer-success-operations:health-review
```

### 3. Business Context Adaptation

**Translate Software Patterns:**
- Software: "API design" → Business: "Pipeline design"
- Software: "Database optimization" → Business: "Forecast accuracy"
- Software: "Code review" → Business: "Deal review"
- Software: "CI/CD pipeline" → Business: "Monthly close process"

**Use Domain Language:**
- Sales: pipeline, deals, quota, ARR, MRR, conversion
- Supply Chain: inventory, logistics, demand, SKU, lead time
- Marketing: campaigns, leads, attribution, MQL, SQL
- Finance: budget, forecast, variance, EBITDA, cash flow
- Customer Success: health score, churn, NRR, expansion

**Avoid Technical Jargon:**
- Don't say: API, database, deployment, CI/CD (unless IT/DevOps plugin)
- Say instead: system, data, process, workflow
- Exception: Technical operations plugins (IT Operations, DevOps)

### 4. Validation Compliance

**Follow validation-rules.md:**
- Plugin manifest includes all required fields
- All component paths exist and are correctly formatted
- Names use hyphen-case consistently
- Descriptions are clear and comprehensive (100-500 chars)
- Version follows semantic versioning
- Component count is 2-8 (optimal range)

**Anthropic Spec Compliance:**
- Skills follow Agent Skills Specification v1.0
- Frontmatter properly formatted (YAML for skills, Markdown for agents/commands)
- Descriptions include activation criteria
- File structure matches specification requirements

### 5. Documentation Quality

**README.md Contents:**
- Plugin purpose and value proposition
- Component list with brief descriptions
- Business domain context
- Integration points (CRMs, ERPs, etc.)
- Usage examples
- Prerequisites and dependencies

**Component Documentation:**
- Agents: Clear capabilities and response approach
- Skills: Detailed methodology with examples
- Commands: Workflow steps and expected outputs

## Progressive Disclosure for Skills

Skills use three-tier architecture for token efficiency:

### Tier 1: Metadata (Always Loaded)

```yaml
---
name: pipeline-health-scoring
description: Comprehensive methodology for assessing sales pipeline quality, coverage, and risk. Use when analyzing pipeline health, identifying deal risks, or optimizing sales processes.
---
```

**Requirements:**
- Name in hyphen-case
- Description < 1024 characters (CRITICAL LIMIT)
- "Use when..." activation clause
- Complete, non-truncated description

### Tier 2: Instructions (Loaded When Activated)

```markdown
# Pipeline Health Scoring

## When to Use This Skill
- Analyzing overall pipeline health
- Identifying high-risk deals
- [5-15 scenarios]

## Core Methodology
### 1. Coverage Ratio Analysis
[Detailed explanation]

### 2. Stage Distribution Health
[Detailed explanation]

[3-8 methodology sections]
```

**Contents:**
- When to use (expanded scenarios)
- Core concepts or methodology
- Patterns and techniques
- Recommended: 100-500 lines

### Tier 3: Resources (Loaded On Demand)

```markdown
## Resources
- references/pipeline-benchmarks.md
- assets/scoring-templates.xlsx
- examples/pipeline-health-report.md
```

**Contents:**
- Detailed examples
- Code samples or templates
- Reference materials
- Extended documentation

## Common Pitfalls to Avoid

### 1. Monolithic Plugins

**Problem:** One plugin tries to do everything
**Impact:** Token inefficiency, slow performance, hard to maintain

**Example (WRONG):**
```
business-operations/  # Too broad!
├── agents/
│   ├── sales-analyst.md
│   ├── inventory-manager.md
│   ├── campaign-analyst.md
│   ├── budget-analyst.md
│   └── [15 more agents]
└── [many more components]
```

**Solution:** Create focused domain plugins
```
revenue-operations/
supply-chain-operations/
marketing-operations/
finance-operations/
```

### 2. Inconsistent Naming

**Problem:** Mixing naming conventions
**Impact:** Unprofessional, confusing, harder to discover

**Examples (WRONG):**
- `Sales_Operations` (underscore)
- `salesOperations` (camelCase)
- `sales operations` (space)
- `revops` (unclear abbreviation)

**Solution:** Always use hyphen-case
- `revenue-operations`
- `sales-analyst`
- `pipeline-review`

### 3. Missing Business Context

**Problem:** Using software terminology in business plugins
**Impact:** Confusing for business users, inappropriate language

**Examples (WRONG in business context):**
- "Database optimization" → Say "Forecast accuracy improvement"
- "API design" → Say "Pipeline design"
- "Code review" → Say "Deal review"
- "Deployment pipeline" → Say "Monthly close process"

**Solution:** Use domain-appropriate business terminology

### 4. Skills Alone Without Entry Points

**Problem:** Plugin contains only skills, no agents or commands
**Impact:** No way to invoke the plugin directly

**Example (WRONG):**
```
revenue-operations/
└── skills/
    ├── forecasting-methods/
    └── pipeline-analysis/
```

**Solution:** Add at least one agent OR command
```
revenue-operations/
├── agents/
│   └── sales-analyst.md      # Entry point
└── skills/
    ├── forecasting-methods/
    └── pipeline-analysis/
```

### 5. Component Path Errors

**Problem:** Incorrect path formats in plugin.json
**Impact:** Components won't load, plugin fails

**Examples (WRONG):**
```json
{
  "agents": [
    "agents/sales-analyst.md",        // Should not include .md
    "./agents/Sales_Analyst"          // Should use hyphen-case
  ],
  "skills": [
    "./skills/forecasting/SKILL.md"   // Should be directory only
  ]
}
```

**Solution:** Use correct path formats
```json
{
  "agents": [
    "./agents/sales-analyst"
  ],
  "skills": [
    "./skills/forecasting-methods"
  ]
}
```

## References

- **Source Framework:** wshobson/agents repository (63 plugins, 85 agents, 47 skills)
- **Architecture Document:** /agents/docs/architecture.md
- **Agent Reference:** /agents/docs/agents.md
- **Skills Reference:** /agents/docs/agent-skills.md
- **Validation Rules:** validation-rules.md in this plugin
- **Anthropic Specification:** Agent Skills Specification v1.0

## Quick Validation Checklist

- [ ] Plugin name in hyphen-case
- [ ] plugin.json includes all required fields
- [ ] Version uses semantic versioning (e.g., 1.0.0)
- [ ] Description 100-500 characters
- [ ] Component paths correctly formatted
- [ ] 2-8 components total (optimal range)
- [ ] At least ONE agent OR command
- [ ] All referenced files exist
- [ ] Names use hyphen-case consistently
- [ ] Business terminology appropriate for domain
- [ ] README.md provides clear documentation
- [ ] Skills follow progressive disclosure
