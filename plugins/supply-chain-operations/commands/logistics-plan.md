---
description: Create optimized logistics and shipment plan including route optimization, carrier selection, and consolidation strategies for specified period.
argument-hint: [planning-period] [region]
model: sonnet
version: 1.0.0
tags: [logistics, transportation, planning]
---

# Logistics and Shipment Planning

Generate optimized transportation plan with route optimization, carrier selection, load consolidation, and cost minimization.

## Context

Effective logistics planning reduces freight costs, improves on-time delivery, and optimizes vehicle utilization while meeting customer service requirements.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Planning Data

Collect shipment requirements for $1 (planning period) in $2 (region):
- Customer orders with delivery dates and locations
- Shipment weights, dimensions, and special handling requirements
- Carrier options with rates and service levels
- Fleet capacity (if using private fleet)
- Time window constraints and appointment requirements

Extract from OMS, TMS, or ERP logistics modules.

### 2. Analyze Shipment Characteristics

Characterize demand:
- Total shipment volume (weight, pallets, orders)
- Geographic distribution (destination clusters)
- Urgency (standard, expedited, time-critical)
- Shipment sizes (parcel, LTL, TL thresholds)
- Consolidation opportunities (multi-customer shipments, milk runs)

Segment shipments:
- Group by destination zone
- Classify by size (TL vs. LTL vs. parcel)
- Identify pooling opportunities

### 3. Optimize Routes and Modes

**Mode Selection**:
- Parcel: Small packages <150 lbs
- LTL: 150-10,000 lbs, multi-stop consolidation
- TL: >10,000 lbs or full truck
- Intermodal: Long-haul if non-urgent

**Route Optimization**:
- For fleet/milk runs: Apply vehicle routing algorithms (VRP)
- Minimize total distance while respecting time windows and capacity
- Balance routes across vehicles
- Calculate delivery sequences

**Consolidation Strategies**:
- Combine multiple LTL shipments into TL if cost-effective
- Pool distribution: Aggregate orders by destination zone
- Cross-dock: Consolidate inbound for outbound efficiency

### 4. Carrier Selection and Assignment

Evaluate carriers:
- Cost: Base rate + fuel surcharge + accessorials
- Service: On-time delivery history, transit time
- Capacity: Availability for required dates
- Geographic coverage: Strength in destination areas

Assign shipments to carriers:
- Award by lane based on cost and service scorecards
- Maintain backup carriers (80/20 primary/secondary split)
- Balance volume commitments with contract terms

Calculate total freight cost and compare to budget.

### 5. Generate Shipment Plan

Produce detailed shipment schedule:
- Shipment manifest (orders, weights, destinations, carriers)
- Route plans with stop sequences and timing
- Carrier assignments and booking requirements
- Cost summary by mode and carrier
- KPIs: Average freight cost per unit, cube utilization, on-time delivery target

Create contingency plans for disruptions.

## Output Format

1. **Shipment Schedule**: Order-level assignments with carriers and dates
2. **Route Maps**: Visualizations of optimized delivery routes
3. **Cost Summary**: Total freight cost by mode, carrier, and lane
4. **Capacity Utilization**: Vehicle loading, cube/weight utilization
5. **Improvement Opportunities**: Consolidation savings, route efficiencies

## Success Criteria

- All shipments planned for $1 in $2
- Optimized routes reducing total distance/cost by >10%
- Carrier assignments meeting service level targets
- Load consolidation opportunities identified
- Plan ready for TMS execution or manual dispatch
