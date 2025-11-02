---
name: orchestration-templates
description: Multi-agent orchestration patterns for common business processes including sequential, parallel, conditional, and iterative workflows. Covers hybrid orchestration, context management, error handling, and quality checkpoints. Use when designing workflows that coordinate multiple agents, automating complex business processes, or optimizing multi-step operations.
---

# Orchestration Templates

Comprehensive patterns for orchestrating multiple specialized agents to execute complex business processes efficiently with proper context management, error handling, and quality control.

## When to Use This Skill

- Designing multi-agent workflows for business processes
- Automating complex operations requiring multiple specialists
- Coordinating sequential or parallel agent execution
- Implementing business process workflows (QBRs, planning cycles)
- Optimizing multi-step analytical workflows
- Building hybrid orchestrations (Sonnet planning + Haiku execution)
- Managing context and data flow between agents
- Implementing error handling and retry logic
- Establishing quality checkpoints in workflows
- Creating reusable orchestration templates

## Core Concepts

### 1. Orchestration Patterns

**Sequential Orchestration**
- Agents execute one after another
- Output of one agent feeds into next
- Use when steps must happen in order
- Example: Planning → Execution → Review

**Parallel Orchestration**
- Multiple agents execute simultaneously
- Independent tasks that can run concurrently
- Use for efficiency when no dependencies
- Example: Analyzing multiple regions simultaneously

**Conditional Orchestration**
- Agent selection based on conditions
- Decision points determine workflow path
- Use when different scenarios require different approaches
- Example: If forecast variance > 10%, escalate to senior analyst

**Iterative Orchestration**
- Repeat agent execution until criteria met
- Refinement loops for quality improvement
- Use when quality threshold required
- Example: Forecast → Review → Refine until accuracy acceptable

### 2. Hybrid Orchestration (Model Mixing)

**Pattern: Sonnet (Planning) → Haiku (Execution) → Sonnet (Review)**

**Benefits:**
- Cost optimization (Haiku cheaper for execution)
- Speed optimization (Haiku faster for deterministic tasks)
- Quality optimization (Sonnet for complex reasoning)

**Example:**
```
1. Sonnet: sales-analyst designs analysis approach
2. Haiku: data-processor executes calculations
3. Haiku: report-generator creates initial draft
4. Sonnet: sales-analyst reviews and adds insights
```

### 3. Context Management

**Context Passing Strategies:**
- **Direct Output:** Agent A output → Agent B input
- **Shared State:** Agents read/write to shared data store
- **Summarization:** Compress context between steps
- **Selective Passing:** Pass only relevant information

**Data Flow Patterns:**
- Linear: A → B → C → D
- Fan-out: A → [B, C, D] (parallel)
- Fan-in: [A, B, C] → D (aggregation)
- Pipeline: A → B → C with intermediate storage

### 4. Error Handling & Quality Checkpoints

**Error Handling:**
- Retry logic with exponential backoff
- Fallback to alternative approaches
- Graceful degradation
- Error reporting and alerting

**Quality Checkpoints:**
- Validation after each critical step
- Human-in-the-loop for high-stakes decisions
- Automated quality scoring
- Confidence thresholds for proceeding

## Orchestration Templates by Business Process

### Template 1: Monthly Revenue Review (QBR Process)

**Purpose:** Comprehensive quarterly business review analyzing revenue performance, pipeline health, and forecast accuracy

**Duration:** 3-7 phases, 1-2 hours execution time

**Orchestration Pattern:** Sequential with parallel sub-processes

**Workflow:**

