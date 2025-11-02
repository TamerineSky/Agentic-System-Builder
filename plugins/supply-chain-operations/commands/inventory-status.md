---
description: Analyze current inventory status, turnover, and health across categories with recommendations for optimization and rebalancing.
argument-hint: [category]
model: haiku
version: 1.0.0
tags: [inventory, analysis, operations]
---

# Inventory Status Analysis

Comprehensive analysis of current inventory levels, turnover rates, slow-moving stock, and stockout risks with actionable recommendations.

## Context

Regular inventory status reviews identify excess inventory, stockout risks, and rebalancing opportunities to optimize working capital and customer service.

## Requirements
$ARGUMENTS

## Instructions

### 1. Inventory Data Collection

Extract current inventory data for $1 (category):
- On-hand inventory by SKU and location
- Inventory value at cost
- Days on hand (DOH) = Inventory / Daily demand
- Inventory aging (30, 60, 90, 180+ days)
- Units on order (purchase orders, production orders)
- Recent demand history (last 90 days)

Source from ERP inventory management module or WMS.

### 2. Inventory Health Analysis

Calculate key inventory metrics:
- **Inventory turnover**: Annual COGS / Average inventory (target: >4-12× depending on industry)
- **Days on hand**: Inventory / Average daily demand (target: 30-90 days)
- **Fill rate**: Demand satisfied from stock / Total demand (target: >95%)
- **Stockout frequency**: % of SKUs out of stock (target: <5%)
- **Excess inventory**: Units with DOH > 180 days
- **Slow-moving (SLOB)**: No movement in 90+ days

Segment inventory:
- ABC classification by value
- XYZ classification by variability
- Fast-moving vs. slow-moving

### 3. Identify Issues and Risks

Highlight inventory problems:
- **Excess inventory**: High DOH, slow turnover, obsolescence risk
- **Stockout risks**: Low DOH, recent stockouts, high demand variability
- **Imbalanced inventory**: Excess in some SKUs, shortage in others
- **Dead stock**: No movement in 180+ days, obsolete or discontinued
- **Working capital tied up**: Total inventory value vs. target

Calculate financial impact:
- Excess inventory value × holding cost rate = opportunity cost
- Stockout impact: Lost sales, expedite costs, customer dissatisfaction

### 4. Develop Recommendations

Provide actionable recommendations:
- **Excess inventory**: Liquidation, promotions, returns to supplier, write-off
- **Stockout risks**: Emergency orders, safety stock increase, expediting
- **Rebalancing**: Transfer between locations, redistribute inventory
- **Policy adjustments**: Update reorder points, order quantities, service levels
- **Process improvements**: Better forecasting, supplier lead time reduction

Prioritize by financial impact and urgency.

## Output Format

1. **Inventory Summary Dashboard**: Key metrics (turnover, DOH, fill rate, stockouts)
2. **Category Breakdown**: Inventory value and health by product category
3. **Top Issues**: Highest priority excess, stockout risks, slow-movers
4. **ABC/XYZ Segmentation**: Inventory distribution by value and variability
5. **Action Plan**: Specific recommendations with expected impact

## Success Criteria

- Complete inventory snapshot as of current date
- Key metrics calculated (turnover, DOH, fill rate)
- Top 10 issues identified and prioritized
- Clear recommendations with financial impact quantified
- Deliverable ready for operations review
