# Agentic System Builder Templates

This directory contains reusable templates for generating new agentic system components (agents, skills, commands, and plugin manifests). These templates were extracted from analyzing the wshobson/agents repository to capture common patterns and structures.

## Template Files

- **agent-template.md** - Template for creating specialized agents
- **skill-template.md** - Template for creating reusable skills
- **command-template.md** - Template for creating workflow commands
- **plugin-manifest-template.json** - Template for plugin configuration

## Usage

### 1. Agent Template (`agent-template.md`)

Creates a specialized agent with defined capabilities and response approaches.

**Key Placeholders:**
- `{{AGENT_NAME}}` - Hyphen-case identifier (e.g., `business-analyst`, `sales-automator`)
- `{{DESCRIPTION}}` - Brief description (should include activation criteria)
- `{{MODEL}}` - `sonnet`, `haiku`, or `opus`
- `{{USE_WHEN_CLAUSE}}` - When to proactively activate (e.g., "for business intelligence or strategic analysis")
- `{{AGENT_ROLE}}` - Full title (e.g., "an expert business analyst")
- `{{SPECIALIZATION}}` - Primary expertise area
- `{{PURPOSE_STATEMENT}}` - Detailed purpose paragraph
- `{{CAPABILITY_CATEGORY_N}}` - Category headers (3-5 categories typical)
- `{{CAPABILITY_N_ITEMS}}` - Bulleted capability lists
- `{{BEHAVIORAL_TRAITS}}` - Bulleted list of behavioral characteristics
- `{{KNOWLEDGE_BASE_ITEMS}}` - Bulleted list of knowledge areas
- `{{STEP_N_TITLE}}` - Response approach step titles
- `{{STEP_N_DESCRIPTION}}` - Step descriptions
- `{{EXAMPLE_INTERACTIONS}}` - Bulleted list of example use cases

**Example:**
```markdown
---
name: inventory-manager
description: Manage inventory tracking, stock levels, and reorder automation. Use PROACTIVELY for inventory management or supply chain operations.
model: haiku
---

You are an inventory management specialist specializing in stock optimization and supply chain automation.

## Purpose
Expert in managing inventory systems with real-time tracking, automated reordering...
```

### 2. Skill Template (`skill-template.md`)

Creates a reusable skill with progressive disclosure structure.

**Key Placeholders:**
- `{{SKILL_NAME}}` - Hyphen-case identifier (e.g., `inventory-optimization`)
- `{{DESCRIPTION}}` - Brief description with "Use when" clause (< 1024 chars)
- `{{WHEN_TO_USE_CLAUSE}}` - Activation scenarios
- `{{SKILL_TITLE}}` - Display title (e.g., "Inventory Optimization Patterns")
- `{{SKILL_OVERVIEW}}` - 1-2 paragraph overview
- `{{WHEN_TO_USE_LIST}}` - Bulleted list of use cases
- `{{CONCEPT_N_TITLE}}` - Core concept titles (2-4 concepts)
- `{{CONCEPT_N_DESCRIPTION}}` - Concept explanations
- `{{QUICK_START_CODE_EXAMPLE}}` - Simple code example
- `{{MAIN_SECTION_TITLE}}` - Main section header
- `{{PATTERN_N_TITLE}}` - Pattern names
- `{{PATTERN_N_DESCRIPTION}}` - Pattern explanations
- `{{PATTERN_N_CODE}}` - Code examples
- `{{CODE_LANGUAGE}}` - Language for syntax highlighting
- `{{ADVANCED_SECTION_TITLE}}` - Advanced section header
- `{{ADVANCED_CONTENT}}` - Advanced techniques
- `{{RESOURCES_LIST}}` - Reference materials
- `{{BEST_PRACTICES_LIST}}` - Best practices
- `{{COMMON_PITFALLS_LIST}}` - Things to avoid

**Example:**
```markdown
---
name: inventory-optimization
description: Optimize inventory levels with demand forecasting and reorder point calculations. Use when managing stock, implementing reorder automation, or reducing carrying costs.
---

# Inventory Optimization Patterns

Master inventory management with advanced forecasting, EOQ calculations, and automated reordering...
```

### 3. Command Template (`command-template.md`)

Creates a workflow command that orchestrates tasks.

**Key Placeholders:**
- `{{COMMAND_DESCRIPTION}}` - What the command does
- `{{ARGUMENT_HINT}}` - Parameter hints (e.g., `[product-category] [timeframe]`)
- `{{VERSION}}` - Semantic version
- `{{TAGS}}` - Comma-separated tags
- `{{TOOL_ACCESS}}` - Required tools (e.g., `Read, Write, Bash, Grep`)
- `{{MODEL}}` - `sonnet` or `haiku`
- `{{COMMAND_TITLE}}` - Display title
- `{{COMMAND_OVERVIEW}}` - Overview paragraph
- `{{CONTEXT_DESCRIPTION}}` - Context explanation
- `{{PHASE_N_TITLE}}` - Phase headers
- `{{PHASE_N_DESCRIPTION}}` - Phase descriptions
- `{{PHASE_N_CONTENT}}` - Phase implementation details
- `{{OUTPUT_FORMAT_ITEMS}}` - Expected outputs
- `{{SUCCESS_CRITERIA_ITEMS}}` - Success metrics
- `{{RELATED_PLUGINS}}` - Related plugin references

