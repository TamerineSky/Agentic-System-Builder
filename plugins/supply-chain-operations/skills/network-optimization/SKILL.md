---
name: network-optimization
description: Supply chain network design and optimization including facility location, distribution network configuration, and inventory-transportation trade-offs. Use when designing distribution networks, evaluating DC locations, or optimizing network configurations.
---

# Supply Chain Network Optimization

Network design and optimization methodologies for distribution center location, network configuration, and balancing inventory-transportation trade-offs.

## When to Use This Skill

- Determining optimal number and locations of distribution centers
- Evaluating centralized vs. decentralized distribution strategies
- Analyzing direct shipment vs. hub-and-spoke configurations
- Optimizing customer-to-DC assignments
- Modeling trade-offs between inventory investment and transportation costs
- Planning for capacity expansion or network consolidation
- Assessing network resilience and risk

## Core Concepts

### Facility Location Models

**P-median Problem**: Locate P facilities to minimize average distance
**Set Covering**: Minimize facilities while covering all demand within distance threshold
**Hub Location**: Identify hub facilities for consolidation

**Center of Gravity** (single facility):
```
X* = Σ(demand[i] × X[i]) / Σdemand[i]
Y* = Σ(demand[i] × Y[i]) / Σdemand[i]

Locates facility at weighted center of demand
```

### Network Configuration Trade-offs

**Centralized** (1 National DC):
- Pros: Lower inventory (pooling), lower facility cost
- Cons: Higher freight, longer lead times

**Decentralized** (Multiple Regional DCs):
- Pros: Lower freight, faster delivery
- Cons: Higher inventory, higher facility costs

**Optimal**: Minimize Total Cost = Inventory + Facility + Transportation

### Inventory-Transportation Trade-off

```
Square Root Law:
Inventory[n DCs] / Inventory[1 DC] ≈ √n

Example: 4 regional DCs
Inventory increase = √4 = 2× (doubling inventory)
Transportation savings from shorter distances
```

## Methodologies

### Network Optimization Process

1. **Data Collection**:
   - Customer locations and demand volumes
   - Candidate DC locations and costs
   - Transportation rates by lane and mode
   - Current inventory levels and policies

2. **Modeling**:
   - Build mixed-integer programming model
   - Objective: Minimize total network cost
   - Constraints: Capacity, service, budget

3. **Scenario Analysis**:
   - Compare 1 DC, 2 DCs, 3 DCs, etc.
   - Evaluate centralized vs. regional strategies
   - Model demand growth scenarios

4. **Validation**:
   - Sensitivity analysis on key assumptions
   - Risk assessment (disruption scenarios)
   - Implementation feasibility

### Network Metrics

**Service Coverage**: % of demand within X miles or Y days
**Facility Utilization**: Throughput vs. capacity
**Freight Cost**: Cost per unit shipped
**Inventory Turns**: Annual sales / average inventory
**Total Network Cost**: Sum of all components

## Resources

- **Software**: LLamasoft (Coupa SCM Design), Llamasoft Supply Chain Guru, Optilogic
- **Books**: "Supply Chain Network Design" by Watson et al.

## Common Pitfalls

- Optimizing transportation without accounting for inventory changes
- Using straight-line distances instead of actual routes
- Static demand assumptions ignoring seasonality or growth
- Neglecting DC capacity constraints
- Not modeling risk and resilience in network design
