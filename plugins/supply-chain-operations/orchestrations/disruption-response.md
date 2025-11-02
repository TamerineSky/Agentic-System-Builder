# Supply Chain Disruption Response Workflow

Rapid response protocol for supply chain disruptions (supplier failure, natural disaster, quality issue, logistics disruption).

## Overview

**Purpose**: Quickly assess disruption impact, activate contingency plans, and restore normal operations.
**Timeline**: Immediate (hours to days)
**Participants**: Supply chain, procurement, operations, quality, customer service, executive leadership
**Outcomes**: Disruption contained, customer impact minimized, recovery plan executed

## Orchestration Workflow

### Phase 1: Incident Detection and Assessment (0-4 hours)

**Incident Identification**
- Trigger event: Supplier notification, Quality alert, Natural disaster news, Logistics delay, Financial distress signal
- Log incident with severity classification: Critical (immediate customer impact), High (impact within 48 hours), Medium (impact within 1 week), Low (minimal impact, monitoring needed)

**Impact Assessment**
- inventory-optimizer: /inventory-status: Check current inventory levels of affected items
- Calculate days of supply remaining
- Identify customer commitments at risk (orders, delivery dates)
- Estimate potential revenue impact and customer service impact

**Situation Analysis**
- /risk-assessment: Assess disruption scope and duration
- Determine root cause (if available)
- Identify affected suppliers, materials, products, customers
- Estimate recovery timeline (days, weeks, months)

**Notification**
- Alert stakeholders: Supply chain leadership, Affected procurement/operations teams, Customer service, Sales (if customer-facing), Executive team (if critical)
- Establish communication cadence

### Phase 2: Immediate Response (4-24 hours)

**Inventory Allocation**
- inventory-optimizer: Allocate available inventory strategically
- Prioritize customers (strategic accounts, contractual commitments, highest margin)
- Calculate rationing if demand exceeds available supply
- Coordinate with sales on customer communication

**Expedited Actions**
- procurement-advisor: Activate contingency suppliers if available
- logistics-planner: /logistics-plan: Expedite shipments (air freight if needed)
- Pull forward orders from alternative suppliers
- Reallocate inventory from other locations (if multi-site)

**Customer Communication**
- Notify affected customers proactively
- Provide transparent situation update and expected resolution
- Offer alternatives (substitutes, delayed delivery, partial fulfillment)
- Escalate executive engagement for strategic accounts

### Phase 3: Mitigation and Contingency Activation (1-7 days)

**Alternative Sourcing**
- procurement-advisor: Qualify emergency suppliers if no backup in place
- /supplier-scorecard: Review alternative supplier capabilities
- Negotiate emergency contracts with expedited onboarding
- Initiate material transfer (specs, tooling, first articles)

**Capacity Reallocation**
- Shift production to alternate facilities (internal or partners)
- Increase capacity at unaffected suppliers (overtime, second shifts)
- Implement temporary process changes to use alternate materials

**Quality Validation (if supplier change)**
- quality-control-analyst: Accelerate qualification of alternative source
- /quality-analysis: Conduct first article inspection
- Run limited production pilot
- Approve for production with monitoring plan

**Logistics Adjustments**
- logistics-planner: Optimize transportation from new sources
- Use faster modes (air vs. ocean) if time-critical
- Establish direct shipments to customers (bypass DC if needed)

### Phase 4: Recovery and Stabilization (1-4 weeks)

**Production Ramp-up**
- Monitor alternative supplier ramp-up
- Track quality and delivery performance closely
- /supplier-scorecard: Score emergency supplier performance
- Build inventory buffers to protect against recurrence

**Customer Service Recovery**
- Fulfill backorders as supply stabilizes
- Track customer satisfaction and address concerns
- Implement goodwill gestures if significant impact (discounts, priority service)

**Financial Assessment**
- Calculate total disruption cost: Expediting costs (air freight, overtime), Lost sales and margin, Customer concessions, Qualification and tooling costs
- Pursue supplier recovery (if supplier-caused)
- Document for insurance claim if applicable

### Phase 5: Root Cause and Prevention (Post-Resolution)

**Root Cause Analysis**
- Conduct detailed investigation: What happened? Why did it happen? Why weren't controls effective?
- Use 5 Whys or fishbone diagram
- Engage affected supplier if supplier-caused

**Process Improvement**
- /risk-assessment: Update supply chain risk assessment
- Implement preventive measures: Qualify backup suppliers proactively, Increase safety stock for high-risk items, Diversify geographic supply base, Improve supplier monitoring (financial, operational), Enhance early warning systems
- Update business continuity plans

**Lessons Learned**
- Document incident timeline and response effectiveness
- Identify what worked well and gaps
- Share learnings across organization
- Update disruption response playbook

## Decision Points

**Severity Classification**
- Critical: Customer shipments stop within 24 hours → Immediate exec escalation, all-hands response
- High: Impact in 2-7 days → Cross-functional team activated, daily updates
- Medium: Impact in 1-4 weeks → Standard mitigation, weekly reviews
- Low: Monitoring only, no immediate action

**Expediting Decisions**
- Cost-benefit: Expedite cost vs. lost sales/customer impact
- Approve air freight if customer impact >2× cost
- Authorize overtime/premiums if revenue at risk

**Supplier Change Decisions**
- Emergency qualification: Accept higher risk if disruption severe
- Permanent supplier change: If root cause indicates long-term risk
- Dual sourcing: Implement if single-source risk validated

## Success Metrics

- Time to detect and assess (target: <4 hours)
- Customer impact (orders missed, revenue lost)
- Recovery time (days to restore normal operations)
- Disruption cost (total financial impact)
- Repeat occurrences (measure prevention effectiveness)

## Collaboration Points

- All agents coordinate through incident command structure
- Daily stand-ups during active disruption
- Clear ownership and accountability
- Transparent communication (internal and customer-facing)
