---
description: Analyze territory performance, workload balance, and optimization opportunities across sales team with rebalancing recommendations
argument-hint: [region] [timeframe]
version: "1.0.0"
tags: [territory, optimization, balance]
model: sonnet
---

# Territory Analysis Command

Comprehensive territory health and balance assessment with optimization recommendations.

## Context
Fair, balanced territories maximize team productivity and revenue outcomes while ensuring rep satisfaction.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Territory Data
For $1 region over $2 timeframe: Account counts by territory, ARR distribution, quota allocations, historical attainment, geographic coverage, account types.

### 2. Calculate Balance Metrics
- ARR variance (std dev, min/max range, Gini coefficient)
- Account count variance
- Workload indicators (travel time, complexity)
- Performance correlation with territory quality

### 3. Identify Imbalances
Territories with: Disproportionate opportunity (>30% variance), excessive workload, coverage gaps, poor geographic logic.

### 4. Model Optimization Scenarios
Design 2-3 rebalancing options with impact analysis (revenue projection, account reassignments, customer impact).

## Output Format
- Current state assessment: Territory balance scores, imbalance indicators
- Territory-by-territory profiles (accounts, ARR, quota, attainment)
- Imbalance analysis with root causes
- Optimization scenarios (minimal disruption, moderate rebalance, full redesign)
- Recommended approach with implementation plan
- Account reassignment list and transition timeline

## Success Criteria
- Analysis completed in 3-4 hours
- All territories scored and compared
- Imbalances quantified with impact calculated
- 2-3 scenarios modeled with trade-offs explained
- Preferred scenario recommended with rationale
- Implementation plan with customer communication strategy
