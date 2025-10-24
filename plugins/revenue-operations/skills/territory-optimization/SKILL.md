---
name: territory-optimization
description: Data-driven territory design principles including workload balancing, coverage optimization, and fair account distribution for maximizing sales team productivity. Use when redesigning territories, balancing workloads, or planning territory expansions.
---

# Territory Optimization

Systematic approaches to territory design that balance opportunity, workload, and coverage to maximize revenue productivity while ensuring fairness across sales teams.

## When to Use This Skill

- Annual territory planning and redesign
- Rebalancing territories due to growth or team changes
- Creating territories for new hires
- Optimizing coverage for underserved markets
- Resolving territory imbalance complaints
- Planning geographic vs. account-based territory models

## Territory Design Principles

### 1. Balance Dimensions

**Opportunity Balance:**
- Total Addressable Market (TAM) per territory
- Existing customer ARR distribution
- Pipeline potential and growth rates

**Workload Balance:**
- Number of accounts per rep
- Geographic coverage area / travel time
- Account complexity and support needs

**Fairness Metrics:**
```
Gini Coefficient for Territory Distribution:
0.0 = Perfect equality
0.3 = Acceptable variance
>0.5 = Significant imbalance

Example Calculation:
Territory ARRs: $2.8M, $3.1M, $2.9M, $3.0M, $2.7M
Gini: 0.08 (excellent balance)

vs.

Territory ARRs: $1.2M, $5.8M, $2.1M, $6.5M, $1.8M
Gini: 0.52 (poor balance, needs rebalancing)
```

### 2. Territory Model Types

**Geographic Territories:**
```
Example: West Region
- Territory A: CA, OR, WA
- Territory B: NV, AZ, UT
- Territory C: ID, MT, WY

Pros: Clear boundaries, local expertise
Cons: Uneven opportunity distribution
```

**Account-Based (Named Accounts):**
```
Example: Enterprise Segment
- Rep A: 50 named accounts ($8M ARR)
- Rep B: 50 named accounts ($8.2M ARR)
- Rep C: 50 named accounts ($7.9M ARR)

Pros: Perfect balance possible
Cons: No geographic specialization
```

**Hybrid (Industry + Geography):**
```
Example:
- Rep A: Healthcare, West Coast
- Rep B: Financial Services, West Coast
- Rep C: Technology, West Coast

Pros: Industry expertise + local coverage
Cons: More complex, potential conflicts
```

### 3. Capacity Modeling

**Accounts Per Rep Guidelines:**
```
Enterprise (>1000 employees):
- Max 50-80 accounts per rep
- High touch, strategic relationships

Mid-Market (100-1000 employees):
- Max 120-150 accounts per rep
- Balanced touch, relationship-driven

SMB (<100 employees):
- Max 200-250 accounts per rep
- High velocity, transactional
```

## Optimization Techniques

### 1. Mathematical Optimization

**Objective Function:**
```
Maximize: Total Expected Revenue
Subject to:
- Each territory has 100-150 accounts
- Geographic contiguity (if applicable)
- Travel time < 3 hours between accounts
- ARR variance < 20% across territories
```

**Tools:**
- Python optimization libraries (PuLP, OR-Tools)
- Tableau territory mapping
- Geopointe (Salesforce app)

### 2. Rebalancing Strategies

**When to Rebalance:**
- Annually during planning cycle
- When adding/removing reps
- When variance exceeds 30%
- When bottom performers cite territory issues

**Rebalancing Approaches:**

**Minimal Disruption:**
- Carve new territories from multiple existing (spread impact)
- Reassign only bottom 20% of accounts (by ARR)
- Grandfather large strategic accounts with existing rep

**Maximum Optimization:**
- Full redesign, all accounts reassigned
- Create perfectly balanced territories
- Higher short-term disruption, better long-term outcomes

## Resources

- Territory design templates
- GIS mapping tools comparison
- Account assignment spreadsheets
- Territory health dashboards

## Best Practices

1. **Annual Review:** Rebalance territories yearly minimum
2. **Data-Driven:** Use actual ARR, not estimates
3. **Stakeholder Input:** Involve reps in design process
4. **Transition Plans:** 60-90 day handoff periods
5. **Protect Relationships:** Keep strategic accounts with current rep when possible
6. **Document Rationale:** Explain territory decisions clearly
7. **Monitor Impact:** Track customer satisfaction and rep productivity post-change

## Common Pitfalls

1. **Static Territories:** Not rebalancing as business grows
2. **Equal Account Counts:** Ignoring account quality/size
3. **Optimizing for Top Performers:** Creating unfair advantages
4. **Frequent Changes:** Destabilizing territories too often
5. **Ignoring Geography:** Creating unserviceable territories
6. **No Transition Planning:** Abrupt account transfers
7. **Political Decisions:** Territory design based on favoritism
