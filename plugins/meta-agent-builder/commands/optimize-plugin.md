---
description: Analyze and optimize plugin for token efficiency
argument-hint: [plugin-path]
version: "1.0.0"
tags: [optimization, token-efficiency, performance, analysis]
tool_access: [Read, Bash, Grep, Glob]
model: haiku
---

# Optimize Plugin

Analyze plugin for token usage efficiency and provide actionable optimization recommendations.

## Context

Token efficiency is critical for plugin performance and cost. This command analyzes component token usage, identifies optimization opportunities, and suggests specific improvements following progressive disclosure patterns and other token-reduction techniques.

## Requirements

**Plugin Path**: $1 (e.g., "plugins/revenue-operations" or absolute path)

If not provided, will analyze all plugins in the current workspace.

## Instructions

### 1. Token Usage Analysis

**Objective**: Measure current token consumption across all plugin components.

**Actions**:
- Scan all plugin components:
  - Agents (*.md files in agents/)
  - Skills (SKILL.md files in skills/*/
  - Commands (*.md files in commands/)
- Calculate token counts for each component:
  - Use character count / 4 as approximation
  - Separate frontmatter from content
  - Track by component type
- Identify token hotspots:
  - Components exceeding recommended limits
  - Largest contributors to total token usage
  - Redundant content across components
- Calculate plugin-level metrics:
  - Total token count
  - Average tokens per component
  - Token distribution by type
  - Percentage of budget used

**Token Budget Targets**:
```yaml
agent: 5000 tokens max
skill_tier1: 100 tokens max
skill_tier2: 2000 tokens max
skill_tier3: 5000 tokens max
command: 3000 tokens max
```

**Analysis Output Example**:
```
Plugin: revenue-operations
Total Token Count: 42,300 tokens

Component Breakdown:
Agents (2):
  - sales-analyst: 5,200 tokens ⚠ EXCEEDS LIMIT
  - pipeline-manager: 3,800 tokens ✓

Skills (2):
  - pipeline-health-scoring: 4,100 tokens ✓
    - Tier 1: 85 tokens ✓
    - Tier 2: 1,900 tokens ✓
    - Tier 3: 2,115 tokens ✓
  - forecast-methodology: 8,500 tokens ⚠ LARGE
    - Tier 1: 120 tokens ⚠ EXCEEDS LIMIT
    - Tier 2: 2,800 tokens ⚠ EXCEEDS LIMIT
    - Tier 3: 5,580 tokens ⚠ EXCEEDS LIMIT

Commands (1):
  - pipeline-review: 2,400 tokens ✓

Hotspots:
1. forecast-methodology skill (8,500 tokens)
2. sales-analyst agent (5,200 tokens)
```

**Output**: Detailed token usage report

### 2. Redundancy & Duplication Detection

**Objective**: Identify repeated content that could be consolidated.

**Actions**:
- Scan for duplicate content:
  - Similar paragraphs across components
  - Repeated examples or templates
  - Redundant explanations
  - Common instruction patterns
- Identify consolidation opportunities:
  - Knowledge that could move to a skill
  - Examples that could be shared
  - Instructions that could reference common resource
- Calculate redundancy metrics:
  - Percentage of duplicated content
  - Token savings from consolidation
  - Impact on usability

**Redundancy Detection Example**:
```
Duplicate Content Found:

1. Pipeline health scoring methodology (850 tokens)
   - Found in: sales-analyst agent
   - Found in: pipeline-manager agent
   - Recommendation: Extract to pipeline-health-scoring skill
   - Savings: 1,700 tokens → 200 tokens (85% reduction)

2. Deal stage definitions (450 tokens)
   - Found in: sales-analyst agent
   - Found in: pipeline-review command
   - Recommendation: Create shared reference in skill
   - Savings: 900 tokens → 100 tokens (89% reduction)

3. Forecast calculation formulas (320 tokens)
   - Found in: forecast-methodology skill (Tier 2)
   - Found in: sales-analyst agent
   - Recommendation: Keep in skill, reference from agent
   - Savings: 320 tokens

Total Redundancy: 3,240 tokens (7.7% of plugin)
Potential Savings: 2,820 tokens
```

**Output**: Redundancy analysis with consolidation recommendations

### 3. Progressive Disclosure Opportunities

**Objective**: Identify content that could use progressive disclosure patterns.

**Actions**:
- Analyze agents for extractable knowledge:
  - Methodologies that could become skills
  - Detailed procedures that could be Tier 3
  - Examples that could be in resources
- Review skills for proper tiering:
  - Is Tier 1 truly minimal metadata?
  - Is Tier 2 focused on core instructions?
  - Are examples properly in Tier 3?
  - Can any Tier 2 content move to Tier 3?
- Evaluate commands for on-demand loading:
  - Can detailed examples be referenced?
  - Are there optional sections that could load later?
- Calculate progressive disclosure impact:
  - Base load vs full load token counts
  - Typical usage patterns
  - Token savings for common paths

**Progressive Disclosure Analysis**:
```
Opportunities:

1. sales-analyst agent (5,200 tokens)
   Current: All content always loaded

   Recommendations:
   a) Extract "Pipeline Scoring Methodology" (850 tokens)
      → Create new skill or reference existing
      → Base load: 5,200 → 4,400 tokens (15% reduction)

   b) Move detailed examples to skill Tier 3 (600 tokens)
      → Reference from agent, load on-demand
      → Further reduction: 4,400 → 3,800 tokens (27% total)

   Net Savings: 1,400 tokens per agent load

2. forecast-methodology skill
   Current Tier 2: 2,800 tokens

   Recommendations:
   a) Move 4 of 6 examples to Tier 3 (650 tokens)
   b) Condense formula explanations (200 tokens)
   c) Reference external calculation templates (150 tokens)

   Net Savings: 1,000 tokens per skill activation

Total Progressive Disclosure Savings: 4,200 tokens
```

**Output**: Progressive disclosure recommendations with impact estimates

### 4. Content Optimization Suggestions

**Objective**: Identify specific content improvements that reduce tokens without losing value.

**Actions**:
- Analyze writing efficiency:
  - Verbose explanations that could be concise
  - Repetitive phrasing
  - Unnecessary qualifiers or filler words
  - Overly formal or academic language
- Review structural efficiency:
  - Redundant headings or sections
  - Unnecessary nesting
  - Lists that could be tables (or vice versa)
  - Markdown formatting overhead
- Evaluate example efficiency:
  - Examples that are too long or detailed
  - Multiple examples showing same concept
  - Examples that could use placeholders
- Identify reference opportunities:
  - External resources that could be linked
  - Standard methodologies that need not be explained
  - Industry concepts that can be named, not described

**Content Optimization Examples**:
```
1. sales-analyst agent - System Prompt
   Current (125 words, ~165 tokens):
   "You are an expert in sales operations and analytics with deep
   expertise in pipeline management, forecasting methodologies, and
   deal health assessment. You specialize in analyzing sales data to
   provide actionable insights that help sales leaders make informed
   decisions about resource allocation, deal prioritization, and
   revenue forecasting. You have extensive experience working with
   CRM systems, particularly Salesforce, and understand the
   complexities of B2B sales cycles across various industries."

   Optimized (68 words, ~90 tokens):
   "You are a sales operations analyst specializing in pipeline
   management, forecasting, and deal health assessment. You analyze
   sales data to provide actionable insights for resource allocation,
   deal prioritization, and revenue forecasting. You work with CRM
   systems and understand B2B sales cycles."

   Savings: 75 tokens (45% reduction)

2. pipeline-health-scoring skill - Example Section
   Current: 3 detailed examples (850 tokens)
   Optimized: 1 comprehensive example + 2 summaries (400 tokens)
   Savings: 450 tokens (53% reduction)

3. pipeline-review command - Output Format
   Current: Verbose description (280 tokens)
   Optimized: Structured template with placeholders (120 tokens)
   Savings: 160 tokens (57% reduction)
```

**Output**: Specific content optimization recommendations

### 5. Architecture Refactoring Recommendations

**Objective**: Suggest structural changes that improve token efficiency.

**Actions**:
- Evaluate component granularity:
  - Are any agents doing too much (should split)?
  - Are any skills too broad (should split)?
  - Are there too many small components (should merge)?
- Assess skill extraction opportunities:
  - Agent knowledge that multiple agents need
  - Commands with embedded methodology
  - Repeated instructional content
- Review command orchestration:
  - Can complex commands be simplified?
  - Should any commands merge or split?
  - Are agent invocations efficient?
- Consider hybrid patterns:
  - Haiku for execution, Sonnet for planning
  - On-demand loading of resources
  - Caching of frequently used content

**Architecture Recommendations**:
```
Refactoring Opportunities:

1. Create new shared skill: "sales-terminology"
   - Extract common definitions from 3 components
   - Current total: 1,100 tokens across components
   - New approach: 400 token skill, referenced
   - Savings: 700 tokens
   - Improves: Consistency and maintainability

2. Split forecast-methodology skill
   - Current: 8,500 token monolithic skill
   - Proposed:
     a) forecast-basics (2,000 tokens)
     b) forecast-advanced (4,000 tokens)
   - Allows: Agents load only what they need
   - Typical savings: 4,000 tokens per agent load

3. Merge pipeline-review and deal-analysis commands
   - Current: Two separate commands with overlap
   - Proposed: Single unified command with parameters
   - Eliminates: 800 tokens of duplicate setup
   - Simplifies: User experience

4. Extract methodology to skill from sales-analyst
   - Current: Agent has 850 tokens of scoring logic
   - Proposed: Reference pipeline-health-scoring skill
   - Savings: 800 tokens per agent load
   - Enables: Reuse by other agents
```

**Output**: Architecture refactoring recommendations with impact analysis

### 6. Generate Optimization Report

**Objective**: Produce comprehensive report with prioritized recommendations.

**Actions**:
- Compile all optimization findings
- Calculate total potential savings
- Prioritize recommendations by:
  - Impact (token savings)
  - Effort (implementation complexity)
  - Risk (likelihood of breaking changes)
- Create implementation roadmap
- Document before/after scenarios
- Generate optimization checklist

**Report Structure**:
```markdown
# Plugin Optimization Report: revenue-operations

## Executive Summary
- Current Token Usage: 42,300 tokens
- Potential Savings: 12,100 tokens (28.6% reduction)
- Optimized Token Usage: 30,200 tokens
- Implementation Effort: Medium
- Risk Level: Low

## Current State
- Agents: 9,000 tokens (2 components)
- Skills: 12,600 tokens (2 components)
- Commands: 2,400 tokens (1 component)
- Hotspots: forecast-methodology skill, sales-analyst agent

## Optimization Opportunities

### High Impact (> 1000 tokens)
1. Extract methodology from sales-analyst to skill (1,400 tokens)
2. Split forecast-methodology skill (4,000 typical savings)
3. Consolidate duplicate definitions (2,820 tokens)

### Medium Impact (500-1000 tokens)
4. Apply progressive disclosure to skills (1,000 tokens)
5. Optimize verbose descriptions (800 tokens)

### Low Impact (< 500 tokens)
6. Compress examples (450 tokens)
7. Refactor output templates (160 tokens)

## Implementation Roadmap

### Phase 1: Quick Wins (Low Effort, High Impact)
- [ ] Consolidate duplicate definitions
- [ ] Optimize verbose descriptions
- [ ] Compress redundant examples
- Effort: 2-3 hours
- Savings: 4,230 tokens (10%)

### Phase 2: Structural Improvements (Medium Effort, High Impact)
- [ ] Extract methodology from sales-analyst
- [ ] Apply progressive disclosure patterns
- [ ] Create shared terminology skill
- Effort: 4-6 hours
- Savings: 3,200 tokens (7.6%)

### Phase 3: Architecture Refactoring (High Effort, High Impact)
- [ ] Split forecast-methodology skill
- [ ] Merge overlapping commands
- [ ] Implement on-demand resource loading
- Effort: 6-8 hours
- Savings: 4,670 tokens (11%)

## Before/After Comparison

| Component | Current | Optimized | Savings |
|-----------|---------|-----------|---------|
| sales-analyst | 5,200 | 3,800 | 1,400 (27%) |
| pipeline-manager | 3,800 | 3,600 | 200 (5%) |
| pipeline-health-scoring | 4,100 | 3,500 | 600 (15%) |
| forecast-methodology | 8,500 | 5,800 | 2,700 (32%) |
| pipeline-review | 2,400 | 2,200 | 200 (8%) |
| **Total** | **42,300** | **30,200** | **12,100 (28.6%)** |

## Next Steps
1. Review recommendations with team
2. Prioritize based on business needs
3. Implement Phase 1 quick wins
4. Validate changes with tests
5. Proceed to Phase 2 and 3
6. Re-run optimization analysis
```

**Output**: Complete optimization report with roadmap

## Output Format

The command produces:

1. **Console Summary**:
```
Analyzing plugin: revenue-operations
✓ Token usage analysis complete
✓ Redundancy detection complete
✓ Progressive disclosure opportunities identified
✓ Content optimization suggestions generated
✓ Architecture recommendations prepared

Current Usage: 42,300 tokens
Potential Savings: 12,100 tokens (28.6%)
Optimized Usage: 30,200 tokens

Full report: plugins/revenue-operations/OPTIMIZATION-REPORT.md
```

2. **Optimization Report File**: `{plugin-path}/OPTIMIZATION-REPORT.md`

3. **Implementation Checklist**: Step-by-step optimization tasks

4. **Before/After Metrics**: Detailed comparison

## Success Criteria

- Token usage accurately measured
- Optimization opportunities identified and prioritized
- Recommendations are actionable and specific
- Savings estimates are realistic
- Implementation effort is assessed
- Risk levels are identified
- Report is comprehensive and clear
- Roadmap provides clear next steps
- Before/after comparison shows value
- Quick wins are identified for immediate impact

## Related Plugins

- **meta-agent-builder**: Parent plugin for generation
- **plugin-validator**: Validates structure and quality
- **token-analyzer**: Deep token usage analysis tools

---

**Best Practice**: Focus on quick wins first to demonstrate value, then tackle larger architectural refactoring. Always validate optimizations don't reduce functionality.

**Performance Tip**: Run optimization analysis periodically as plugins grow and evolve. Token efficiency can degrade over time without active management.
