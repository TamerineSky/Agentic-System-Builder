# Scenario Planning Skill

## Overview
This skill covers scenario development, sensitivity analysis, Monte Carlo simulation, and strategic scenario planning techniques for financial modeling and decision-making under uncertainty.

## Core Concepts

### What is Scenario Planning?
Scenario planning is the process of developing multiple plausible future states to:
- Test strategic decisions under different conditions
- Assess risk and uncertainty
- Identify robust strategies that work across scenarios
- Prepare contingency plans
- Support executive decision-making

### Scenarios vs. Forecasts
```
Forecast: Single "most likely" projection
Scenario: Multiple plausible futures

Example:
Forecast: Revenue will be $100M next year
Scenarios:
- Base case: $100M (50% probability)
- Upside: $120M (25% probability)
- Downside: $80M (25% probability)
```

## Scenario Types

### 1. Financial Planning Scenarios

**Base Case:**
- Most likely outcome based on current trends
- Conservative assumptions where uncertain
- 50-60% probability of achievement
- Used for official guidance and budgeting

**Upside Case:**
- Optimistic but achievable outcome
- Favorable market conditions
- Better-than-expected execution
- 20-30% probability
- Used for capacity planning and opportunity assessment

**Downside Case:**
- Conservative outcome for risk planning
- Unfavorable market conditions
- Execution challenges
- 20-30% probability
- Used for stress testing and contingency planning

**Example - SaaS Company:**
```
                    Downside    Base    Upside
Revenue growth      15%         25%     35%
Gross margin        70%         75%     78%
Net retention       95%         105%    115%
New customers/q     100         150     200
CAC payback (mo)    24          18      15
EBITDA margin       5%          15%     22%

Full-year impact:
Revenue             $80M        $100M   $120M
EBITDA              $4M         $15M    $26M
```

### 2. Strategic Scenarios

**Business Model Scenarios:**
```
Scenario A: Focus on enterprise customers
- Higher ACV ($100K vs $50K)
- Longer sales cycles (6 months vs 3 months)
- Higher gross margins (80% vs 75%)
- Lower customer count but higher quality

Scenario B: SMB land-and-expand
- Lower ACV ($20K vs $50K)
- Faster sales cycles (1 month vs 3 months)
- Lower gross margins (65% vs 75%)
- High volume, expansion revenue

Model both to determine optimal strategy
```

**Market Entry Scenarios:**
```
Scenario 1: Organic growth
- 3-year timeline to $10M revenue
- $5M investment
- Lower risk, slower growth

Scenario 2: Acquisition-led growth
- 1-year timeline to $10M revenue
- $20M investment (acquisition + integration)
- Higher risk, faster growth
- Requires successful integration

Compare NPV, IRR, risk profiles
```

### 3. Risk Scenarios

**Stress Testing:**
```
Scenario: Severe recession
Assumptions:
- Revenue declines 30%
- Customer churn increases to 15% (from 5%)
- Unable to raise prices
- Cost reductions limited (people-heavy business)

Impact:
- EBITDA turns negative
- Cash runway reduced to 8 months
- Violates debt covenants

Mitigation:
- Immediate 20% cost reduction
- Secure additional credit line
- Pivot to cash-generative segments
```

**Black Swan Events:**
```
Examples:
- Major customer bankruptcy (30% of revenue)
- Regulatory change eliminating product category
- Cyber attack causing data breach
- Key executive departure

Approach:
- Identify plausible but unlikely events
- Model financial impact
- Develop response plans
- Build resilience into strategy
```

## Scenario Development Process

### Step 1: Identify Key Uncertainties
```
Ask: What factors most impact our results that we can't control?

Examples:
- Market growth rate
- Competitive intensity
- Technology disruption
- Regulatory changes
- Economic conditions
- Customer preferences

Prioritize:
- High impact + High uncertainty = Focus here
- High impact + Low uncertainty = Plan for
- Low impact = Monitor but don't over-analyze
```

### Step 2: Define Scenario Axes
```
Two-dimensional framework:

Example for SaaS company:

Axis 1: Market Growth (Slow vs. Fast)
Axis 2: Competitive Intensity (Low vs. High)

Four scenarios:
1. Fast Growth + Low Competition = "Blue Sky"
2. Fast Growth + High Competition = "Land Grab"
3. Slow Growth + Low Competition = "Steady State"
4. Slow Growth + High Competition = "Dogfight"

Develop full narratives for each quadrant
```

