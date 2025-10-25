---
name: supplier-scorecards
description: Supplier performance scorecarding methodologies including quality, delivery, cost, and responsiveness metrics to evaluate and manage supplier relationships. Use when measuring supplier performance, conducting business reviews, or identifying improvement opportunities.
---

# Supplier Performance Scorecards

Comprehensive framework for measuring, tracking, and improving supplier performance across quality, delivery, cost, responsiveness, and innovation dimensions.

## When to Use This Skill

- Designing supplier performance measurement systems
- Conducting monthly or quarterly supplier business reviews
- Identifying underperforming suppliers requiring improvement plans
- Comparing suppliers for strategic sourcing decisions
- Supporting supplier recognition and awards programs
- Tracking supplier improvement over time
- Justifying supplier changes or consolidation
- Aligning procurement team on supplier expectations

## Core Scorecard Principles

### Balanced Scorecard Approach

Measure multiple dimensions beyond cost:
- **Quality**: Defect rates, PPM, returns
- **Delivery**: On-time delivery, lead time, fill rate
- **Cost**: Price competitiveness, cost-down achievements
- **Responsiveness**: Issue resolution, communication, flexibility
- **Innovation**: New products, value engineering, collaboration

### Weighted Scoring

Assign weights based on business priorities:
```
Total Score = (Quality × 40%) + (Delivery × 30%) + (Cost × 20%) + (Responsiveness × 10%)
```

Adjust weights by commodity or supplier segment.

### Performance Tiers

Create performance tiers:
- **Strategic Partner**: 90-100 (top performers)
- **Preferred**: 80-89 (meeting expectations)
- **Approved**: 70-79 (acceptable with improvement needed)
- **Development**: 60-69 (serious issues, improvement plan required)
- **At Risk**: <60 (consider replacement)

## Key Performance Indicators

### Quality Metrics

**Defect Rate**:
```
Defect Rate = (Defective Units / Total Units Received) × 100%

Target: <1% for most categories, <0.1% for critical components
```

**PPM (Parts Per Million)**:
```
PPM = (Defective Units / Total Units Received) × 1,000,000

Target: <100 PPM for automotive, <10 PPM for medical devices
```

**First Pass Yield**:
```
FPY = (Units Passing Inspection / Total Units Inspected) × 100%

Target: >99%
```

**Customer Returns**:
```
Return Rate = (Units Returned / Units Shipped) × 100%
```

### Delivery Metrics

**On-Time Delivery (OTD)**:
```
OTD = (Deliveries On-Time / Total Deliveries) × 100%

On-time window: Typically ±1 day from requested date
Target: >95%
```

**On-Time In-Full (OTIF)**:
```
OTIF = (Deliveries On-Time AND In-Full / Total Deliveries) × 100%

Combines delivery timing and quantity accuracy
Target: >90% (harder than OTD alone)
```

**Lead Time Performance**:
```
Lead Time Variance = (Actual Lead Time - Committed Lead Time) / Committed Lead Time

Target: <10% variance
```

**Fill Rate**:
```
Fill Rate = (Units Delivered / Units Ordered) × 100%

Target: >98%
```

### Cost Metrics

**Price Competitiveness**:
```
Price Index = (Supplier Price / Market Benchmark Price) × 100

Target: <105 (within 5% of market)
```

**Cost-Down Achievement**:
```
Cost Savings % = (Previous Price - Current Price) / Previous Price × 100%

Annual target: 2-5% year-over-year reduction
```

**Total Cost of Ownership**:
```
TCO = Purchase Price + Quality Cost + Delivery Cost + Risk Cost

Include: Unit price, defect/rework costs, freight premiums, stockout costs
```

### Responsiveness Metrics

**Issue Resolution Time**:
```
Average days from issue identification to resolution
Target: <5 days for non-critical, <24 hours for critical
```

**Communication Quality**:
```
Subjective rating: 1-5 scale
- Proactive communication
- Responsiveness to inquiries
- Transparency about issues
```

