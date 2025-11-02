You are tasked with performing scenario and sensitivity analysis for strategic planning and decision support.

## Objective
Develop multiple plausible future scenarios, assess their financial impact, and provide decision-makers with insights into risks, opportunities, and robust strategies.

## Process

### 1. Objective Definition
Clarify the decision or question:
- Strategic initiative evaluation (new product, market expansion, M&A)
- Risk assessment (economic downturn, competitive threat)
- Capital allocation decisions
- Budget planning with uncertainty
- Fundraising and valuation support

### 2. Key Uncertainty Identification
Identify 2-5 critical uncertainties that:
- Have high impact on outcomes
- Are largely beyond company control
- Have meaningful probability of occurring

**Examples:**
- Market growth rate (slow vs. fast)
- Competitive intensity (low vs. high)
- Customer adoption rate
- Regulatory environment
- Economic conditions
- Technology disruption

### 3. Scenario Definition
Create 3-4 distinct scenarios:

**Base Case** (most likely, 50-60% probability):
- Current trends continue with moderate adjustments
- Conservative assumptions where uncertain
- Used for official planning

**Upside Scenario** (optimistic, 20-30% probability):
- Favorable market conditions materialize
- Strong execution on initiatives
- Market leadership position strengthened

**Downside Scenario** (pessimistic, 20-30% probability):
- Unfavorable conditions emerge
- Execution challenges occur
- Competitive or market headwinds

**Alternative Scenarios** (as needed):
- Strategic scenario (e.g., M&A case)
- Stress test (extreme downside)
- Opportunity scenario (new market/product)

### 4. Scenario Narratives
For each scenario, develop:
- **Name**: Descriptive name (e.g., "Market Leadership", "Steady Growth", "Competitive Dogfight")
- **Probability**: Estimated likelihood
- **Time Horizon**: Period covered
- **Narrative**: Story of how this scenario unfolds
- **Key Drivers**: Specific assumptions for critical variables
- **External Factors**: Market, competitive, regulatory context

### 5. Quantification
Build financial models for each scenario:

**Key Assumptions by Scenario:**
- Revenue growth rates
- Customer acquisition and churn
- Pricing and gross margins
- OpEx growth and investment levels
- Working capital requirements
- Capital expenditures

**Financial Outputs:**
- P&L (Revenue, EBITDA, Net Income)
- Balance Sheet (Cash, Working Capital, Debt)
- Cash Flow (Operating, Investing, Financing)
- Key Metrics (Margins, Returns, Runway)

### 6. Sensitivity Analysis
Test impact of changing individual assumptions:

**One-Way Sensitivity:**
- Vary single assumption (e.g., revenue growth ±20%)
- Hold all others constant
- Show impact on key output (e.g., EBITDA, NPV)

**Two-Way Sensitivity:**
- Vary two assumptions simultaneously
- Create sensitivity table or matrix
- Identify combination effects

**Tornado Diagram:**
- Show variables with largest impact on outcome
- Prioritize focus areas for management

### 7. Scenario Comparison
Compare scenarios across dimensions:
- Financial performance (Revenue, EBITDA, Cash)
- Strategic position (Market share, competitive strength)
- Risk profile (Volatility, downside protection)
- Resource requirements (Investment, headcount)
- Return metrics (NPV, IRR, Payback)

### 8. Early Warning Indicators
For each scenario, define indicators to monitor:
- Which scenario is materializing?
- When should contingency plans activate?
- What metrics signal scenario shifts?

**Example:**
If customer CAC exceeds $50K for 2 consecutive months → Downturn scenario likely → Activate cost reduction plan

### 9. Strategy Recommendations
Based on analysis:
- **Robust Strategies**: Work well across multiple scenarios
- **Hedges**: Actions to reduce downside risk
- **Options**: Investments that create future flexibility
- **Contingency Plans**: Prepared responses if scenarios unfold
- **Recommended Path**: Best strategy given probabilities and risk tolerance

## Required Inputs
- **Decision Context**: What decision is being supported?
- **Time Horizon**: "1-year", "3-years", "5-years"
- **Scenarios**: "standard" (base/upside/downside) or "custom" with definitions
- **Key Variables**: Critical assumptions to vary
- **Base Model**: Existing financial model or build new
- **Sensitivity Focus**: Which outputs matter most (NPV, cash, EBITDA, etc.)

## Output Format

1. **Executive Summary**:
   - Decision context and recommendation
   - Scenario comparison table
   - Key insights and takeaways
   - Recommended strategy

2. **Scenario Narratives**:
   - Description of each scenario
   - Probability and key assumptions
   - Business context and drivers

3. **Financial Models**:
   - Complete financial statements for each scenario
   - Side-by-side scenario comparison
   - Key metrics dashboard

4. **Sensitivity Analysis**:
   - Tornado diagram showing key drivers
   - One-way and two-way sensitivity tables
   - Break-even and threshold analysis

5. **Early Warning Dashboard**:
   - Indicators to monitor
   - Trigger points for action
   - Contingency plans

6. **Strategic Recommendations**:
   - Robust strategies across scenarios
   - Risk mitigation approaches
   - Recommended decisions and timing

## Usage Examples

### Strategic Initiative Evaluation
```
/scenario-analysis --decision "expand-to-europe" --horizon "3-years" --scenarios "base,upside,downside"
```

### M&A Scenario Planning
```
/scenario-analysis --decision "acquire-competitor-x" --horizon "5-years" --scenarios "standalone,acquire,strategic-partnership"
```

### Budget Uncertainty Analysis
```
/scenario-analysis --decision "2025-budget" --horizon "1-year" --scenarios "base,upside,downside" --sensitivity "revenue-growth,churn-rate,hiring-plan"
```

### Stress Testing
```
/scenario-analysis --decision "recession-preparedness" --horizon "2-years" --scenarios "base,mild-recession,severe-recession"
```

## Best Practices
- Focus on 2-3 critical uncertainties (avoid too many scenarios)
- Make scenarios plausible and internally consistent
- Use probability weighting when calculating expected values
- Link scenarios to specific business strategies
- Update scenarios as new information emerges
- Monitor indicators to detect which scenario is unfolding
- Maintain scenario discipline (don't just average them)
- Communicate scenarios narratively, not just numbers

## Applications
- Annual strategic planning
- Budget and long-range planning
- Major investment decisions (M&A, new markets, products)
- Risk assessment and stress testing
- Fundraising and valuation support
- Board strategic discussions
- Contingency planning

---

**Skills Utilized:** scenario-planning, financial-modeling, financial-forecasting-methods, budget-variance-analysis
**Agent:** fpa-advisor
