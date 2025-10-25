---
description: Analyze supplier lead time performance, variability, and improvement opportunities with recommendations.
argument-hint: [supplier-group] [period]
model: haiku
version: 1.0.0
tags: [supplier, lead-time, performance]
---

# Supplier Lead Time Analysis

Analyze supplier lead time performance, variability, and root causes with recommendations for reduction and improved reliability.

## Context

Lead time directly impacts inventory investment, customer service, and supply chain responsiveness. Shorter, more reliable lead times reduce safety stock and improve competitiveness.

## Requirements
$ARGUMENTS

## Instructions

### 1. Lead Time Data Collection
For $1 (supplier group) during $2 (period): Extract PO data with order date, requested delivery date, actual delivery date. Calculate: Committed lead time = Requested - Order date, Actual lead time = Actual - Order date, Lead time variance = Actual - Committed.

### 2. Performance Analysis
Calculate metrics: Average lead time, Lead time standard deviation, On-time delivery %, Lead time variability (CoV = σ/μ), 90th percentile lead time. Segment by supplier, commodity, or order characteristics.

### 3. Trend and Pattern Analysis
Plot lead time over time. Identify trends (increasing, stable, improving). Detect seasonality or cyclical patterns. Compare committed vs. actual lead times (supplier quote reliability). Identify outliers and investigate causes.

### 4. Root Cause Investigation
Analyze lead time components: Order processing time, Production/procurement time, Quality inspection, Shipping transit time. Identify bottlenecks and delays. Interview suppliers for constraints. Compare best-in-class vs. average performers.

### 5. Improvement Recommendations
Suggest actions: Negotiate shorter lead times with reliable suppliers, Reduce order processing time (e-procurement, EDI), Work with suppliers on cycle time reduction, Qualify faster alternative suppliers, Use expedited shipping for critical items, Implement vendor-managed inventory (VMI) to eliminate order cycle.

Calculate impact: Safety stock reduction from lower lead time variability, Inventory turns improvement, Cost-benefit of lead time initiatives.

## Output Format
1. Lead time performance dashboard
2. Supplier comparison table
3. Trend charts and variability analysis
4. Root cause analysis
5. Improvement action plan with impact estimates

## Success Criteria
- Complete lead time analysis for $1 over $2
- Variability and reliability metrics calculated
- Root causes of delays identified
- Top 5 improvement opportunities with savings estimates
- Action plan ready for supplier collaboration