```
Phase 1: Context Gathering (Parallel)
├─ Agent: data-processor (Haiku)
│  Task: Gather revenue data, pipeline snapshots, forecast submissions
│  Output: Consolidated dataset with validation report
│
├─ Agent: data-processor (Haiku)
│  Task: Gather historical performance data (last 4 quarters)
│  Output: Historical trends dataset
│
└─ Agent: data-processor (Haiku)
   Task: Gather team and rep-level data
   Output: Team performance dataset

Phase 2: Revenue Analysis (Sequential)
└─ Agent: sales-analyst (Sonnet)
   Task: Analyze revenue vs. target, identify trends and variances
   Output: Revenue analysis report with insights
   Quality Checkpoint: Variance > 10% triggers additional analysis

Phase 3: Pipeline Analysis (Sequential)
└─ Agent: sales-analyst (Sonnet)
   Task: Assess pipeline health, coverage, stage distribution
   Skills: pipeline-health-scoring
   Output: Pipeline health report with risk assessment
   Quality Checkpoint: Coverage < 3x triggers alert

Phase 4: Forecast Accuracy Analysis (Sequential)
└─ Agent: forecast-optimizer (Sonnet)
   Task: Compare forecast to actuals, calculate accuracy metrics
   Skills: forecasting-methods
   Output: Forecast accuracy report with improvement recommendations
   Quality Checkpoint: MAPE > 15% triggers deep dive

Phase 5: Rep Performance Analysis (Sequential)
└─ Agent: sales-analyst (Sonnet)
   Task: Analyze rep-level performance, identify coaching needs
   Output: Rep scorecards and coaching recommendations
   Quality Checkpoint: Variance from team average > 20% flagged

Phase 6: Synthesis and Recommendations (Sequential)
└─ Agent: sales-analyst (Sonnet)
   Task: Synthesize findings, develop action plan
   Output: Executive summary with prioritized recommendations

Phase 7: Report Generation (Sequential)
└─ Agent: report-generator (Haiku)
   Task: Create formatted QBR presentation
   Output: Executive-ready QBR deck with visualizations
```

**Context Flow:**
```
Data → Revenue Analysis → Pipeline Analysis → Forecast Analysis → Rep Analysis → Synthesis → Report
```

**Error Handling:**
- If data quality issues: Alert and request data refresh
- If analysis fails: Retry with simplified methodology
- If metrics incomplete: Flag and proceed with available data

**Success Criteria:**
- All key metrics calculated and visualized
- Clear identification of trends and variances
- Actionable recommendations with owners and timelines
- Executive-ready deliverable

### Template 2: Demand Planning Cycle (S&OP Process)

**Purpose:** Monthly Sales and Operations Planning process for demand forecasting and supply planning

**Duration:** 5-8 phases, 2-4 hours execution time

**Orchestration Pattern:** Sequential with conditional branches

**Workflow:**

```
Phase 1: Historical Demand Analysis (Sequential)
└─ Agent: demand-forecaster (Sonnet)
   Task: Analyze historical demand patterns, seasonality, trends
   Skills: demand-forecasting-methods
   Output: Demand pattern analysis report
   Quality Checkpoint: Data completeness > 90%

Phase 2: Statistical Forecast Generation (Sequential)
└─ Agent: demand-forecaster (Sonnet)
   Task: Generate baseline statistical forecasts
   Skills: demand-forecasting-methods
   Output: Statistical forecast by SKU/category
   Quality Checkpoint: Forecast accuracy on holdout > 85%

Phase 3: Market Intelligence Integration (Parallel)
├─ Agent: market-analyst (Sonnet)
│  Task: Analyze market trends, competitive dynamics
│  Output: Market intelligence summary
│
├─ Agent: sales-analyst (Sonnet)
│  Task: Gather sales team input on upcoming deals
│  Output: Sales intelligence report
│
└─ Agent: marketing-analyst (Sonnet)
   Task: Assess impact of planned campaigns/promotions
   Output: Marketing calendar with demand impact

Phase 4: Forecast Adjustment (Sequential)
└─ Agent: demand-forecaster (Sonnet)
   Task: Adjust statistical forecast with business intelligence
   Output: Consensus demand forecast
   Quality Checkpoint: Material adjustments (>20%) require justification

Phase 5: Inventory Optimization (Sequential)
└─ Agent: inventory-optimizer (Sonnet)
   Task: Calculate optimal inventory levels and reorder points
   Skills: inventory-optimization-methods
   Output: Inventory plan with safety stock recommendations
   Quality Checkpoint: Service level targets met (95%+)

Phase 6: Capacity Analysis (Conditional)
└─ If (Demand Exceeds Capacity):
   ├─ Agent: capacity-planner (Sonnet)
   │  Task: Identify capacity constraints and alternatives
   │  Output: Capacity gap analysis
   │
   └─ Agent: supply-planner (Sonnet)
      Task: Develop supply strategy (overtime, outsourcing, etc.)
      Output: Supply plan recommendations

   Else:
   └─ Skip to Phase 7

Phase 7: Financial Impact Analysis (Sequential)
└─ Agent: budget-analyst (Sonnet)
   Task: Calculate financial impact of plan (COGS, inventory investment)
   Output: Financial impact summary
   Quality Checkpoint: Budget variance < 5%

Phase 8: S&OP Report Generation (Sequential)
└─ Agent: report-generator (Haiku)
   Task: Create S&OP review presentation
   Output: S&OP executive presentation with scenarios
```

