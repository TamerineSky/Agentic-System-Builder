# Meta-Agent Builder Implementation Plan
## Issue #9: Plugin/Agent/Skill Generator System

**Feature Branch**: `feature/meta-agent-builder-issue-9`
**Worktree Location**: `.worktrees/meta-agent-builder`
**Target**: Version 1 (Human-Guided Builder)
**Timeline**: 4-6 weeks

---

## Strategic Approach: Subagent Delegation

To conserve context for maximum orchestration, this implementation leverages specialized subagents for heavy lifting:

### Subagent Delegation Strategy

| Task | Subagent | Rationale |
|------|----------|-----------|
| Template extraction from /agents/ repo | `repo-research-analyst` | Deep repository analysis expertise |
| Agent file generation | `docs-architect` | Technical documentation creation |
| Skill creation with progressive disclosure | `best-practices-researcher` | Pattern research and documentation |
| Validation rules | `pattern-recognition-specialist` | Pattern matching and rule creation |
| Testing scenarios | `testing-automation-agent` | Test design expertise |
| Final documentation | `docs-architect` | Comprehensive documentation |

---

## Implementation Structure

```
plugins/
└── meta-agent-builder/
    ├── .claude-plugin/
    │   └── plugin.json           # Plugin manifest
    ├── agents/                    # 7 meta-agents (Version 1)
    │   ├── domain-analyzer.md
    │   ├── agent-generator.md
    │   ├── skill-builder.md
    │   ├── command-composer.md
    │   ├── orchestration-designer.md
    │   ├── integration-architect.md
    │   └── plugin-validator.md
    ├── skills/                    # 4 meta-skills
    │   ├── meta-plugin-patterns/
    │   │   └── SKILL.md
    │   ├── agent-creation-patterns/
    │   │   └── SKILL.md
    │   ├── skill-development-patterns/
    │   │   └── SKILL.md
    │   └── orchestration-templates/
    │       └── SKILL.md
    ├── commands/                  # 7 generation commands
    │   ├── generate-plugin.md
    │   ├── generate-agent.md
    │   ├── generate-skill.md
    │   ├── generate-command.md
    │   ├── generate-orchestration.md
    │   ├── validate-plugin.md
    │   └── optimize-plugin.md
    ├── templates/                 # Component templates
    │   ├── agent-template.md
    │   ├── skill-template.md
    │   ├── command-template.md
    │   └── plugin-manifest-template.json
    └── README.md                  # Plugin documentation
```

---

## Phase 1: Foundation - Templates & Validation (Week 1)

### Task 1.1: Extract Templates from Reference Repo
**Delegate to**: `repo-research-analyst`

**Prompt**:
```
Analyze the wshobson/agents repository at ../../../agents/ and extract the following templates:

1. **Agent Template**: Analyze 5-10 agents from different plugins to identify the common structure:
   - Frontmatter format (name, description, model, tools)
   - System prompt structure
   - Capabilities section format
   - Response approach section
   - Example usage patterns

2. **Skill Template**: Analyze 5-10 skills to extract:
   - YAML frontmatter format
   - Progressive disclosure structure (metadata → instructions → resources)
   - Activation criteria patterns
   - Content organization

3. **Command Template**: Analyze 5-10 commands to extract:
   - Frontmatter format
   - Argument handling patterns
   - Workflow structure
   - Documentation style

4. **Plugin Manifest Template**: Extract from .claude-plugin/marketplace.json:
   - Plugin definition structure
   - Agents/skills/commands array format
   - Metadata requirements

Create markdown templates with placeholders for variables like {{AGENT_NAME}}, {{DESCRIPTION}}, {{MODEL}}, etc.

Save templates to: plugins/meta-agent-builder/templates/
```

**Expected Output**:
- `templates/agent-template.md`
- `templates/skill-template.md`
- `templates/command-template.md`
- `templates/plugin-manifest-template.json`

---

### Task 1.2: Create Validation Rules
**Delegate to**: `pattern-recognition-specialist`

**Prompt**:
```
Based on the Anthropic Agent Skills Specification and wshobson/agents patterns, create validation rules for:

1. **Agent Validation**:
   - Required frontmatter fields (name, description, model)
   - Name format (hyphen-case)
   - Description format and length
   - Model values (sonnet, haiku, opus)
   - System prompt completeness

2. **Skill Validation**:
   - Required YAML frontmatter
   - Description must include "Use when" clause
   - Description < 1024 characters
   - Progressive disclosure structure
   - SKILL.md filename requirement

3. **Command Validation**:
   - Required frontmatter fields
   - Argument hint format
   - Workflow completeness

4. **Plugin Validation**:
   - Directory structure requirements
   - plugin.json completeness
   - File naming conventions
   - Component cross-references

Create a validation specification document that can be used by the plugin-validator agent.

Save to: plugins/meta-agent-builder/validation-rules.md
```

