---
description: Calculate optimal reorder points and order quantities using EOQ, safety stock, and service level analysis for specified products.
argument-hint: [product-category] [service-level]
model: sonnet
version: 1.0.0
tags: [inventory, optimization, reorder-point]
---

# Reorder Point and Order Quantity Calculation

Calculate optimal reorder points, order quantities, and safety stock levels using EOQ methodology and service level targets.

## Context

Reorder points and quantities balance inventory investment with customer service, preventing both stockouts and excess inventory.

## Requirements
$ARGUMENTS

## Instructions

### 1. Collect Required Data

For each SKU in $1 (product category):
- Average demand per period (weekly or daily)
- Demand standard deviation
- Lead time (supplier or production lead time)
- Lead time variability (if applicable)
- Unit cost
- Ordering cost (procurement, setup, or transportation)
- Holding cost rate (typically 20-30% annually)
- Target service level from $2

Extract from ERP, demand planning system, or historical analysis.

### 2. Calculate Economic Order Quantity (EOQ)

Apply EOQ formula:
```
EOQ = √(2 × D × S / h)

Where:
D = Annual demand
S = Ordering cost per order
h = Annual holding cost per unit (holding rate × unit cost)
```

Calculate order frequency and cycle stock:
```
Orders per year = D / EOQ
Order interval = 365 / Orders per year
Average cycle stock = EOQ / 2
```

Adjust EOQ for constraints (minimum order qty, packaging multiples, storage capacity).

### 3. Calculate Safety Stock

Determine safety stock based on $2 (service level):

For normal distribution:
```
Safety Stock = z × σ_LT

Where:
z = Normal distribution z-value for target service level
  (95% CSL: z = 1.65, 98% CSL: z = 2.05, 99% CSL: z = 2.33)
σ_LT = Standard deviation of demand during lead time

If lead time constant:
  σ_LT = σ_demand × √LT
  
If both demand and lead time variable:
  σ_LT = √(LT × σ_demand² + demand² × σ_LT²)
```

Calculate resulting fill rate and stockout frequency.

### 4. Compute Reorder Point

Calculate reorder point:
```
Reorder Point (ROP) = Expected demand during lead time + Safety stock
ROP = (Average demand × Lead time) + Safety stock
```

Determine inventory policy:
- **Continuous review (Q,R)**: Order EOQ when inventory hits ROP
- **Periodic review (R,S)**: Review every R periods, order up to S
  ```
  S = Expected demand during (Review + Lead time) + Safety stock
  ```

### 5. Generate Recommendations

For each SKU provide:
- Recommended order quantity (EOQ or adjusted)
- Reorder point with safety stock breakdown
- Expected inventory turnover and DOH
- Estimated annual holding and ordering costs
- Service level achievement (CSL and fill rate)
- Implementation notes (system parameters to update)

## Output Format

1. **Summary Table**: EOQ, ROP, safety stock for all SKUs
2. **Policy Parameters**: Inventory control policy (Q,R or R,S) for each SKU
3. **Financial Impact**: Total inventory investment, holding cost, expected service levels
4. **Implementation Guide**: ERP/WMS parameters to configure
5. **Sensitivity Analysis**: Impact of service level changes on inventory

## Success Criteria

- EOQ and ROP calculated for all SKUs in $1
- Target service level $2 achieved through safety stock
- Parameters ready for ERP/WMS implementation
- Expected inventory reduction or service improvement quantified
- Clear documentation for operations team