### Step 3: Build Scenario Narratives
```
Template:

Scenario Name: "Blue Sky"
Probability: 20%
Time Horizon: 3 years

Narrative:
Market adoption accelerates due to regulatory mandate. Annual market
growth reaches 40%. Barriers to entry remain high due to technical
complexity and compliance requirements. Company captures 25% market share.

Key Assumptions:
- TAM growth: 40% annually
- Win rate: 35% (vs 25% base)
- Churn: 3% (vs 5% base)
- Pricing power: Can increase 10% annually

Financial Impact:
- Revenue Year 3: $200M (vs $100M base)
- EBITDA margin: 30% (vs 15% base)
- Cash generation: Strong
```

### Step 4: Quantify Scenarios
```
Build financial models for each:

                    Dogfight    Steady    Land Grab   Blue Sky
Year 3 Revenue      $60M        $80M      $150M       $200M
EBITDA margin       -5%         10%       12%         30%
Cash position       $5M         $20M      $15M        $50M
Market share        8%          12%       18%         25%

Key metrics:
- NPV (at 12% discount)
- Cumulative cash burn/generation
- Time to profitability
- Strategic position (market share, competitive strength)
```

### Step 5: Develop Contingency Plans
```
For each scenario, determine:

If "Dogfight" scenario emerges:
- Signals to watch: Pricing pressure, increasing customer acquisition costs
- Trigger points: CAC exceeds $50K, win rate drops below 20%
- Response plan:
  * Shift to niche vertical with less competition
  * Reduce CAC by 30% through product-led growth
  * Cut OpEx by 20% to extend runway
  * Explore strategic acquisition or merger

Early warning dashboard:
- Monitor key indicators monthly
- Alert when trending toward specific scenario
- Enable proactive response
```

## Sensitivity Analysis

### One-Way Sensitivity
```
Vary one assumption, hold others constant

Example: Revenue sensitivity to churn rate

Churn Rate    Year 3 Revenue    Change from Base
2%            $110M             +10%
3%            $105M             +5%
5% (base)     $100M             baseline
7%            $95M              -5%
10%           $85M              -15%

Insight: Each 1% of churn = ~$5M revenue impact
Action: Invest in retention programs if cost < $5M per 1% churn reduction
```

### Two-Way Sensitivity
```
Vary two assumptions simultaneously

Example: EBITDA sensitivity to revenue growth and gross margin

              Gross Margin
              70%     75%     80%
Revenue
Growth:
15%           $8M     $12M    $16M
20%           $10M    $15M    $20M
25%           $12M    $18M    $24M
30%           $14M    $21M    $28M

Insight: EBITDA highly sensitive to both factors
Action: Focus on gross margin improvement AND growth
```

### Tornado Diagram
```
Shows which variables have largest impact on outcome

Example: Impact on NPV (range from -20% to +20% change in each variable)

Revenue growth        |=============================| $50M range
Gross margin          |====================|         $30M range
Churn rate            |===============|              $22M range
CAC                   |========|                     $12M range
OpEx growth           |=====|                        $8M range

Longest bar = highest sensitivity
Focus management attention on top 2-3 drivers
```

## Monte Carlo Simulation

### Process
```
1. Identify uncertain variables
   - Revenue growth
   - Churn rate
   - Gross margin
   - Customer acquisition

2. Assign probability distributions
   - Revenue growth: Normal (mean=20%, std dev=5%)
   - Churn: Uniform (3% to 7%)
   - Gross margin: Triangular (min=70%, mode=75%, max=80%)

3. Run simulations (10,000+ iterations)
   - Randomly sample from distributions
   - Calculate financial outcomes
   - Store results

4. Analyze output distribution
   - P10, P50, P90 outcomes
   - Probability of achieving targets
   - Risk metrics (downside probability, Value at Risk)
```

### Example Output
```
Year 3 EBITDA Distribution (10,000 simulations):

P10 (worst 10%):      $5M or below
P25:                  $10M
P50 (median):         $15M
P75:                  $20M
P90 (best 10%):       $25M or above

Probability analysis:
- P(EBITDA > $20M) = 25%
- P(EBITDA > $15M) = 50%
- P(EBITDA > $10M) = 75%
- P(EBITDA < $0) = 5%

Risk-adjusted expected value: $15.2M (vs $15M base case)
```