**Expected Output**:
- `validation-rules.md` with comprehensive validation criteria

---

## Phase 2: Meta-Agents Creation (Week 2)

### Task 2.1: Create Domain Analyzer Agent
**Delegate to**: `docs-architect`

**Prompt**:
```
Create the domain-analyzer agent based on Issue #9 specifications:

**Agent Name**: domain-analyzer
**Model**: sonnet
**Purpose**: Analyze business domain requirements and map to agentic system patterns

**System Prompt Should Include**:
1. Expertise in business operations domains (RevOps, SupplyOps, MarketingOps, etc.)
2. Ability to interview users with clarifying questions
3. Capability to identify key processes and pain points
4. Mapping requirements to plugin patterns from reference repository
5. Recommending agent roles and capabilities
6. Suggesting appropriate skills and knowledge packages
7. Identifying integration requirements with business systems
8. Assessing complexity and scope

**Capabilities Section**:
- Interview techniques for business requirements
- Process mapping methodologies
- Pattern matching to existing plugins
- Complexity assessment frameworks
- Integration requirement analysis

**Response Approach**:
1. Ask 5-7 targeted questions about the business domain
2. Analyze responses to identify patterns
3. Map to existing patterns in wshobson/agents
4. Recommend plugin structure
5. Suggest specific agents, skills, and commands
6. Provide complexity estimate

Use the agent template from templates/agent-template.md

Save to: plugins/meta-agent-builder/agents/domain-analyzer.md
```

**Expected Output**: `agents/domain-analyzer.md`

---

### Task 2.2: Create Agent Generator Agent
**Delegate to**: `docs-architect`

**Prompt**:
```
Create the agent-generator agent based on Issue #9 specifications:

**Agent Name**: agent-generator
**Model**: sonnet
**Purpose**: Generate specialized agent definitions from business role descriptions

**System Prompt Should Include**:
1. Expertise in creating AI agent system prompts
2. Understanding of business operations roles
3. Model selection criteria (Sonnet vs Haiku)
4. Tool access configuration
5. Activation criteria design
6. Example generation

**Capabilities Section**:
- System prompt generation for business roles
- Capability definition and scoping
- Model selection (Sonnet for reasoning, Haiku for execution)
- Tool access configuration (Read, Write, Bash, etc.)
- Activation criteria design
- Usage example creation
- Agent specification validation

**Response Approach**:
1. Analyze business role description
2. Identify required capabilities
3. Select appropriate model based on complexity
4. Generate comprehensive system prompt
5. Create activation criteria
6. Generate usage examples
7. Validate against agent template

Use the agent template and reference agents from ../../../agents/plugins/

Save to: plugins/meta-agent-builder/agents/agent-generator.md
```

**Expected Output**: `agents/agent-generator.md`

---

### Task 2.3: Create Remaining 5 Meta-Agents
**Delegate to**: `docs-architect` (batch task)

**Prompt**:
```
Create the remaining 5 meta-agents for Version 1 of the Meta-Agent Builder plugin:

1. **skill-builder** (Model: sonnet)
   - Creates agent skills with progressive disclosure architecture
   - Packages domain knowledge into SKILL.md format
   - Ensures Anthropic specification compliance
   - Optimizes for token efficiency

2. **command-composer** (Model: haiku)
   - Generates slash commands from workflow descriptions
   - Creates parameterized, reusable templates
   - Handles argument structures
   - Generates documentation

3. **orchestration-designer** (Model: sonnet)
   - Designs multi-agent workflow orchestrations
   - Creates phase-based workflows
   - Plans context passing between agents
   - Designs error handling and quality checkpoints

4. **integration-architect** (Model: sonnet)
   - Designs integrations with business systems (CRM, ERP, etc.)
   - Creates API connection patterns
   - Handles authentication and data transformation
   - Generates integration code and documentation

5. **plugin-validator** (Model: haiku)
   - Validates plugin structure and completeness
   - Checks file naming and organization
   - Verifies frontmatter requirements
   - Tests agent activations
   - Generates validation reports

For each agent:
- Use agent-template.md as the base
- Reference similar agents from ../../../agents/plugins/
- Include comprehensive capabilities and response approach
- Add specific examples for that agent's function

Save to: plugins/meta-agent-builder/agents/[agent-name].md
```

**Expected Output**:
- `agents/skill-builder.md`
- `agents/command-composer.md`
- `agents/orchestration-designer.md`
- `agents/integration-architect.md`
- `agents/plugin-validator.md`

