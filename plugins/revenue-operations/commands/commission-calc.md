---
description: Calculate sales commissions based on comp plan rules including base, accelerators, splits, and adjustments with audit trail
argument-hint: [rep-name] [period]
version: "1.0.0"
tags: [commission, compensation, calculation]
model: haiku
---

# Commission Calculation Command

Accurate commission calculation with plan compliance and dispute resolution support.

## Context
Timely, accurate commission payments are critical for rep motivation and trust in compensation systems.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Commission Inputs
For $1 rep in $2 period: Closed deals (amounts, dates, products), quota targets, comp plan rules (rates, tiers, accelerators), splits/overlays, adjustments/clawbacks.

### 2. Apply Comp Plan Rules
- Calculate base commission per deal
- Apply tier/accelerator logic based on quota attainment
- Process any split arrangements
- Apply timing rules (booking vs. cash collection)
- Include SPIFFs or bonuses

### 3. Validate and Audit
Cross-check calculations, compare to previous periods, identify anomalies, document all adjustments.

### 4. Generate Commission Statement
Itemized breakdown with deal-by-deal detail, total commission, payment timeline.

## Output Format
- Commission summary: Total amount, base vs. accelerator, comparison to target
- Deal-by-deal breakdown with commission per deal
- Quota attainment calculation showing tier brackets
- Splits and adjustments log
- Payment schedule
- Audit trail of all calculations and rules applied

## Success Criteria
- Commission calculated within 1 hour of period close
- All deals accounted for
- Comp plan rules correctly applied
- Calculations auditable and explainable
- Disputes preventable through clear documentation
- Rep can verify calculations independently
