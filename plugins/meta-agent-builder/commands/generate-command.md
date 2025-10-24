---
description: Create slash command from workflow description
argument-hint: [command-name] [workflow-description]
version: "1.0.0"
tags: [generator, command, workflow, slash-command]
tool_access: [Read, Write, Bash, Grep, Glob]
model: haiku
---

# Generate Slash Command

Create a user-facing workflow command that orchestrates agents and provides reusable business processes.

## Context

Slash commands are reusable workflows that users invoke with `/command-name`. They:
- Orchestrate one or more agents
- Accept parameters via $1, $2, $3 notation
- Provide step-by-step instructions
- Define clear output formats
- Include validation criteria

Commands make complex multi-agent workflows accessible and repeatable.

## Requirements

**Command Name**: $1 (e.g., "pipeline-review", "forecast-update")
**Workflow Description**: $2 (e.g., "Analyze sales pipeline health and identify at-risk deals")

## Instructions

### 1. Workflow Analysis & Decomposition

**Objective**: Break the workflow into clear, sequential steps.

**Actions**:
- Invoke the `command-composer` meta-agent with command name and description
- Analyze the workflow to identify:
  - Input requirements (what parameters are needed?)
  - Process steps (what actions occur in what order?)
  - Agent involvement (which agents execute steps?)
  - Decision points (where do branches occur?)
  - Output deliverables (what does user receive?)
- Map workflow to 3-7 steps (more than 7 suggests breaking into multiple commands)
- Identify parameter requirements ($1, $2, $3)

**Questions to Answer**:
- What initiates this workflow?
- What inputs are required from the user?
- What processing steps occur?
- Which agents handle each step?
- What decisions or branches exist?
- What outputs are produced?

**Output**: Workflow specification with steps and parameters

### 2. Parameter & Argument Design

**Objective**: Define what inputs the command accepts.

**Actions**:
- Identify required vs optional parameters:
  - Required: Essential to workflow execution
  - Optional: Provide customization or filtering
- Define parameter order and naming:
  - $1: Most important parameter (e.g., target to analyze)
  - $2: Secondary parameter (e.g., time period)
  - $3: Optional customization (e.g., output format)
- Create argument hint for frontmatter:
  - Format: `[param1] [param2] [optional-param3]`
  - Use descriptive names: `[pipeline-id]` not `[id]`
  - Indicate optional with angle brackets if needed
- Add parameter validation:
  - Check required parameters exist
  - Validate format or range
  - Provide helpful error messages

**Argument Examples**:
- `/pipeline-review [team-name] [month]`
- `/forecast-update [product-line] [quarter]`
- `/deal-risk-analysis [deal-id]`

**Output**: Parameter specification and validation rules

### 3. Agent & Tool Orchestration

**Objective**: Define which agents execute which steps and in what order.

**Actions**:
- Map agents to workflow steps:
  - Step 1: "Agent X analyzes Y using Z"
  - Step 2: "Agent A processes results and generates B"
  - Step 3: "Agent C validates and formats output"
- Consider hybrid orchestration:
  - Sonnet for analysis and planning steps
  - Haiku for execution and formatting steps
  - Sonnet for validation and review
- Define tool requirements:
  - Read: For accessing data or documents
  - Write: For generating reports or outputs
  - Bash: For executing system commands
  - Grep: For searching patterns
  - Glob: For finding files
- Specify agent invocation approach:
  - Direct invocation: "Invoke {agent-name} with {parameters}"
  - Context-based: "Context will activate {agent-name}"
  - Explicit: "Use {agent-name} to {action}"

**Orchestration Pattern**:
```markdown
### 1. Analysis Phase
Invoke the `{analyst-agent}` to analyze {target}.

### 2. Processing Phase
Use the `{processor-agent}` to process results.

### 3. Validation Phase
Have the `{validator-agent}` check quality.
```

**Output**: Step-by-step agent orchestration plan

### 4. Command File Generation

**Objective**: Create the command markdown file with proper structure.

**Actions**:
- Create file at `plugins/{plugin-name}/commands/{command-name}.md`
- Generate frontmatter:
  ```yaml
  ---
  description: {What this command does}
  argument-hint: {[param1] [param2]}
  version: "1.0.0"
  tags: [{domain}, {workflow-type}]
  tool_access: [{tools needed}]
  model: sonnet|haiku
  ---
  ```
- Write command overview:
  - Purpose and value
  - When to use
  - What it produces
- Add context section:
  - Background information
  - Prerequisites
  - Related workflows
- Document requirements:
  - Parameter definitions
  - Input data needed
  - Access requirements
- Write instruction steps:
  - Number clearly (1, 2, 3...)
  - Each step has objective and actions
  - Include agent invocations
  - Note validation points
- Define output format:
  - Structure of deliverables
  - Format specifications
  - Example outputs
- Add success criteria:
  - Quality checks
  - Validation rules
  - Completeness criteria

**Output**: Complete command file

### 5. Validation & Testing

**Objective**: Ensure command is functional and follows conventions.

**Actions**:
- Validate frontmatter:
  - Description is clear
  - Argument hint matches parameters used
  - Model selection appropriate
  - Tool access is minimal but sufficient
- Review workflow logic:
  - Steps are sequential and logical
  - Agent invocations are correct
  - Parameters are properly referenced ($1, $2)
  - No missing steps or gaps
- Check documentation:
  - Instructions are clear
  - Output format is specified
  - Success criteria are measurable
  - Examples are helpful
- Test integration:
  - Referenced agents exist
  - Skills are available
  - No circular dependencies
  - Command can be invoked

**Quality Checklist**:
- [ ] Frontmatter complete
- [ ] Description clear and concise
- [ ] Argument hint accurate
- [ ] Parameters properly used
- [ ] Steps are sequential
- [ ] Agent invocations correct
- [ ] Output format defined
- [ ] Success criteria clear
- [ ] No broken references

**Output**: Validation report

## Output Format

The command produces:

1. **Command File**: `plugins/{plugin-name}/commands/{command-name}.md`

2. **Generation Summary**:
```
Command Generated: /{command-name}
Parameters: {count}
Steps: {count}
Agents Used: {list}
Model: {haiku|sonnet}
Status: Ready to use
```

3. **Usage Example**:
```
To use this command:
/{command-name} [param1] [param2]

Example:
/{command-name} "west-region" "2024-Q1"
```

4. **Integration Notes**:
```
This command orchestrates:
- {agent-1}: For {purpose}
- {agent-2}: For {purpose}

And produces:
- {output-1}
- {output-2}
```

## Success Criteria

- Command follows naming conventions (kebab-case)
- Frontmatter is complete and valid
- Description clearly states purpose
- Argument hint matches parameters
- Parameters are properly referenced ($1, $2, $3)
- Workflow steps are clear and sequential
- Agent invocations are correct
- Model selection is appropriate
- Tool access is minimal but sufficient
- Output format is clearly specified
- Success criteria are measurable
- Command integrates with existing components
- Documentation is comprehensive
- Can be immediately invoked by users

## Related Plugins

- **meta-agent-builder**: Parent plugin providing generation capability
- **workflow-patterns**: Reference patterns for command orchestration
- **agent-library**: Agents that commands can orchestrate

---

**Naming Convention**: Use format `{domain}-{action}` or `{action}-{target}`:
- `/pipeline-review` (domain-action)
- `/forecast-update` (action-target)
- `/deal-risk-analysis` (target-action)

**Model Selection Tip**:
- Use **Haiku** for simple, linear workflows (< 3 steps, deterministic)
- Use **Sonnet** for complex workflows (> 3 steps, decision points, analysis)