---

## Phase 3: Meta-Skills Creation (Week 3)

### Task 3.1: Create Meta-Plugin Patterns Skill
**Delegate to**: `best-practices-researcher`

**Prompt**:
```
Create the meta-plugin-patterns skill based on Issue #9 and wshobson/agents patterns:

**Skill Name**: meta-plugin-patterns
**Description**: Comprehensive patterns for plugin organization, naming, and structure from the Agentic System Builder framework. Use when generating plugins or validating plugin architecture.

**Content Structure**:

1. **When to Use This Skill** (Activation Criteria)
   - Generating new plugins
   - Validating plugin architecture
   - Organizing plugin components
   - Applying naming conventions

2. **Plugin Structure Templates**
   - Reference: wshobson/agents .claude-plugin/marketplace.json
   - Directory structure patterns
   - Component organization (agents/, skills/, commands/)
   - File naming conventions (hyphen-case)
   - plugin.json manifest format

3. **Naming Conventions**
   - Plugin names: {domain}-operations
   - Agent names: {role}-{function}
   - Skill names: {methodology}-patterns
   - Command names: {action}-{object}

4. **Organization Patterns**
   - By business function (revenue, supply, marketing)
   - By process type (forecasting, analysis, planning)
   - By domain expertise (sales, logistics, campaigns)

5. **Best Practices**
   - Token optimization through granular design
   - Composability principles
   - Single responsibility focus
   - Progressive disclosure for skills
   - Model selection guidelines

6. **Examples**
   - Extract 3-5 well-structured plugins from ../../../agents/plugins/
   - Show complete directory structures
   - Demonstrate naming consistency

Use progressive disclosure: overview → detailed patterns → examples
Use skill-template.md as base structure

Save to: plugins/meta-agent-builder/skills/meta-plugin-patterns/SKILL.md
```

**Expected Output**: `skills/meta-plugin-patterns/SKILL.md`

---

### Task 3.2: Create Remaining 3 Meta-Skills
**Delegate to**: `best-practices-researcher` (batch task)

**Prompt**:
```
Create the remaining 3 meta-skills for the Meta-Agent Builder plugin:

1. **agent-creation-patterns**
   - Description: Patterns and templates for creating specialized business operations agents. Use when generating agent definitions.
   - Content: Agent anatomy, system prompt templates by business function, model selection logic, tool access patterns, activation criteria design, usage examples
   - Reference: Extract patterns from ../../../agents/docs/agents.md and 10+ actual agent files

2. **skill-development-patterns**
   - Description: Progressive disclosure architecture and skill specification patterns. Use when creating agent skills.
   - Content: Progressive disclosure structure (metadata → instructions → resources), activation criteria design, token optimization techniques, Anthropic spec compliance
   - Reference: Extract from ../../../agents/docs/agent-skills.md and actual SKILL.md files

3. **orchestration-templates**
   - Description: Multi-agent orchestration patterns for common business processes. Use when designing workflows.
   - Content: Sequential patterns (linear workflows), parallel patterns (concurrent execution), conditional patterns (branching logic), iterative patterns (refinement loops), context passing, error handling
   - Reference: Extract from ../../../agents/docs/usage.md and orchestration examples

For each skill:
- Use skill-template.md as base
- Include clear "Use when" activation clause in description
- Structure with progressive disclosure
- Add concrete examples from reference repository
- Keep descriptions under 1024 characters

Save to: plugins/meta-agent-builder/skills/[skill-name]/SKILL.md
```

**Expected Output**:
- `skills/agent-creation-patterns/SKILL.md`
- `skills/skill-development-patterns/SKILL.md`
- `skills/orchestration-templates/SKILL.md`

---

## Phase 4: Generation Commands (Week 3-4)

### Task 4.1: Create Plugin Generation Commands
**Self-Implementation** (these are simpler, use command template)

Create these 7 commands using the command-template.md:

1. **generate-plugin.md** - Interactive wizard for complete plugin creation
2. **generate-agent.md** - Create individual agent from role description
3. **generate-skill.md** - Create skill with progressive disclosure
4. **generate-command.md** - Create slash command from workflow
5. **generate-orchestration.md** - Design multi-agent orchestration
6. **validate-plugin.md** - Validate plugin structure and completeness
7. **optimize-plugin.md** - Analyze and optimize for token efficiency

Each command should:
- Use appropriate arguments
- Reference meta-agents and meta-skills
- Include step-by-step workflow
- Provide clear output format

Save to: plugins/meta-agent-builder/commands/

---

