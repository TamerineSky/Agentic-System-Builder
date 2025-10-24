---
name: deal-scoring-models
description: Frameworks for scoring deals based on qualification criteria, risk factors, propensity to close, and strategic value to prioritize sales efforts. Use when prioritizing deals, assessing win probability, or building predictive close models.
---

# Deal Scoring Models

Systematic approaches to evaluate and rank sales opportunities based on qualification, win probability, strategic fit, and risk factors to optimize resource allocation and forecast accuracy.

## When to Use This Skill

- Prioritizing which deals to focus sales resources on
- Building predictive models for close probability
- Identifying high-value, high-probability opportunities
- Coaching reps on deal qualification
- Allocating SE, executive sponsor, or other scarce resources
- Improving forecast accuracy through better probability assignment
- Identifying patterns in won vs. lost deals

## Core Scoring Frameworks

### 1. MEDDIC Scoring

**Metrics:** Quantifiable business value and success criteria
**Economic Buyer:** Decision-maker with budget authority engaged
**Decision Criteria:** Evaluation process and requirements understood
**Decision Process:** Timeline, stakeholders, approval steps mapped
**Identify Pain:** Business problem clearly articulated
**Champion:** Internal advocate actively selling on your behalf

**Scoring Matrix (0-100 points):**
```
Metrics Defined (20 points):
- No metrics: 0
- Vague ROI discussion: 10
- Specific, quantified metrics: 20

Economic Buyer Engaged (25 points):
- Not identified: 0
- Identified, not engaged: 10
- Met once: 15
- Multiple meetings, strong relationship: 25

Decision Criteria Known (15 points):
- Unknown: 0
- Partially understood: 8
- Fully documented: 15

Decision Process Mapped (15 points):
- No visibility: 0
- Basic understanding: 8
- Detailed timeline with milestones: 15

Pain Identified (10 points):
- No clear pain: 0
- Pain mentioned: 5
- Urgent, quantified pain: 10

Champion Secured (15 points):
- No champion: 0
- Identified, not committed: 8
- Active champion selling internally: 15

Total Score Interpretation:
- 80-100: Highly qualified, high win probability
- 60-79: Qualified, needs work on key areas
- 40-59: Weak qualification, significant gaps
- <40: Poorly qualified, consider disqualifying
```

### 2. BANT Scoring (Budget, Authority, Need, Timeline)

**Budget (25 points):**
- No budget: 0
- Budget discussions started: 10
- Budget confirmed verbally: 18
- Budget approved in writing: 25

**Authority (30 points):**
- Speaking to individual contributor: 0
- Manager level: 10
- Director level: 18
- VP/C-level decision maker: 30

**Need (25 points):**
- No clear need: 0
- Nice-to-have: 10
- Important problem: 18
- Critical, urgent need: 25

**Timeline (20 points):**
- No timeline: 0
- Timeline > 6 months: 5
- Timeline 3-6 months: 10
- Timeline < 3 months: 15
- Urgent (< 30 days): 20

### 3. Propensity-to-Close Scoring

**Multi-Factor Model:**

**Company Fit (20 points):**
- Company size match: 10 points (ICP range)
- Industry fit: 5 points (target vertical)
- Geography fit: 5 points (coverage area)

**Engagement Signals (25 points):**
- Email open/click rates: 5 points
- Meeting frequency: 5 points
- Stakeholder breadth (# contacts): 10 points
- Content consumption: 5 points

**Sales Process Advancement (25 points):**
- Current stage completion: 15 points
- Days in stage vs. benchmark: 10 points

**Historical Patterns (15 points):**
- Similar deals won rate: 15 points

**External Signals (15 points):**
- Company growth indicators: 5 points
- Funding/budget signals: 5 points
- Job postings relevant to solution: 5 points

**Example Calculation:**
```
Acme Corp Deal:
- Company Fit: 18/20 (right size, target industry)
- Engagement: 21/25 (good activity, 4 contacts)
- Process: 19/25 (Stage 3, on pace)
- Historical: 12/15 (58% win rate for similar)
- External: 13/15 (growing, recent funding)

Total: 83/100 → High propensity to close
Predicted Win Probability: 78%
```

### 4. Strategic Value Scoring

**Deal Value Dimensions:**

**Financial Value (30 points):**
- Deal size relative to average: 10 points
- Potential expansion opportunity: 10 points
- Lifetime value: 10 points

**Strategic Value (30 points):**
- New vertical/segment entry: 10 points
- Reference account potential: 10 points
- Competitive displacement: 10 points

**Operational Value (20 points):**
- Complexity/resource requirements: 10 points
- Alignment with product roadmap: 10 points

**Risk Factors (20 points):**
- Implementation risk: 10 points
- Churn risk: 10 points

**Prioritization Matrix:**
```
High Strategic Value + High Win Probability = TOP PRIORITY
High Strategic Value + Low Win Probability = INVEST HEAVILY
Low Strategic Value + High Win Probability = QUICK WINS
Low Strategic Value + Low Win Probability = DEPRIORITIZE
```

## Implementation Examples

### Pipeline Prioritization Report

```
Q4 Deal Priorities - Ranked by Score

Priority 1 (Score 85+, Value $500K+):
1. Global Industries - $890K, Score 91, Win Prob 85%
2. TechCorp - $650K, Score 88, Win Prob 80%
3. Enterprise LLC - $720K, Score 86, Win Prob 76%

Priority 2 (Score 75-84, Value $300K+):
4. Innovate Systems - $580K, Score 82
5. DataDriven Inc - $490K, Score 79
6. CloudFirst - $510K, Score 78

Priority 3 (Score 65-74, or Value <$300K):
7. StartupXYZ - $380K, Score 73
8. MarketLeaders - $280K, Score 71
...

Action: Allocate exec sponsors to Priority 1 deals
```

### Forecast Calibration

```
Traditional Stage-Based Probability:
- Stage 3 (Proposal): 50% probability

Enhanced with Deal Scoring:
- Stage 3 + MEDDIC Score 85: 72% probability
- Stage 3 + MEDDIC Score 65: 48% probability
- Stage 3 + MEDDIC Score 45: 28% probability

Result: More accurate probability assignments, better forecasts
```

## Resources

- MEDDIC qualification template
- BANT assessment checklist
- Deal scoring calculator (Excel)
- CRM custom scoring fields setup guide

## Best Practices

1. **Consistent Application:** Train all reps on same scoring criteria
2. **Regular Updates:** Score deals weekly as new information emerges
3. **Validation:** Compare scores to actual outcomes, refine model
4. **Transparency:** Make scoring criteria visible to entire team
5. **Automate Where Possible:** Use CRM workflows to calculate scores
6. **Balance Factors:** Don't over-weight single dimension
7. **Adjust for Context:** Segment-specific scoring (enterprise vs. SMB)

## Common Pitfalls

1. **Subjective Scoring:** Reps inflate scores without evidence
2. **Static Scores:** Not updating as deal progresses
3. **Over-Complication:** Too many factors, becomes unusable
4. **No Validation:** Not comparing scores to actual win rates
5. **Ignoring Negative Signals:** Focusing only on positive factors
6. **Gaming:** Reps manipulate scores to hit thresholds
7. **One-Size-Fits-All:** Same model for different deal types