### Monte Carlo Tools
- Excel add-ins: @RISK, Crystal Ball
- Python: NumPy, SciPy, Monte Carlo libraries
- R: Simulation packages
- Specialized software: Palisade DecisionTools

## Scenario Planning Best Practices

### 1. Make Scenarios Plausible
```
Good scenario:
"Market grows 40% due to regulatory change requiring our solution"
- Specific driver identified
- Reasonable magnitude
- Clear causation

Bad scenario:
"Everything goes perfectly and we 10x revenue"
- No specific drivers
- Unrealistic
- Not useful for planning
```

### 2. Focus on Key Uncertainties
```
Don't create scenarios for everything
Focus on 2-3 critical uncertainties

Example - SaaS company:
Critical: Market growth rate, competitive intensity
Less critical: Office rent, laptop costs
Don't scenario plan for minor items
```

### 3. Use Consistent Scenario Framework
```
Standard scenarios across organization:
- Base, Upside, Downside
- Same probability assignments
- Common assumptions where appropriate
- Enables portfolio-level analysis

Department-specific variations allowed but maintain
consistency on company-wide drivers (revenue, market growth)
```

### 4. Update Scenarios Regularly
```
Annual: Full scenario refresh
Quarterly: Update probabilities based on actuals
Monthly: Monitor indicators, adjust if needed

When to update:
- Major market changes
- Competitive shifts
- Company strategic pivots
- Actual results significantly diverge from forecast
```

### 5. Link Scenarios to Decisions
```
Don't just model scenarios - use them!

Example decision framework:
Decision: Should we invest $10M in new product?

Analysis:
- NPV in Base case: $5M → Marginal GO
- NPV in Upside: $20M → Strong GO
- NPV in Downside: ($8M) → NO GO

Decision: Proceed if confidence >60% we're in Base or better
Action: Validate market assumptions before committing full $10M
Approach: Stage investment, pilot first ($2M), then reassess
```

## Common Scenario Planning Applications

### Annual Planning
```
Develop 3 scenarios for annual budget:

Base (Official Budget):
- Submitted to board
- Basis for incentive comp
- Conservative

Upside (Stretch Plan):
- If things go well
- Capacity planning (hiring, infrastructure)
- Identify upside opportunities

Downside (Contingency Plan):
- If market softens
- Cost reduction plans
- Cash preservation strategies
```

### Strategic Initiatives
```
M&A Scenarios:

Scenario 1: Standalone (no acquisition)
- Organic growth: 20% annually
- 5-year revenue: $150M
- Investment: $10M in product development

Scenario 2: Acquire competitor for $50M
- Accelerated growth: 35% annually
- 5-year revenue: $250M
- Investment: $50M acquisition + $20M integration

Scenario 3: Acquire complementary product for $30M
- Enhanced growth: 28% annually
- 5-year revenue: $200M
- Investment: $30M acquisition + $10M integration

Compare NPV, IRR, risk, strategic positioning
```

### Fundraising
```
Present multiple scenarios to investors:

Conservative: $80M revenue, $10M EBITDA
Base: $100M revenue, $15M EBITDA
Aggressive: $120M revenue, $22M EBITDA

Shows range of outcomes
Demonstrates thoughtful planning
Addresses investor questions about risk
Justifies valuation range
```

## Integration with Other Skills

- **financial-forecasting-methods**: Base forecasts that feed scenarios
- **financial-modeling**: Build models supporting multiple scenarios
- **budget-variance-analysis**: Track which scenario is materializing
- **cash-flow-management**: Scenario-based cash planning
- **cost-allocation**: Allocate costs in different scenarios

## Key Terminology

- **Scenario**: Plausible future state with specific assumptions
- **Base Case**: Most likely scenario (50-60% probability)
- **Upside/Downside**: Optimistic/pessimistic scenarios
- **Sensitivity Analysis**: Testing impact of changing assumptions
- **Monte Carlo**: Probabilistic simulation with thousands of iterations
- **Tornado Diagram**: Visual showing variables with highest impact
- **P10/P50/P90**: 10th/50th/90th percentile outcomes
- **Stress Test**: Extreme downside scenario
- **Black Swan**: Highly unlikely but high-impact event
- **Contingency Plan**: Prepared response if scenario materializes

---

**Skill Type**: Strategic/Analytical
**Difficulty**: Intermediate to Advanced
**Prerequisites**: Financial modeling, statistics basics, strategic thinking
**Related Skills**: financial-modeling, financial-forecasting-methods, budget-variance-analysis
