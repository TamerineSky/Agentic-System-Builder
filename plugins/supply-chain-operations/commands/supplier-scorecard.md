---
description: Generate comprehensive supplier performance scorecard with quality, delivery, cost, and responsiveness metrics for specified period.
argument-hint: [supplier-name] [period]
model: haiku
version: 1.0.0
tags: [supplier, performance, scorecard]
---

# Supplier Performance Scorecard

Comprehensive supplier evaluation across quality, delivery, cost, and responsiveness dimensions with weighted scoring and recommendations.

## Context

Supplier scorecards drive performance improvement, support sourcing decisions, and facilitate supplier business reviews.

## Requirements
$ARGUMENTS

## Instructions

### 1. Data Collection

Gather performance data for $1 (supplier) during $2 (period):
- **Quality**: Defect rates, PPM, first pass yield, customer returns
- **Delivery**: On-time delivery %, lead time performance, fill rate
- **Cost**: Price competitiveness, cost-down achievements, total cost
- **Responsiveness**: Issue resolution time, communication quality, flexibility

Sources: Quality system, ERP receiving data, procurement records, stakeholder surveys.

### 2. Calculate Performance Metrics

**Quality Metrics**:
```
PPM = (Defective units / Total received) × 1,000,000
First Pass Yield = (Passed inspection / Total inspected) × 100%
Return Rate = (Units returned / Units shipped) × 100%
```

**Delivery Metrics**:
```
On-Time Delivery = (Deliveries on-time / Total deliveries) × 100%
Lead Time Variance = (Actual LT - Committed LT) / Committed LT × 100%
Fill Rate = (Units delivered / Units ordered) × 100%
```

**Cost Metrics**:
```
Price Index = (Supplier price / Benchmark price) × 100
Cost Savings % = (Previous price - Current price) / Previous price × 100%
```

### 3. Apply Weighted Scoring

Score each dimension (0-100 scale):
- Compare actual vs. target performance
- Apply linear or threshold scoring method

Apply category weights (adjust based on commodity):
```
Total Score = Quality × 40% + Delivery × 30% + Cost × 20% + Responsiveness × 10%
```

Determine performance tier:
- 90-100: Strategic Partner
- 80-89: Preferred
- 70-79: Approved
- 60-69: Development (improvement plan required)
- <60: At Risk

### 4. Trend Analysis and Insights

Compare to previous periods:
- Identify improving, stable, or declining trends
- Highlight significant changes (>5 points)
- Pinpoint root causes of performance shifts

Benchmark against:
- Internal targets and thresholds
- Other suppliers in same category
- Industry standards

### 5. Develop Recommendations

Based on scorecard results:
- **Top performers**: Recognition, increased allocation, partnership opportunities
- **Adequate performers**: Maintain current relationship, monitor
- **Underperformers**: Improvement plan, corrective actions, reduced allocation
- **At-risk**: Supplier development program or replacement

Specific actions:
- Quality issues: Root cause analysis, CAPA, supplier audits
- Delivery problems: Capacity review, buffer stock, dual sourcing
- Cost opportunities: Negotiations, value engineering, competitive bidding

## Output Format

1. **Scorecard Dashboard**: Visual summary with overall score and dimension scores
2. **Detailed Metrics Table**: All KPIs with actual, target, and score
3. **Trend Chart**: Performance over last 4 quarters
4. **Top Issues**: 3-5 highest priority improvement areas
5. **Action Plan**: Specific recommendations and next steps

## Success Criteria

- Complete scorecard for $1 covering $2 period
- All key dimensions measured (quality, delivery, cost, responsiveness)
- Clear performance tier assignment
- Actionable recommendations for improvement or recognition
- Ready for supplier business review presentation
