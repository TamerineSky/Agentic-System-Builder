---
name: quality-control
description: Quality control methodologies including Statistical Process Control, Six Sigma DMAIC, process capability analysis, and root cause investigation to ensure quality. Use when analyzing quality issues, implementing SPC charts, or conducting Six Sigma improvement projects.
---

# Quality Control and Statistical Process Control

Systematic approaches to quality measurement, monitoring, and improvement using statistical process control, process capability analysis, and Six Sigma methodologies.

## When to Use This Skill

- Monitoring production processes for quality stability
- Investigating quality issues and identifying root causes
- Implementing statistical process control (SPC) systems
- Calculating process capability indices (Cp, Cpk)
- Conducting Six Sigma DMAIC improvement projects
- Reducing scrap, rework, and cost of poor quality
- Ensuring compliance with ISO 9001 or industry quality standards
- Validating measurement systems through gage R&R studies

## Core Quality Principles

### Process Variation

**Common Cause Variation**: Natural process variation (random, always present)
**Special Cause Variation**: Assignable causes (equipment malfunction, operator error, material defect)

Goal: Eliminate special causes, reduce common cause variation through process improvement

### Process Capability vs. Control

**In Control**: Process exhibits only common cause variation (predictable)
**Capable**: Process meets specification limits (Cpk > 1.33 typically)

A process can be in control but not capable (consistently produces defects)
A process can be capable but out of control (special causes present)

## Statistical Process Control (SPC)

### Control Chart Fundamentals

Control charts monitor process over time:
- **Center Line (CL)**: Process average
- **Upper Control Limit (UCL)**: CL + 3σ
- **Lower Control Limit (LCL)**: CL - 3σ

Points outside control limits indicate special cause (investigate immediately)

### X-bar and R Charts

For monitoring process mean and variability (continuous data)

**X-bar Chart** (averages):
```
CL = X̄̄ (grand average of subgroup averages)
UCL = X̄̄ + A₂ × R̄
LCL = X̄̄ - A₂ × R̄
```

**R Chart** (ranges):
```
CL = R̄ (average range)
UCL = D₄ × R̄
LCL = D₃ × R̄
```

A₂, D₃, D₄ are constants based on subgroup size (from tables)

**Example**: Monitoring shaft diameter
- Specification: 10.00 ± 0.05 mm
- Subgroup size: n=5
- X̄̄ = 10.01 mm, R̄ = 0.03 mm
- A₂ = 0.577, D₃ = 0, D₄ = 2.115

```
X-bar Chart:
UCL = 10.01 + 0.577 × 0.03 = 10.027 mm
LCL = 10.01 - 0.577 × 0.03 = 9.993 mm

R Chart:
UCL = 2.115 × 0.03 = 0.063 mm
LCL = 0 × 0.03 = 0 mm
```

### p-Chart (Proportion Defective)

For attribute data (defective vs. non-defective)

```
p̄ = Total Defectives / Total Inspected
UCL = p̄ + 3√[p̄(1-p̄)/n]
LCL = p̄ - 3√[p̄(1-p̄)/n]
```

**Example**: Monitoring defect rate in assembly
- Sample size: n=100 per day
- Average defect rate: p̄ = 0.03 (3%)

```
UCL = 0.03 + 3√[0.03 × 0.97/100] = 0.03 + 0.051 = 0.081 (8.1%)
LCL = 0.03 - 0.051 = -0.021 → 0 (cannot be negative)
```

### Out-of-Control Signals

Beyond control limits, watch for patterns:
1. **1 point beyond 3σ** (UCL or LCL)
2. **2 of 3 consecutive points beyond 2σ** (same side)
3. **4 of 5 consecutive points beyond 1σ** (same side)
4. **8 consecutive points on same side of center line** (shift)
5. **6 consecutive points increasing or decreasing** (trend)
6. **14 points alternating up and down** (over-control)
7. **15 points within 1σ of center line** (stratification, too good)

## Process Capability Analysis

### Capability Indices

**Cp (Process Capability)**:
```
Cp = (USL - LSL) / (6σ)

Where:
USL = Upper Specification Limit
LSL = Lower Specification Limit
σ = Process standard deviation
```

