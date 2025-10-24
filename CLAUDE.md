# CLAUDE.md - Repository Context & Structure

> **Purpose**: This file provides essential context for Claude Code about the Agentic System Builder repository structure, relationships, and patterns to ensure efficient and accurate assistance.

---

## Repository Overview

**Agentic System Builder** is a meta-framework for building business operations agentic systems using Claude Code. It adapts software development patterns to general-purpose business operations including RevOps, SupplyOps, Marketing Operations, Finance Operations, and more.

### Key Distinction
- This repository focuses on **business operations** (sales, supply chain, marketing, finance, HR, customer success)
- Adapts patterns from software development to business domains
- Not focused on software/code development agents (that's the reference repo below)

---

## Directory Structure

```
/home/tamer/projects/Seth-Dobson-Agents/
├── Agentic-System-Builder/          # THIS REPOSITORY (Business Operations Focus)
│   ├── .git/                        # Git repository for this project
│   ├── README.md                    # Main documentation
│   ├── GETTING-STARTED.md          # Quick start guide
│   ├── CONTRIBUTING.md             # Contribution guidelines
│   ├── CLAUDE.md                   # This file (repository context)
│   ├── docs/                       # Documentation
│   │   ├── domains/                # Business domain guides (coming)
│   │   ├── reference/              # Reference catalogs (coming)
│   │   └── tutorials/              # How-to guides (coming)
│   ├── examples/                   # Example implementations
│   │   ├── revenue-operations/     # RevOps examples (coming)
│   │   ├── supply-operations/      # SupplyOps examples (coming)
│   │   └── marketing-operations/   # MarketingOps examples (coming)
│   └── templates/                  # Component templates
│       ├── agents/                 # Agent templates (coming)
│       ├── commands/               # Command templates (coming)
│       ├── plugins/                # Plugin templates (coming)
│       └── skills/                 # Skill templates (coming)
│
└── agents/                         # REFERENCE REPOSITORY (Software Development Focus)
    ├── README.md                   # Seth Dobson's original documentation
    ├── .claude-plugin/
    │   └── marketplace.json        # 63 plugin definitions
    ├── plugins/                    # 63 focused plugins
    │   ├── python-development/
    │   ├── javascript-typescript/
    │   ├── backend-development/
    │   ├── kubernetes-operations/
    │   ├── security-scanning/
    │   └── ... (58 more plugins)
    └── docs/                       # Complete documentation
        ├── agents.md               # 85 agent catalog
        ├── agent-skills.md         # 47 skills catalog
        ├── architecture.md         # Architecture patterns
        ├── plugins.md              # Plugin catalog
        └── usage.md                # Usage guide
```

---

## Key Relationships

### Parent Directory: `/home/tamer/projects/Seth-Dobson-Agents/`

Contains TWO separate repositories:

#### 1. **`/agents/`** - Reference Implementation (Seth Dobson's Repo)
- **Source**: Local copy from https://github.com/wshobson/agents
- **Focus**: Software development agents (coding, testing, deployment, infrastructure)
- **Purpose**: Reference patterns, architecture, and proven implementations
- **Status**: Complete, production-ready system with 85 agents, 47 skills, 63 plugins
- **Usage**: READ ONLY - Study patterns, don't modify

**Key Resources from /agents/**:
- `/agents/docs/agents.md` - Complete agent catalog with model assignments
- `/agents/docs/architecture.md` - Granular plugin architecture principles
- `/agents/docs/agent-skills.md` - 47 skills with progressive disclosure
- `/agents/plugins/*/` - 63 plugin implementations to reference

#### 2. **`/Agentic-System-Builder/`** - This Project (Business Operations Focus)
- **Source**: New repository being built
- **Focus**: Business operations agents (sales, supply chain, marketing, finance, HR)
- **Purpose**: Create meta-framework adapting software patterns to business domains
- **Status**: Foundation phase - documentation and GitHub issues defining architecture
- **Usage**: ACTIVE DEVELOPMENT - Build new plugins, agents, skills here

---

## GitHub Issues Structure

The Agentic System Builder project is organized through GitHub issues that define the framework:

### Core Concept Issues (#1-7):
- **Issue #1**: Foundation Concepts - Architecture & design principles
- **Issue #2**: Plugin Architecture - Organizational structure
- **Issue #3**: Specialized Agents - Domain expert agents
- **Issue #4**: Agent Skills - Modular knowledge packages
- **Issue #5**: Slash Commands - Reusable workflows
- **Issue #6**: Workflow Orchestration - Multi-agent coordination
- **Issue #7**: Business Operations Agents - Domain-specific patterns

### Implementation Issues (#8-9):
- **Issue #8**: Implementation Projects - 6 complete plugin ecosystems:
  1. Revenue Operations Plugin (sales, forecasting, pipeline)
  2. Supply Chain Operations Plugin (inventory, logistics, demand)
  3. Marketing Operations Plugin (campaigns, attribution, content)
  4. Finance Operations Plugin (budgeting, forecasting, reporting)
  5. Customer Success Operations Plugin (health scoring, churn, expansion)
  6. Human Resources Operations Plugin (workforce planning, attrition, compensation)

- **Issue #9**: Meta-Agent Builder - Plugin/Agent/Skill generator system
  - **Version 1**: Human-guided interactive builder
  - **Version 2**: Autonomous meta-agent (fully automated)

**Current Focus**: Issue #9 is the active work item - building the meta-system that generates other systems.

---

## Key Architectural Patterns

### From wshobson/agents (Software Development Focus)

#### 1. Granular Plugin Architecture
- **63 focused plugins** (not monolithic bundles)
- Average **3.4 components per plugin** (follows Anthropic's 2-8 pattern)
- Single responsibility principle
- Composability over bundling
- Token efficiency through minimal loading

#### 2. Three-Tier Component Structure
```
Plugin/
├── agents/       # Specialized AI assistants with domain expertise
├── commands/     # User-invoked reusable workflows
└── skills/       # Modular knowledge packages (progressive disclosure)
```

#### 3. Model Selection Strategy
- **Haiku (47 agents)**: Fast execution, deterministic tasks, ops work
- **Sonnet (97 agents)**: Complex reasoning, architecture, language expertise
- **Opus (1 agent)**: Highest complexity (incident-responder)

**Hybrid Orchestration Pattern**:
```
Sonnet (planning) → Haiku (execution) → Sonnet (review)
```

#### 4. Progressive Disclosure (Agent Skills)
Three-tier architecture for token efficiency:
1. **Metadata** (Frontmatter): Name + activation criteria (always loaded)
2. **Instructions**: Core guidance (loaded when activated)
3. **Resources**: Examples + templates (loaded on demand)

#### 5. Agent Anatomy
```markdown
---
name: agent-name
description: What it does. Use PROACTIVELY when [trigger].
model: sonnet|haiku|opus
tools: Read, Write, Bash, Grep, Glob
---

You are an expert in [domain]...

## Capabilities
- [List of abilities]

## Response Approach
1. [Step-by-step process]
```

#### 6. Skill Anatomy
```yaml
---
name: skill-name
description: What it does. Use when [activation trigger].
---

# Skill Content
[Progressive disclosure structure]
```

#### 7. Command Anatomy
```markdown
---
description: What this command does
argument-hint: [arg1] [arg2]
model: sonnet|haiku
---

[Detailed workflow using $1, $2 for arguments]
```

---

## Adaptation to Business Operations

### Key Differences from Software Development Focus

#### Language & Terminology
- **Software**: Technical language, code-focused
- **Business**: Domain language (pipeline, forecast, inventory, campaign)
- Use business metrics (ARR, churn, COGS) not technical metrics (latency, throughput)

#### Analysis Types
- **Software**: Code analysis, architecture review, performance profiling
- **Business**: Data analysis, trend identification, forecasting, variance analysis

#### Workflows
- **Software**: CI/CD, deployment, testing, code review
- **Business**: Pipeline reviews, QBRs, S&OP meetings, budget planning

#### Integration Points
- **Software**: Git, CI/CD tools, monitoring systems
- **Business**: CRMs (Salesforce, HubSpot), ERPs (SAP, NetSuite), data warehouses

#### Success Metrics
- **Software**: Code quality, test coverage, deployment frequency
- **Business**: Time savings, forecast accuracy, process efficiency, decision quality

---

## Working with This Repository

### When Starting New Work

1. **Check GitHub Issues First**: All specifications are in issues #1-9
2. **Reference /agents/ for Patterns**: Don't reinvent - adapt proven patterns
3. **Focus on Business Context**: This is about RevOps, not DevOps
4. **Follow Naming Conventions**:
   - Plugins: `domain-operations` (e.g., `revenue-operations`)
   - Agents: `business-role-expert` (e.g., `sales-analyst`, `demand-forecaster`)
   - Skills: `business-methodology` (e.g., `pipeline-health-scoring`)
   - Commands: `/domain-action` (e.g., `/pipeline-review`, `/forecast-update`)

### Current State (as of implementation)

**Completed**:
- ✅ README.md - Framework overview
- ✅ GETTING-STARTED.md - Quick start guide
- ✅ CONTRIBUTING.md - Contribution guidelines
- ✅ GitHub Issues #1-9 - Complete specifications
- ✅ CLAUDE.md - This file (repository context)

**In Progress**:
- 🚧 Issue #9: Meta-Agent Builder implementation

**Upcoming**:
- 📋 Documentation files for docs/ directory (based on issues)
- 📋 Example implementations for examples/ directory
- 📋 Component templates for templates/ directory
- 📋 6 complete plugins from Issue #8

---

## Development Guidelines

### File Locations

**Creating New Business Operations Plugins**:
```
Agentic-System-Builder/
└── plugins/
    └── {domain}-operations/
        ├── .claude-plugin/
        │   └── plugin.json
        ├── agents/
        │   ├── {role}-{function}.md
        │   └── ...
        ├── skills/
        │   ├── {methodology}/SKILL.md
        │   └── ...
        └── commands/
            ├── {action}.md
            └── ...
```

**Documentation**:
```
Agentic-System-Builder/
└── docs/
    ├── domains/                    # Business domain guides
    │   ├── revenue-operations.md
    │   ├── supply-operations.md
    │   └── ...
    ├── reference/                  # Catalogs
    │   ├── agent-catalog.md
    │   ├── skills-catalog.md
    │   └── ...
    └── tutorials/                  # How-to guides
        └── ...
```

**Examples**:
```
Agentic-System-Builder/
└── examples/
    ├── revenue-operations/
    │   ├── README.md
    │   ├── sample-data/
    │   └── use-cases/
    └── ...
```

### Referencing Patterns

**Always reference /agents/ patterns when building new components**:
```
# Example: Building a revenue-operations plugin
# Reference: /agents/plugins/backend-development/
# Adapt: Backend patterns → Business operations patterns
# Change: API design → Pipeline design
# Change: Database optimization → Forecast accuracy
```

### Testing Approach

1. **Pattern Validation**: Does it follow /agents/ architecture?
2. **Business Relevance**: Does it solve real business operations needs?
3. **Token Efficiency**: Is progressive disclosure used?
4. **Composability**: Can it work with other plugins?
5. **Naming Clarity**: Is the purpose immediately obvious?

---

## Common Tasks & Quick References

### Finding Pattern Examples

**Task**: "I need to create a new agent for sales forecasting"
**Reference**: `/agents/plugins/*/agents/*.md` - Study agent structure
**Adapt**: Change from code-focused to business-focused system prompt

**Task**: "I need to understand skill progressive disclosure"
**Reference**: `/agents/docs/agent-skills.md` - Read full specification
**Examples**: `/agents/plugins/*/skills/*/SKILL.md` - See implementations

**Task**: "I need to create a multi-agent orchestration"
**Reference**: `/agents/docs/usage.md` - Multi-agent workflow examples
**Adapt**: Change from software workflows to business process workflows

### Reading GitHub Issues

**Task**: "What should a plugin contain?"
**Answer**: Issue #2 - Plugin Architecture

**Task**: "How do I design specialized agents?"
**Answer**: Issue #3 - Specialized Agents

**Task**: "What business domains should I target?"
**Answer**: Issue #8 - Implementation Projects (6 domains defined)

**Task**: "How do I build the meta-agent?"
**Answer**: Issue #9 - Meta-Agent Builder (current focus)

---

## Important Notes

### DO:
✅ Reference `/agents/` repo extensively for proven patterns
✅ Adapt software patterns to business operations contexts
✅ Follow progressive disclosure for skills
✅ Use appropriate models (Haiku for speed, Sonnet for reasoning)
✅ Maintain token efficiency through granular design
✅ Check GitHub issues for specifications before building
✅ Focus on business operations domains (RevOps, SupplyOps, etc.)

### DON'T:
❌ Modify files in `/agents/` directory (reference only)
❌ Create software development agents (use /agents/ for that)
❌ Build monolithic "do everything" plugins
❌ Ignore progressive disclosure patterns
❌ Mix business and technical contexts inappropriately
❌ Duplicate what already exists in /agents/ - adapt it

---

## Version Control & Collaboration

### Git Repository
- **Location**: `/home/tamer/projects/Seth-Dobson-Agents/Agentic-System-Builder/.git`
- **Remote**: TamerineSky/Agentic-System-Builder (GitHub)
- **Branch**: master
- **Status**: Clean working tree (as of last check)

### Commit Strategy
- Use descriptive commit messages
- Reference GitHub issue numbers
- Group related changes
- Document significant pattern decisions

---

## Resources & External References

### Official Documentation
- [Claude Code Documentation](https://docs.claude.com/en/docs/claude-code/overview)
- [Plugins Guide](https://docs.claude.com/en/docs/claude-code/plugins)
- [Subagents Guide](https://docs.claude.com/en/docs/claude-code/sub-agents)
- [Agent Skills Guide](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)
- [Slash Commands Reference](https://docs.claude.com/en/docs/claude-code/slash-commands)

### Reference Repositories
- [wshobson/agents](https://github.com/wshobson/agents) - Original software development repo (local copy at `/agents/`)
- [anthropics/skills](https://github.com/anthropics/skills) - Official Anthropic skills repository
- [Agent Skills Specification](https://github.com/anthropics/skills/blob/main/agent_skills_spec.md)

### This Repository
- **GitHub**: TamerineSky/Agentic-System-Builder
- **Issues**: Core specifications in issues #1-9
- **Local**: `/home/tamer/projects/Seth-Dobson-Agents/Agentic-System-Builder/`

---

## Current Implementation Status

### Phase: Foundation & Meta-Agent Development

**Active Work**: Issue #9 - Meta-Agent Builder
- Building system that generates other agentic systems
- Version 1: Human-guided interactive builder (in progress)
- Version 2: Autonomous meta-agent (planned)

**Next Steps**:
1. Create component templates directory
2. Build domain-analyzer agent (first meta-agent)
3. Build remaining 6 meta-agents
4. Create 4 meta-skills
5. Implement 7 generation commands
6. Test with real business domains from Issue #8

---

## Tips for Future Claude Sessions

### Context Restoration
If starting a new session, read these files in order:
1. `CLAUDE.md` (this file) - Repository structure
2. `README.md` - Framework overview
3. `GETTING-STARTED.md` - Quick start
4. Relevant GitHub issue - Specific task context
5. `/agents/docs/architecture.md` - Pattern reference

### Quick Orientation
```bash
# Where am I?
pwd
# Should show: /home/tamer/projects/Seth-Dobson-Agents/Agentic-System-Builder

# What's the current task?
gh issue list --state open
# Should show open GitHub issues

# What patterns can I reference?
ls ../agents/plugins/
# Shows all reference plugins from Seth Dobson's repo
```

### Pattern Lookup
```bash
# Find agent examples
find ../agents/plugins -name "*.md" -path "*/agents/*"

# Find skill examples
find ../agents/plugins -name "SKILL.md"

# Find command examples
find ../agents/plugins -name "*.md" -path "*/commands/*"
```

---

## Acknowledgments

This framework is built upon:
- **Seth Dobson's wshobson/agents repository** - Proven patterns and architecture
- **Anthropic's Claude Code** - Platform and capabilities
- **Anthropic's Agent Skills Specification** - Skills architecture

---

**Last Updated**: 2025-10-24
**Maintained By**: Project team
**Purpose**: Ensure Claude Code has complete context for efficient assistance

---

## Quick Reference Card

| Need | Location |
|------|----------|
| Framework overview | `README.md` |
| Quick start guide | `GETTING-STARTED.md` |
| Repository context | `CLAUDE.md` (this file) |
| Task specifications | GitHub Issues #1-9 |
| Pattern reference | `../agents/docs/*.md` |
| Plugin examples | `../agents/plugins/*/` |
| Architecture patterns | `../agents/docs/architecture.md` |
| Agent catalog | `../agents/docs/agents.md` |
| Skills catalog | `../agents/docs/agent-skills.md` |

---

**Remember**: This is a business operations framework adapting software development patterns. Always translate technical concepts to business contexts!