**Context Flow:**
```
Historical Data → Statistical Forecast → [Market Intelligence + Sales Intelligence + Marketing Intelligence] → Adjusted Forecast → Inventory Plan → Capacity Analysis (conditional) → Financial Impact → Report
```

**Error Handling:**
- If forecast accuracy low: Flag for manual review before proceeding
- If capacity constraints: Trigger alternative scenario planning
- If data gaps: Interpolate or use conservative estimates

**Success Criteria:**
- Consensus demand forecast with < 10% variance from statistical baseline
- Inventory plan meets service level targets
- Financial impact within budget constraints
- Executive alignment on plan

### Template 3: Marketing Attribution Analysis

**Purpose:** Multi-touch attribution analysis to understand marketing channel effectiveness and optimize spend

**Duration:** 4-6 phases, 1-3 hours execution time

**Orchestration Pattern:** Sequential with parallel data gathering

**Workflow:**

```
Phase 1: Data Collection (Parallel)
├─ Agent: data-processor (Haiku)
│  Task: Extract marketing touchpoint data from platforms
│  Output: Marketing touchpoint dataset
│
├─ Agent: data-processor (Haiku)
│  Task: Extract conversion and revenue data from CRM
│  Output: Conversion dataset
│
└─ Agent: data-processor (Haiku)
   Task: Extract cost data from financial systems
   Output: Marketing spend dataset

Phase 2: Customer Journey Mapping (Sequential)
└─ Agent: attribution-specialist (Sonnet)
   Task: Map customer journeys from first touch to conversion
   Output: Journey path analysis
   Quality Checkpoint: > 80% of conversions have complete journey data

Phase 3: Attribution Modeling (Parallel)
├─ Agent: attribution-specialist (Sonnet)
│  Task: Build first-touch attribution model
│  Output: First-touch attribution results
│
├─ Agent: attribution-specialist (Sonnet)
│  Task: Build last-touch attribution model
│  Output: Last-touch attribution results
│
├─ Agent: attribution-specialist (Sonnet)
│  Task: Build linear attribution model
│  Output: Linear attribution results
│
└─ Agent: attribution-specialist (Sonnet)
   Task: Build time-decay attribution model
   Skills: attribution-modeling-methods
   Output: Time-decay attribution results

Phase 4: Model Comparison and Selection (Sequential)
└─ Agent: attribution-specialist (Sonnet)
   Task: Compare attribution models, recommend best fit
   Output: Model comparison report with recommendation
   Quality Checkpoint: Recommended model aligns with business understanding

Phase 5: Channel Effectiveness Analysis (Sequential)
└─ Agent: campaign-analyst (Sonnet)
   Task: Analyze ROI and efficiency by channel
   Output: Channel effectiveness report with metrics (ROAS, CPA, etc.)
   Quality Checkpoint: All major channels represented

Phase 6: Optimization Recommendations (Sequential)
└─ Agent: campaign-analyst (Sonnet)
   Task: Recommend budget reallocation for optimal ROI
   Output: Budget optimization recommendations with expected impact
   Quality Checkpoint: Recommendations sum to current budget constraint

Phase 7: Report Generation (Sequential)
└─ Agent: report-generator (Haiku)
   Task: Create attribution analysis presentation
   Output: Executive report with visualizations and recommendations
```

**Context Flow:**
```
[Marketing Data + Conversion Data + Cost Data] → Customer Journeys → [Multiple Attribution Models] → Model Selection → Channel Analysis → Optimization → Report
```

**Error Handling:**
- If journey data incomplete: Use partial attribution with confidence intervals
- If models disagree significantly: Present multiple perspectives
- If optimization infeasible: Provide constrained recommendations

**Success Criteria:**
- Complete customer journey mapping for >80% of conversions
- Multiple attribution models compared
- Clear channel effectiveness metrics
- Actionable budget optimization recommendations

### Template 4: Customer Churn Analysis and Prevention

**Purpose:** Identify at-risk customers and develop targeted retention strategies

**Duration:** 5-7 phases, 2-3 hours execution time

**Orchestration Pattern:** Sequential with iterative refinement

