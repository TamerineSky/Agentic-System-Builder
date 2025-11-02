---
description: Perform ABC inventory classification by revenue contribution with recommendations for differentiated management policies.
argument-hint: [inventory-scope]
model: haiku
version: 1.0.0
tags: [inventory, segmentation, abc]
---

# ABC Inventory Classification

Classify inventory using ABC analysis to enable differentiated management policies and resource allocation.

## Context

ABC analysis applies Pareto principle (80/20 rule) to focus management attention and investment on high-value items while simplifying low-value items.

## Requirements
$ARGUMENTS

## Instructions

### 1. Data Collection
For $1 (inventory scope): Extract SKU list with annual usage volume and unit cost. Calculate annual dollar usage = Volume × Unit cost. Include on-hand inventory value.

### 2. ABC Classification
Sort SKUs by annual dollar usage descending. Calculate cumulative percentage of total usage. Classify: A items (top 20% of SKUs contributing ~80% of usage value), B items (next 30% of SKUs contributing ~15% of usage), C items (remaining 50% of SKUs contributing ~5% of usage). Validate thresholds match Pareto distribution.

### 3. Supplementary Analysis
Perform XYZ classification by demand variability (CoV = σ/μ): X (stable, CoV<0.5), Y (moderate, 0.5<CoV<1.0), Z (erratic, CoV>1.0). Create 9-box matrix (AX, AY, AZ, BX, BY, BZ, CX, CY, CZ).

### 4. Policy Recommendations
Suggest differentiated policies: **A items**: Tight control, frequent review, accurate forecasts, low safety stock %  (high value justifies attention). **B items**: Moderate control, periodic review, standard policies. **C items**: Simple rules (two-bin, min-max), higher safety stock % (low holding cost), infrequent review, consider consignment or VMI.

### 5. Implementation Planning
Recommend review frequencies, service level targets, and inventory control methods by segment. Calculate expected inventory investment change. Provide ERP/WMS configuration guidance.

## Output Format
1. ABC classification table with counts and values
2. 9-box ABC-XYZ matrix
3. Differentiated management policies by segment
4. Expected inventory investment impact
5. Implementation checklist

## Success Criteria
- All SKUs in $1 classified (A, B, or C)
- Pareto principle validated (~80/20 distribution)
- Clear policy differences by class
- Implementation-ready recommendations
- Expected benefits quantified
