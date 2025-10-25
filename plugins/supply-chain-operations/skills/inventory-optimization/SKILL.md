---
name: inventory-optimization
description: Inventory optimization methodologies including EOQ, safety stock calculations, reorder points, and multi-echelon optimization to minimize costs while meeting service levels. Use when optimizing inventory levels, calculating safety stock, or designing inventory policies.
---

# Inventory Optimization

Master inventory optimization techniques to balance customer service with inventory investment through Economic Order Quantity, safety stock optimization, reorder point calculations, and multi-echelon network optimization.

## When to Use This Skill

- Calculating optimal order quantities to minimize total inventory costs
- Determining safety stock levels to achieve target service levels
- Computing reorder points for continuous or periodic review policies
- Optimizing inventory positioning across multi-tier distribution networks
- Reducing working capital tied up in inventory
- Improving inventory turnover while maintaining fill rates
- Designing differentiated inventory policies by product segment (ABC/XYZ)
- Evaluating trade-offs between inventory investment and customer service

## Core Inventory Principles

### 1. Inventory Cost Components

**Holding Cost (h)**: Cost to hold one unit for one year
- Warehouse space and handling
- Capital cost (opportunity cost of cash tied up)
- Insurance and taxes
- Obsolescence and shrinkage
- Typical range: 20-30% of item value annually

**Ordering Cost (S)**: Fixed cost per order
- Purchase order processing
- Transportation and receiving
- Setup costs for production
- Typical range: $50-500 per order

**Stockout Cost**: Cost of not having inventory
- Lost sales and margin
- Backorder costs and expediting
- Customer dissatisfaction and lost goodwill
- Often difficult to quantify precisely

### 2. Service Level Definitions

**Cycle Service Level (CSL)**: Probability of not stocking out during lead time
- 95% CSL = 95% of replenishment cycles have no stockout
- Most common service level metric

**Fill Rate**: Percentage of demand satisfied from stock
- Unit fill rate: Percentage of units filled
- Order fill rate: Percentage of orders completely filled
- Harder to achieve than CSL (e.g., 95% CSL ≈ 98-99% fill rate)

**Ready Rate**: Percentage of time item is in stock
- Item is in stock X% of days

### 3. ABC/XYZ Segmentation

**ABC Analysis** (by revenue contribution):
- A items: Top 20% of SKUs contributing 80% of revenue
- B items: Next 30% of SKUs contributing 15% of revenue
- C items: Remaining 50% of SKUs contributing 5% of revenue

**XYZ Analysis** (by demand variability):
- X items: Low variability (CoV < 0.5) - stable demand
- Y items: Medium variability (0.5 < CoV < 1.0)
- Z items: High variability (CoV > 1.0) - erratic demand

Where CoV = Coefficient of Variation = σ / μ

**Policy Differentiation**:
- AX: High value, stable → Tight control, optimize carefully
- CZ: Low value, erratic → Simple rules, accept stockouts

## EOQ and Order Quantity Optimization

### Pattern 1: Economic Order Quantity (EOQ)

Basic EOQ formula for deterministic demand:

```
EOQ = √(2DS/h)

Where:
D = Annual demand (units/year)
S = Ordering cost ($ per order)
h = Holding cost ($ per unit per year)
```

**Total Annual Cost**:
```
TC = (D/Q)×S + (Q/2)×h + D×c

Where Q = Order quantity, c = Unit cost
```

At EOQ, ordering cost equals holding cost: (D/EOQ)×S = (EOQ/2)×h

**Example**:
- Annual demand: D = 10,000 units
- Ordering cost: S = $100
- Unit cost: c = $50
- Holding cost: h = 25% × $50 = $12.50/unit/year

```
EOQ = √(2 × 10,000 × 100 / 12.50) = √160,000 = 400 units
Orders per year = 10,000 / 400 = 25
Order frequency = 365 / 25 = every 14.6 days
```

