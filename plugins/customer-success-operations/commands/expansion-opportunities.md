---
description: Identify and qualify upsell, cross-sell, and expansion opportunities with whitespace analysis and revenue potential
argument-hint: [segment] [min-propensity]
version: "1.0.0"
tags: [expansion, upsell, growth]
model: sonnet
---

# Expansion Opportunities Command

Identify high-probability expansion revenue opportunities within customer base.

## Context
Systematic expansion identification drives net revenue retention and maximizes customer lifetime value with 3-5x lower CAC than new customer acquisition.

## Requirements
$ARGUMENTS

## Instructions

### 1. Define Target Segment
Analyze $1 segment with minimum propensity score of $2 (e.g., healthy-customers, enterprise, all with >60 propensity).

### 2. Calculate Expansion Propensity
For each customer: Score expansion readiness (0-100) based on health (80+ = ready), product adoption (>60% = mature), company growth signals (hiring, funding), engagement (executive involvement), budget capacity (historical expansion).

### 3. Conduct Whitespace Analysis
Identify untapped potential: Seat expansion (user headcount vs. licensed seats), tier upgrades (usage limits being hit), cross-sell (additional modules/products), geographic expansion (new offices/regions), use case expansion (additional departments).

### 4. Quantify Revenue Potential
For each opportunity: Calculate expansion ARR potential, estimate close probability by type (seats 60-70%, tier upgrades 45-55%, cross-sell 35-45%), project expected value (ARR × probability).

### 5. Prioritize Opportunities
Rank by: High propensity + high value + near-term timing (BANT qualified), effort-to-close assessment, strategic account value (reference potential, market significance).

### 6. Develop Execution Plan
Create playbooks by opportunity type: Seat expansion (license audit, department mapping), tier upgrade (ROI analysis, feature demos), cross-sell (use case workshops, pilots).

## Output Format
- Portfolio expansion summary (total pipeline, expected revenue, coverage vs. target)
- Tier 1 opportunities (top 25, high propensity + high value, close now)
- Tier 2-3 opportunities (developing, longer cycle)
- Whitespace analysis by dimension (seats, features, departments, geographies)
- Expansion playbook recommendations by type
- 30/60/90 day execution plan with targets
- Resource allocation (CSM vs. sales involvement)
- NRR impact projection

## Success Criteria
- Analysis completed in 45-60 minutes
- All qualified opportunities identified and scored
- Revenue potential quantified with probabilities
- Top 25 opportunities detailed with specific plays
- Execution plan with clear ownership and timelines
- Expected NRR impact calculated
