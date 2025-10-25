---
description: Recruiting funnel analysis with efficiency metrics and optimization recommendations
argument-hint: [period] [function]
version: "1.0.0"
tags: [recruiting, funnel, time-to-fill, efficiency]
tool_access: [Read, Write, Bash]
model: haiku
---

# Recruiting Funnel & Efficiency Analysis

Analyze recruiting funnel performance, identify bottlenecks, optimize time-to-fill, and evaluate source effectiveness.

## Requirements
- **Period**: Analysis timeframe (e.g., "last 6 months", "2024 YTD")
- **Function**: Department or "all"
- **ATS Data**: Candidate funnel data, source, stage durations, outcomes

## Instructions

### 1. Funnel Metrics
- End-to-end conversion rates (Applied → Hired)
- Stage-by-stage conversion (Screen, Interview, Offer, Accept)
- Benchmark vs. industry standards
- Identify drop-off points and bottlenecks

### 2. Time-to-Fill Analysis
- Overall time-to-fill (median, mean, P90)
- By function, level, role type
- Stage-level duration analysis
- Identify slowest stages (sourcing, interviewing, offer approval)

### 3. Source Effectiveness
- Source of hire distribution
- Conversion rates by source
- Cost-per-hire by source
- Quality of hire by source (performance, retention)
- ROI analysis and recommendations

### 4. Offer Metrics
- Offer acceptance rate overall and by source
- Reasons for offer declines
- Time from interview to offer
- Competitive offer analysis

### 5. Optimization Recommendations
- Bottleneck mitigation strategies
- Source mix optimization
- Interview process improvements
- Time-to-fill reduction opportunities

## Output Format
- Executive summary with key metrics and trends
- Full funnel visualization with conversion rates
- Time-to-fill breakdown by segment
- Source effectiveness scorecard
- Optimization recommendations with expected impact

## Related Plugins
**Skills**: recruiting-analytics
**Agents**: recruiting-efficiency-analyst
**Commands**: /offer-analysis, /talent-pipeline
