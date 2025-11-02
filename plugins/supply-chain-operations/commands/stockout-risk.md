---
description: Analyze stockout risk by product with root cause identification and mitigation recommendations.
argument-hint: [product-category]
model: haiku
version: 1.0.0
tags: [inventory, stockout, risk]
---

# Stockout Risk Analysis

Identify products at risk of stockout with root cause analysis and proactive mitigation strategies.

## Context

Stockouts cause lost sales, customer dissatisfaction, and expediting costs. Proactive risk identification enables preventive action.

## Requirements
$ARGUMENTS

## Instructions

### 1. Current Inventory Assessment
For $1 (product category): Calculate days on hand (DOH) = Inventory / Daily demand. Identify SKUs with DOH < safety threshold (typically 14-30 days). Review units on order and expected receipt dates.

### 2. Demand and Supply Analysis
Analyze recent demand trend (last 30 days vs. forecast). Identify demand spikes or seasonality. Review supplier lead times and on-time delivery performance. Calculate lead time demand variability.

### 3. Stockout Risk Scoring
Calculate risk score = f(Low DOH, High demand variability, Supplier reliability issues, Long lead time). Rank products by risk score. Classify as Critical (imminent stockout), High, Medium, Low risk.

### 4. Root Cause Identification
Investigate root causes: Forecast error (under-forecasted demand), Supply delay (supplier late deliveries), Policy error (inadequate safety stock or ROP), Allocation issues (inventory misplaced in network).

### 5. Mitigation Actions
Recommend immediate actions for critical risks: Emergency orders, expedited shipping, allocation from other locations, customer communication, temporary substitutes. Long-term fixes: Adjust forecasts, increase safety stock, improve supplier performance, dual sourcing.

## Output Format
1. Stockout risk ranking table
2. Root cause analysis for top 10 at-risk items
3. Immediate mitigation plan (1-7 days)
4. Long-term prevention strategy
5. Customer impact assessment

## Success Criteria
- All $1 SKUs risk-scored
- Top 10 at-risk items identified with root causes
- Immediate mitigation plan for critical risks
- Long-term prevention measures defined
- Ready for operations execution
