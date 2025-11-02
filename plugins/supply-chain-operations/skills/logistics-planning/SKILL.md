---
name: logistics-planning
description: Logistics planning and transportation optimization including route planning, carrier selection, load consolidation, and network design. Use when optimizing transportation routes, selecting carriers, or designing distribution networks.
---

# Logistics Planning and Optimization

Master logistics planning techniques for transportation optimization, route planning, carrier selection, and distribution network design to minimize freight costs while meeting delivery requirements.

## When to Use This Skill

- Optimizing delivery routes for fleet of vehicles with capacity and time window constraints
- Selecting carriers and modes based on cost, service, and reliability
- Consolidating shipments to achieve economies of scale and reduce freight costs
- Designing distribution networks with optimal DC locations and service territories
- Planning inbound and outbound transportation strategies
- Evaluating trade-offs between transportation cost and inventory investment
- Calculating break-even points for mode and carrier decisions
- Improving on-time delivery and reducing transportation spend

## Core Logistics Principles

### Transportation Modes and Trade-offs

**Truckload (TL)**: Full truck capacity (40,000+ lbs or 24+ linear feet)
- Cost: ~$1.50-3.00 per mile
- Speed: Fast (1-3 days for regional)
- Best for: Large shipments, dedicated deliveries

**Less-than-Truckload (LTL)**: Shared truck with multiple customers
- Cost: ~$0.25-0.75 per lb for 500-5,000 lbs
- Speed: Moderate (2-5 days for regional)
- Best for: Smaller shipments, multiple destinations

**Parcel**: Small packages <150 lbs
- Cost: $10-50 for typical package
- Speed: Fast (1-3 days)
- Best for: E-commerce, small orders

**Intermodal (Rail+Truck)**: Long-haul rail, local truck drayage
- Cost: 20-40% cheaper than TL for long distances
- Speed: Slower (5-7 days)
- Best for: Non-urgent, high-volume lanes >500 miles

**Consolidation Decision**: Ship 500 lbs LTL at $0.50/lb = $250, or wait to accumulate 2,000 lbs and ship TL at $300?
- LTL: $250, ships today
- TL: $300, ships in 3 days (after accumulation)
- Trade-off: $50 higher cost vs. 3-day delay and holding cost

### Network Design Concepts

**Direct Shipment**: Plant → Customer (simple, fast, higher freight cost)
**Hub-and-Spoke**: Plant → Regional DC → Customers (consolidation savings, adds inventory)
**Cross-Dock**: Breakbulk without storage (speed + consolidation)
**Milk Run**: Multi-stop pickup or delivery route

## Vehicle Routing Problem (VRP)

### Classic VRP Formulation

Minimize total distance while serving all customers subject to:
- Vehicle capacity constraints
- Time window constraints (customer availability)
- Driver hour limits
- Route duration limits

**Objective Function**:
```
Minimize: Σ distance[i,j] × x[i,j]

Subject to:
- Each customer visited exactly once
- Vehicle capacity not exceeded
- Time windows respected
- Routes start and end at depot
```

### Savings Algorithm (Clarke-Wright)

Heuristic for combining routes:

1. Start with individual route for each customer (depot → customer → depot)
2. Calculate savings for combining routes i and j:
   ```
   Savings[i,j] = distance[depot,i] + distance[depot,j] - distance[i,j]
   ```
3. Sort savings in descending order
4. Merge routes with highest savings if constraints satisfied
5. Repeat until no more savings possible

**Example**:
```
Customers: A, B, C
Distance matrix:
  Depot  A    B    C
Depot 0   10   15   20
A    10   0    12   18
B    15   12   0    16
C    20   18   16   0

Savings:
S[A,B] = 10+15-12 = 13
S[A,C] = 10+20-18 = 12
S[B,C] = 15+20-16 = 19 (highest)

Combine B-C first, then add A if capacity allows
```

### Route Optimization with Time Windows

**VRPTW (VRP with Time Windows)**:
- Each customer has delivery window [earliest, latest]
- Vehicle must arrive within window (may wait if early)
- Adds complexity: Feasibility depends on route sequence

**Insertion Heuristic**:
1. Start with seed route
2. For unrouted customers, calculate insertion cost at each position
3. Insert customer with minimum cost increase
4. Repeat until all customers routed or infeasible

**Time Window Example**:
```
Customer A: [8:00, 10:00] - can deliver 8-10 AM
Customer B: [9:00, 11:00]
Customer C: [10:00, 12:00]

Route sequence: Depot → A (arrive 8:30) → B (arrive 9:45) → C (arrive 10:30) → Depot
All time windows satisfied
```

## Carrier Selection and Freight Procurement

### Total Cost of Transportation

Beyond rate per mile or per pound:

```
Total Delivered Cost = 
  Base Freight Rate
  + Fuel Surcharge
  + Accessorials (liftgate, residential, inside delivery)
  + Claims/Damage Cost
  + Delay/Stockout Cost from late delivery
```

