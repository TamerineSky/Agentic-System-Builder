---
description: Analyze total cost breakdown and cost drivers for product or service with recommendations for cost optimization.
argument-hint: [product-service]
model: sonnet
version: 1.0.0
tags: [cost, analysis, optimization]
---

# Total Cost Breakdown Analysis

Detailed cost analysis including total landed cost, cost-to-serve, and cost driver identification for optimization.

## Context

Understanding total cost components enables informed sourcing decisions, pricing strategies, and cost reduction initiatives.

## Requirements
$ARGUMENTS

## Instructions

### 1. Total Cost Data Collection
For $1 (product/service), gather: Unit price, inbound freight, duties/tariffs, packaging, inventory carrying cost (holding rate × value × time), quality costs (defects, rework), transaction costs (procurement, AP, receiving).

### 2. Cost Component Breakdown
Calculate total landed cost = Sum of all cost components. Express each as percentage of total. Identify top 3-5 cost drivers (typically materials, freight, labor).

### 3. Cost Driver Analysis
Analyze root causes: Material costs (commodities, specifications), Labor costs (rates, productivity), Freight (mode, distance, consolidation), Overhead (allocation methods). Benchmark against industry or alternative suppliers.

### 4. Should-Cost Modeling
Build bottom-up should-cost: Direct material (BOM costing), Direct labor (time × rate), Manufacturing overhead, G&A, Profit margin. Compare to actual cost to identify gaps.

### 5. Optimization Recommendations
Identify opportunities: Material substitution, design-to-cost, supplier negotiations, logistics optimization, process improvements. Quantify savings potential. Prioritize by impact and feasibility.

## Output Format
1. Total cost waterfall chart
2. Cost component breakdown table
3. Should-cost vs. actual comparison
4. Top 5 cost reduction opportunities
5. Implementation roadmap

## Success Criteria
- Complete cost breakdown for $1
- All major cost components identified and quantified
- Should-cost model validated
- Cost reduction opportunities totaling >10% identified
- Action plan with savings estimates