## Phase 5: Plugin Manifest & Documentation (Week 4)

### Task 5.1: Create Plugin Manifest
**Self-Implementation**

Create `.claude-plugin/plugin.json`:
```json
{
  "name": "meta-agent-builder",
  "version": "1.0.0",
  "description": "Plugin/Agent/Skill generator system for building business operations agentic systems",
  "author": "Agentic System Builder",
  "agents": [
    "./agents/domain-analyzer",
    "./agents/agent-generator",
    "./agents/skill-builder",
    "./agents/command-composer",
    "./agents/orchestration-designer",
    "./agents/integration-architect",
    "./agents/plugin-validator"
  ],
  "skills": [
    "./skills/meta-plugin-patterns",
    "./skills/agent-creation-patterns",
    "./skills/skill-development-patterns",
    "./skills/orchestration-templates"
  ],
  "commands": [
    "./commands/generate-plugin",
    "./commands/generate-agent",
    "./commands/generate-skill",
    "./commands/generate-command",
    "./commands/generate-orchestration",
    "./commands/validate-plugin",
    "./commands/optimize-plugin"
  ]
}
```

---

### Task 5.2: Create Plugin README
**Delegate to**: `docs-architect`

**Prompt**:
```
Create a comprehensive README.md for the meta-agent-builder plugin:

**Structure**:
1. Overview - What this plugin does (meta-system that builds other systems)
2. Concept - Explanation of meta-agents
3. Version 1 Features - Human-guided builder capabilities
4. Installation - How to use this plugin
5. Quick Start - Simple example of generating a plugin
6. Components:
   - 7 Meta-Agents (brief description of each)
   - 4 Meta-Skills (brief description of each)
   - 7 Commands (usage examples)
7. Workflow - Step-by-step process of plugin generation
8. Examples - Complete example of generating a sales-operations plugin
9. Validation - How validation works
10. Best Practices - Tips for using the meta-agent system
11. Roadmap - Version 2 (Autonomous Meta-Agent) plans
12. References - Links to Issues #1-9

Use the existing README.md as a style guide but focus on this specific plugin.

Save to: plugins/meta-agent-builder/README.md
```

**Expected Output**: `README.md`

---

## Phase 6: Testing & Validation (Week 5)

### Task 6.1: Test with Sample Domain
**Delegate to**: `testing-automation-agent`

**Prompt**:
```
Test the meta-agent-builder plugin by generating a simple business operations plugin:

**Test Scenario**: Generate a "customer-retention-operations" plugin

**Steps**:
1. Use domain-analyzer to analyze customer retention domain
2. Use agent-generator to create 2-3 retention-focused agents:
   - churn-predictor
   - retention-strategist
   - customer-health-scorer
3. Use skill-builder to create 1-2 skills:
   - churn-prediction-models
   - retention-strategies
4. Use command-composer to create 2-3 commands:
   - /analyze-churn-risk
   - /retention-plan
5. Use plugin-validator to validate the generated plugin

**Validation Criteria**:
- All files created with correct structure
- Frontmatter complies with specifications
- Content is coherent and business-relevant
- Skills follow progressive disclosure
- Plugin manifest is valid JSON

Document results, issues found, and fixes needed.

Save test results to: plugins/meta-agent-builder/tests/customer-retention-test.md
```

**Expected Output**:
- Test results documentation
- Sample generated plugin (for validation)
- List of issues and improvements

---

### Task 6.2: Refinement Based on Testing
**Self-Implementation**

Based on test results:
1. Fix any issues in meta-agents
2. Improve templates
3. Enhance validation rules
4. Update documentation

---

## Phase 7: Final Documentation & PR (Week 5-6)

### Task 7.1: Create Comprehensive Documentation
**Delegate to**: `docs-architect`

**Prompt**:
```
Create comprehensive documentation for the meta-agent-builder plugin:

1. **User Guide** (docs/meta-agent-builder-guide.md):
   - Getting started
   - Step-by-step tutorials
   - Best practices
   - Troubleshooting

2. **Developer Guide** (docs/meta-agent-builder-dev.md):
   - Architecture overview
   - Component details
   - Extension points
   - Contributing guidelines

3. **API Reference** (docs/meta-agent-builder-api.md):
   - All agents with usage examples
   - All skills with activation examples
   - All commands with parameter references

Save to: docs/
```

---

### Task 7.2: Create Pull Request
**Self-Implementation**