**Workflow:**

```
Phase 1: Customer Data Collection (Parallel)
├─ Agent: data-processor (Haiku)
│  Task: Extract customer profile and contract data
│  Output: Customer profile dataset
│
├─ Agent: data-processor (Haiku)
│  Task: Extract product usage and engagement data
│  Output: Usage metrics dataset
│
├─ Agent: data-processor (Haiku)
│  Task: Extract support ticket and NPS data
│  Output: Customer feedback dataset
│
└─ Agent: data-processor (Haiku)
   Task: Extract historical churn data
   Output: Churn history dataset

Phase 2: Cohort Retention Analysis (Sequential)
└─ Agent: retention-analyst (Sonnet)
   Task: Analyze retention patterns by cohort
   Skills: cohort-retention-analysis
   Output: Retention curve analysis with trends
   Quality Checkpoint: Statistical significance of observed patterns

Phase 3: Churn Risk Scoring (Sequential)
└─ Agent: churn-predictor (Sonnet)
   Task: Score all active customers for churn risk
   Skills: churn-prediction-methods
   Output: Churn risk scores with confidence intervals
   Quality Checkpoint: Model accuracy > 75% on validation set

Phase 4: At-Risk Customer Identification (Sequential)
└─ Agent: churn-predictor (Sonnet)
   Task: Identify high-risk customers requiring intervention
   Output: Prioritized list of at-risk customers
   Quality Checkpoint: Risk scores above threshold (>70%)

Phase 5: Root Cause Analysis (Parallel)
├─ Agent: retention-analyst (Sonnet)
│  Task: Analyze usage patterns of at-risk customers
│  Output: Usage-based churn drivers
│
├─ Agent: retention-analyst (Sonnet)
│  Task: Analyze support and satisfaction data
│  Output: Sentiment-based churn drivers
│
└─ Agent: retention-analyst (Sonnet)
   Task: Analyze competitive and market factors
   Output: External churn drivers

Phase 6: Intervention Strategy Development (Iterative)
└─ Agent: retention-strategist (Sonnet)
   Task: Develop targeted retention strategies by segment
   Output: Retention playbook with specific interventions
   Quality Checkpoint: Strategies aligned with root causes
   Iteration: If strategies insufficient, refine based on feedback

Phase 7: Impact Projection (Sequential)
└─ Agent: retention-analyst (Sonnet)
   Task: Project impact of retention strategies on churn and NRR
   Output: Expected impact analysis with scenarios
   Quality Checkpoint: Projections based on historical intervention data

Phase 8: Report Generation (Sequential)
└─ Agent: report-generator (Haiku)
   Task: Create churn analysis and retention strategy presentation
   Output: Executive report with at-risk accounts and action plan
```

**Context Flow:**
```
[Customer Data + Usage Data + Feedback Data + Churn History] → Cohort Analysis → Risk Scoring → At-Risk Identification → [Usage Drivers + Sentiment Drivers + External Drivers] → Intervention Strategy (iterative) → Impact Projection → Report
```

**Error Handling:**
- If prediction accuracy low: Flag model for retraining
- If root causes unclear: Conduct deeper qualitative analysis
- If intervention strategies untested: Pilot with subset before rollout

**Success Criteria:**
- All active customers scored for churn risk
- At-risk customers identified and prioritized
- Root causes clearly identified
- Targeted intervention strategies with expected impact
- Executive-ready action plan

### Template 5: Budget Variance Analysis

**Purpose:** Monthly budget variance analysis with root cause identification and corrective action planning

**Duration:** 4-6 phases, 1-2 hours execution time

**Orchestration Pattern:** Sequential with conditional deep dives

**Workflow:**

