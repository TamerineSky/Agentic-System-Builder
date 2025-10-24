---
description: Interactive wizard for complete plugin creation from business domain description
argument-hint: [domain-name] [description]
version: "1.0.0"
tags: [generator, plugin, wizard, interactive]
tool_access: [Read, Write, Bash, Grep, Glob]
model: sonnet
---

# Generate Complete Plugin

Create a complete, production-ready plugin from a business domain description through an interactive guided workflow.

## Context

This command orchestrates the full plugin generation process, leveraging multiple meta-agents to analyze your business domain, design the architecture, generate all components (agents, skills, commands), validate quality, and produce comprehensive documentation.

The workflow follows the proven patterns from Seth Dobson's agent architecture while adapting them specifically for business operations contexts.

## Requirements

**Domain Name**: $1 (e.g., "revenue-operations", "supply-chain")
**Business Description**: $2 (e.g., "Sales pipeline management and forecasting")

If arguments are not provided, the wizard will prompt interactively.

## Instructions

### 1. Domain Analysis & Discovery

**Objective**: Understand the business domain deeply to inform all subsequent design decisions.

**Actions**:
- Invoke the `domain-analyzer` agent to analyze the business domain description
- Identify key business processes, metrics, and workflows
- Map stakeholders and their primary concerns
- Determine integration points (CRMs, ERPs, data sources)
- Define success criteria and value propositions

**Questions to Answer**:
- What are the core business processes in this domain?
- What metrics matter most to stakeholders?
- What are the typical pain points and workflows?
- What systems need to integrate?
- What business outcomes define success?

**Output**: Domain analysis document capturing:
- Business process map
- Stakeholder needs analysis
- Key metrics and KPIs
- Integration requirements
- Success criteria

### 2. Component Architecture Design

**Objective**: Design the plugin architecture following granular, composable patterns.

**Actions**:
- Invoke the `orchestration-designer` agent to plan the component structure
- Define which agents are needed (roles and responsibilities)
- Identify which skills provide reusable knowledge
- Design command workflows that users will invoke
- Ensure 2-8 components per plugin (Anthropic best practice)
- Map component interactions and dependencies

**Design Principles**:
- Granular over monolithic (single responsibility)
- Composable over bundled (reusable components)
- Business-focused language (domain terminology)
- Token-efficient (progressive disclosure)

**Output**: Architecture specification including:
- Plugin structure diagram
- Agent definitions (name, role, model)
- Skill definitions (name, knowledge domain)
- Command definitions (name, workflow)
- Component interaction map

### 3. Agent Generation

**Objective**: Generate all specialized agents for the plugin.

**Actions**:
- For each agent in the architecture specification:
  - Invoke the `agent-generator` agent
  - Provide role name and expertise area from architecture
  - Review generated system prompt for domain accuracy
  - Validate tool assignments are appropriate
  - Confirm model selection (Haiku for execution, Sonnet for reasoning)

**Quality Checks**:
- System prompt uses business domain language
- Capabilities are clearly enumerated
- Response approach is step-by-step
- Tool access is minimal but sufficient
- Model selection matches complexity

**Output**: Agent markdown files in `plugins/{domain}/agents/` directory

### 4. Skill Generation

**Objective**: Create knowledge packages using progressive disclosure architecture.

**Actions**:
- For each skill in the architecture specification:
  - Invoke the `skill-builder` agent
  - Provide skill name and methodology description
  - Ensure three-tier structure (metadata, instructions, resources)
  - Validate activation criteria are clear
  - Confirm knowledge is appropriately scoped

**Progressive Disclosure Structure**:
1. **Metadata** (always loaded): Name, description, activation trigger
2. **Instructions** (loaded when activated): Core guidance and methods
3. **Resources** (loaded on demand): Examples, templates, checklists

**Output**: Skill directories in `plugins/{domain}/skills/` with SKILL.md files

### 5. Command Generation

**Objective**: Create user-facing workflow commands.

**Actions**:
- For each command in the architecture specification:
  - Invoke the `command-composer` agent
  - Provide command name and workflow description
  - Define parameters using $1, $2 notation
  - Specify model (Haiku for simple, Sonnet for complex)
  - Include clear argument hints in frontmatter

**Command Elements**:
- Clear description of what the command does
- Argument hints for user guidance
- Step-by-step workflow instructions
- Output format specification
- Success criteria

**Output**: Command markdown files in `plugins/{domain}/commands/` directory

### 6. Integration & Validation

**Objective**: Ensure all components work together and meet quality standards.

**Actions**:
- Create the plugin.json manifest file:
  - List all agents, skills, and commands
  - Set appropriate versioning
  - Define plugin metadata
- Invoke the `plugin-validator` agent to check:
  - Directory structure compliance
  - File naming conventions
  - Component completeness
  - Cross-reference integrity
  - Documentation quality
- Run integration checks:
  - Agent references to skills are valid
  - Commands invoke appropriate agents
  - No circular dependencies
  - Token budgets are reasonable

**Validation Criteria**:
- All components follow naming conventions
- Directory structure matches specification
- Frontmatter is complete and valid
- No broken references between components
- Documentation is comprehensive

**Output**: Validation report with pass/fail status and remediation guidance

### 7. Documentation Generation

**Objective**: Create comprehensive documentation for plugin users.

**Actions**:
- Generate README.md for the plugin:
  - Overview and value proposition
  - Component catalog (agents, skills, commands)
  - Usage examples
  - Integration requirements
  - Quick start guide
- Create ARCHITECTURE.md:
  - Design decisions and rationale
  - Component interaction diagrams
  - Token efficiency notes
  - Extension points
- Generate CONTRIBUTING.md:
  - How to add new agents/skills/commands
  - Testing procedures
  - Quality standards

**Documentation Standards**:
- Business-focused language (not technical jargon)
- Clear examples with sample outputs
- Troubleshooting guidance
- Links to related resources

**Output**: Complete documentation suite in plugin root directory

## Output Format

The command will produce:

1. **Plugin Directory Structure**:
```
plugins/{domain-name}/
├── .claude-plugin/
│   └── plugin.json
├── agents/
│   ├── {role-1}.md
│   ├── {role-2}.md
│   └── ...
├── skills/
│   ├── {methodology-1}/
│   │   └── SKILL.md
│   └── ...
├── commands/
│   ├── {workflow-1}.md
│   ├── {workflow-2}.md
│   └── ...
├── README.md
├── ARCHITECTURE.md
└── CONTRIBUTING.md
```

2. **Summary Report**:
- Total components generated
- Token budget estimates
- Validation results
- Quick start commands
- Next steps for testing

3. **Installation Instructions**:
- How to enable the plugin
- First command to try
- Sample workflows

## Success Criteria

- Plugin passes all validation checks
- Components follow naming conventions
- Documentation is complete and clear
- Token budgets are within reasonable limits (< 50k per component)
- Business language is used throughout (not technical jargon)
- All file paths are valid and references work
- Plugin can be immediately used for target domain
- Architecture follows granular plugin principles

## Related Plugins

- **meta-agent-builder**: Core plugin providing generation capabilities
- **domain-specific plugins**: Examples from Issue #8 (revenue-operations, supply-chain, etc.)

---

**Note**: This command provides interactive prompts if arguments are missing. You can run `/generate-plugin` without arguments to be guided through the wizard, or provide domain name and description upfront for faster generation.