```bash
# Stage all changes
git add .

# Commit
git commit -m "feat: Implement Meta-Agent Builder (Issue #9)

- Add 7 meta-agents for plugin/agent/skill generation
- Add 4 meta-skills with framework patterns
- Add 7 generation commands
- Include templates and validation rules
- Add comprehensive documentation
- Test with sample customer-retention plugin

Version 1: Human-Guided Builder
- Interactive workflow for plugin creation
- Template-based generation
- Validation and optimization
- Ready for production use

Resolves #9

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude <noreply@anthropic.com>"

# Push to remote
git push -u origin feature/meta-agent-builder-issue-9

# Create PR
gh pr create --title "feat: Meta-Agent Builder - Plugin/Agent/Skill Generator (Issue #9)" \
  --body "$(cat <<'EOF'
## Overview
Implements the Meta-Agent Builder plugin (Issue #9, Version 1) - a self-building agentic system that generates complete plugins, agents, skills, commands, and orchestrations based on business requirements.

## What's Included

### Meta-Agents (7)
- **domain-analyzer**: Analyze business domains and map to patterns
- **agent-generator**: Generate specialized agent definitions
- **skill-builder**: Create skills with progressive disclosure
- **command-composer**: Generate workflow commands
- **orchestration-designer**: Design multi-agent orchestrations
- **integration-architect**: Design business system integrations
- **plugin-validator**: Validate generated components

### Meta-Skills (4)
- **meta-plugin-patterns**: Plugin organization and structure patterns
- **agent-creation-patterns**: Agent generation templates
- **skill-development-patterns**: Progressive disclosure architecture
- **orchestration-templates**: Multi-agent workflow patterns

### Generation Commands (7)
- `/generate-plugin` - Interactive plugin creation wizard
- `/generate-agent` - Create individual agents
- `/generate-skill` - Create skills
- `/generate-command` - Create commands
- `/generate-orchestration` - Design orchestrations
- `/validate-plugin` - Validate structure
- `/optimize-plugin` - Optimize token usage

### Supporting Components
- Component templates (agent, skill, command, plugin manifest)
- Validation rules engine
- Comprehensive documentation
- Test scenarios

## Testing
- ✅ Tested with customer-retention-operations sample plugin
- ✅ All validation rules pass
- ✅ Generated components follow framework specifications
- ✅ Progressive disclosure working correctly

## Documentation
- Plugin README with quick start
- User guide with tutorials
- Developer guide with architecture
- API reference for all components

## Next Steps
- Version 2: Autonomous Meta-Agent (Issue #9, Phase 2)
- Integration with Anthropic skills repository
- Enhanced validation and optimization
- Additional templates for specialized domains

## Related Issues
- Resolves #9
- Builds on #1, #2, #3, #4, #5, #6, #7
- Enables #8 (Implementation Projects)

## Breaking Changes
None - this is a new plugin

## Migration Guide
N/A - new feature

---

**Ready for review!** This implements the foundation for democratizing agentic system creation.
EOF
)"
```

---

## Success Criteria

### Version 1 (Human-Guided Builder)
- ✅ User can create basic plugin in 2-4 hours using the wizard
- ✅ Generated components follow framework standards
- ✅ Validation catches common issues
- ✅ Documentation is complete and clear
- ✅ 80% of use cases don't require manual editing

### Measurements
- Test with 3 different business domains
- Validate generated plugins against specifications
- Measure time-to-plugin creation
- Gather user feedback

---

## Timeline Summary

| Week | Phase | Key Deliverables |
|------|-------|------------------|
| 1 | Foundation | Templates, validation rules |
| 2 | Meta-Agents | 7 agent files |
| 3 | Meta-Skills | 4 skill directories |
| 3-4 | Commands | 7 command files |
| 4 | Manifest | plugin.json, README |
| 5 | Testing | Test results, refinements |
| 5-6 | Documentation | User/dev guides, PR |

---

## Notes

### Subagent Usage
This plan heavily leverages subagents to conserve orchestrator context:
- **repo-research-analyst**: Template extraction (deep analysis)
- **docs-architect**: Agent and documentation creation (2-3 tasks)
- **best-practices-researcher**: Skill creation (pattern research)
- **pattern-recognition-specialist**: Validation rules
- **testing-automation-agent**: Testing scenarios

### Context Conservation
By delegating heavy lifting to specialized subagents, the orchestrator:
- Maintains high-level coordination
- Makes strategic decisions
- Reviews subagent output
- Ensures consistency across components
- Focuses on integration and testing

### Reference Repository Usage
All tasks reference `../../../agents/` for proven patterns:
- Agent structures
- Skill formats
- Command styles
- Plugin organization
- Naming conventions

This ensures generated components follow established, production-tested patterns.

---

**Status**: Ready to begin Phase 1
**Next Action**: Delegate Task 1.1 to repo-research-analyst
