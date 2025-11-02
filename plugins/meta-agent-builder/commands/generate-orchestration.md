---
description: Design multi-agent orchestration for complex business process
argument-hint: [process-name] [phases-description]
version: "1.0.0"
tags: [generator, orchestration, workflow, multi-agent]
tool_access: [Read, Write, Bash, Grep, Glob]
model: sonnet
---

# Generate Multi-Agent Orchestration

Design and implement complex multi-agent workflows that coordinate multiple specialized agents to execute sophisticated business processes.

## Context

Multi-agent orchestrations handle business processes too complex for a single agent. They:
- Coordinate multiple specialized agents
- Manage state and context across phases
- Handle error conditions and retries
- Optimize for token efficiency through hybrid model usage
- Provide clear progress tracking and reporting

Orchestrations are essential for processes like quarterly business reviews, strategic planning, or comprehensive audits.

## Requirements

**Process Name**: $1 (e.g., "quarterly-business-review", "strategic-planning-cycle")
**Phases Description**: $2 (e.g., "Data collection → Analysis → Insights → Recommendations → Presentation")

## Instructions

### 1. Process Decomposition & Phase Mapping

**Objective**: Break complex process into distinct phases with clear boundaries.

**Actions**:
- Invoke the `orchestration-designer` meta-agent
- Analyze the business process to identify:
  - Natural phase boundaries (when one activity ends, another begins)
  - Input/output relationships (what each phase consumes/produces)
  - Dependencies (what must complete before what)
  - Parallelization opportunities (what can run concurrently)
  - Decision points (where branching occurs)
- Map phases to a sequence:
  - Phase 1: Data Collection & Validation
  - Phase 2: Analysis & Processing
  - Phase 3: Insight Generation
  - Phase 4: Recommendation Development
  - Phase 5: Deliverable Creation
- Define phase transitions:
  - Exit criteria (when is phase complete?)
  - Handoff artifacts (what passes to next phase?)
  - Validation requirements (what must be true to proceed?)

**Questions to Answer**:
- What are the distinct stages of this process?
- What inputs does each stage need?
- What outputs does each stage produce?
- Which stages can run in parallel?
- What decisions or branches exist?
- What happens if a stage fails?

**Output**: Process flow diagram with phases, dependencies, and transitions

### 2. Agent Role Assignment & Specialization

**Objective**: Map specialized agents to phases based on capabilities.

**Actions**:
- For each phase, identify agent requirements:
  - What expertise is needed?
  - What complexity level (Haiku vs Sonnet)?
  - What tools are required?
  - Can existing agents be used or new ones needed?
- Apply hybrid orchestration pattern:
  - **Sonnet agents** for:
    - Strategic planning
    - Complex analysis
    - Insight generation
    - Quality assessment
  - **Haiku agents** for:
    - Data collection
    - Report formatting
    - Validation checks
    - Status updates
- Define agent coordination:
  - Sequential: Agent B starts after Agent A completes
  - Parallel: Agent A and B run simultaneously
  - Conditional: Agent C runs only if condition met
- Map agent interactions:
  - Which agents pass artifacts to others?
  - Where does context need to be maintained?
  - What shared state is required?

**Agent Assignment Example**:
```
Phase 1: Data Collection
- data-collector-agent (Haiku) → Gather inputs
- data-validator-agent (Haiku) → Check quality

Phase 2: Analysis
- business-analyst-agent (Sonnet) → Analyze data
- trend-identifier-agent (Sonnet) → Find patterns

Phase 3: Insights
- insight-synthesizer-agent (Sonnet) → Generate insights
- recommendation-engine-agent (Sonnet) → Develop recommendations

Phase 4: Deliverables
- report-generator-agent (Haiku) → Format outputs
- presentation-builder-agent (Haiku) → Create slides
```

**Output**: Agent assignment matrix with roles and responsibilities

### 3. Context & State Management Design

**Objective**: Define how information flows and persists across phases.

**Actions**:
- Identify shared context requirements:
  - What information do multiple agents need?
  - What state must persist across phases?
  - What results feed forward to later phases?
- Design context structure:
  ```yaml
  orchestration_context:
    process_id: {unique identifier}
    phase: {current phase}
    inputs:
      - {input 1}
      - {input 2}
    outputs:
      - {output 1}
      - {output 2}
    state:
      - {state variable 1}
      - {state variable 2}
  ```
- Define handoff mechanisms:
  - Files: Structured outputs written to disk
  - Variables: State passed in orchestration context
  - References: Pointers to artifacts created
- Plan token efficiency:
  - What can be summarized vs passed verbatim?
  - Where can progressive disclosure help?
  - What can be cached vs regenerated?

**Context Management Patterns**:
- **Accumulation**: Each phase adds to growing context
- **Refinement**: Each phase transforms previous output
- **Summarization**: Periodic compression of context
- **Checkpointing**: Save state at key milestones

**Output**: Context management specification

### 4. Error Handling & Recovery Strategy

**Objective**: Design resilience into the orchestration.

**Actions**:
- Identify failure modes:
  - What can go wrong in each phase?
  - What are external dependencies that could fail?
  - What validation checks might fail?
  - What data quality issues might arise?
- Define error handling strategies:
  - **Retry**: Attempt phase again (for transient failures)
  - **Fallback**: Use alternative approach or agent
  - **Skip**: Continue with warning (for non-critical phases)
  - **Abort**: Stop orchestration (for critical failures)