**Accessorial Charges** (can add 20-50% to base rate):
- Liftgate service: $50-150
- Residential delivery: $50-100
- Inside delivery: $75-200
- Appointment delivery: $50-75
- Reconsignment (address change): $50-100

### Carrier Scorecard

Weight multiple factors beyond cost:

| Criterion | Weight | Carrier A | Carrier B |
|-----------|--------|-----------|-----------|
| Cost competitiveness | 40% | 85 | 92 |
| On-time delivery % | 30% | 96 | 88 |
| Claims/damage rate | 20% | 90 | 95 |
| Customer service | 10% | 85 | 90 |
| **Total Score** | | **89.5** | **91.0** |

Carrier B wins despite higher OTD due to better cost and claims performance.

### Freight RFP Process

1. **Data Preparation**: Compile lane-level volume (origin-destination pairs)
2. **Carrier Selection**: Identify qualified carriers (5-10 for bid)
3. **RFP Package**: Provide historical volume, service requirements, evaluation criteria
4. **Bid Analysis**: Compare rates, service commitments, contract terms
5. **Award Strategy**: Primary carrier + backup (e.g., 80/20 split)
6. **Implementation**: Onboard carrier, set up routing guide

**Lane Optimization**: Award lanes to carriers based on cost + service + geographic strength

## Load Consolidation Strategies

### LTL-to-TL Conversion

**Break-even Analysis**:
```
LTL cost per lb: $0.40
TL cost per truck: $800
TL capacity: 40,000 lbs

Break-even: $800 / $0.40 = 2,000 lbs

If shipment > 2,000 lbs → Use TL
If shipment < 2,000 lbs → Use LTL
```

**Consolidation Window**: Wait to accumulate volume
- Delay cost: Inventory holding + customer service impact
- Freight savings: LTL ($0.40/lb × 5,000 lbs = $2,000) vs TL ($800)
- Net savings: $1,200
- If holding cost <$400/day, wait up to 3 days to consolidate

### Milk Run Consolidation

Combine multiple pickups or deliveries into multi-stop route:

**Example**: Supplier pickups
- Suppliers: A, B, C (all within 50-mile radius)
- Individual TL pickups: 3 × $300 = $900
- Milk run: Single truck visits all three, $450
- Savings: $450 (50%)
- Trade-off: Coordination complexity, pickup time windows

### Pool Distribution

Consolidate orders by destination zone:
```
Individual parcel shipments: 20 packages × $15 = $300
Consolidated LTL to local hub: $120
Local delivery service: $80
Total: $200
Savings: $100 (33%)
```

## Distribution Network Design

### Facility Location Optimization

**Single Facility Location**: Minimize total transportation cost

**Center of Gravity Method**:
```
X* = Σ(volume[i] × X[i]) / Σvolume[i]
Y* = Σ(volume[i] × Y[i]) / Σvolume[i]

Where:
(X[i], Y[i]) = coordinates of customer i
volume[i] = annual shipment volume to customer i
```

Locates DC at weighted center of customer demand.

**Multi-Facility Location**: P-median problem (locate P facilities to minimize average distance)

Use optimization software or heuristics:
1. Identify candidate DC locations
2. Cluster customers by geography/volume
3. Assign customers to nearest DC
4. Calculate total cost (facility + transportation)
5. Iterate to find optimal configuration

### Network Trade-off Analysis

**Centralized** (1 national DC):
- Lower inventory (risk pooling reduces safety stock by ~30-50%)
- Lower facility costs (one building vs. multiple)
- Higher outbound freight (longer distances to customers)
- Slower delivery (2-3 day average vs. 1-day)

**Decentralized** (3-5 regional DCs):
- Higher inventory (less risk pooling)
- Higher facility costs (multiple buildings)
- Lower outbound freight (shorter distances)
- Faster delivery (1-day to most customers)

**Optimization**: Find network configuration minimizing total cost = inventory + facility + transportation

## Resources

### Books
- "Logistics Engineering & Management" by Blanchard
- "The Distribution Management Handbook" by Tompkins & Smith
- "Supply Chain Network Design" by Watson et al.

### Software
- Route optimization: Routific, OptimoRoute, Route4Me
- TMS: Oracle OTM, SAP TM, Manhattan Active TMS, Blue Yonder TMS
- Network design: LLamasoft Supply Chain Guru, Coupa Supply Chain Design

## Common Pitfalls

- Optimizing transportation without considering inventory trade-offs
- Selecting carriers on cost alone, ignoring service quality
- Assuming linear freight rates (economies of scale matter)
- Not accounting for accessorial charges in carrier comparison
- Over-consolidating shipments, causing unacceptable delivery delays
- Building network models with outdated or incomplete demand data
- Ignoring seasonal demand variation in network design
- Forgetting to validate routing constraints (hours of service, equipment availability)
