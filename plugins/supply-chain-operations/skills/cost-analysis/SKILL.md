---
name: cost-analysis
description: Supply chain cost analysis including total cost of ownership, cost-to-serve modeling, activity-based costing, and cost breakdown analysis. Use when evaluating total product costs, analyzing customer profitability, or identifying cost reduction opportunities.
---

# Supply Chain Cost Analysis

Comprehensive cost analysis methodologies including total cost of ownership, cost-to-serve, ABC costing, and cost driver identification for supply chain optimization.

## When to Use This Skill

- Calculating total landed cost for sourcing decisions
- Analyzing cost-to-serve by customer or channel
- Identifying cost reduction opportunities
- Evaluating make-vs-buy decisions
- Allocating supply chain costs accurately
- Analyzing customer or product profitability
- Building should-cost models for negotiations

## Core Concepts

### Total Landed Cost

```
Total Landed Cost = 
  Product Cost (unit price)
  + Freight (inbound + outbound)
  + Duties and Tariffs
  + Packaging
  + Insurance
  + Inventory Carrying Cost
  + Quality Costs (defects, returns)
  + Payment Terms Cost (early pay discount or financing)
  + Transaction Costs (procurement, receiving, AP)
```

**Example**:
```
Product: $100
Freight: $8
Duty (10%): $10
Packaging: $3
Carrying cost (25% × $100 × 60 days / 365): $4
Quality cost (2% defect rate × $100): $2
Total Landed Cost: $127

Compare suppliers on TLC, not just unit price
```

### Cost-to-Serve Model

Activity-based costing for serving customers:

```
Cost-to-Serve = 
  Order Processing
  + Warehousing and Handling
  + Transportation
  + Inventory Carrying
  + Returns and Service
```

**Example**: Two customers, same revenue
```
Customer A:
- Large orders, predictable, low returns
- Cost-to-serve: 8% of revenue

Customer B:
- Small orders, frequent changes, high returns
- Cost-to-serve: 18% of revenue

Customer A is more profitable despite same revenue
```

## Methodologies

### Activity-Based Costing (ABC)

Allocate costs based on activities, not just volume:

**Traditional**: Allocate warehouse cost by units shipped
**ABC**: Allocate by:
- Receiving: Number of receipts
- Put-away: Number of pallets stored
- Picking: Number of picks
- Packing: Number of orders
- Shipping: Number of shipments

More accurate for diverse product/customer mix.

### Cost Driver Analysis

Identify root causes of costs:
- **Volume drivers**: Units, weight, cube
- **Complexity drivers**: SKU count, order lines, customization
- **Service drivers**: Lead time, frequency, special handling

**Pareto Analysis**:
- 80% of costs driven by 20% of activities
- Focus improvement on high-impact cost drivers

### Should-Cost Modeling

Bottom-up cost buildup for benchmarking:

```
Manufacturing Should-Cost:
  Direct Material: $50 (from bill of materials)
  Direct Labor: $15 (time study × labor rate)
  Manufacturing Overhead: $20 (indirect labor, utilities, depreciation)
  General & Administrative: $5
  Profit Margin (15%): $14
  Should-Cost: $104

Compare to supplier quote: $120
Gap analysis: $16 (15% premium)
```

## Resources

- **Costing software**: SAP PCM, Oracle Cost Management, Coupa Total Cost
- **Books**: "Cost Management" by Horngren, "Activity-Based Costing" by Kaplan & Cooper

## Common Pitfalls

- Comparing suppliers on price alone, ignoring total landed cost
- Using average costs instead of activity-based for decision-making
- Not tracking cost-to-serve by customer or channel
- Incomplete cost model missing key cost components
- Static cost models not updated for rate changes