- Design validation checkpoints:
  - Phase completion criteria
  - Data quality gates
  - Business rule validation
  - Output format verification
- Implement recovery mechanisms:
  - Checkpoint save/restore
  - Partial result preservation
  - Rollback capabilities
  - Manual intervention points
- Create monitoring and alerting:
  - Progress tracking
  - Error notification
  - Performance metrics
  - Completion status

**Error Handling Example**:
```markdown
### Phase 2: Data Analysis
Try to analyze data using business-analyst-agent.

If analysis fails due to data quality:
1. Invoke data-cleaner-agent to fix issues
2. Retry analysis up to 2 times
3. If still failing, generate partial analysis with warnings

If analysis succeeds but confidence is low:
1. Request human review before proceeding
2. Continue with validated subset of insights
```

**Output**: Error handling and recovery specification

### 5. Orchestration Implementation

**Objective**: Create the orchestration command file with full workflow.

**Actions**:
- Create orchestration command file:
  - Name: `/{process-name}-orchestration.md`
  - Location: `plugins/{plugin-name}/commands/`
- Write comprehensive documentation:
  - Process overview and value
  - Phase descriptions
  - Agent coordination logic
  - Context management approach
  - Error handling strategy
- Implement phase instructions:
  - Clear entry criteria
  - Step-by-step agent invocations
  - Context passing mechanisms
  - Validation checkpoints
  - Exit criteria
- Define monitoring and reporting:
  - Progress indicators
  - Phase completion summaries
  - Error logs
  - Final deliverables
- Add usage guidance:
  - When to use this orchestration
  - Required inputs
  - Expected duration
  - Output description

**Orchestration Structure**:
```markdown
---
description: {Complex multi-phase process}
argument-hint: {[params]}
model: sonnet
---

# {Process Name} Orchestration

## Overview
{What this orchestration does}

## Phases
1. {Phase 1 name}
2. {Phase 2 name}
...

## Instructions

### Phase 1: {Name}
**Objective**: {What this phase accomplishes}

**Agents**: {Which agents are used}

**Actions**:
1. {Step 1}
2. {Step 2}

**Validation**: {Exit criteria}

### Phase 2: {Name}
...

## Output Format
{What user receives}

## Error Handling
{How failures are managed}
```

**Output**: Complete orchestration command file

### 6. Documentation & Optimization

**Objective**: Document the orchestration and identify efficiency opportunities.

**Actions**:
- Create architecture diagram:
  - Show phase flow
  - Indicate agent assignments
  - Mark decision points
  - Show error paths
- Document design decisions:
  - Why phases are structured this way
  - Rationale for agent assignments
  - Model selection justification
  - Context management approach
- Identify optimization opportunities:
  - Where can phases run in parallel?
  - Can any agents be combined?
  - Are token budgets reasonable?
  - Can caching reduce redundancy?
- Write operational guide:
  - How to monitor progress
  - What to do if errors occur
  - How to customize for specific cases
  - Performance expectations

**Optimization Checklist**:
- [ ] Parallel execution where possible
- [ ] Hybrid model usage (Sonnet/Haiku)
- [ ] Context is minimal but sufficient
- [ ] Validation is appropriate, not excessive
- [ ] Error handling is comprehensive
- [ ] Token usage is optimized
- [ ] Checkpointing at key milestones

**Output**: Complete documentation package

## Output Format

The command produces:

1. **Orchestration Command File**: `plugins/{plugin-name}/commands/{process-name}-orchestration.md`

2. **Architecture Diagram**:
```
[Phase 1: Collection] → [Phase 2: Analysis] → [Phase 3: Insights]
   ↓ (data-collector)      ↓ (analyst)           ↓ (synthesizer)
   → data.json         →   analysis.md        →  insights.md
```

3. **Agent Coordination Matrix**:
```
| Phase | Agent | Model | Purpose |
|-------|-------|-------|---------|
| 1 | data-collector | Haiku | Gather inputs |
| 2 | analyst | Sonnet | Analyze data |
| 3 | synthesizer | Sonnet | Generate insights |
```

4. **Usage Guide**:
```
To execute orchestration:
/{process-name}-orchestration [param1] [param2]

Expected duration: {time estimate}
Agents involved: {count}
Checkpoints: {count}
```

5. **Monitoring Dashboard Spec**:
```
Progress: [=====>    ] 50%
Current Phase: Analysis
Last Checkpoint: Data validated
Agents Active: business-analyst-agent
Estimated Completion: 15 minutes
```

## Success Criteria

- Process is decomposed into logical phases (3-7 phases optimal)
- Each phase has clear objectives and boundaries
- Agent assignments match complexity requirements
- Hybrid orchestration uses appropriate models
- Context management is efficient and effective
- Error handling covers major failure modes
- Recovery mechanisms are practical
- Validation checkpoints are at key milestones
- Parallelization opportunities are exploited
- Token usage is optimized across phases
- Documentation is comprehensive
- Monitoring provides visibility
- Command can be immediately used
- Orchestration follows plugin patterns

## Related Plugins

- **meta-agent-builder**: Parent plugin for generation
- **workflow-patterns**: Reference orchestration patterns
- **process-library**: Reusable business process orchestrations

---

**Best Practice**: Start with a high-level phase diagram before diving into agent details. Ensure phase boundaries represent natural breakpoints in the business process.

**Optimization Tip**: Use Sonnet for planning and Haiku for execution within the same orchestration to balance quality and token efficiency.