Measures potential capability (assumes centered process)

**Cpk (Process Capability Index)**:
```
Cpk = min[(USL - μ)/3σ, (μ - LSL)/3σ]

Where μ = process mean
```

Measures actual capability (accounts for centering)

**Interpretation**:
- Cpk ≥ 1.67: Excellent (Six Sigma target ≈ 1.67 for 5σ)
- Cpk ≥ 1.33: Adequate (industry standard)
- Cpk ≥ 1.00: Marginal (3σ, ~0.27% defects)
- Cpk < 1.00: Inadequate (process produces defects)

**Example**:
- Specification: 100 ± 10 (LSL=90, USL=110)
- Process: μ=102, σ=2

```
Cp = (110-90)/(6×2) = 20/12 = 1.67

Cpk = min[(110-102)/(3×2), (102-90)/(3×2)]
    = min[8/6, 12/6]
    = min[1.33, 2.00]
    = 1.33
```

Process capable (Cpk=1.33) but off-center (Cp=1.67 > Cpk)
**Action**: Center process to increase Cpk to match Cp

### Pp and Ppk (Performance Indices)

Similar to Cp/Cpk but use overall σ instead of within-subgroup σ:
- Use Pp/Ppk for long-term performance assessment
- Use Cp/Cpk for process potential (short-term, controlled)

## Six Sigma DMAIC Methodology

### Define Phase
- Define problem and project scope
- Identify critical customer requirements (CTQs)
- Create project charter and team
- Develop high-level process map

### Measure Phase
- Select key process metrics
- Develop data collection plan
- Validate measurement system (gage R&R)
- Establish baseline performance
- Calculate current sigma level

**Sigma Level Calculation**:
```
DPMO = (Defects / Opportunities) × 1,000,000
Sigma Level ≈ NORMSINV(1 - DPMO/1,000,000) + 1.5
```

Example: 3,000 DPMO → 4.2 sigma level

### Analyze Phase
- Identify potential root causes
- Analyze process data and variation sources
- Perform hypothesis testing
- Determine vital few root causes

### Improve Phase
- Generate improvement solutions
- Conduct design of experiments (DOE)
- Implement solutions and pilot test
- Validate improvement with data

### Control Phase
- Implement process controls (SPC, poka-yoke)
- Update procedures and train operators
- Monitor sustained improvement
- Calculate financial benefits

## Root Cause Analysis Tools

### 5 Whys

Ask "why" repeatedly to drill down to root cause:

```
Problem: Customer received defective parts

Why? Parts failed final inspection
Why? Parts were out of specification
Why? Machine tolerance drifted during production
Why? Machine was not calibrated per schedule
Why? Calibration schedule not enforced
Root Cause: Lack of preventive maintenance system
```

### Fishbone Diagram (Ishikawa)

Categories of potential causes (6 Ms):
- **Man**: Operator error, training, fatigue
- **Machine**: Equipment malfunction, wear, calibration
- **Method**: Process design, procedures, work instructions
- **Material**: Raw material defects, variation, storage
- **Measurement**: Gage accuracy, inspection methods
- **Mother Nature (Environment)**: Temperature, humidity, contamination

## Resources

### Quality Standards
- ISO 9001: Quality Management Systems
- IATF 16949: Automotive Quality
- AS9100: Aerospace Quality
- ISO 13485: Medical Devices

### Software Tools
- SPC software: InfinityQS, SPC for Excel, QI Macros
- Statistical analysis: Minitab, JMP, R (qcc package)
- QMS platforms: ETQ, MasterControl, TrackWise

### Books
- "Statistical Quality Control" by Montgomery
- "The Six Sigma Handbook" by Pyzdek & Keller
- "Understanding Statistical Process Control" by Wheeler

## Common Pitfalls

- Collecting data without understanding process (garbage in, garbage out)
- Using control charts on unstable processes (fix special causes first)
- Confusing specifications with control limits (different purposes)
- Not acting on out-of-control signals (defeats purpose of SPC)
- Over-adjusting process based on common cause variation
- Calculating Cpk on non-normal data without transformation
- Implementing SPC without training operators
- Focusing on detection rather than prevention
