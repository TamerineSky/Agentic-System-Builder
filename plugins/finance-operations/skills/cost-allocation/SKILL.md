# Cost Allocation Skill

## Overview
This skill covers cost allocation methodologies, activity-based costing, overhead distribution, and techniques for accurately assigning costs to products, services, departments, and projects.

## Core Concepts

### What is Cost Allocation?
Cost allocation is the process of assigning indirect costs to cost objects (products, services, departments, customers) using systematic and rational methods. It enables:
- Accurate product/service profitability analysis
- Fair cost distribution across departments
- Informed pricing decisions
- Performance measurement and accountability

### Direct vs. Indirect Costs

**Direct Costs:**
- Traceable directly to cost object
- No allocation needed
- Examples: Direct materials, direct labor, dedicated equipment

**Indirect Costs:**
- Benefit multiple cost objects
- Require allocation
- Examples: Rent, utilities, shared services, management salaries

## Allocation Methods

### 1. Simple Allocation (Single Driver)
```
Allocation Formula:
Department Share = (Department Driver / Total Driver) × Total Cost

Example - Rent Allocation by Square Footage:
Total rent: $100,000
Total square feet: 10,000

Department A: 3,000 sq ft
Department B: 4,000 sq ft
Department C: 3,000 sq ft

Allocation:
Dept A: (3,000 / 10,000) × $100,000 = $30,000
Dept B: (4,000 / 10,000) × $100,000 = $40,000
Dept C: (3,000 / 10,000) × $100,000 = $30,000
```

**Common Single Drivers:**
- **Rent**: Square footage occupied
- **IT costs**: Number of employees or devices
- **HR costs**: Headcount
- **Finance costs**: Revenue or transaction volume
- **Facilities**: Headcount or square footage

### 2. Step-Down Allocation
```
Method: Allocate service departments sequentially to other departments

Example:
Step 1: Allocate HR (based on headcount) to all other depts
Step 2: Allocate IT (based on users) to remaining depts
Step 3: Allocate Finance (based on transactions) to operating depts

Order matters: Allocate largest or most service-intensive first
Once allocated, don't reallocate back to prior departments
```

### 3. Reciprocal Allocation
```
Method: Recognize that service departments support each other

Requires solving simultaneous equations:
HR = Direct HR costs + % of IT costs
IT = Direct IT costs + % of HR costs

Example:
HR direct: $500K, provides 20% service to IT
IT direct: $800K, provides 30% service to HR

HR total = $500K + 0.30 × IT total
IT total = $800K + 0.20 × HR total

Solve:
HR total = $500K + 0.30 × ($800K + 0.20 × HR total)
HR total = $500K + $240K + 0.06 × HR total
0.94 × HR total = $740K
HR total = $787K

IT total = $800K + 0.20 × $787K = $957K

Most accurate but complex; typically done in systems
```

### 4. Activity-Based Costing (ABC)
```
Method: Allocate costs based on activities consumed

Steps:
1. Identify activities (order processing, customer support, etc.)
2. Assign costs to activities (cost pools)
3. Determine activity drivers (orders processed, support tickets)
4. Calculate activity rates (cost per order, cost per ticket)
5. Allocate to cost objects (products, customers) based on consumption

Example - Customer Support Costs:
Total support cost: $1,000,000
Total support tickets: 20,000
Cost per ticket: $50

Customer A: 100 tickets → $5,000 allocated
Customer B: 500 tickets → $25,000 allocated
Customer C: 50 tickets → $2,500 allocated
```

## Activity-Based Costing (ABC) Deep Dive

### ABC vs. Traditional Costing
```
Traditional Costing:
Allocate overhead using single driver (labor hours, revenue)
Simple but can distort costs

ABC:
Allocate overhead using multiple activity drivers
More accurate but more complex

Example Comparison:
Product A: High volume, simple (10,000 units)
Product B: Low volume, complex (1,000 units)

Traditional (allocate by units):
Overhead $100K allocated equally: $9.09 per unit both products

ABC (allocate by activities):
Product A: Few setups, simple → $7 per unit
Product B: Many setups, complex → $30 per unit

Result: ABC shows Product B is more expensive to produce
```

