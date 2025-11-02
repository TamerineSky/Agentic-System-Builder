---
description: Create agent skill with progressive disclosure architecture
argument-hint: [skill-name] [methodology-description]
version: "1.0.0"
tags: [generator, skill, knowledge, progressive-disclosure]
tool_access: [Read, Write, Bash, Grep, Glob]
model: sonnet
---

# Generate Agent Skill

Create a modular knowledge package using progressive disclosure architecture for maximum token efficiency and reusability across agents.

## Context

Agent skills are structured knowledge packages that agents can load on-demand. They follow a three-tier progressive disclosure pattern:

1. **Metadata** (always loaded): Name, description, activation criteria
2. **Instructions** (loaded when activated): Core methodology and guidance
3. **Resources** (loaded on explicit request): Examples, templates, checklists

This architecture ensures token efficiency while providing deep domain knowledge when needed.

## Requirements

**Skill Name**: $1 (e.g., "pipeline-health-scoring", "demand-forecasting-methods")
**Methodology Description**: $2 (e.g., "Weighted scoring model for sales pipeline quality assessment")

## Instructions

### 1. Knowledge Extraction & Domain Analysis

**Objective**: Identify what knowledge should be encoded and how to structure it.

**Actions**:
- Invoke the `skill-builder` meta-agent with skill name and methodology
- Analyze the methodology to extract:
  - Core concepts and principles
  - Step-by-step processes
  - Decision frameworks
  - Best practices
  - Common patterns and anti-patterns
  - Quality criteria
- Identify what agents would need this knowledge
- Determine activation triggers (when should this load?)

**Questions to Answer**:
- What problem does this methodology solve?
- What are the key steps in applying this methodology?
- What expertise is required to use it effectively?
- When would an agent need this knowledge?
- What examples make it clear?

**Output**: Knowledge inventory and structure outline

### 2. Progressive Disclosure Structure Design

**Objective**: Organize knowledge into three tiers for optimal token usage.

**Actions**:
- **Tier 1 - Metadata** (always loaded, < 100 tokens):
  - Skill name
  - Concise description (1-2 sentences)
  - Activation trigger ("Use when...")
  - Version information
- **Tier 2 - Instructions** (loaded when activated, 500-2000 tokens):
  - Core methodology explanation
  - Step-by-step process
  - Decision frameworks
  - Key principles
  - Quality standards
  - When to escalate or request resources
- **Tier 3 - Resources** (loaded on demand, 1000-5000 tokens):
  - Detailed examples
  - Templates and checklists
  - Edge case handling
  - Troubleshooting guides
  - Advanced techniques
  - Reference materials

**Structure Example**:
```markdown
---
name: pipeline-health-scoring
description: Weighted scoring model for sales pipeline quality. Use when analyzing deal quality or pipeline health.
version: "1.0.0"
---

# Pipeline Health Scoring Methodology

[Tier 2: Core instructions go here]

## Resources

[Tier 3: Examples and templates referenced but not inlined]
```

**Output**: Three-tier content structure

### 3. Content Creation - Core Instructions

**Objective**: Write clear, actionable guidance for the methodology.

**Actions**:
- Write methodology overview:
  - Purpose and value
  - When to use
  - Prerequisites
- Document step-by-step process:
  - Number steps clearly
  - Make each step actionable
  - Include decision points
  - Note quality checks
- Define key concepts:
  - Business terminology
  - Formulas or frameworks
  - Success criteria
- Add guidance sections:
  - Common pitfalls
  - Quality standards
  - When to request resources

**Writing Guidelines**:
- Use business language (not academic or overly technical)
- Be prescriptive ("Do X", not "One might consider X")
- Include "why" along with "what" and "how"
- Reference Tier 3 resources where detailed examples help
- Keep focused (single methodology per skill)

**Output**: Complete Tier 2 instructions content

### 4. Resource Development - Examples & Templates

