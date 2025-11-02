---
description: Validate plugin structure, completeness, and quality
argument-hint: [plugin-path]
version: "1.0.0"
tags: [validation, quality, testing, plugin]
tool_access: [Read, Bash, Grep, Glob]
model: haiku
---

# Validate Plugin

Comprehensive validation of plugin structure, component quality, and adherence to architectural patterns.

## Context

Plugin validation ensures that generated or manually created plugins meet quality standards and follow established architectural patterns. This command performs automated checks across structure, content, and integration points.

## Requirements

**Plugin Path**: $1 (e.g., "plugins/revenue-operations" or absolute path)

If not provided, will validate all plugins in the current workspace.

## Instructions

### 1. Load Validation Rules & Standards

**Objective**: Establish the criteria against which the plugin will be validated.

**Actions**:
- Load structural requirements:
  - Required directory structure
  - File naming conventions
  - Frontmatter schemas
  - Component type definitions
- Load quality standards:
  - Token budget limits
  - Documentation completeness
  - Naming conventions
  - Progressive disclosure patterns
- Load architectural patterns:
  - Granular plugin principles (2-8 components)
  - Three-tier component structure
  - Model selection guidelines
  - Tool access minimization
- Invoke the `plugin-validator` meta-agent

**Validation Rules**:
```yaml
structure:
  required_directories: [agents, commands, skills, .claude-plugin]
  required_files: [.claude-plugin/plugin.json, README.md]

naming:
  plugin: kebab-case, suffix "-operations" or specific domain
  agents: kebab-case, format "{role}-{function}"
  skills: kebab-case, directory with SKILL.md
  commands: kebab-case, .md extension

quality:
  agent_token_limit: 5000
  skill_tier1_limit: 100
  skill_tier2_limit: 2000
  component_count: [2, 8]

content:
  frontmatter_required: [name, description, model]
  business_language: true
  progressive_disclosure: true (skills only)
```

**Output**: Loaded validation rules and standards

### 2. Structural Validation

**Objective**: Verify directory structure and file organization.

**Actions**:
- Check plugin directory exists at specified path
- Verify required directories present:
  - `.claude-plugin/` (plugin manifest)
  - `agents/` (if any agents defined)
  - `skills/` (if any skills defined)
  - `commands/` (if any commands defined)
- Validate plugin.json:
  - File exists and is valid JSON
  - Contains required fields (name, version, description)
  - Component lists match actual files
  - Version follows semantic versioning
- Check file naming conventions:
  - Agents: `{name}.md` in kebab-case
  - Skills: `{name}/SKILL.md` structure
  - Commands: `{name}.md` in kebab-case
- Verify README.md exists and has minimum content
- Check for unexpected files or directories

**Validation Checks**:
```
✓ Plugin directory exists
✓ Required directories present
✓ plugin.json valid and complete
✓ All agent files follow naming convention
✓ All skill directories have SKILL.md
✓ All command files properly named
✓ README.md exists
✗ Unexpected file found: temp.txt
```

**Output**: Structural validation report with pass/fail for each check

### 3. Component Content Validation

**Objective**: Verify each component meets content quality standards.

**Actions**:
- **Validate Agents**:
  - Frontmatter complete (name, description, model, tools)
  - Description includes proactive trigger
  - Model selection is appropriate (sonnet/haiku/opus)
  - Tool access is minimal but sufficient
  - System prompt uses business language
  - Capabilities are enumerated
  - Response approach is defined
  - Token count within limits (< 5000)

- **Validate Skills**:
  - Frontmatter complete (name, description, version)
  - Three-tier progressive disclosure structure
  - Tier 1 (metadata) < 100 tokens
  - Tier 2 (instructions) actionable and clear
  - Tier 3 (resources) properly organized
  - Activation trigger is specific
  - Total token count reasonable (< 10k)

- **Validate Commands**:
  - Frontmatter complete (description, argument-hint, model)
  - Parameters properly referenced ($1, $2, $3)
  - Workflow steps are sequential and clear
  - Agent invocations are correct
  - Output format specified
  - Success criteria defined
  - Token count reasonable

**Component Validation Example**:
```
Agent: sales-analyst
✓ Frontmatter complete
✓ Model: sonnet (appropriate for analysis)
✓ Tools: Read, Grep (minimal)
✓ Business language used
✗ Warning: Token count 5200 (exceeds 5000 limit)
✓ Capabilities enumerated (5)
✓ Proactive trigger in description

Skill: pipeline-health-scoring
✓ Progressive disclosure structure
✓ Tier 1: 85 tokens
✓ Tier 2: 1850 tokens
✓ Activation trigger clear
✗ Warning: Missing examples in Tier 3

Command: pipeline-review
✓ Frontmatter complete
✓ Parameters: $1, $2 properly used
✓ 5 sequential steps
✗ Error: References non-existent agent "forecaster"
```

**Output**: Component-by-component validation results

### 4. Integration & Cross-Reference Validation

**Objective**: Ensure components reference each other correctly and integrate properly.

**Actions**:
- Validate agent-to-skill references:
  - Agents mention skills that exist
  - Skill names are spelled correctly
  - Activation criteria are consistent