### ABC Implementation
```
Step 1: Identify Activities
- Order processing
- Production setups
- Quality inspections
- Customer support
- Shipping and handling

Step 2: Build Cost Pools
Activity: Quality Inspections
Costs included:
- Inspector salaries: $300K
- Testing equipment: $50K
- Lab supplies: $30K
Total cost pool: $380K

Step 3: Select Cost Drivers
Activity: Quality Inspections
Driver: Number of inspection hours
Total hours: 19,000
Rate: $380K / 19,000 = $20 per inspection hour

Step 4: Allocate to Products
Product A: 100 inspection hours → $2,000
Product B: 500 inspection hours → $10,000
```

## Cost Allocation Base Selection

### Choosing Appropriate Bases
```
Cost Type              Recommended Base
-----------------------------------------
Rent/Facilities        Square footage, headcount
IT support            Number of users, devices, tickets
HR services           Headcount, new hires
Finance/Accounting    Revenue, transactions
Legal                 Matters, time tracking
Marketing             Revenue, customer acquisition
Manufacturing OH      Machine hours, labor hours
R&D                   Product lines, engineers
```

### Multiple Bases for Single Cost
```
Example - IT Costs Total: $2M

Allocation approach:
- 50% by headcount (user support): $1M
  - Sales (100 HC of 500): $200K
  - Engineering (200 HC): $400K
  - G&A (200 HC): $400K

- 30% by data storage (infrastructure): $600K
  - Sales (10% of storage): $60K
  - Engineering (70% of storage): $420K
  - G&A (20% of storage): $120K

- 20% by help desk tickets (support): $400K
  - Sales (200 tickets of 1,000): $80K
  - Engineering (300 tickets): $120K
  - G&A (500 tickets): $200K

Total IT allocation:
- Sales: $200K + $60K + $80K = $340K
- Engineering: $400K + $420K + $120K = $940K
- G&A: $400K + $120K + $200K = $720K
```

## Common Allocation Scenarios

### Scenario 1: Corporate Overhead to Business Units
```
Corporate costs: $5M (Finance, HR, Legal, Exec team)
Three business units: Enterprise, SMB, Consumer

Allocation method: Revenue-based
- Enterprise: $50M revenue (50%)
- SMB: $30M revenue (30%)
- Consumer: $20M revenue (20%)

Allocation:
- Enterprise: 50% × $5M = $2.5M
- SMB: 30% × $5M = $1.5M
- Consumer: 20% × $5M = $1M

Alternative: Headcount or number of transactions
Consider: Which base best reflects consumption of services?
```

### Scenario 2: Shared Services Allocation
```
Shared Services Center costs: $3M
Services: Finance, HR, IT
Servicing: 5 regional offices

Allocation bases:
- Finance: Transaction volume
  - North America: 10,000 txns (50%)
  - Europe: 6,000 txns (30%)
  - Asia: 4,000 txns (20%)

- HR: Headcount
  - North America: 500 FTE (45%)
  - Europe: 400 FTE (36%)
  - Asia: 200 FTE (19%)

- IT: Number of users
  - North America: 550 users (48%)
  - Europe: 420 users (37%)
  - Asia: 180 users (15%)

Blended allocation or separate by function
```

### Scenario 3: Product Profitability Analysis
```
Company produces Products X, Y, Z
Need to allocate manufacturing overhead for profitability

Overhead costs: $2M
- Machine depreciation: $800K
- Factory rent: $400K
- Supervisors: $500K
- Utilities: $300K

Allocation drivers:
- Machine depreciation: Machine hours
- Factory rent: Floor space used
- Supervisors: Direct labor hours
- Utilities: Machine hours

Product X (high volume, simple):
- Machine hours: 10,000 (50%)
- Floor space: 30%
- Labor hours: 8,000 (40%)
Allocated overhead: $1.02M

Product Y (low volume, complex):
- Machine hours: 6,000 (30%)
- Floor space: 40%
- Labor hours: 8,000 (40%)
Allocated overhead: $0.70M

Product Z (medium volume):
- Machine hours: 4,000 (20%)
- Floor space: 30%
- Labor hours: 4,000 (20%)
Allocated overhead: $0.48M
```

## Best Practices