**Note:** Commands use `$ARGUMENTS` as the standard placeholder for user input.

**Example:**
```markdown
---
description: Generate inventory reorder recommendations based on demand forecast and current stock levels
argument-hint: [product-category] [forecast-period]
version: "1.0.0"
tags: [inventory, supply-chain, forecasting, automation]
tool_access: [Read, Write, Bash]
model: haiku
---

# Inventory Reorder Automation

Generate data-driven reorder recommendations...
```

### 4. Plugin Manifest Template (`plugin-manifest-template.json`)

Creates plugin configuration for the marketplace.

**Key Placeholders:**
- `{{PLUGIN_NAME}}` - Hyphen-case plugin identifier
- `{{PLUGIN_DESCRIPTION}}` - Plugin purpose and capabilities
- `{{VERSION}}` - Semantic version (e.g., "1.0.0")
- `{{AUTHOR_NAME}}` - Author full name
- `{{AUTHOR_URL}}` - Author URL or GitHub profile
- `{{HOMEPAGE_URL}}` - Plugin homepage
- `{{REPOSITORY_URL}}` - Git repository URL
- `{{LICENSE}}` - License type (typically "MIT")
- `{{KEYWORDS}}` - Comma-separated keyword list in quotes
- `{{CATEGORY}}` - Plugin category (see categories below)
- `{{COMMANDS_ARRAY}}` - Command file paths in quotes, comma-separated
- `{{AGENTS_ARRAY}}` - Agent file paths in quotes, comma-separated
- `{{SKILLS_ARRAY}}` - Skill directory paths in quotes, comma-separated

**Plugin Categories:**
- `business` - Business operations and analytics
- `operations` - Supply chain, logistics, inventory
- `workflows` - Workflow automation and orchestration
- `utilities` - General utilities and tools
- `quality` - Quality assurance and testing
- `documentation` - Documentation generation
- `development` - Software development
- `data` - Data engineering and analytics
- `ai-ml` - AI and machine learning
- `marketing` - Marketing and content
- `finance` - Financial operations

**Example:**
```json
{
  "name": "inventory-management",
  "source": "./plugins/inventory-management",
  "description": "Inventory tracking, stock optimization, and automated reordering",
  "version": "1.0.0",
  "author": {
    "name": "Your Name",
    "url": "https://github.com/yourusername"
  },
  "homepage": "https://github.com/yourusername/agents",
  "repository": "https://github.com/yourusername/agents",
  "license": "MIT",
  "keywords": [
    "inventory",
    "supply-chain",
    "stock-management",
    "forecasting"
  ],
  "category": "operations",
  "strict": false,
  "commands": [
    "./commands/reorder-automation.md",
    "./commands/stock-forecast.md"
  ],
  "agents": [
    "./agents/inventory-manager.md",
    "./agents/supply-chain-optimizer.md"
  ],
  "skills": [
    "./skills/inventory-optimization",
    "./skills/demand-forecasting"
  ]
}
```

## Naming Conventions

### Agents
- Use hyphen-case: `inventory-manager`, `sales-automator`
- Suffix with role: `-manager`, `-analyst`, `-automator`, `-optimizer`
- Keep names descriptive and domain-specific

### Skills
- Use hyphen-case: `inventory-optimization`, `demand-forecasting`
- Focus on technique or methodology
- Avoid redundant suffixes like `-skill` or `-patterns`

### Commands
- Use hyphen-case: `reorder-automation`, `stock-forecast`
- Use action verbs: `generate`, `analyze`, `optimize`, `automate`
- Keep concise (2-3 words maximum)

### Plugins
- Use hyphen-case: `inventory-management`, `supply-chain-ops`
- Group related functionality
- Avoid overly broad names

## Model Selection Guidelines

**Sonnet (claude-sonnet-4-5):**
- Complex analysis and decision-making
- Strategic planning and architecture
- Multi-step reasoning required
- Security-critical operations
- High-stakes business decisions

**Haiku (claude-haiku):**
- Routine automation tasks
- Data processing and transformation
- Template generation
- Simple CRUD operations
- High-frequency, low-complexity tasks

**Opus (reserved for future use):**
- Most complex reasoning tasks
- Critical analysis requiring maximum capability

## Progressive Disclosure Pattern (Skills)

Skills should follow progressive disclosure:

1. **Metadata** (name, description with "Use when")
2. **Overview** (what and why)
3. **When to Use** (activation scenarios)
4. **Core Concepts** (2-4 fundamental concepts)
5. **Quick Start** (minimal working example)
6. **Patterns** (3-5 common patterns with code)
7. **Advanced Techniques** (optional)
8. **Resources** (references, links)
9. **Best Practices** (do's)
10. **Common Pitfalls** (don'ts)

## Business Operations Focus

When adapting these templates for **business operations** (vs software development):

### Agents
- Focus on business processes, not technical implementation
- Emphasize decision-making, analysis, and automation
- Use business terminology, not programming jargon

**Good:** "inventory-manager specializing in stock optimization"
**Bad:** "database-admin specializing in SQL queries"

### Skills
- Teach business methodologies and frameworks
- Include business metrics and KPIs
- Provide industry-standard calculations

**Good:** "EOQ calculation and reorder point optimization"
**Bad:** "Binary tree traversal patterns"

### Commands
- Orchestrate business workflows
- Focus on outcomes, not implementation
- Use business-relevant arguments

**Good:** `stock-forecast [product-category] [period]`
**Bad:** `run-tests [test-suite] [coverage-threshold]`

## Variable Naming Patterns

When generating content for templates:

- Use **title case** for display names: "Inventory Manager", "Stock Optimization"
- Use **hyphen-case** for identifiers: `inventory-manager`, `stock-optimization`
- Use **SCREAMING_SNAKE_CASE** for placeholders: `{{AGENT_NAME}}`, `{{SKILL_TITLE}}`
- Use **sentence case** for descriptions: "Manage inventory with automated reordering"

## Token Efficiency

Keep components concise while comprehensive:

- **Agent descriptions**: < 200 chars (fits in selection UI)
- **Skill descriptions**: < 1024 chars (includes "Use when" clause)
- **Purpose statements**: 1-2 paragraphs
- **Capability lists**: 5-7 items per category
- **Code examples**: < 50 lines when possible

## Source Examples

These templates were derived from analyzing:

**Agents:**
- payment-integration.md (haiku, simple structure)
- deployment-engineer.md (haiku, detailed capabilities)
- security-auditor.md (sonnet, comprehensive structure)
- business-analyst.md (haiku, business focus)
- hr-pro.md (sonnet, disclaimer pattern)

**Skills:**
- terraform-module-library/SKILL.md
- rag-implementation/SKILL.md
- monorepo-management/SKILL.md
- stripe-integration/SKILL.md
- auth-implementation-patterns/SKILL.md

**Commands:**
- sql-migrations.md (detailed, technical)
- ml-pipeline.md (multi-agent orchestration)
- error-analysis.md (comprehensive workflow)
- tdd-cycle.md (strict workflow)

## Programmatic Usage

For automated generation:

1. Load template file
2. Define replacement map
3. Replace all `{{VARIABLE}}` placeholders
4. Validate resulting structure
5. Write to target location

**Python Example:**
```python
import re

def fill_template(template_path, replacements):
    with open(template_path, 'r') as f:
        template = f.read()

    for key, value in replacements.items():
        template = template.replace(f'{{{{{key}}}}}', value)

    return template

# Usage
replacements = {
    'AGENT_NAME': 'inventory-manager',
    'DESCRIPTION': 'Manage inventory with stock tracking and reorder automation',
    'MODEL': 'haiku',
    # ... more replacements
}

agent_content = fill_template('templates/agent-template.md', replacements)
```

## Validation Checklist

Before creating a new component:

**Agents:**
- [ ] Name is hyphen-case and descriptive
- [ ] Description < 200 chars with activation criteria
- [ ] Model selection is appropriate (sonnet vs haiku)
- [ ] Purpose statement is clear and specific
- [ ] Capabilities are organized into 3-5 categories
- [ ] Behavioral traits define agent personality
- [ ] Response approach has 5-9 clear steps
- [ ] Example interactions demonstrate use cases

**Skills:**
- [ ] Name is hyphen-case without redundant suffixes
- [ ] Description < 1024 chars with "Use when" clause
- [ ] Overview explains what and why
- [ ] 2-4 core concepts are defined
- [ ] Quick start provides minimal example
- [ ] 3-5 patterns with code examples
- [ ] Best practices and pitfalls included
- [ ] Resources list external references

**Commands:**
- [ ] Description is clear and actionable
- [ ] Argument hint shows expected parameters
- [ ] Tool access lists required capabilities
- [ ] Phases are logically ordered
- [ ] Output format is well-defined
- [ ] Success criteria are measurable
- [ ] `$ARGUMENTS` placeholder is used

**Plugin Manifests:**
- [ ] Name matches directory structure
- [ ] Version follows semantic versioning
- [ ] Category is appropriate
- [ ] Keywords are relevant and specific
- [ ] All file paths are correct
- [ ] Arrays are properly formatted JSON

## Integration with Meta-Agent Builder

The meta-agent-builder plugin uses these templates to:

1. **Analyze Requirements** - Extract component specifications from user requests
2. **Select Template** - Choose appropriate template based on component type
3. **Generate Variables** - Create replacement map from specifications
4. **Fill Template** - Replace placeholders with generated content
5. **Validate Output** - Ensure structure matches repository standards
6. **Write Files** - Create component files in correct locations
7. **Update Manifest** - Add component to plugin manifest

## Contributing

When updating templates:

1. Analyze 5+ examples from wshobson/agents
2. Identify common patterns and variations
3. Update template to accommodate patterns
4. Update this README with changes
5. Test template with multiple scenarios
6. Validate generated components work correctly

## License

These templates are derived from the wshobson/agents repository structure and are provided for use in generating compatible components for business operations automation.