- Validate command-to-agent orchestration:
  - Commands invoke agents that exist
  - Agent names in commands match file names
  - Command parameters align with agent expectations
- Check for circular dependencies:
  - Agent A references Skill B which references Agent A
  - Command C invokes Command D which invokes Command C
- Verify plugin.json completeness:
  - All component files are listed
  - No listed components are missing
  - Versions are consistent
- Validate naming consistency:
  - Component names match across references
  - No naming conflicts or duplicates

**Integration Checks**:
```
Cross-References:
✓ sales-analyst → pipeline-health-scoring (skill exists)
✓ pipeline-review → sales-analyst (agent exists)
✗ forecast-update → demand-forecaster (agent not found)

plugin.json:
✓ All agents listed
✓ All skills listed
✗ Command "pipeline-review" not in manifest

Dependencies:
✓ No circular references detected
```

**Output**: Integration validation report

### 5. Quality & Best Practices Assessment

**Objective**: Evaluate adherence to architectural patterns and best practices.

**Actions**:
- Check component count:
  - Total components in range 2-8 (granular plugin principle)
  - If outside range, flag for review
- Evaluate token efficiency:
  - Agent token counts reasonable
  - Skills use progressive disclosure
  - No excessive redundancy
- Assess business language usage:
  - Descriptions use domain terms
  - System prompts avoid technical jargon
  - Examples are business-relevant
- Review model selection:
  - Haiku for fast, deterministic tasks
  - Sonnet for complex reasoning
  - Hybrid orchestration where appropriate
- Check documentation quality:
  - README is comprehensive
  - Each component has clear description
  - Usage examples provided
  - Architecture is documented
- Validate naming conventions:
  - Plugin name follows domain-operations pattern
  - Agent names use business roles
  - Skill names describe methodologies
  - Command names are action-oriented

**Quality Metrics**:
```
Component Count: 5 (optimal: 2-8) ✓
Token Efficiency:
  - Agents avg: 3800 tokens ✓
  - Skills avg: 4200 tokens ✓
  - Commands avg: 1500 tokens ✓

Business Language: 95% ✓
Model Selection: Appropriate ✓
Documentation: Complete ✓

Recommendations:
- Consider splitting large agents
- Add more usage examples
- Document integration patterns
```

**Output**: Quality assessment report with recommendations

### 6. Generate Validation Report

**Objective**: Produce comprehensive validation report with actionable findings.

**Actions**:
- Compile all validation results
- Categorize issues:
  - **Critical Errors**: Must fix (broken references, missing files)
  - **Warnings**: Should fix (exceeds limits, missing optional)
  - **Recommendations**: Nice to have (optimization opportunities)
- Provide remediation guidance for each issue
- Calculate overall quality score
- Generate summary statistics
- Create prioritized fix list

**Report Format**:
```markdown
# Plugin Validation Report: revenue-operations

## Summary
- Status: PASS WITH WARNINGS
- Components: 5 (agents: 2, skills: 2, commands: 1)
- Issues: 0 critical, 3 warnings, 5 recommendations
- Quality Score: 85/100

## Critical Errors (0)
None

## Warnings (3)
1. Agent "sales-analyst" exceeds token limit (5200 > 5000)
   - Remediation: Extract knowledge to skill or split agent

2. Skill "pipeline-health-scoring" missing Tier 3 examples
   - Remediation: Add at least 2 examples to Resources section

3. Command "forecast-update" not listed in plugin.json
   - Remediation: Add to manifest file

## Recommendations (5)
1. Add ARCHITECTURE.md to document design decisions
2. Include usage examples in README.md
3. Consider adding integration-test command
4. Document token efficiency strategies
5. Add CONTRIBUTING.md for extension guidance

## Component Details
[Detailed per-component validation results]

## Next Steps
1. Fix critical errors (if any)
2. Address warnings
3. Consider recommendations
4. Re-run validation
```

**Output**: Complete validation report

## Output Format

The command produces:

1. **Console Output**:
```
Validating plugin: revenue-operations
✓ Structure validation complete
✓ Component validation complete
⚠ Integration validation warnings
✓ Quality assessment complete

Summary: PASS WITH WARNINGS
Issues: 0 critical, 3 warnings, 5 recommendations
Quality Score: 85/100

Full report: plugins/revenue-operations/VALIDATION-REPORT.md
```

2. **Validation Report File**: `{plugin-path}/VALIDATION-REPORT.md`

3. **Issue List**: Prioritized list of items to address

4. **Quality Metrics**: Detailed metrics and benchmarks

## Success Criteria

- All structural requirements met
- No critical errors found
- Component count within optimal range (2-8)
- All cross-references valid
- Token budgets within limits
- Business language used consistently
- Documentation is complete
- Naming conventions followed
- plugin.json matches actual components
- No circular dependencies
- Model selections are appropriate
- Progressive disclosure used in skills
- Quality score > 70/100

## Related Plugins

- **meta-agent-builder**: Parent plugin for generation
- **quality-assurance**: Additional quality checks
- **plugin-optimizer**: Token and performance optimization

---

**Tip**: Run validation after any plugin changes to catch issues early. Fix critical errors first, then warnings, then consider recommendations.

**Automation**: This command can be integrated into CI/CD pipelines to validate plugins before deployment or commit.