### 1. Match Allocation Base to Cost Behavior
```
Good Match:
- Rent allocated by square footage (space drives cost)
- IT support by number of users (users drive cost)
- Shipping by weight or distance (drives freight cost)

Poor Match:
- Legal costs by headcount (legal matters not proportional to HC)
- R&D by revenue (revenue doesn't drive R&D consumption)
- Marketing by office space (no relationship)
```

### 2. Document Allocation Methods
```
Allocation Documentation Template:

Cost Pool: Information Technology
Total Cost: $2,000,000
Allocation Base: Number of employees
Total Base: 500 employees

Allocation Rate: $2M / 500 = $4,000 per employee

Recipients:
- Sales: 100 employees × $4,000 = $400,000
- Engineering: 200 employees × $4,000 = $800,000
- G&A: 200 employees × $4,000 = $800,000

Rationale: IT costs primarily driven by user support
Review Frequency: Annually
Last Updated: 2024-01-01
Owner: CFO
```

### 3. Review and Update Regularly
```
Review triggers:
- Annually: Standard review of all allocation methods
- Organizational changes: Restructuring, new departments
- Cost behavior changes: New cost drivers emerge
- Significant variance: Allocations seem unfair or inaccurate
- New systems: Better data available for allocation
```

### 4. Consider Behavioral Impacts
```
Allocation method affects behavior:

Revenue-based allocation:
- Pro: Simple, aligns with ability to pay
- Con: Penalizes high-revenue units, discourages growth

Headcount-based allocation:
- Pro: Easy to understand and track
- Con: Encourages keeping headcount artificially low

Usage-based allocation (ABC):
- Pro: Fair, encourages efficient consumption
- Con: Requires tracking usage data
- Best: Aligns incentives with cost control
```

## Advanced Topics

### Transfer Pricing
```
Setting prices for goods/services between divisions:

Methods:
1. Cost-based: Allocated cost + markup
2. Market-based: External market price
3. Negotiated: Divisions agree on price

Example:
Manufacturing division sells to Sales division
Unit cost: $100 (including allocated overhead)
Market price: $150
Transfer price options:
- Cost-based: $100 + 10% = $110
- Market-based: $150 (or $150 - discount)
- Negotiated: $130 (split the margin)

Tax and regulatory considerations apply
```

### Allocated vs. Direct Assignment
```
When possible, assign directly rather than allocate:

Example: Cloud infrastructure costs
Instead of: Allocate total AWS bill by headcount
Better: Tag resources by department, charge directly

Benefits:
- More accurate cost assignment
- Better visibility and control
- Encourages cost awareness
- Enables showback/chargeback models
```

## Tools and Systems

### Allocation in Financial Systems
- NetSuite: Allocation schedules, automated allocation
- SAP: Cost center allocation, assessment cycles
- Adaptive Insights: Allocation rules in planning models
- Excel: Allocation templates and models

### Automation Opportunities
- Automated driver data collection (headcount, transactions)
- Rule-based allocation calculations
- Monthly allocation journal entries
- Allocation variance analysis

## Integration with Other Skills

- **budget-variance-analysis**: Analyze allocation variances
- **financial-modeling**: Include allocations in models
- **cost-optimizer**: Use allocations to identify cost reduction opportunities
- **management-reporting**: Report costs with allocations
- **gaap-ifrs-compliance**: Ensure allocations comply with accounting standards

## Key Terminology

- **Cost Allocation**: Assigning indirect costs to cost objects
- **Cost Pool**: Group of costs to be allocated
- **Cost Driver**: Factor that causes costs (activity, volume)
- **Allocation Base**: Metric used to distribute costs
- **Direct Cost**: Traceable to single cost object
- **Indirect Cost**: Benefits multiple cost objects, requires allocation
- **Activity-Based Costing (ABC)**: Allocation using activity drivers
- **Step-Down Method**: Sequential allocation of service departments
- **Reciprocal Method**: Simultaneous allocation recognizing interdependencies
- **Cost Object**: Thing receiving allocated costs (product, department, customer)

---

**Skill Type**: Accounting methodology
**Difficulty**: Intermediate
**Prerequisites**: Basic accounting, cost concepts
**Related Skills**: budget-variance-analysis, cost-optimizer, financial-modeling