### Pattern 2: EOQ with Quantity Discounts

When supplier offers price breaks at higher quantities:

```
Price Tiers:
0-999 units: $50/unit
1,000-4,999 units: $48/unit (4% discount)
5,000+ units: $46/unit (8% discount)
```

**Approach**:
1. Calculate EOQ for each price tier
2. If EOQ falls below tier minimum, use tier minimum instead
3. Calculate total cost for each feasible quantity
4. Select quantity with minimum total cost

**Total Cost Formula**:
```
TC = (D/Q)×S + (Q/2)×h + D×c(Q)

Where c(Q) = unit cost at quantity Q
```

Remember: h changes with price! h = i×c (where i = holding cost %)

### Pattern 3: Economic Production Quantity (EPQ)

For manufactured items where production and consumption occur simultaneously:

```
EPQ = √(2DS/h) × √(1/(1-d/p))

Where:
d = Daily demand rate
p = Daily production rate
```

**Example**:
- Annual demand: D = 50,000 units
- Setup cost: S = $500
- Holding cost: h = $5/unit/year
- Daily demand: d = 200 units/day
- Daily production: p = 800 units/day

```
EPQ = √(2 × 50,000 × 500 / 5) × √(1/(1-200/800))
    = √10,000,000 × √(1/0.75)
    = 3,162 × 1.15 = 3,651 units
```

## Safety Stock and Service Levels

### Pattern 4: Safety Stock with Normal Distribution

When demand during lead time is normally distributed:

```
Safety Stock = z × σ_LT

Where:
z = Safety factor for target service level (from normal table)
σ_LT = Standard deviation of demand during lead time
```

**Common z values**:
- 90% CSL: z = 1.28
- 95% CSL: z = 1.65
- 98% CSL: z = 2.05
- 99% CSL: z = 2.33
- 99.9% CSL: z = 3.08

**Standard Deviation During Lead Time**:

If demand variability and lead time variability independent:
```
σ_LT = √(LT × σ_D² + D² × σ_LT²)

Where:
LT = Average lead time
σ_D = Std dev of demand per period
D = Average demand per period
σ_LT = Std dev of lead time
```

**Simplified** (if lead time is constant):
```
σ_LT = σ_D × √LT
```

**Example**:
- Average demand: 100 units/week, σ_D = 25 units/week
- Lead time: 4 weeks (constant)
- Target service level: 95% (z = 1.65)

```
σ_LT = 25 × √4 = 25 × 2 = 50 units
Safety Stock = 1.65 × 50 = 83 units
```

### Pattern 5: Fill Rate Approach

Optimize safety stock to achieve target fill rate (FR):

```
Safety Stock = z × σ_LT

Where z is found iteratively to achieve:
FR = 1 - [E(z) / (σ_LT × (Q/σ_LT))]
```

E(z) = Unit normal loss function (from tables)

**Relationship**: Higher order quantity Q → lower safety stock needed for same fill rate

**Example**:
- Target fill rate: 98%
- Order quantity: Q = 400 units
- σ_LT = 50 units
- Using loss function tables → z ≈ 2.05
- Safety Stock = 2.05 × 50 = 103 units

## Reorder Point Policies

### Pattern 6: Continuous Review (Q,R) Policy

Order quantity Q when inventory reaches reorder point R.

```
Reorder Point (R) = D_LT + SS

Where:
D_LT = Expected demand during lead time = LT × D
SS = Safety stock
```

**Example**:
- Weekly demand: D = 100 units, σ_D = 25 units
- Lead time: LT = 4 weeks
- Target CSL: 95% (z = 1.65)

```
D_LT = 4 × 100 = 400 units
SS = 1.65 × 25 × √4 = 83 units
R = 400 + 83 = 483 units
```

**Policy**: When inventory drops to 483 units, order EOQ quantity

### Pattern 7: Periodic Review (R,S) Policy

Review inventory every R periods, order up to S.

