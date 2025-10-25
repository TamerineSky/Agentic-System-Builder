---
description: Conduct comprehensive quality control analysis including SPC, defect analysis, and process capability assessment for specified period.
argument-hint: [process-area] [analysis-period]
model: haiku
version: 1.0.0
tags: [quality, SPC, analysis]
---

# Quality Control Analysis

Analyze quality performance using statistical process control, defect analysis, and process capability assessment to identify improvement opportunities.

## Context

Quality analysis identifies process stability, capability gaps, and root causes of defects to drive continuous improvement and reduce cost of poor quality.

## Requirements
$ARGUMENTS

## Instructions

### 1. Data Collection

Gather quality data for $1 (process area) during $2 (analysis period):
- Inspection results (continuous measurements or defect counts)
- Defect data by type, location, and root cause
- Production volume and scrap/rework quantities
- Customer complaints and returns
- First pass yield (FPY) by product or process step

Sources: Quality management system, SPC software, production records.

### 2. Statistical Process Control (SPC) Analysis

Create control charts:
- **Continuous data**: X-bar and R charts (process mean and variability)
- **Attribute data**: p-chart (defect rate) or c-chart (defect count)

Calculate control limits:
```
UCL = Center Line + 3σ
LCL = Center Line - 3σ
```

Assess process stability:
- Identify out-of-control points (beyond control limits)
- Detect patterns (trends, shifts, cycles)
- Distinguish special cause vs. common cause variation

For out-of-control processes: Investigate and eliminate special causes before capability analysis.

### 3. Process Capability Analysis

Calculate capability indices:
```
Cp = (USL - LSL) / (6σ)
Cpk = min[(USL - μ)/3σ, (μ - LSL)/3σ]

Where:
USL/LSL = Upper/Lower specification limits
μ = Process mean
σ = Process standard deviation
```

Interpret results:
- Cpk ≥ 1.33: Capable (industry standard)
- 1.0 ≤ Cpk < 1.33: Marginal (improvement needed)
- Cpk < 1.0: Inadequate (produces defects)

If Cp > Cpk: Process off-center (adjust mean)
If Cp ≈ Cpk but low: Reduce process variation

### 4. Defect Analysis

Perform Pareto analysis:
- Rank defect types by frequency or cost
- Focus on top 20% of defects causing 80% of impact

Conduct root cause analysis (5 Whys or Fishbone):
- Investigate top defect types
- Identify root causes (materials, methods, equipment, operators, environment)
- Develop corrective actions

Calculate quality costs:
```
COPQ = Scrap + Rework + Warranty + Returns + Inspection
```

### 5. Recommendations

Provide improvement actions:
- **Out-of-control processes**: Eliminate special causes, implement process controls
- **Low capability**: Reduce variation (process improvement, equipment upgrade, training)
- **Off-center processes**: Adjust process settings to center on target
- **Top defects**: Address root causes with corrective actions
- **Cost reduction**: Calculate COPQ reduction from improvements

Prioritize by impact and feasibility.

## Output Format

1. **SPC Charts**: Control charts showing process stability
2. **Capability Report**: Cp/Cpk indices with interpretation
3. **Defect Pareto Chart**: Top defect types by frequency/cost
4. **Root Cause Analysis**: Fishbone or 5 Whys for top issues
5. **Action Plan**: Prioritized improvement initiatives

## Success Criteria

- Process stability assessed via SPC
- Capability indices calculated for critical characteristics
- Top 3-5 defect types identified with root causes
- Cost of poor quality quantified
- Actionable improvement plan with expected quality gains