```
Phase 1: Data Gathering (Parallel)
├─ Agent: data-processor (Haiku)
│  Task: Extract actual financial results from ERP
│  Output: Actuals dataset
│
├─ Agent: data-processor (Haiku)
│  Task: Extract budget/forecast data
│  Output: Budget dataset
│
└─ Agent: data-processor (Haiku)
   Task: Extract prior period data for trending
   Output: Historical comparison dataset

Phase 2: Variance Calculation (Sequential)
└─ Agent: budget-analyst (Sonnet)
   Task: Calculate variances at all levels (total, category, line item)
   Output: Variance analysis with materiality flags
   Quality Checkpoint: Variances reconcile to totals

Phase 3: Material Variance Identification (Sequential)
└─ Agent: budget-analyst (Sonnet)
   Task: Identify material variances (>5% and >$X threshold)
   Output: Material variance report with priorities
   Quality Checkpoint: All >10% variances flagged

Phase 4: Root Cause Analysis (Conditional, Parallel)
For Each Material Variance:
├─ If Revenue Variance:
│  └─ Agent: revenue-analyst (Sonnet)
│     Task: Analyze revenue drivers (volume, price, mix)
│     Output: Revenue variance decomposition
│
├─ If COGS Variance:
│  └─ Agent: cost-analyst (Sonnet)
│     Task: Analyze cost drivers (material, labor, overhead)
│     Output: COGS variance decomposition
│
├─ If Opex Variance:
│  └─ Agent: budget-analyst (Sonnet)
│     Task: Analyze operating expense drivers
│     Output: Opex variance explanation
│
└─ If Timing Variance:
   └─ Agent: budget-analyst (Sonnet)
      Task: Assess if variance is timing or permanent
      Output: Timing vs. permanent classification

Phase 5: Forecast Impact Assessment (Sequential)
└─ Agent: budget-analyst (Sonnet)
   Task: Assess impact on full-year forecast
   Output: Revised forecast with variance projections
   Quality Checkpoint: Forecast assumptions documented

Phase 6: Corrective Action Planning (Sequential)
└─ Agent: budget-analyst (Sonnet)
   Task: Develop corrective action plans for negative variances
   Output: Action plan with owners, timelines, and expected impact
   Quality Checkpoint: Actions address root causes

Phase 7: Report Generation (Sequential)
└─ Agent: report-generator (Haiku)
   Task: Create variance analysis presentation
   Output: Executive variance report with action plans
```

**Context Flow:**
```
[Actuals + Budget + History] → Variance Calculation → Material Variance Identification → Root Cause Analysis (conditional by variance type) → Forecast Impact → Corrective Actions → Report
```

**Error Handling:**
- If data doesn't reconcile: Alert finance team for data correction
- If root cause unclear: Escalate for manual investigation
- If corrective actions insufficient: Request additional budget or revised forecast

**Success Criteria:**
- All material variances explained with root causes
- Forecast updated with variance impact
- Corrective action plans with clear owners and timelines
- Executive-ready variance report

## Performance Optimization Strategies

### 1. Parallel Execution

**When to Use:**
- Independent data gathering tasks
- Multiple model or scenario runs
- Analysis of different segments or regions

**Example:**
```
Instead of:
  Gather Region 1 data → Gather Region 2 data → Gather Region 3 data (3 hours)

Run in parallel:
  [Gather Region 1, Region 2, Region 3 simultaneously] (1 hour)
```

**Implementation:**
```
Phase X: Regional Analysis (Parallel)
├─ Agent: sales-analyst (Sonnet) - Region 1
├─ Agent: sales-analyst (Sonnet) - Region 2
└─ Agent: sales-analyst (Sonnet) - Region 3
```

### 2. Hybrid Model Orchestration

**Pattern:**
```
Sonnet (planning/design) → Haiku (execution/processing) → Sonnet (review/insights)
```

**Benefits:**
- Cost: Haiku cheaper for execution
- Speed: Haiku faster for deterministic tasks
- Quality: Sonnet for complex reasoning

**Example:**
```
Phase 1: Analysis Design
└─ Agent: sales-analyst (Sonnet)
   Task: Design analysis approach and metrics

Phase 2: Data Processing and Calculation
└─ Agent: data-processor (Haiku)
   Task: Execute calculations per design

Phase 3: Insight Generation
└─ Agent: sales-analyst (Sonnet)
   Task: Interpret results and generate insights
```

### 3. Conditional Execution

**Skip unnecessary steps based on conditions**

**Example:**
```
Phase 3: Detailed Analysis (Conditional)
If (Variance > 10%):
  └─ Execute detailed root cause analysis
Else:
  └─ Skip to summary report
```

**Benefits:**
- Save time when detailed analysis not needed
- Focus resources on material issues
- Faster execution for routine scenarios

### 4. Result Caching

**Cache intermediate results to avoid recomputation**

**Example:**
```
Phase 1: Historical Analysis
└─ Agent: demand-forecaster
   Task: Analyze last 24 months demand patterns
   Cache: Historical pattern analysis (valid for 1 month)

Phase 2: Forecast Generation (uses cached historical analysis)
```