**Change Order Flexibility**:
```
% of change orders accepted
Average lead time for changes
Target: >90% acceptance, <5 day change lead time
```

## Scorecard Design and Implementation

### Multi-Dimensional Scorecard Template

```
Supplier: ABC Manufacturing
Period: Q4 2024
Category: Machined Components

┌─────────────────┬────────┬────────┬────────┬────────┐
│ Metric          │ Weight │ Target │ Actual │ Score  │
├─────────────────┼────────┼────────┼────────┼────────┤
│ QUALITY (40%)                                       │
├─────────────────┼────────┼────────┼────────┼────────┤
│ PPM             │  20%   │  <100  │   75   │  100   │
│ First Pass Yield│  15%   │  >99%  │  99.2% │   96   │
│ Customer Returns│   5%   │  <0.5% │  0.3%  │  100   │
│ Quality Score   │  40%   │        │        │  98.6  │
├─────────────────┼────────┼────────┼────────┼────────┤
│ DELIVERY (30%)                                      │
├─────────────────┼────────┼────────┼────────┼────────┤
│ On-Time Delivery│  20%   │  >95%  │  92%   │   77   │
│ Lead Time       │   7%   │  4 wks │ 4.5 wks│   75   │
│ Fill Rate       │   3%   │  >98%  │  99%   │  100   │
│ Delivery Score  │  30%   │        │        │  79.4  │
├─────────────────┼────────┼────────┼────────┼────────┤
│ COST (20%)                                          │
├─────────────────┼────────┼────────┼────────┼────────┤
│ Price Index     │  15%   │  <105  │  102   │   90   │
│ Cost Down       │   5%   │  3%    │  2.5%  │   83   │
│ Cost Score      │  20%   │        │        │  88.5  │
├─────────────────┼────────┼────────┼────────┼────────┤
│ RESPONSIVENESS (10%)                                │
├─────────────────┼────────┼────────┼────────┼────────┤
│ Issue Resolution│   5%   │  <5 d  │  4 d   │   90   │
│ Communication   │   5%   │  4/5   │  4/5   │   80   │
│ Response Score  │  10%   │        │        │   85.0 │
├─────────────────┼────────┼────────┼────────┼────────┤
│ TOTAL SCORE     │ 100%   │        │        │  90.7  │
└─────────────────┴────────┴────────┴────────┴────────┘

Rating: Strategic Partner (90-100)
Trend: ↑ Improving (was 88.2 in Q3)
```

### Scoring Methodology

**Linear Scaling**:
```
Score = 100 × (Actual - Minimum) / (Target - Minimum)

Example: OTD
Target = 95%, Minimum = 80%, Actual = 92%
Score = 100 × (92 - 80) / (95 - 80) = 100 × 12/15 = 80
```

**Threshold Scaling**:
```
If Actual >= Target: Score = 100
If Actual >= Acceptable: Score = 70-99 (linear)
If Actual < Acceptable: Score = 0-69 (linear or step function)
```

## Resources

### Templates and Tools
- Excel/Google Sheets supplier scorecard templates
- ERP supplier performance modules (SAP SRM, Oracle Supplier Portal)
- SRM platforms: Ariba, Coupa, Ivalua

### Best Practices
- Review scorecards monthly for critical suppliers, quarterly for others
- Share scorecards with suppliers and conduct collaborative reviews
- Track trends over time, not just point-in-time performance
- Link scorecard performance to business allocation decisions
- Recognize top performers publicly, coach poor performers privately

## Common Pitfalls

- Too many metrics dilute focus (keep to 5-10 key metrics)
- Equal weighting when some dimensions clearly more important
- Measuring what's easy rather than what matters
- Not sharing results with suppliers
- No corrective action plan for poor performance
- Static scorecards that don't evolve with business needs
- Scoring without context (seasonal variation, market disruptions)
- Focusing only on lagging indicators, not leading
