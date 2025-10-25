---
name: scor-framework
description: SCOR (Supply Chain Operations Reference) model framework for standardized supply chain process mapping, metrics, and best practices. Use when mapping supply chain processes, defining KPIs, or benchmarking performance.
---

# SCOR Framework (Supply Chain Operations Reference Model)

The SCOR model provides standardized process definitions, performance metrics, and best practices for supply chain management across Plan, Source, Make, Deliver, Return, and Enable processes.

## When to Use This Skill

- Mapping end-to-end supply chain processes
- Defining standardized supply chain metrics and KPIs
- Benchmarking supply chain performance against industry
- Identifying process improvement opportunities
- Aligning cross-functional teams on process definitions
- Designing supply chain transformation programs
- Implementing supply chain best practices

## Core Concepts

### SCOR Process Framework

**Level 1: Process Types**
- **Plan**: Demand/supply planning, S&OP
- **Source**: Procurement, supplier management
- **Make**: Manufacturing, assembly
- **Deliver**: Order management, warehousing, transportation
- **Return**: Returns, reverse logistics
- **Enable**: Supporting processes (IT, finance, quality, compliance)

**Level 2: Process Categories**
- Plan: Plan Supply Chain, Plan Source, Plan Make, Plan Deliver, Plan Return
- Source: Source Stocked Product, Source MTO Product, Source ETO Product
- Make: Make-to-Stock, Make-to-Order, Engineer-to-Order
- Deliver: Deliver Stocked Product, Deliver MTO, Deliver ETO, Deliver Retail

**Level 3**: Decompose each category into detailed process steps
**Level 4**: Implement with technology and procedures (company-specific)

### SCOR Performance Attributes

**Customer-Facing (Reliability, Responsiveness, Agility)**:
- **Perfect Order Fulfillment**: On-time, complete, damage-free, correct invoice
- **Order Fulfillment Cycle Time**: Order receipt to customer delivery
- **Upside Supply Chain Flexibility**: Ability to increase output
- **Upside Supply Chain Adaptability**: Adapt to market changes
- **Downside Supply Chain Adaptability**: Reduce output without penalty

**Internal-Facing (Cost, Assets)**:
- **Total Supply Chain Cost**: Plan, Source, Make, Deliver, Return costs
- **Cash-to-Cash Cycle Time**: Days payable outstanding + inventory days - days sales outstanding
- **Return on Supply Chain Fixed Assets**: Revenue / fixed assets
- **Return on Working Capital**: Revenue / working capital

## Key SCOR Metrics

### Level 1 Metrics (Strategic)

**Reliability**:
```
Perfect Order % = Orders perfect / Total orders

Perfect = On-time AND complete AND undamaged AND correct invoice
Target: >95%
```

**Responsiveness**:
```
Order Fulfillment Cycle Time = Average days from order to delivery
Target: Industry-dependent (1-5 days retail, 30-60 days industrial)
```

**Agility**:
```
Supply Chain Flexibility = % increase in output sustainable for 30 days
Target: 20-50% depending on industry
```

**Cost**:
```
Total Supply Chain Cost = (Plan + Source + Make + Deliver + Return) / Revenue %
Target: 4-12% depending on industry
```

**Assets**:
```
Cash-to-Cash Cycle Time = DPO + DIO - DSO (in days)

DPO = Days Payable Outstanding = (AP / COGS) × 365
DIO = Days Inventory Outstanding = (Inventory / COGS) × 365
DSO = Days Sales Outstanding = (AR / Revenue) × 365

Target: Minimize (negative is best - getting paid before paying suppliers)
```

### Level 2 Metrics (Operational)

**Source**:
- Supplier on-time delivery
- Supplier quality (PPM)
- Procurement cycle time

**Make**:
- Manufacturing cycle time
- Capacity utilization
- First pass yield

**Deliver**:
- Fill rate
- On-time shipment
- Warehouse cost per unit

## Best Practices

### Process Mapping
1. Map current state (AS-IS) using SCOR framework
2. Identify gaps and inefficiencies
3. Design future state (TO-BE) incorporating best practices
4. Implement changes with clear metrics

### Metrics Cascading
- Level 1: Executive dashboard (strategic)
- Level 2: Functional management (operational)
- Level 3: Process owner (tactical)

Ensure alignment: Level 2/3 metrics support Level 1 goals

## Resources

- **APICS SCOR**: Official SCOR model (now part of ASCM)
- **Certification**: SCOR-P (SCOR Professional) certification
- **Software**: SCOR-enabled planning systems (SAP IBP, Kinaxis)
- **Books**: "Supply Chain Management Best Practices" by Bolstorff & Rosenbaum

## Common Pitfalls

- Implementing SCOR as rigid framework instead of flexible reference model
- Focusing on process mapping without metrics and improvement
- Not customizing Level 4 to company-specific context
- Measuring too many metrics without prioritization
- Benchmarking against wrong industry or maturity level