## Quality Checkpoint Patterns

### 1. Data Quality Checks

**Pattern:**
```
Phase X: Data Validation
└─ Agent: data-processor (Haiku)
   Task: Validate data completeness and consistency
   Checks:
   - Completeness: > 95% of expected records
   - Consistency: No duplicate records
   - Accuracy: Values within expected ranges
   - Freshness: Data within 24 hours

   If Failed: Alert and request data refresh
   If Passed: Proceed to analysis
```

### 2. Analysis Quality Checks

**Pattern:**
```
Phase X: Analysis Validation
└─ Agent: sales-analyst (Sonnet)
   Task: Perform analysis
   Quality Checks:
   - Statistical significance: p-value < 0.05
   - Sample size: n > minimum threshold
   - Confidence intervals: Within acceptable range

   If Failed: Flag results as low confidence
   If Passed: Proceed with recommendations
```

### 3. Recommendation Quality Checks

**Pattern:**
```
Phase X: Recommendation Validation
└─ Agent: budget-analyst (Sonnet)
   Task: Develop recommendations
   Quality Checks:
   - Actionability: Clear owner and timeline
   - Feasibility: Within resource constraints
   - Impact: Quantified expected outcome
   - Alignment: Consistent with strategy

   If Failed: Refine recommendations
   If Passed: Generate report
```

### 4. Human-in-the-Loop Checkpoints

**Pattern:**
```
Phase X: Critical Decision Point
└─ Agent: sales-analyst (Sonnet)
   Task: Generate forecast adjustment recommendations

   Checkpoint: Human Review Required
   - If adjustment > 20%: Require executive approval
   - If high-stakes decision: Present multiple scenarios
   - If data quality concerns: Flag for manual validation
```

## Error Handling Patterns

### 1. Retry with Exponential Backoff

**Pattern:**
```
Try:
  Execute agent task
Catch TransientError:
  Wait 1 second
  Retry (max 3 attempts with exponential backoff: 1s, 2s, 4s)
  If all retries fail: Log error and proceed to fallback
```

### 2. Fallback Strategies

**Pattern:**
```
Phase X: Primary Approach
Try:
  └─ Agent: demand-forecaster (Sonnet)
     Task: Build ARIMA forecast model
Catch ModelError:
  └─ Fallback: Simple moving average forecast
     Log: "ARIMA failed, using simple moving average"
```

### 3. Graceful Degradation

**Pattern:**
```
Phase X: Comprehensive Analysis
Try:
  └─ Complete analysis with all data sources
Catch DataUnavailable:
  └─ Partial analysis with available data
     Flag: "Analysis incomplete due to missing data source X"
     Confidence: Reduced to 75%
```

### 4. Error Reporting and Alerting

**Pattern:**
```
On Error:
1. Log error details (phase, agent, task, error type, timestamp)
2. Assess impact (critical, high, medium, low)
3. If critical: Send alert to operations team
4. If high: Flag in report for manual review
5. If medium/low: Log and continue
```

## Best Practices

### 1. Design for Modularity

**Principles:**
- Each phase should be self-contained
- Clear inputs and outputs for each phase
- Agents can be swapped or upgraded independently
- Workflows can be reused across processes

### 2. Optimize for Efficiency

**Strategies:**
- Run independent tasks in parallel
- Use Haiku for deterministic execution
- Cache results when appropriate
- Skip unnecessary steps conditionally

### 3. Build in Quality Controls

**Checkpoints:**
- Data validation before analysis
- Statistical significance checks
- Recommendation feasibility validation
- Human review for high-stakes decisions

### 4. Plan for Errors

**Approach:**
- Identify potential failure points
- Implement retry logic for transient errors
- Define fallback strategies
- Ensure graceful degradation

### 5. Document Workflows

**Documentation:**
- Workflow diagram with phases and agents
- Context flow and data dependencies
- Error handling and quality checkpoints
- Success criteria and KPIs

## Resources

- **Source Framework:** wshobson/agents (multi-agent workflows in full-stack-orchestration, ml-pipeline, security-hardening)
- **Usage Guide:** /agents/docs/usage.md
- **Architecture:** /agents/docs/architecture.md (hybrid orchestration section)
- **Validation Rules:** validation-rules.md in this plugin
- **Examples:** Real business process workflows in command templates
