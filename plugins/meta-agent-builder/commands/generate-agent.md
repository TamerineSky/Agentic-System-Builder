---
description: Create specialized agent from business role description
argument-hint: [role-name] [expertise-area]
version: "1.0.0"
tags: [generator, agent, role, specialist]
tool_access: [Read, Write, Bash, Grep, Glob]
model: sonnet
---

# Generate Specialized Agent

Create a domain expert agent with tailored capabilities, appropriate model selection, and business-focused system prompts.

## Context

Agents are specialized AI assistants designed for specific business roles. Each agent has:
- A clear role and responsibility
- Domain expertise encoded in system prompt
- Appropriate tool access
- Right-sized model (Haiku for execution, Sonnet for reasoning)
- Business-focused language and capabilities

This command generates production-ready agents following proven architectural patterns.

## Requirements

**Role Name**: $1 (e.g., "sales-analyst", "demand-forecaster")
**Expertise Area**: $2 (e.g., "pipeline health analysis", "inventory optimization")

## Instructions

### 1. Role Analysis & Capability Mapping

**Objective**: Define what the agent should do and what knowledge it needs.

**Actions**:
- Invoke the `agent-generator` meta-agent with role and expertise parameters
- Analyze the business role to identify:
  - Primary responsibilities
  - Required domain knowledge
  - Common tasks and workflows
  - Decision-making patterns
  - Stakeholder interactions
  - Success metrics

**Questions to Answer**:
- What business problems does this role solve?
- What expertise distinguishes this role from others?
- What workflows does this role execute regularly?
- What data or systems does this role interact with?
- What decisions does this role make?

**Output**: Role specification document

### 2. System Prompt Design

**Objective**: Craft a system prompt that encodes domain expertise and guides behavior.

**Actions**:
- Generate expert persona statement:
  - "You are an expert in [domain]..."
  - Define the expertise boundaries
  - Use business language, not technical jargon
- Enumerate capabilities:
  - List specific skills this agent provides
  - Focus on business outcomes
  - Make capabilities actionable
- Define response approach:
  - Step-by-step process
  - Decision-making framework
  - Quality standards
  - Escalation criteria

**System Prompt Structure**:
```markdown
You are an expert in [business domain expertise].

You specialize in [specific capabilities] for [target users/stakeholders].

## Capabilities
- [Business capability 1]
- [Business capability 2]
- [Business capability 3]

## Response Approach
1. [Analysis step]
2. [Processing step]
3. [Output step]
4. [Validation step]

## Quality Standards
- [Standard 1]
- [Standard 2]

When [trigger condition], you should [proactive behavior].
```

**Output**: Complete system prompt content

### 3. Tool & Model Selection

**Objective**: Assign appropriate tools and model for the agent's complexity.

**Actions**:
- Determine required tools:
  - **Read**: If agent needs to analyze documents/data
  - **Write**: If agent creates new files
  - **Bash**: If agent needs to execute commands
  - **Grep**: If agent searches for patterns
  - **Glob**: If agent needs to find files
  - Minimize tool access (principle of least privilege)
- Select appropriate model:
  - **Haiku**: Fast execution, deterministic tasks, operational work
  - **Sonnet**: Complex reasoning, analysis, strategic planning
  - **Opus**: Highest complexity (rarely needed)
- Consider hybrid orchestration if needed:
  - Sonnet for planning, Haiku for execution

**Decision Matrix**:
| Task Type | Complexity | Model Choice |
|-----------|-----------|--------------|
| Data analysis | High | Sonnet |
| Report generation | Low | Haiku |
| Strategic planning | High | Sonnet |
| Process execution | Low | Haiku |
| Problem diagnosis | High | Sonnet |

**Output**: Tool list and model selection with rationale

### 4. Agent File Generation

**Objective**: Create the agent markdown file with proper frontmatter and content.

**Actions**:
- Create file at `plugins/{plugin-name}/agents/{role-name}.md`
- Generate frontmatter:
  ```yaml
  ---
  name: {role-name}
  description: {What agent does}. Use PROACTIVELY when {trigger}.
  model: sonnet|haiku
  tools: [Read, Write, Bash, Grep, Glob]
  ---
  ```
- Insert system prompt content
- Add usage examples if applicable
- Include related skills or commands

**Naming Conventions**:
- Use kebab-case: `sales-analyst`, `demand-forecaster`
- Format: `{business-role}-{function}`
- Be specific: "pipeline-analyst" not "data-analyst"
- Use business terms: "forecast-manager" not "prediction-model"

**Output**: Complete agent file ready to use

### 5. Validation & Testing

**Objective**: Ensure the agent meets quality standards and functions correctly.

**Actions**:
- Validate frontmatter:
  - All required fields present
  - Model selection is appropriate
  - Tools are minimal but sufficient
  - Description includes proactive trigger
- Review system prompt:
  - Uses business language
  - Capabilities are clear and actionable
  - Response approach is step-by-step
  - No technical jargon inappropriate for audience
- Test token efficiency:
  - System prompt is < 5000 tokens
  - References skills for detailed knowledge (not inline)
  - Uses progressive disclosure where appropriate
- Check integration:
  - Agent references valid skills
  - Commands can invoke this agent
  - No circular dependencies

**Quality Checklist**:
- [ ] Frontmatter complete and valid
- [ ] Model selection justified
- [ ] Tool access minimized
- [ ] System prompt uses business language
- [ ] Capabilities are actionable
- [ ] Response approach is clear
- [ ] Token budget reasonable
- [ ] No broken references

**Output**: Validation report with pass/fail status

## Output Format

The command produces:

1. **Agent File**: `plugins/{plugin-name}/agents/{role-name}.md`

2. **Generation Summary**:
```
Agent Generated: {role-name}
Model: {sonnet|haiku}
Tools: {tool list}
Token Count: {estimated tokens}
Capabilities: {count}
Status: Ready to use
```

3. **Usage Example**:
```
To invoke this agent:
- From command: Mention "{role-name}" in workflow
- Directly: Context will activate automatically
- With skill: Agent will load {related-skills}
```

4. **Next Steps**:
- Test agent with sample prompts
- Create related skills if needed
- Build commands that use this agent
- Add to plugin.json manifest

## Success Criteria

- Agent file follows naming conventions
- Frontmatter is complete and valid
- Model selection is appropriate for complexity
- Tool access is minimal but sufficient
- System prompt uses business language (not technical jargon)
- Capabilities are clearly enumerated and actionable
- Response approach provides step-by-step guidance
- Token count is reasonable (< 5000 tokens)
- Agent can be immediately integrated into plugin
- Proactive trigger is defined in description

## Related Plugins

- **meta-agent-builder**: Parent plugin providing generation capability
- **agent-patterns**: Reference patterns for different agent types
- **skill-library**: Skills that agents can reference

---

**Tip**: Review agents from `/agents/plugins/*/agents/*.md` for proven patterns before generating. Adapt software development patterns to business operations contexts.
