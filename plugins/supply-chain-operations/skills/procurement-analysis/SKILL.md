---
name: procurement-analysis
description: Procurement spend analysis, strategic sourcing, RFx process management, and total cost of ownership analysis to optimize purchasing. Use when analyzing spend data, developing sourcing strategies, or conducting supplier evaluations.
---

# Procurement Analysis and Strategic Sourcing

Comprehensive procurement analytics including spend analysis, category management, RFx process design, and total cost of ownership (TCO) evaluation for strategic sourcing.

## When to Use This Skill

- Analyzing procurement spend to identify savings opportunities
- Developing category strategies and sourcing plans
- Designing RFI, RFQ, and RFP processes with evaluation criteria
- Calculating total cost of ownership beyond unit price
- Performing make-vs-buy analysis
- Conducting should-cost modeling to benchmark prices
- Evaluating suppliers using weighted scoring methodologies
- Tracking and reporting procurement savings

## Core Concepts

### Spend Cube Analysis
Three-dimensional view: Category × Supplier × Business Unit
- Identify consolidation opportunities (same category, multiple suppliers)
- Spot maverick spend (non-contract purchases)
- Calculate supplier concentration risk

### Kraljic Matrix Segmentation
Segment categories by spend impact and supply risk:
- **Strategic**: High spend, high risk → Partnership
- **Leverage**: High spend, low risk → Competitive bidding
- **Bottleneck**: Low spend, high risk → Secure supply
- **Non-Critical**: Low spend, low risk → Simplify/automate

### Total Cost of Ownership (TCO)
```
TCO = Purchase Price + Acquisition Cost + Usage Cost + End-of-Life Cost

Components:
- Purchase price (unit cost × volume)
- Quality costs (defects, returns, rework)
- Delivery costs (freight, expediting, stockouts)
- Transaction costs (ordering, invoicing, receiving)
- Risk costs (supply disruption, obsolescence)
```

## Methodologies

### Spend Analysis Process
1. Data collection from AP, ERP, P-cards
2. Data cleansing and normalization
3. Categorization using UNSPSC or custom taxonomy
4. Analysis: Pareto, trends, supplier concentration
5. Opportunity identification

**Pareto Analysis**: 80/20 rule
- Typically 20% of categories = 80% of spend
- Focus sourcing efforts on high-spend categories

### RFx Process Design

**RFI (Request for Information)**:
- Purpose: Gather market intelligence, identify suppliers
- When: New category, market research
- Content: Company overview, capabilities, references

**RFQ (Request for Quotation)**:
- Purpose: Price comparison for well-defined items
- When: Commodities, standard specifications
- Content: Specifications, volumes, pricing template

**RFP (Request for Proposal)**:
- Purpose: Evaluate complex services or solutions
- When: Custom requirements, multiple evaluation criteria
- Content: Requirements, evaluation criteria, SOW

**Evaluation Criteria Example**:
```
Weight:
- Cost (40%): Total price, payment terms
- Technical (30%): Capabilities, quality, references
- Delivery (20%): Lead time, on-time performance
- Risk (10%): Financial stability, business continuity
```

### Should-Cost Modeling
Bottom-up cost estimation:
```
Should-Cost = Direct Material + Direct Labor + Overhead + Profit

Example: Machined part
- Material: $15 (2 lbs × $7.50/lb aluminum)
- Labor: $8 (0.4 hrs × $20/hr)
- Overhead: $12 (150% of labor)
- Profit: $7 (20% margin)
- Should-Cost: $42

Compare to supplier quote of $55 → 30% gap
Negotiate down or investigate cost drivers
```

## Resources

- **ERP**: SAP MM/SRM, Oracle Procurement, NetSuite
- **Procurement platforms**: Ariba, Coupa, Ivalua, GEP SMART
- **Spend analytics**: Zycus, Sievo, SpendHQ
- **Books**: "Strategic Sourcing" by Monczka et al., "The Procurement Value Proposition" by Bozarth

## Common Pitfalls

- Incomplete spend data (missing P-card, maverick spend)
- Lowest price without considering TCO
- RFPs with unclear requirements leading to non-comparable bids
- Not validating should-cost assumptions with suppliers
- Chasing small spend categories (violates Pareto principle)
