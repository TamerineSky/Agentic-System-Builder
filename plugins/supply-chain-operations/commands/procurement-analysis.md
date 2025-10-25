---
description: Analyze procurement spend and sourcing strategies with recommendations for cost reduction and supplier optimization.
argument-hint: [category] [time-period]
model: sonnet
version: 1.0.0
tags: [procurement, spend-analysis, sourcing]
---

# Procurement Spend and Sourcing Analysis

Comprehensive procurement analysis identifying cost reduction opportunities, supplier consolidation, and strategic sourcing initiatives.

## Context

Procurement spend analysis reveals savings opportunities, supplier concentration risks, and strategic sourcing priorities for category management.

## Requirements
$ARGUMENTS

## Instructions

### 1. Spend Data Collection
Extract spend data for $1 (category) over $2 (time period) from AP, ERP, or procurement systems. Include supplier name, amount, commodity, business unit, payment terms. Cleanse and normalize data.

### 2. Spend Analysis
Calculate total spend, spend by supplier (concentration), spend trend, unit price trend. Perform Pareto analysis (80/20 rule). Benchmark against market prices. Identify maverick spend (off-contract).

### 3. Supplier Evaluation
Assess current suppliers on cost competitiveness, quality, delivery, risk. Calculate total cost of ownership (TCO) including quality and delivery costs. Identify consolidation opportunities.

### 4. Sourcing Strategy Development
Apply Kraljic matrix segmentation. Recommend competitive bidding for leverage items, partnership for strategic, secure supply for bottleneck. Identify make-vs-buy or multi-source opportunities.

### 5. Generate Recommendations
Quantify savings opportunities. Prioritize initiatives by impact. Provide implementation roadmap (RFP, negotiations, supplier transitions).

## Output Format
1. Spend summary and trends
2. Supplier concentration analysis
3. Cost reduction opportunities with savings estimates
4. Strategic sourcing recommendations
5. Implementation action plan

## Success Criteria
- Complete spend analysis for $1 over $2
- Top 5 savings opportunities identified and quantified
- Sourcing strategy aligned with category characteristics
- Action plan with timelines and ownership
