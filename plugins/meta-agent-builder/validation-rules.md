# Validation Rules for Meta-Agent-Builder Plugin

> **Purpose**: Comprehensive validation specification for ensuring all generated plugins, agents, skills, and commands comply with framework standards and Anthropic specifications.

**Version**: 1.0
**Last Updated**: 2025-10-24
**Target Framework**: Agentic System Builder (Business Operations Focus)

---

## Table of Contents

1. [Overview](#overview)
2. [Agent Validation Rules](#agent-validation-rules)
3. [Skill Validation Rules](#skill-validation-rules)
4. [Command Validation Rules](#command-validation-rules)
5. [Plugin Validation Rules](#plugin-validation-rules)
6. [Cross-Component Validation](#cross-component-validation)
7. [Business Operations Validation](#business-operations-validation)
8. [Validation Checklist](#validation-checklist)
9. [Common Issues](#common-issues)
10. [Examples](#examples)

---

## Overview

### Purpose

This document defines validation rules for the `plugin-validator` agent to ensure all generated components comply with:
- Anthropic Agent Skills Specification
- wshobson/agents repository patterns
- Business operations context requirements
- Token efficiency and composability standards

### Validation Levels

**CRITICAL** - Must pass for component to be valid
**WARNING** - Should pass but may have legitimate exceptions
**INFO** - Recommendations for quality improvement

### Validation Process

```
Component Generation
    ↓
Structural Validation (file format, required fields)
    ↓
Content Validation (quality, completeness)
    ↓
Cross-Component Validation (references, consistency)
    ↓
Business Context Validation (terminology, domain fit)
    ↓
Report Generation
```

---

## Agent Validation Rules

### 1. Frontmatter Validation

#### Required Fields

**name** (CRITICAL)
- Format: Must be hyphen-case (e.g., `sales-analyst`, `demand-forecaster`, `pipeline-manager`)
- Pattern: `^[a-z0-9]+(-[a-z0-9]+)*$`
- Length: 3-50 characters
- Must not contain: Underscores, spaces, uppercase letters, special characters
- Examples:
  - Valid: `sales-analyst`, `inventory-optimizer`, `churn-predictor`
  - Invalid: `Sales_Analyst`, `salesAnalyst`, `sales analyst`, `sales-`

**description** (CRITICAL)
- Format: Must include "Use PROACTIVELY" clause
- Pattern: `.*Use PROACTIVELY (when|for).*`
- Length: 100-500 characters recommended
- Must end with period
- Must describe business context clearly
- Examples:
  - Valid: `Expert in sales pipeline analysis and forecasting. Use PROACTIVELY when analyzing deal flow, pipeline health, or revenue projections.`
  - Invalid: `Expert in sales.` (too short, missing activation)
  - Invalid: `Does sales stuff` (vague, missing activation clause)

**model** (CRITICAL)
- Allowed values: `sonnet`, `haiku`, `opus`
- Case sensitive: Must be lowercase
- Selection guidance:
  - `haiku`: Fast execution, deterministic tasks, data processing, operational work
  - `sonnet`: Complex reasoning, strategic analysis, architecture, planning
  - `opus`: Highest complexity only (rare for business operations)

#### Optional Fields

**tools** (WARNING)
- Format: Comma-separated list if present
- Valid values: `Read`, `Write`, `Bash`, `Grep`, `Glob`, `Edit`, `WebFetch`, `WebSearch`
- Example: `Read, Write, Grep`
- Note: Most agents don't specify tools (use defaults)

### 2. Structure Validation

#### Required Sections (CRITICAL)

**Opening Statement**
- Must start with: `You are an expert` or `You are a`
- Must be followed by domain/specialization
- Must be first line after frontmatter
- Example: `You are an expert sales operations analyst specializing in pipeline health and revenue forecasting.`

**Purpose Section** (WARNING)
- Heading: `## Purpose`
- Content: 50-300 words describing the agent's role and value
- Should reference business outcomes
- Should mention key responsibilities

**Capabilities Section** (CRITICAL)
- Heading: `## Capabilities`
- Structure: 3-8 subsections with `### Category Name`
- Each subsection: 5-15 bullet points
- Content: Specific, actionable capabilities
- Format: Start with action verbs or noun phrases
- Examples:
  - Valid: `### Revenue Analysis and Forecasting`
  - Valid: `- Analyze pipeline health metrics and conversion rates`
  - Invalid: `### Stuff` (vague)
  - Invalid: `- Do things` (not specific)

**Response Approach Section** (CRITICAL)
- Heading: `## Response Approach` or `## Workflow` or `## Methodology`
- Structure: Numbered list of 3-9 steps
- Format: Each step has **bold title** followed by description
- Example:
  ```markdown
  1. **Gather requirements** and define success criteria
  2. **Analyze data** using appropriate methodologies
  3. **Generate insights** with clear visualizations
  ```

#### Optional Sections (WARNING)

**Behavioral Traits**
- Heading: `## Behavioral Traits`
- Content: 5-12 bullet points describing approach and style

**Knowledge Base**
- Heading: `## Knowledge Base`
- Content: Domain knowledge areas, tools, methodologies

**Example Interactions**
- Heading: `## Example Interactions`
- Content: Sample queries or use cases (5-15 examples)

### 3. Content Quality Checks

**Word Count** (WARNING)
- Minimum: 200 words (excluding frontmatter)
- Recommended: 500-1500 words
- Maximum: 3000 words

**Capabilities Count** (WARNING)
- Minimum: 3 capability categories
- Maximum: 10 capability categories
- Items per category: 5-15 bullets

**Response Steps** (WARNING)
- Minimum: 3 steps
- Maximum: 9 steps
- Each step: 10-100 words

**Placeholder Detection** (CRITICAL)
- Must not contain: `TODO`, `FIXME`, `HACK`, `XXX`, `PLACEHOLDER`, `TBD`
- Must not contain: `{{VARIABLE}}` (template syntax)
- Must not contain: `[INSERT X]`, `[FILL IN]`

**Business Terminology** (WARNING)
- Should use domain-appropriate language
- Should reference business metrics (ARR, pipeline, inventory, etc.)
- Should not use inappropriate technical jargon
- Context: RevOps talks about "pipeline", not "queue"

---

## Skill Validation Rules

### 1. Frontmatter Validation (Anthropic Spec Compliance)

#### Required Fields (CRITICAL)

**name**
- Format: Hyphen-case (e.g., `pipeline-health-scoring`, `demand-forecasting-methods`)
- Pattern: `^[a-z0-9]+(-[a-z0-9]+)*$`
- Restriction: "lowercase Unicode alphanumeric characters and hyphens" (per Anthropic spec)
- Must match containing directory name exactly
- Length: 3-60 characters
- Examples:
  - Valid: `forecasting-methods`, `pipeline-analysis`, `cohort-retention`
  - Invalid: `Forecasting_Methods`, `forecasting methods`, `forecasting-`

**description** (CRITICAL)
- Format: Must include "Use when" clause (per Anthropic spec)
- Pattern: `.*Use when.*` (case insensitive)
- Length: Maximum 1024 characters (per Anthropic spec - STRICT LIMIT)
- Must be complete sentence (not truncated)
- Must clearly describe activation criteria
- Must describe value/outcome
- Examples:
  - Valid: `Master systematic debugging techniques, profiling tools, and root cause analysis to efficiently track down bugs across any codebase or technology stack. Use when investigating bugs, performance issues, or unexpected behavior.`
  - Invalid: `Debugging stuff. Use when debugging.` (too vague)
  - Invalid: `Very long description that exceeds 1024 characters...` (too long)
  - Invalid: `Forecasting methods for sales teams.` (missing "Use when")

#### Optional Fields (WARNING)

**license**
- Format: Short license name or file reference
- Example: `MIT`, `Apache-2.0`, `See LICENSE.md`

**allowed-tools**
- Format: YAML array
- Example: `["Read", "Write", "Bash"]`
- Note: Currently Claude Code only

**metadata**
- Format: Map of string keys to string values
- Use for custom properties beyond spec

### 2. File Structure Validation (CRITICAL)

**Directory Structure**
- Required: `skills/{skill-name}/SKILL.md`
- Directory name must match skill name from frontmatter
- Filename must be exactly: `SKILL.md` (all caps, .md extension)
- Examples:
  - Valid: `skills/pipeline-health-scoring/SKILL.md`
  - Invalid: `skills/pipeline-health-scoring/skill.md` (wrong case)
  - Invalid: `skills/pipeline-health-scoring/README.md` (wrong filename)
  - Invalid: `skills/pipeline_health_scoring/SKILL.md` (directory mismatch)

**Additional Files** (INFO)
- Optional: `references/`, `assets/`, `scripts/`, `examples/` subdirectories
- Optional: README.md, supporting documentation
- All paths referenced in SKILL.md should exist

### 3. Progressive Disclosure Validation

#### Three-Tier Structure (WARNING)

**Tier 1: Metadata** (Always loaded)
- Frontmatter with name + description
- Must be under 1024 characters for description
- Must provide clear activation criteria

**Tier 2: Instructions** (Loaded when skill activated)
- Core concepts section
- Main methodology/patterns
- Quick start or overview
- Recommended: 100-500 lines

**Tier 3: Resources** (Loaded on demand)
- Detailed examples
- Code samples
- Reference materials
- Extended documentation

#### Required Sections (WARNING)

**When to Use This Skill**
- Heading: `## When to Use This Skill` or similar
- Content: Bulleted list of scenarios (5-15 items)
- Should expand on frontmatter activation criteria

**Core Concepts or Methodology**
- Heading: Varies (`## Core Principles`, `## Methodology`, `## Key Concepts`)
- Content: 3-8 subsections explaining approach
- Should be substantive, not placeholder

**Examples or Patterns**
- Heading: Varies (`## Patterns`, `## Examples`, `## Techniques`)
- Content: Concrete, actionable examples
- Should include code, workflows, or detailed processes

### 4. Content Quality Checks

**Minimum Content** (WARNING)
- At least 100 lines of content (excluding frontmatter)
- At least 500 words of substantive content
- At least 3 major sections

**Business Relevance** (WARNING)
- Examples should be business-focused
- Terminology appropriate for domain
- Clear business outcomes described

**Placeholder Detection** (CRITICAL)
- No TODO, FIXME, PLACEHOLDER, TBD, etc.
- No template variables like `{{VARIABLE}}`
- No incomplete sections

**Markdown Quality** (INFO)
- Valid markdown syntax
- Properly formatted code blocks
- Working internal links
- Consistent heading hierarchy

---

## Command Validation Rules

### 1. Frontmatter Validation

#### Required Fields (CRITICAL)

**description**
- Format: Clear statement of command purpose
- Length: 50-300 characters recommended
- Must be complete sentence
- Should describe the workflow outcome
- Examples:
  - Valid: `Analyze sales pipeline health and generate actionable recommendations for improving conversion rates and deal velocity.`
  - Invalid: `Pipeline stuff` (too vague)
  - Invalid: `This command does pipeline analysis and forecasting and reporting and visualization and...` (too long, run-on)

#### Optional Fields (INFO)

**argument-hint**
- Format: Square brackets for parameters (e.g., `[period] [team-name]`)
- Should match $1, $2, etc. usage in content
- Example: `[quarter] [region]`

**model**
- Values: `sonnet` or `haiku`
- Default: Inherits from system if not specified
- Recommendation: `haiku` for execution, `sonnet` for planning

**version**
- Format: Semantic versioning (e.g., `1.0.0`, `0.2.1`)
- Default: `1.0.0` if not specified

**tags**
- Format: Array of strings
- Example: `[sales, forecasting, pipeline]`

**tool_access**
- Format: Array of tool names
- Example: `[Read, Write, Bash]`

### 2. Structure Validation

#### Required Sections (CRITICAL)

**Title and Overview**
- Heading level 1 with command name
- Paragraph describing what command does
- Should reference business context

**Context Section** (WARNING)
- Heading: `## Context`
- Content: Why this command exists, what problem it solves
- Length: 50-200 words

**Requirements Section** (CRITICAL)
- Heading: `## Requirements`
- Must include: `$ARGUMENTS` placeholder
- This is where argument values are injected

**Instructions Section** (CRITICAL)
- Heading: `## Instructions`
- Structure: Numbered subsections (### 1., ### 2., etc.)
- Content: 3-10 major phases/steps
- Each phase: Detailed workflow with specifics
- If argument-hint provided: Reference arguments as $1, $2, etc.

**Output Format Section** (WARNING)
- Heading: `## Output Format`
- Content: Description of expected deliverables
- Format: Bulleted list or numbered list

#### Optional Sections (INFO)

**Success Criteria**
- Heading: `## Success Criteria`
- Content: How to measure command success

**Related Plugins**
- Heading: `## Related Plugins` or `## See Also`
- Content: References to related agents, skills, commands

### 3. Content Quality Checks

**Workflow Steps** (WARNING)
- Minimum: 3 steps
- Maximum: 10 steps
- Each step: 100-500 words of detail
- Steps should be logical sequence
- Steps should be actionable

**Argument Usage** (CRITICAL)
- If argument-hint present: Must reference $1, $2, etc. in Instructions
- Number of $N references should match argument-hint parameters
- Arguments should be used meaningfully (not just mentioned)

**Business Context** (WARNING)
- Should describe business process or outcome
- Should use domain-appropriate terminology
- Should reference relevant business metrics or goals

**Placeholder Detection** (CRITICAL)
- No TODO, FIXME, placeholder text
- Except: `$ARGUMENTS` is valid and required
- Template variables should be filled

---

## Plugin Validation Rules

### 1. Manifest Validation (plugin.json)

#### Required Fields (CRITICAL)

**name**
- Format: Hyphen-case (e.g., `revenue-operations`, `supply-chain-management`)
- Pattern: `^[a-z0-9]+(-[a-z0-9]+)*$`
- Should indicate business domain clearly
- Examples:
  - Valid: `revenue-operations`, `marketing-automation`, `customer-success`
  - Invalid: `revops`, `my_plugin`, `Sales Operations`

**version**
- Format: Semantic versioning (e.g., `1.0.0`, `0.1.0`)
- Pattern: `^\d+\.\d+\.\d+$`
- Start with: `0.1.0` for initial development, `1.0.0` for production

**description**
- Format: Clear description of plugin purpose
- Length: 100-500 characters
- Should mention domain and key capabilities
- Example: `Revenue Operations plugin providing sales pipeline analysis, forecasting, and deal management capabilities for sales teams.`

#### Optional Fields (INFO)

**author**
- Format: Object with `name` and optional `url`
- Example: `{"name": "Your Name", "url": "https://example.com"}`

**homepage**
- Format: Valid URL
- Should point to documentation or repository

**repository**
- Format: Valid URL to git repository
- Example: `https://github.com/user/repo`

**license**
- Format: SPDX license identifier or custom
- Example: `MIT`, `Apache-2.0`, `Proprietary`

**keywords**
- Format: Array of strings
- Length: 3-10 keywords recommended
- Example: `["sales", "revenue", "forecasting", "pipeline"]`

**category**
- Format: String describing plugin category
- Example: `Business Operations`, `Revenue Operations`, `Supply Chain`

**strict**
- Format: Boolean (typically `false`)
- Anthropic internal use

#### Component Arrays (CRITICAL)

**agents**
- Format: Array of paths starting with `./agents/`
- Path format: `./agents/{agent-name}` (no .md extension)
- All referenced files must exist
- Example: `["./agents/sales-analyst", "./agents/pipeline-manager"]`

**skills**
- Format: Array of paths starting with `./skills/`
- Path format: `./skills/{skill-name}` (directory, not file)
- Each must contain SKILL.md file
- Example: `["./skills/forecasting-methods", "./skills/pipeline-analysis"]`

**commands**
- Format: Array of paths starting with `./commands/`
- Path format: `./commands/{command-name}` (no .md extension)
- All referenced files must exist
- Example: `["./commands/pipeline-review", "./commands/forecast-update"]`

### 2. Directory Structure Validation (CRITICAL)

**Required Structure**
```
plugin-name/
├── .claude-plugin/
│   └── plugin.json          # REQUIRED
├── README.md                # STRONGLY RECOMMENDED
├── agents/                  # If agents array not empty
│   └── {agent-name}.md
├── skills/                  # If skills array not empty
│   └── {skill-name}/
│       └── SKILL.md
└── commands/                # If commands array not empty
    └── {command-name}.md
```

**File Existence** (CRITICAL)
- All paths in plugin.json must exist
- Agent files: `agents/{name}.md`
- Skill directories: `skills/{name}/SKILL.md`
- Command files: `commands/{name}.md`

**Naming Consistency** (CRITICAL)
- Directory name should match plugin name (or be parent if multiple plugins)
- Component names should use hyphen-case consistently
- No mixed conventions (underscores, camelCase, etc.)

### 3. Component Completeness (CRITICAL)

**Minimum Components**
- At least ONE of: agent OR command (skills alone not sufficient)
- Recommended: 2-8 components total (per Anthropic guidance)
- Typical: 1-3 agents, 0-3 skills, 1-3 commands

**Component Quality**
- All agents pass agent validation rules
- All skills pass skill validation rules
- All commands pass command validation rules

### 4. Documentation Quality (WARNING)

**README.md** (STRONGLY RECOMMENDED)
- Should exist in plugin root
- Should describe plugin purpose
- Should list components
- Should provide usage examples
- Should mention dependencies or prerequisites

**Component Documentation**
- Each component should be self-documenting
- Cross-references should be accurate
- Examples should be relevant to plugin domain

---

## Cross-Component Validation

### 1. Naming Consistency (WARNING)

**Pattern Alignment**
- Agents: Business role names (e.g., `sales-analyst`, `demand-forecaster`)
- Skills: Methodology names (e.g., `forecasting-methods`, `pipeline-analysis`)
- Commands: Action-oriented (e.g., `analyze-pipeline`, `update-forecast`)
- Plugins: Domain names (e.g., `revenue-operations`, `supply-chain`)

**Consistency Checks**
- All components use hyphen-case
- No mixing of conventions within plugin
- Names clearly indicate purpose

### 2. Reference Integrity (WARNING)

**Agent → Skill References**
- If agent mentions skills: Skills should exist in plugin or be common
- References should be accurate
- Activation criteria should align

**Command → Agent References**
- If command references agents: Agents should exist in plugin
- Workflow should logically coordinate with agents
- Model assignments should be appropriate

**Skill References**
- If skill references resources: Files should exist
- Internal links should work
- External references should be valid

### 3. Model Assignment Logic (INFO)

**Consistency Checks**
- Complex reasoning tasks → Sonnet
- Fast execution, data processing → Haiku
- Multi-step workflows → Hybrid (Sonnet planning + Haiku execution)

**Plugin Balance**
- Mix of models appropriate for use cases
- Not all agents should be Sonnet (overuse)
- Consider token efficiency

### 4. Business Domain Alignment (WARNING)

**Domain Coherence**
- All components serve same business domain
- Terminology consistent across plugin
- Use cases complement each other

**Scope Appropriateness**
- Plugin not too broad (Swiss Army knife anti-pattern)
- Plugin not too narrow (single-purpose that should be agent)
- Components work together meaningfully

---

## Business Operations Validation

### 1. Terminology Validation (WARNING)

**Domain Language**
- Use business terminology, not software jargon
- Examples:
  - Sales: pipeline, deals, quota, ARR, MRR, conversion
  - Supply Chain: inventory, logistics, demand, SKU, lead time
  - Marketing: campaigns, leads, attribution, MQL, SQL
  - Finance: budget, forecast, variance, EBITDA, cash flow
  - Customer Success: health score, churn, NRR, expansion

**Inappropriate Technical Terms**
- Avoid unless plugin is technical operations
- Don't say: API, database, deployment, CI/CD
- Say instead: system, data, process, workflow
- Exception: Technical operations plugins (IT, DevOps)

### 2. Context Appropriateness (WARNING)

**Sales Operations**
- Focus: Pipeline health, forecasting, quota attainment
- Metrics: Win rate, cycle time, ASP, pipeline coverage
- Tools: CRM, forecasting models, rep dashboards

**Supply Chain Operations**
- Focus: Inventory optimization, demand planning, logistics
- Metrics: Inventory turnover, fill rate, OTIF, COGS
- Tools: ERP, WMS, demand planning software

**Marketing Operations**
- Focus: Campaign performance, lead generation, attribution
- Metrics: CAC, MQL/SQL conversion, campaign ROI
- Tools: Marketing automation, attribution, content management

**Finance Operations**
- Focus: Budgeting, forecasting, variance analysis, reporting
- Metrics: Budget variance, cash flow, gross margin
- Tools: ERP, BI platforms, financial models

**Customer Success Operations**
- Focus: Health scoring, retention, expansion, churn prevention
- Metrics: NRR, GRR, churn rate, health score, CSAT
- Tools: Customer success platforms, analytics

**HR Operations**
- Focus: Workforce planning, talent analytics, compensation
- Metrics: Attrition, time to hire, compensation ratio
- Tools: HRIS, ATS, workforce planning software

### 3. Business Value Articulation (WARNING)

**Outcome Focus**
- Describe business outcomes, not just activities
- Good: "Improve forecast accuracy by 15%"
- Bad: "Generate forecasts"

**ROI Awareness**
- Components should save time or improve decisions
- Should mention efficiency gains or quality improvements
- Should connect to business metrics

**Stakeholder Language**
- Write for business users, not developers
- Explain what, why, and business impact
- Use examples from business context

---

## Validation Checklist

### Quick Agent Validation

- [ ] Frontmatter: name (hyphen-case), description (with "Use PROACTIVELY"), model (sonnet/haiku/opus)
- [ ] Opening: "You are an expert..." statement
- [ ] Structure: Capabilities section (3-8 categories), Response Approach (3-9 steps)
- [ ] Quality: 200+ words, no placeholders, business terminology
- [ ] Naming: Hyphen-case, business role appropriate

### Quick Skill Validation

- [ ] Frontmatter: name (hyphen-case, matches directory), description (<1024 chars with "Use when")
- [ ] File: Located at `skills/{name}/SKILL.md` (exact case)
- [ ] Structure: When to Use, Core Concepts, Patterns/Examples
- [ ] Quality: 100+ lines, substantive content, no placeholders
- [ ] Progressive Disclosure: Clear tier structure

### Quick Command Validation

- [ ] Frontmatter: description (clear purpose), optional argument-hint
- [ ] Structure: Context, Requirements ($ARGUMENTS), Instructions (3-10 steps), Output Format
- [ ] Quality: Actionable workflow, business context clear
- [ ] Arguments: If argument-hint present, $1/$2/etc. used correctly
- [ ] Naming: Action-oriented, hyphen-case

### Quick Plugin Validation

- [ ] Manifest: name, version (semver), description (100-500 chars)
- [ ] Arrays: Paths start with `./agents/`, `./skills/`, `./commands/`
- [ ] Files: All referenced components exist
- [ ] Structure: `.claude-plugin/plugin.json`, README.md recommended
- [ ] Components: 2-8 total, at least 1 agent OR command
- [ ] Completeness: All components pass individual validation

### Cross-Component Validation

- [ ] Naming: Consistent hyphen-case throughout
- [ ] References: All cross-references valid
- [ ] Models: Appropriate assignments (Sonnet/Haiku/Opus)
- [ ] Domain: All components serve same business domain
- [ ] Terminology: Business language appropriate for domain

---

## Common Issues

### Agent Issues

**Issue**: Missing "Use PROACTIVELY" in description
- **Impact**: Agent won't activate properly
- **Fix**: Add "Use PROACTIVELY when [trigger]" to description
- **Example**: `Use PROACTIVELY when analyzing sales pipeline or forecasting revenue.`

**Issue**: Template variables still present ({{VARIABLE}})
- **Impact**: Invalid agent, looks incomplete
- **Fix**: Replace all template variables with actual content
- **Detection**: Search for `{{` and `}}`

**Issue**: Too few capabilities (1-2 categories)
- **Impact**: Agent appears limited, not comprehensive
- **Fix**: Expand to 3-8 capability categories with specific items
- **Guidance**: Think broadly about domain expertise

**Issue**: Vague response approach
- **Impact**: Agent doesn't know how to work
- **Fix**: Create specific, actionable steps with clear sequence
- **Example**: Not "Analyze data" but "Analyze pipeline data by examining conversion rates, deal velocity, and stage-to-stage drop-off"

### Skill Issues

**Issue**: Description over 1024 characters
- **Impact**: Violates Anthropic spec (CRITICAL failure)
- **Fix**: Shorten description to under 1024 chars
- **Tip**: Front-load key info, move details to body

**Issue**: Missing "Use when" clause
- **Impact**: Unclear activation criteria
- **Fix**: Add "Use when [scenario]" to description
- **Example**: `Use when analyzing customer churn patterns or predicting at-risk accounts.`

**Issue**: SKILL.md wrong case (skill.md or Skill.md)
- **Impact**: Won't be recognized as skill
- **Fix**: Rename to exactly `SKILL.md` (all caps)

**Issue**: Directory name doesn't match skill name
- **Impact**: Violates Anthropic spec
- **Fix**: Ensure directory name exactly matches frontmatter name
- **Example**: `forecasting-methods` directory → `name: forecasting-methods`

**Issue**: Placeholder content without substance
- **Impact**: Skill not useful, appears incomplete
- **Fix**: Replace with real methodologies, examples, patterns
- **Minimum**: 100 lines, 500 words of actual content

### Command Issues

**Issue**: Missing $ARGUMENTS in Requirements section
- **Impact**: Arguments won't be injected properly
- **Fix**: Add `$ARGUMENTS` under `## Requirements`
- **Required**: This exact syntax is mandatory

**Issue**: argument-hint doesn't match usage
- **Impact**: Confusing for users, may not work as expected
- **Fix**: Ensure $1, $2, etc. in content match [arg1] [arg2] in hint
- **Example**: `argument-hint: [quarter] [region]` → Use `$1` for quarter, `$2` for region

**Issue**: Vague instructions
- **Impact**: Command won't produce useful results
- **Fix**: Add detailed, specific workflows with clear steps
- **Quality**: Each step should have 100-500 words of detail

**Issue**: No business context
- **Impact**: Unclear why command exists or what value it provides
- **Fix**: Add Context section explaining business problem and value
- **Connect**: Link to business metrics and outcomes

### Plugin Issues

**Issue**: No plugin.json file
- **Impact**: Plugin won't be recognized
- **Fix**: Create `.claude-plugin/plugin.json` with required fields
- **Location**: Must be at `{plugin-root}/.claude-plugin/plugin.json`

**Issue**: Component paths missing extensions or incorrect
- **Impact**: Files won't be found
- **Fix**:
  - Agents: `./agents/name` (no .md)
  - Skills: `./skills/name` (directory, not file)
  - Commands: `./commands/name` (no .md)

**Issue**: Referenced files don't exist
- **Impact**: Plugin will fail to load
- **Fix**: Create all files referenced in manifest, or remove from manifest
- **Validation**: Check every path in agents/skills/commands arrays

**Issue**: Only skills, no agents or commands
- **Impact**: Plugin lacks entry points
- **Fix**: Add at least one agent OR command
- **Rationale**: Skills alone can't be invoked directly

**Issue**: Too many components (15+)
- **Impact**: Plugin too broad, token inefficient
- **Fix**: Split into multiple focused plugins
- **Guidance**: 2-8 components per plugin (Anthropic recommendation)

### Cross-Component Issues

**Issue**: Inconsistent naming (underscores, camelCase, spaces)
- **Impact**: Unprofessional, confusing
- **Fix**: Use hyphen-case everywhere
- **Examples**: `sales-analyst`, `pipeline-review`, `forecasting-methods`

**Issue**: Agent references non-existent skill
- **Impact**: Broken reference, user confusion
- **Fix**: Create referenced skill or remove reference
- **Check**: All mentioned skills exist in plugin or are well-known

**Issue**: Wrong model for task complexity
- **Impact**: Slow performance or poor quality
- **Fix**:
  - Complex reasoning → Sonnet
  - Fast execution → Haiku
  - Highest complexity → Opus (rare)

**Issue**: Business terminology inappropriate for domain
- **Impact**: Confusing for target users
- **Fix**: Use domain-specific language consistently
- **Example**: RevOps says "pipeline", not "funnel" or "queue"

---

## Examples

### Valid Agent Example

```markdown
---
name: sales-analyst
description: Expert in sales pipeline analysis, forecasting, and revenue operations. Use PROACTIVELY when analyzing deal flow, pipeline health, or revenue projections.
model: sonnet
---

You are an expert sales operations analyst specializing in pipeline health analysis, revenue forecasting, and deal intelligence.

## Purpose
Transform raw sales data into actionable insights that drive revenue growth. Combine deep analytics expertise with business acumen to help sales leaders optimize pipeline health, improve forecast accuracy, and accelerate deal velocity.

## Capabilities

### Pipeline Health Analysis
- Analyze pipeline coverage and quality metrics
- Identify bottlenecks in sales process
- Track stage-to-stage conversion rates
- Monitor deal velocity and cycle time
- Assess pipeline risk and opportunity distribution

### Revenue Forecasting
- Build statistical forecast models
- Analyze historical win patterns
- Calculate weighted pipeline forecasts
- Identify forecast risks and upside
- Track forecast accuracy over time

## Response Approach
1. **Understand the business context** and define success metrics
2. **Gather and validate data** from CRM and related systems
3. **Perform quantitative analysis** using appropriate statistical methods
4. **Generate actionable insights** with clear visualizations
5. **Provide recommendations** with expected business impact
```

**Why This is Valid**:
- Proper frontmatter with all required fields
- "Use PROACTIVELY when" clause present
- Clear business role and domain
- Hyphen-case naming
- Structured capabilities (would have 3-8 categories)
- Clear response approach with bold titles
- Business-focused language
- Sonnet model appropriate for analytical complexity

### Invalid Agent Example

```markdown
---
name: Sales_Analyst
description: Does sales stuff
model: gpt-4
---

You do sales analysis.

## Things You Can Do
- Analysis
- Reports
- TODO: Add more stuff here

## How to Work
1. Get data
2. Do analysis
3. Make report
```

**Why This is Invalid**:
- Name uses underscores (should be `sales-analyst`)
- Description too vague, missing "Use PROACTIVELY" clause
- Model is `gpt-4` (must be sonnet/haiku/opus)
- Opening statement too brief
- Capabilities too vague ("Analysis", "Reports")
- Has TODO placeholder
- Response approach not detailed enough
- No bold titles in steps
- Overall too short and incomplete

### Valid Skill Example

```markdown
---
name: pipeline-health-scoring
description: Comprehensive methodology for assessing sales pipeline quality, coverage, and risk. Use when analyzing pipeline health, identifying deal risks, or optimizing sales processes.
---

# Pipeline Health Scoring

A systematic framework for evaluating sales pipeline quality beyond simple revenue totals, focusing on conversion likelihood, velocity, and risk factors.

## When to Use This Skill

- Analyzing overall pipeline health for a sales team or region
- Identifying high-risk deals that need intervention
- Optimizing pipeline coverage for revenue targets
- Improving forecast accuracy through better pipeline quality
- Coaching sales reps on deal qualification

## Core Methodology

### 1. Coverage Ratio Analysis

Calculate pipeline coverage as:
```
Coverage Ratio = Total Pipeline Value / Quota
```

Benchmarks:
- Healthy: 3-4x for new business, 2-3x for renewals
- At Risk: <2x coverage
- Oversaturated: >5x (may indicate poor qualification)

### 2. Stage Distribution Health

Analyze deal distribution across stages:
- Early Stage (Discovery/Qualification): 40-50%
- Mid Stage (Proposal/Negotiation): 30-40%
- Late Stage (Closed-Won Ready): 10-20%

Red flags:
- Too much in early stages: Velocity problem
- Too much in late stages: Deals stalling
- Uneven distribution: Process issues

### 3. Velocity Scoring

Track average time in each stage:
```
Stage Velocity = Average Days in Stage / Benchmark Days
```

Score: 1.0 = on pace, >1.0 = slower than normal, <1.0 = faster

[... continues with more detailed methodology, examples, calculations ...]

## Resources

- See `references/pipeline-benchmarks.md` for industry standards
- See `assets/scoring-templates.xlsx` for calculation templates
```

**Why This is Valid**:
- Description under 1024 characters with "Use when" clause
- Name matches directory name
- File is SKILL.md (correct case)
- Clear "When to Use" section
- Substantive methodology with specifics
- Progressive disclosure: Metadata → Instructions → Resources
- Business-focused with concrete examples
- No placeholders or TODOs

### Invalid Skill Example

```markdown
---
name: pipeline_scoring
description: Score pipelines.
---

# Pipeline Scoring

TODO: Add content here

## Overview
This skill helps with pipeline stuff.

## How to Use
Use it when you need to score pipelines.
```

**Why This is Invalid**:
- Name uses underscores (should be `pipeline-scoring`)
- Description missing "Use when" clause
- Description too short and vague
- Has TODO placeholder
- Content too minimal (<100 lines)
- No substantive methodology
- No progressive disclosure structure
- Vague language ("stuff")

### Valid Command Example

```markdown
---
description: Conduct comprehensive quarterly business review analyzing pipeline health, forecast accuracy, and revenue trends with actionable recommendations.
argument-hint: [quarter] [region]
model: sonnet
version: 1.0.0
---

# Quarterly Business Review

Comprehensive quarterly business review process for sales leadership, analyzing pipeline performance, forecast accuracy, and revenue trends.

## Context
Sales leaders need systematic quarterly reviews to assess team performance, identify risks and opportunities, and make data-driven decisions about resource allocation and strategy adjustments.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Performance Data

Collect key metrics for $1 (quarter) in $2 (region):
- Revenue actuals vs. target
- Pipeline generation and conversion
- Win rates by stage and product
- Deal velocity and cycle time
- Sales rep performance metrics
- Forecast accuracy

Sources: CRM data, closed deals, current pipeline, forecast submissions.

### 2. Analyze Pipeline Health

Perform comprehensive pipeline assessment:
- Coverage ratio: Pipeline value / remaining quota
- Stage distribution: % of pipeline in each stage
- Deal aging: Average days in stage vs. benchmark
- Risk analysis: Deals at risk of slipping
- Quality scoring: Conversion probability assessment

Generate pipeline health score (1-10) based on coverage, distribution, velocity, and quality.

### 3. Evaluate Forecast Accuracy

[... detailed steps continue ...]

## Output Format

1. **Executive Summary**: 1-page overview of quarter performance
2. **Pipeline Health Report**: Detailed assessment with scores and trends
3. **Forecast Accuracy Analysis**: Variance analysis and improvement recommendations
4. **Action Items**: Prioritized list of initiatives for next quarter
5. **Risk Register**: Identified risks with mitigation strategies

## Success Criteria

- QBR completed within 3 business days of quarter end
- All key metrics calculated and visualized
- Clear action items with owners and timelines
- Stakeholder alignment on priorities
```

**Why This is Valid**:
- Clear, descriptive description of command purpose
- argument-hint properly formatted with square brackets
- Appropriate model (sonnet for complex analysis)
- Context explains business value
- $ARGUMENTS present in Requirements section
- Instructions reference $1 and $2 for quarter and region
- Detailed, actionable steps (3+ phases)
- Clear output format
- Success criteria defined
- Business-focused throughout

### Invalid Command Example

```markdown
---
description: QBR
argument-hint: args
---

Do a QBR.

## Instructions

1. Get data
2. Make report
```

**Why This is Invalid**:
- Description too vague ("QBR" without explanation)
- argument-hint not properly formatted (should be `[arg1] [arg2]`)
- No Context section
- Missing $ARGUMENTS in Requirements
- Instructions too vague
- No reference to arguments ($1, $2)
- No Output Format section
- Too short overall
- No business context or value articulation

### Valid Plugin Manifest Example

```json
{
  "name": "revenue-operations",
  "source": "./plugins/revenue-operations",
  "description": "Comprehensive revenue operations plugin providing sales pipeline analysis, forecasting, deal management, and revenue intelligence capabilities for sales teams.",
  "version": "1.0.0",
  "author": {
    "name": "Your Name",
    "url": "https://example.com"
  },
  "homepage": "https://github.com/user/revenue-operations",
  "repository": "https://github.com/user/revenue-operations",
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
    "./agents/pipeline-manager"
  ],
  "skills": [
    "./skills/forecasting-methods",
    "./skills/pipeline-health-scoring"
  ],
  "commands": [
    "./commands/pipeline-review",
    "./commands/forecast-update"
  ]
}
```

**Why This is Valid**:
- All required fields present (name, version, description)
- Name in hyphen-case
- Version is semantic versioning
- Description 100-500 characters, clear and comprehensive
- Paths properly formatted (`./agents/`, `./skills/`, `./commands/`)
- Agent and command paths without .md extensions
- Skill paths are directories
- 2-8 components total (2 agents + 2 skills + 2 commands = 6)
- Keywords relevant and useful
- Consistent naming throughout

### Invalid Plugin Manifest Example

```json
{
  "name": "Sales_Ops",
  "version": "1",
  "description": "Sales stuff",
  "agents": [
    "agents/sales-analyst.md",
    "./agents/Pipeline_Manager"
  ],
  "skills": [
    "./skills/forecasting-methods/SKILL.md"
  ]
}
```

**Why This is Invalid**:
- Name uses underscores and not fully descriptive
- Version not semantic versioning (should be `1.0.0`)
- Description too vague and short
- Agent paths inconsistent: One missing `./`, one has `.md` extension
- One agent name inconsistent (Pipeline_Manager uses underscore)
- Skill path includes `/SKILL.md` (should be directory only)
- Missing commands (skills alone not sufficient)
- No source field

---

## Validation Implementation Notes

### Automated Validation

**Priority Order**:
1. CRITICAL validations (must pass)
2. WARNING validations (should pass)
3. INFO validations (recommendations)

**Validation Flow**:
```
Parse Component → Check Structure → Validate Content → Cross-Reference → Report
```

**Error Reporting Format**:
```
[LEVEL] Component Type - Rule ID: Description
  Location: file/path:line
  Current: actual value
  Expected: expected value
  Fix: how to resolve
```

### Manual Validation Checklist

For each component, run through:
1. Quick checklist (section 8)
2. Component-specific rules (sections 2-5)
3. Cross-component checks (section 6)
4. Business validation (section 7)

### Validation Output

**Per-Component Report**:
- Component name and type
- Validation status: PASS / FAIL / WARNINGS
- List of issues by severity
- Suggested fixes

**Plugin-Level Report**:
- Overall status
- Component summary (X/Y passed)
- Critical issues list
- Warning summary
- Recommendations

---

## Version History

**1.0.0** (2025-10-24)
- Initial validation rules specification
- Based on Anthropic Agent Skills Spec 1.0
- Adapted from wshobson/agents patterns
- Business operations context requirements
- Complete validation coverage for all component types

---

## References

- **Anthropic Agent Skills Specification**: https://github.com/anthropics/skills/blob/main/agent_skills_spec.md
- **wshobson/agents Repository**: Reference implementation patterns
- **Agentic System Builder CLAUDE.md**: Repository context and conventions
- **Meta-Agent-Builder Templates**: Component templates in this plugin

---

**End of Validation Rules**

This document should be used by the `plugin-validator` agent when validating generated components. All rules marked CRITICAL must pass. Rules marked WARNING should pass unless there's a legitimate exception. Rules marked INFO are recommendations for quality improvement.