**Objective**: Create supporting materials that agents load only when needed.

**Actions**:
- Develop examples:
  - Real-world scenarios (anonymized)
  - Before/after comparisons
  - Common variations
  - Edge cases
- Create templates:
  - Checklists
  - Scoring rubrics
  - Report formats
  - Analysis frameworks
- Build reference materials:
  - Calculation details
  - Industry benchmarks
  - Related methodologies
  - Troubleshooting guide

**Resource Organization**:
- Use clear headings for each resource
- Make resources independently useful
- Cross-reference between resources
- Keep each resource focused and modular

**Output**: Complete Tier 3 resources content

### 5. Skill File Creation & Validation

**Objective**: Generate the skill file and validate it meets quality standards.

**Actions**:
- Create skill directory: `plugins/{plugin-name}/skills/{skill-name}/`
- Generate SKILL.md file with three-tier structure
- Validate frontmatter:
  - Name matches directory
  - Description is clear and concise
  - Activation trigger is specific
  - Version is specified
- Check progressive disclosure:
  - Tier 1 (metadata) < 100 tokens
  - Tier 2 (instructions) 500-2000 tokens
  - Tier 3 (resources) available but not inlined
  - Clear separation between tiers
- Test token efficiency:
  - Total size reasonable (< 10k tokens)
  - No redundancy between tiers
  - Resources are truly optional
- Validate content quality:
  - Uses business language
  - Actionable guidance
  - Clear examples
  - No technical jargon inappropriate for audience

**Quality Checklist**:
- [ ] Three-tier structure implemented
- [ ] Frontmatter complete
- [ ] Activation trigger is clear
- [ ] Instructions are actionable
- [ ] Resources add value
- [ ] Token budgets met
- [ ] Business language used
- [ ] No broken references

**Output**: Complete skill ready for agent use

## Output Format

The command produces:

1. **Skill Directory**: `plugins/{plugin-name}/skills/{skill-name}/`

2. **SKILL.md File**:
```markdown
---
name: {skill-name}
description: {methodology summary}. Use when {activation trigger}.
version: "1.0.0"
---

# {Methodology Title}

## Overview
[Purpose and when to use]

## Core Process
1. [Step one]
2. [Step two]
3. [Step three]

## Key Concepts
[Essential knowledge]

## Resources
### Examples
[Detailed examples]

### Templates
[Reusable templates]

### Reference
[Additional details]
```

3. **Generation Summary**:
```
Skill Generated: {skill-name}
Tier 1 Size: {token count} tokens
Tier 2 Size: {token count} tokens
Tier 3 Size: {token count} tokens
Total Size: {token count} tokens
Status: Ready to use
```

4. **Integration Guide**:
```
To use this skill:
- Agents auto-load Tier 1 (metadata)
- Tier 2 loads when skill activated
- Agents request Tier 3 resources explicitly

Related agents that should use this skill:
- {agent-1}
- {agent-2}
```

## Success Criteria

- Skill follows progressive disclosure three-tier architecture
- Frontmatter is complete and valid
- Activation trigger is clear and specific
- Tier 1 (metadata) < 100 tokens
- Tier 2 (instructions) is actionable and clear
- Tier 3 (resources) adds value without bloat
- Total token count is reasonable (< 10k tokens)
- Content uses business language (not academic jargon)
- Methodology is focused on single topic
- Examples are realistic and helpful
- Skill is reusable across multiple agents
- File structure follows conventions

## Related Plugins

- **meta-agent-builder**: Parent plugin providing generation capability
- **skill-library**: Collection of reusable business methodology skills
- **agent-patterns**: Agents that reference skills

---

**Best Practice**: Start with Tier 2 content first, then extract metadata (Tier 1) and create supporting resources (Tier 3). This ensures proper information layering.

**Token Efficiency Tip**: If Tier 2 exceeds 2000 tokens, consider splitting into multiple focused skills or moving detail to Tier 3 resources.