```
Order-up-to Level (S) = D_(R+LT) + SS

Where:
D_(R+LT) = Demand during review + lead time
SS = Safety stock for service level
σ_(R+LT) = σ_D × √(R+LT)
```

**Example**:
- Weekly demand: D = 100 units, σ_D = 25 units
- Review period: R = 2 weeks
- Lead time: LT = 4 weeks
- Target CSL: 95% (z = 1.65)

```
σ_(R+LT) = 25 × √(2+4) = 25 × √6 = 61.2 units
SS = 1.65 × 61.2 = 101 units
S = 100 × 6 + 101 = 701 units
```

**Policy**: Every 2 weeks, order enough to bring inventory to 701 units

## Multi-Echelon Inventory Optimization (MEIO)

### Pattern 8: Network Stocking Optimization

Optimize total safety stock across multi-tier network.

**Network Structure**:
```
Plant/Central DC → Regional DCs → Local Warehouses → Customers
```

**Key Concepts**:

**Installation Stock**: Inventory physically at a location
**Echelon Stock**: Installation stock + downstream pipeline inventory

**Allocation Principle**: Push safety stock upstream when:
- Lead times are similar across tiers
- Demand variability is high at downstream locations
- Risk pooling benefit from centralization is significant

**Example Trade-off**:
- Centralized safety stock at plant: 500 units (serves all regions)
- Decentralized safety stock at 5 regional DCs: 300 units each = 1,500 total
- Savings from centralization: 1,000 units (67% reduction)
- Trade-off: Longer delivery lead time to customers

**MEIO Approach**:
1. Model network topology and lead times
2. Calculate demand variability at each echelon
3. Set service level targets by customer segment
4. Solve optimization: Minimize total inventory subject to service constraints
5. Allocate safety stock by echelon (often favors upstream)

## Advanced Topics

### Newsvendor Model (Single-Period Inventory)

For seasonal or perishable products (fashion, fresh food):

```
Optimal Order Quantity (Q*) where:

P(Demand ≤ Q*) = Cu / (Cu + Co)

Where:
Cu = Cost of understocking (shortage cost per unit)
Co = Cost of overstocking (excess inventory cost per unit)
```

**Example**: Seasonal fashion item
- Selling price: $100, Cost: $40
- Salvage value: $10
- Cu = $100 - $40 = $60 (lost margin)
- Co = $40 - $10 = $30 (overstocking cost)
- Critical ratio = 60/(60+30) = 0.67
- Order quantity at 67th percentile of demand distribution

### Inventory Pooling and Risk Pooling

Consolidating inventory to reduce total safety stock:

```
SS_pooled / SS_separate = √n / n = 1/√n

Where n = number of locations pooled
```

**Example**: Pooling 4 regional warehouses
- Reduction factor = 1/√4 = 0.5
- Safety stock reduced by 50%

**Benefit increases with**:
- Higher demand variability
- Lower demand correlation between locations
- More locations pooled

## Resources

### Books and Publications
- "Inventory Management and Production Planning and Scheduling" by Silver, Pyke, Thomas
- "The Logistics Handbook" by Tompkins & Smith
- "Foundations of Inventory Management" by Zipkin
- "Inventory Optimization" by Axsäter

### Software Tools
- **Inventory optimization**: ToolsGroup, Smart IP&O, Logility
- **Supply chain planning**: SAP IBP, Kinaxis, o9 Solutions, Blue Yonder
- **Simulation**: Arena, AnyLogic, Simul8

## Common Pitfalls

- Using EOQ blindly without considering storage capacity or cash flow constraints
- Ignoring demand variability when calculating safety stock
- Setting same service level for all products (use ABC segmentation)
- Forgetting to adjust safety stock when lead times or demand variability change
- Not accounting for order minimums, multiples, or supplier constraints
- Overlooking the impact of forecast error on safety stock requirements
- Optimizing individual locations without considering network effects
- Static inventory policies - need periodic review and adjustment
