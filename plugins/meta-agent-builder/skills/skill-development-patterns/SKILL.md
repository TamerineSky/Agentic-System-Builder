---
name: skill-development-patterns
description: Progressive disclosure architecture and skill specification patterns following Anthropic Agent Skills Specification v1.0. Use when creating agent skills, packaging domain knowledge, or establishing skill development standards.
---

# Skill Development Patterns

Comprehensive patterns for creating agent skills with progressive disclosure architecture, following Anthropic's Agent Skills Specification v1.0 for token-efficient knowledge packaging.

## When to Use This Skill

- Creating new agent skills for business methodologies
- Packaging domain knowledge into reusable skills
- Establishing skill development standards
- Validating skill specifications for compliance
- Optimizing token usage through progressive disclosure
- Designing skill activation criteria
- Adapting technical skills to business contexts
- Refactoring monolithic content into skills

## Anthropic Agent Skills Specification v1.0

### Core Requirements

**File Structure:**
```
skills/{skill-name}/
└── SKILL.md                 # Required: Exact filename (all caps)
```

**Directory Name:** Must match skill `name` in frontmatter exactly

**Frontmatter (Required):**
```yaml
---
name: skill-name             # Required: hyphen-case, matches directory
description: What it does. Use when [activation trigger].  # Required: < 1024 chars
license: MIT                 # Optional: License identifier
metadata:                    # Optional: Custom key-value pairs
  domain: business-operations
  version: 1.0.0
---
```

### Critical Requirements

1. **Description Length:** MUST be < 1024 characters (STRICT LIMIT)
2. **Activation Clause:** MUST include "Use when..." (or similar)
3. **Name Format:** MUST be hyphen-case: `^[a-z0-9]+(-[a-z0-9]+)*$`
4. **Directory Match:** Directory name MUST match frontmatter name
5. **Filename:** MUST be exactly `SKILL.md` (all uppercase)
6. **Complete Description:** MUST NOT be truncated mid-sentence

## Progressive Disclosure Architecture

Skills use three-tier architecture for token efficiency:

### Tier 1: Metadata (Always Loaded)

**Purpose:** Activation decision
**Size:** < 1024 characters (description limit)
**Contents:** Frontmatter only

```yaml
---
name: pipeline-health-scoring
description: Comprehensive methodology for assessing sales pipeline quality, coverage, and risk using statistical analysis. Includes coverage ratio calculation, stage distribution analysis, velocity scoring, and deal health assessment. Use when analyzing pipeline health, identifying deal risks, optimizing sales processes, or coaching sales teams.
---
```

**Design Principles:**
- Front-load most important information
- Include all key activation triggers
- Be specific about methodology/approach
- Mention primary use cases
- Stay under 1024 character limit

### Tier 2: Instructions (Loaded When Activated)

**Purpose:** Core guidance and methodology
**Size:** 100-500 lines recommended
**Contents:** When to use, core concepts, patterns, quick start

**Structure:**
```markdown
# Skill Title

Brief overview (1-2 paragraphs)

## When to Use This Skill

- Scenario 1
- Scenario 2
[5-15 specific scenarios]

## Core Concepts

### 1. Concept Name
Explanation with key principles

### 2. Concept Name
Explanation with key principles

[3-8 core concepts]

## Quick Start

Basic example demonstrating the skill
```

### Tier 3: Resources (Loaded On Demand)

**Purpose:** Detailed examples, templates, references
**Contents:** Extended documentation, code samples, detailed examples

**Structure:**
```markdown
## Detailed Patterns

### Pattern 1: Name
Comprehensive explanation with code/examples

### Pattern 2: Name
Comprehensive explanation with code/examples

## Real-World Examples

### Example 1: Business Scenario
Complete walkthrough

### Example 2: Business Scenario
Complete walkthrough

## Resources

- Reference documents
- Templates and tools
- External links
- Additional reading
```

## Activation Criteria Design

### Pattern: "Use when..."

**Strong Activation Clauses:**
```
Use when analyzing pipeline health, identifying deal risks, or optimizing sales processes.

Use when forecasting demand, planning inventory, or optimizing supply schedules.

Use when building attribution models, tracking customer journeys, or optimizing marketing mix.

Use when calculating safety stock, optimizing reorder points, or reducing stockouts.

Use when predicting churn risk, scoring customer health, or identifying expansion opportunities.
```

**Weak Activation Clauses (Avoid):**
```
Use for sales stuff.                    // Too vague
Use when needed.                        // Not specific
Use for pipeline analysis.              // Single trigger only
Use in various scenarios.               // Not actionable
```

**Multiple Triggers Pattern:**
```
Use when [primary use case], [secondary use case], or [tertiary use case].
```

### Activation Trigger Types

**Action-Based Triggers:**
- analyzing, forecasting, optimizing, planning, calculating
- designing, building, implementing, evaluating, assessing
- scoring, predicting, identifying, tracking, measuring

**Context-Based Triggers:**
- pipeline health analysis
- demand forecasting workflows
- attribution modeling scenarios
- inventory optimization problems
- churn prediction exercises

**Outcome-Based Triggers:**
- improving forecast accuracy
- reducing stockouts
- optimizing marketing spend
- increasing conversion rates
- accelerating deal velocity

## Business Methodology Packaging Patterns

### Pattern 1: Forecasting Methodology Skill

```markdown
---
name: demand-forecasting-methods
description: Statistical demand forecasting methodologies including time-series analysis, seasonality detection, trend modeling, and forecast accuracy measurement. Covers ARIMA, exponential smoothing, moving averages, and intermittent demand patterns. Use when forecasting demand, planning inventory, building S&OP forecasts, or improving forecast accuracy.
---

# Demand Forecasting Methods

Comprehensive statistical methodologies for creating accurate demand forecasts that drive inventory optimization and supply planning decisions.

## When to Use This Skill

- Building demand forecasts for products or categories
- Selecting appropriate forecasting methods for demand patterns
- Handling seasonal and trend patterns in demand
- Forecasting intermittent or lumpy demand
- Measuring and improving forecast accuracy
- Creating forecasts at multiple aggregation levels
- Supporting S&OP (Sales and Operations Planning) processes
- Incorporating external factors into forecasts
- Generating forecast confidence intervals

## Core Concepts

### 1. Time-Series Forecasting Fundamentals

**Key Components:**
- **Level**: Average value around which data fluctuates
- **Trend**: Long-term increase or decrease in data
- **Seasonality**: Regular patterns that repeat over time
- **Noise**: Random variation that can't be explained

**Decomposition:**
```
Demand = Level + Trend + Seasonality + Noise
```

### 2. Forecasting Method Selection

**Stable Demand:** Simple moving average or single exponential smoothing
**Trending Demand:** Double exponential smoothing (Holt's method)
**Seasonal Demand:** Triple exponential smoothing (Holt-Winters)
**Complex Patterns:** ARIMA or machine learning methods
**Intermittent Demand:** Croston's method or bootstrapping

### 3. Forecast Accuracy Metrics

**MAPE (Mean Absolute Percentage Error):**
```
MAPE = (1/n) * Σ|Actual - Forecast| / Actual * 100%
```

**MAD (Mean Absolute Deviation):**
```
MAD = (1/n) * Σ|Actual - Forecast|
```

**Bias:**
```
Bias = (1/n) * Σ(Forecast - Actual)
```

## Forecasting Methods

### Method 1: Simple Moving Average

**When to Use:** Stable demand with no trend or seasonality

**Formula:**
```
Forecast(t+1) = (Demand(t) + Demand(t-1) + ... + Demand(t-n+1)) / n
```

**Example:**
```
Last 3 months demand: [100, 105, 98]
Forecast for next month = (100 + 105 + 98) / 3 = 101
```

**Advantages:**
- Simple to calculate and explain
- Smooths out random variation
- Works well for stable demand

**Disadvantages:**
- Lags behind trends
- Ignores seasonal patterns
- Equal weight to all periods

### Method 2: Exponential Smoothing

**When to Use:** Stable demand with recent data more important

**Formula:**
```
Forecast(t+1) = α * Demand(t) + (1-α) * Forecast(t)
```

**Parameters:**
- α (alpha): Smoothing constant (0 to 1)
- Higher α = more weight on recent data
- Lower α = more smoothing

**Example:**
```
α = 0.3
Last month demand = 120
Last month forecast = 100
New forecast = 0.3 * 120 + 0.7 * 100 = 106
```

### Method 3: Holt's Method (Double Exponential Smoothing)

**When to Use:** Demand with trend but no seasonality

**Formulas:**
```
Level(t) = α * Demand(t) + (1-α) * (Level(t-1) + Trend(t-1))
Trend(t) = β * (Level(t) - Level(t-1)) + (1-β) * Trend(t-1)
Forecast(t+h) = Level(t) + h * Trend(t)
```

**Parameters:**
- α: Level smoothing constant
- β: Trend smoothing constant
- h: Forecast horizon

### Method 4: Holt-Winters Method (Triple Exponential Smoothing)

**When to Use:** Demand with trend AND seasonality

**Components:**
- Level smoothing
- Trend smoothing
- Seasonal smoothing

**Seasonality Types:**
- **Additive:** Seasonal variation constant in absolute terms
- **Multiplicative:** Seasonal variation proportional to level

**Example Use Case:**
```
Product with 20% higher demand in December
Use multiplicative seasonality
Seasonal indices: [0.9, 0.85, 0.9, 1.0, 1.05, 1.0, 0.95, 0.9, 1.0, 1.1, 1.15, 1.2]
```

### Method 5: ARIMA Models

**When to Use:** Complex patterns requiring sophisticated modeling

**Components:**
- **AR (AutoRegressive):** Uses past values
- **I (Integrated):** Uses differencing for stationarity
- **MA (Moving Average):** Uses past forecast errors

**Model Selection:**
1. Check for stationarity (use Dickey-Fuller test)
2. Difference data if needed (I component)
3. Examine ACF/PACF plots for AR and MA orders
4. Fit candidate models and compare AIC/BIC
5. Validate with residual diagnostics

## Best Practices

### 1. Data Preparation

**Steps:**
1. Handle missing data (interpolation, forward fill)
2. Identify and treat outliers
3. Aggregate to appropriate time bucket
4. Split into train/test sets (80/20 typical)

### 2. Model Selection Process

**Decision Tree:**
```
Is demand stable with no pattern?
  → Yes: Simple moving average or single exponential smoothing
  → No: Continue

Is there a trend?
  → Yes: Holt's method (double exponential smoothing)
  → No: Continue

Is there seasonality?
  → Yes: Holt-Winters method (triple exponential smoothing)
  → No: Continue

Are patterns complex?
  → Yes: ARIMA or machine learning
```

### 3. Forecast Validation

**Backtesting:**
- Test on historical out-of-sample data
- Calculate accuracy metrics (MAPE, MAD, bias)
- Compare multiple methods
- Select best performer

**Monitoring:**
- Track forecast accuracy over time
- Identify systematic errors (bias)
- Update models regularly
- Adjust for known events

### 4. Confidence Intervals

**Why Important:**
- Quantify forecast uncertainty
- Support risk-based decision making
- Enable scenario planning

**Methods:**
- Historical forecast error distribution
- Statistical prediction intervals
- Bootstrap resampling

## Common Pitfalls

### 1. Overfitting

**Problem:** Model fits historical data too closely, poor on new data
**Solution:** Use simpler models, validate on holdout data, avoid too many parameters

### 2. Ignoring Domain Knowledge

**Problem:** Pure statistical forecasts ignore business reality
**Solution:** Incorporate known events, adjust for promotions, involve business experts

### 3. Wrong Aggregation Level

**Problem:** Forecasting at wrong granularity (too detailed or too aggregated)
**Solution:** Start aggregated, drill down selectively, leverage forecast hierarchy

### 4. Static Models

**Problem:** Models not updated as patterns change
**Solution:** Retrain regularly, monitor performance, adapt to shifts

## Resources

- **references/forecasting-methods-comparison.md**: Detailed comparison of methods
- **references/seasonality-detection-guide.md**: How to identify seasonal patterns
- **assets/forecast-accuracy-calculator.xlsx**: Calculate MAPE, MAD, bias
- **examples/demand-forecast-examples.md**: Complete forecasting workflows
```

### Pattern 2: Scoring Methodology Skill

```markdown
---
name: pipeline-health-scoring
description: Methodology for assessing sales pipeline quality using coverage ratios, stage distribution analysis, velocity metrics, and deal health scores. Includes benchmark targets, red flag identification, and coaching recommendations. Use when analyzing pipeline health, identifying at-risk deals, coaching sales reps, or optimizing sales processes.
---

# Pipeline Health Scoring

Systematic framework for evaluating sales pipeline quality beyond simple revenue totals, focusing on conversion likelihood, velocity, and risk factors.

## When to Use This Skill

- Conducting pipeline reviews for QBRs or forecast calls
- Identifying deals requiring sales management intervention
- Coaching sales reps on deal qualification
- Optimizing pipeline coverage for quota attainment
- Forecasting revenue with confidence intervals
- Comparing pipeline health across teams or regions
- Setting pipeline generation targets
- Diagnosing sales process bottlenecks

## Core Methodology

### 1. Coverage Ratio Analysis

**Definition:**
```
Coverage Ratio = Total Pipeline Value / Quota (or Target)
```

**Benchmarks:**
- **Healthy:** 3-4x for new business, 2-3x for renewals
- **At Risk:** < 2x coverage
- **Oversaturated:** > 5x (may indicate poor qualification)

**Segmentation:**
- By sales stage (early, mid, late pipeline)
- By time period (in-quarter vs. future quarters)
- By rep, team, region, or product line

**Red Flags:**
- Coverage dropping below threshold mid-quarter
- Uneven coverage across reps (some < 2x, others > 6x)
- Coverage concentrated in early stages

### 2. Stage Distribution Health

**Ideal Distribution:**
- **Early Stage** (Discovery/Qualification): 40-50%
- **Mid Stage** (Proposal/Negotiation): 30-40%
- **Late Stage** (Closed-Won Ready): 10-20%

**Analysis:**
```
Stage Distribution = (Value in Stage / Total Pipeline) * 100%
```

**Red Flags:**
- **Too much in early stages:** Velocity problem, poor conversion
- **Too much in late stages:** Deals stalling, pricing issues
- **Uneven distribution:** Process inconsistency
- **Missing middle stages:** Qualification or discovery issues

### 3. Velocity Scoring

**Deal Velocity:**
```
Velocity = Average Days in Stage / Benchmark Days
```

**Scoring:**
- **1.0** = On pace with benchmark
- **> 1.0** = Slower than normal (red flag)
- **< 1.0** = Faster than normal (good sign)

**Benchmarks by Stage:**
- Discovery: 15-30 days
- Qualification: 10-20 days
- Proposal: 20-40 days
- Negotiation: 15-30 days

**Red Flags:**
- Deals 2x benchmark days in any stage
- Deals regressing to earlier stages
- Velocity slowing compared to historical average

### 4. Deal Health Score

**Scoring Components:**
```
Health Score = (Activity Score * 0.3) +
               (Progression Score * 0.3) +
               (Engagement Score * 0.2) +
               (Qualification Score * 0.2)
```

**Activity Score (0-100):**
- Number of touchpoints (emails, calls, meetings)
- Recency of last activity
- Compared to benchmark for stage

**Progression Score (0-100):**
- Time in current stage vs. benchmark
- Forward movement vs. regression
- Deal age vs. average cycle time

**Engagement Score (0-100):**
- Multi-threading (contacts engaged)
- Decision-maker involvement
- Champion identification

**Qualification Score (0-100):**
- BANT/MEDDIC criteria met
- Budget confirmed
- Authority identified
- Timeline aligned

### 5. Conversion Rate Analysis

**Stage-to-Stage Conversion:**
```
Conversion Rate = (Deals Advanced / Deals Entered Stage) * 100%
```

**Benchmarks:**
- Discovery → Qualification: 50-60%
- Qualification → Proposal: 60-70%
- Proposal → Negotiation: 70-80%
- Negotiation → Closed-Won: 60-70%

**Overall Win Rate:**
```
Win Rate = Closed-Won / (Closed-Won + Closed-Lost) * 100%
```

**Red Flags:**
- Conversion rates below benchmarks at any stage
- Declining conversion rates over time
- Wide variance in conversion rates across reps

## Composite Pipeline Health Score

**Formula:**
```
Pipeline Health = (Coverage Score * 0.25) +
                  (Distribution Score * 0.25) +
                  (Velocity Score * 0.25) +
                  (Quality Score * 0.25)
```

**Scoring (0-100 scale):**
- **90-100:** Excellent - Pipeline healthy and well-managed
- **75-89:** Good - Pipeline solid with minor areas for improvement
- **60-74:** Fair - Pipeline adequate but needs attention
- **Below 60:** Poor - Pipeline requires immediate intervention

## Best Practices

### 1. Regular Reviews

**Frequency:**
- Weekly: Rep-level reviews with manager
- Monthly: Team-level reviews with leadership
- Quarterly: Organization-wide pipeline reviews

**Process:**
1. Calculate health scores
2. Identify red flags and at-risk deals
3. Develop action plans
4. Assign ownership and deadlines
5. Track progress and outcomes

### 2. Benchmarking

**Internal Benchmarks:**
- Historical performance by stage
- Top performer metrics
- Win rate trends

**External Benchmarks:**
- Industry standards by segment
- Peer company metrics (if available)
- Sales methodology best practices

### 3. Coaching Applications

**Individual Rep Coaching:**
- Compare rep scores to team average
- Identify specific skill gaps
- Create targeted coaching plans
- Track improvement over time

**Team Coaching:**
- Share best practices from high performers
- Address systemic process issues
- Align on qualification standards
- Improve overall conversion rates

## Resources

- **references/pipeline-benchmarks.md**: Industry-standard benchmarks
- **assets/health-scoring-calculator.xlsx**: Automated calculation templates
- **examples/pipeline-review-reports.md**: Sample review outputs
```

### Pattern 3: Analysis Technique Skill

```markdown
---
name: cohort-retention-analysis
description: Methodology for analyzing customer retention using cohort analysis, retention curves, churn prediction, and lifetime value calculation. Includes segmentation strategies, visualization techniques, and actionable insight generation. Use when analyzing retention trends, predicting churn, calculating LTV, or identifying retention improvement opportunities.
---

# Cohort Retention Analysis

Comprehensive methodology for understanding customer retention patterns, predicting churn, and calculating customer lifetime value through cohort-based analysis.

## When to Use This Skill

- Analyzing customer retention trends over time
- Identifying factors that impact retention
- Calculating customer lifetime value (LTV)
- Predicting churn risk for customer segments
- Evaluating impact of retention initiatives
- Comparing retention across customer segments
- Setting retention targets and goals
- Optimizing customer success strategies

## Core Concepts

### 1. Cohort Definition

**Cohort:** Group of customers who share a common characteristic or start date

**Common Cohort Types:**
- **Acquisition Cohort:** Grouped by signup/purchase month
- **Feature Cohort:** Grouped by product tier or plan
- **Channel Cohort:** Grouped by acquisition channel
- **Segment Cohort:** Grouped by company size, industry, geography

### 2. Retention Metrics

**Retention Rate:**
```
Retention Rate (Month N) = (Customers Active in Month N / Cohort Size) * 100%
```

**Churn Rate:**
```
Churn Rate (Month N) = (Customers Churned in Month N / Customers Active at Start of Month N) * 100%
```

**Survival Rate:**
```
Survival Rate = 1 - Cumulative Churn Rate
```

### 3. Retention Curve Analysis

**Retention Curve Shape:**
- **Initial Drop:** Sharp decline in first 3-6 months (normal)
- **Stabilization:** Curve flattens as retained customers become sticky
- **Long-tail:** Stable retention rate for long-term customers

**Healthy vs. Unhealthy Curves:**
- **Healthy:** Quick stabilization, high long-term retention (>80% at 12 months)
- **Unhealthy:** Continuous decline, low retention at 12 months (<50%)

## Analysis Techniques

### Technique 1: Cohort Retention Table

**Structure:**
```
Cohort   Month 0  Month 1  Month 2  Month 3  ...  Month 12
Jan'24     100%      85%      78%      72%    ...     65%
Feb'24     100%      87%      80%      75%    ...     68%
Mar'24     100%      82%      75%      69%    ...     62%
```

**Insights:**
- Compare cohorts to identify improving/declining trends
- Identify seasonal patterns
- Measure impact of product changes

### Technique 2: Retention Curve Visualization

**Best Practices:**
- Plot all cohorts on same chart
- Use different colors for different segments
- Add benchmarks or targets
- Highlight cohorts with significant changes

**Analysis:**
- Where do cohorts diverge?
- Which cohorts retain better?
- Is retention improving over time?

### Technique 3: Churn Prediction

**Predictive Features:**
- Product usage metrics (logins, feature usage)
- Engagement metrics (support tickets, NPS)
- Account characteristics (size, industry)
- Lifecycle stage (onboarding, maturity)
- Contract characteristics (length, value)

**Models:**
- Logistic regression for interpretability
- Random forest for accuracy
- Survival analysis for time-to-churn

**Output:**
```
Churn Probability Score (0-100)
+ Key drivers of churn risk
+ Recommended interventions
```

### Technique 4: Customer Lifetime Value (LTV)

**Simple LTV:**
```
LTV = (Average Revenue Per Customer * Average Lifespan in Months) - Customer Acquisition Cost
```

**Cohort-Based LTV:**
```
LTV = Σ(Revenue(Month N) * Retention Rate(Month N))
```

**Example:**
```
Monthly revenue = $100
Retention: Month 1 = 85%, Month 2 = 78%, Month 3 = 72%
LTV = $100*0.85 + $100*0.78 + $100*0.72 + ... = $X
```

## Best Practices

### 1. Segmentation Strategy

**Segment by:**
- Acquisition cohort (month/quarter)
- Product tier or plan type
- Customer size (SMB, Mid-Market, Enterprise)
- Industry vertical
- Geographic region
- Acquisition channel

**Benefits:**
- Identify high-value segments
- Tailor retention strategies
- Allocate resources effectively

### 2. Actionable Insights

**Framework:**
1. **Observation:** What does the data show?
2. **Insight:** Why is this happening?
3. **Recommendation:** What should we do?
4. **Expected Impact:** What results do we expect?

**Example:**
```
Observation: Enterprise cohorts retain 20% better than SMB
Insight: Longer onboarding and dedicated CSM drive retention
Recommendation: Expand CSM coverage to Mid-Market segment
Expected Impact: Improve Mid-Market retention from 65% to 75%
```

### 3. Monitoring and Alerting

**Track:**
- Month-over-month retention changes
- Cohort retention vs. benchmarks
- Churn rate trends
- Early warning indicators

**Alert Thresholds:**
- Retention drops > 5% below benchmark
- Churn rate increases > 10% month-over-month
- High-value customer churn events

## Resources

- **references/retention-benchmarks.md**: Industry retention benchmarks
- **assets/cohort-analysis-template.xlsx**: Cohort table calculator
- **examples/retention-analysis-reports.md**: Sample analysis outputs
```

## Token Optimization Techniques

### 1. Front-Load Critical Information

**Frontmatter:**
- Put most important keywords early in description
- List primary use cases before secondary ones
- Mention key methodologies or techniques

**Content:**
- Lead with "When to Use" section
- Quick start before detailed patterns
- Essential concepts before advanced topics

### 2. Use Clear Section Hierarchy

**Structure:**
```markdown
# Skill Title (H1)

## Major Section (H2)

### Subsection (H3)

#### Detail (H4)
```

**Benefits:**
- Easy to scan
- Claude can load sections as needed
- Clear progression from basic to advanced

### 3. Minimize Redundancy

**Avoid:**
- Repeating same concepts in multiple places
- Duplicating examples with slight variations
- Redundant explanations

**Instead:**
- Reference earlier sections: "See Coverage Ratio Analysis above"
- Use single comprehensive example
- Link to external resources for details

### 4. Leverage External Resources

**In SKILL.md:**
- Core methodology and patterns
- Essential examples
- Quick reference

**In Separate Files:**
- Extensive code samples
- Detailed case studies
- Supplementary documentation
- Templates and tools

**Reference Pattern:**
```markdown
## Resources

- **references/detailed-guide.md**: Comprehensive methodology
- **assets/template.xlsx**: Calculation template
- **examples/case-study.md**: Real-world application
```

## Common Pitfalls to Avoid

### 1. Description Over 1024 Characters

**Problem:** Exceeds Anthropic spec limit (CRITICAL FAILURE)
**Impact:** Skill rejected, won't load
**Solution:** Edit ruthlessly, front-load key info, move details to content

**Before (1100 chars - TOO LONG):**
```yaml
description: This comprehensive skill provides detailed methodologies for analyzing sales pipeline health through multiple lenses including coverage ratio analysis which measures pipeline value against quota targets, stage distribution analysis examining the percentage of pipeline in each sales stage, velocity scoring to track how quickly deals progress through stages, deal health scoring combining activity engagement progression and qualification metrics into composite scores, and conversion rate analysis tracking stage-to-stage advancement rates. The skill includes benchmark targets from industry research, red flag identification patterns for early warning signals, coaching recommendations for sales managers to improve rep performance, and integration with CRM systems like Salesforce and HubSpot. Use when conducting pipeline reviews for quarterly business reviews, identifying deals requiring immediate sales management intervention, coaching sales representatives on proper deal qualification standards, optimizing pipeline coverage to ensure quota attainment likelihood, forecasting revenue with statistical confidence intervals, or comparing pipeline health metrics across different teams regions or time periods.
```

**After (495 chars - GOOD):**
```yaml
description: Methodology for assessing sales pipeline quality using coverage ratios, stage distribution analysis, velocity metrics, and deal health scores. Includes benchmark targets, red flag identification, and coaching recommendations. Use when analyzing pipeline health, identifying at-risk deals, coaching sales reps, or optimizing sales processes.
```

### 2. Missing "Use when" Clause

**Problem:** No clear activation criteria
**Impact:** Skill won't activate appropriately
**Solution:** Add specific "Use when..." triggers

**Before:**
```yaml
description: Demand forecasting methodologies for inventory planning.
```

**After:**
```yaml
description: Statistical demand forecasting methodologies including time-series analysis and seasonality detection. Use when forecasting demand, planning inventory, or improving forecast accuracy.
```

### 3. Vague Activation Triggers

**Problem:** Too generic to activate appropriately
**Impact:** Over-activation or under-activation

**Before:**
```yaml
description: Forecasting methods. Use for forecasting.
```

**After:**
```yaml
description: Statistical demand forecasting including time-series analysis, seasonality detection, and ARIMA models. Use when forecasting product demand, planning inventory levels, or building S&OP forecasts.
```

### 4. No Progressive Disclosure

**Problem:** All content at same level, no clear tiers
**Impact:** Token inefficiency, poor user experience

**Solution:** Structure content in tiers:
- Tier 1 (Metadata): Frontmatter only
- Tier 2 (Instructions): Core methodology
- Tier 3 (Resources): Detailed examples and references

### 5. Wrong Directory Name

**Problem:** Directory name doesn't match skill name in frontmatter
**Impact:** Skill won't load (validation failure)

**Example:**
```
Directory: skills/forecasting/          # Wrong
Frontmatter: name: demand-forecasting  # Doesn't match

Should be:
Directory: skills/demand-forecasting/   # Correct
Frontmatter: name: demand-forecasting  # Matches
```

## Validation Checklist

- [ ] File located at `skills/{skill-name}/SKILL.md` (exact case)
- [ ] Directory name matches frontmatter name exactly
- [ ] Name in hyphen-case: `^[a-z0-9]+(-[a-z0-9]+)*$`
- [ ] Description < 1024 characters (COUNT CAREFULLY)
- [ ] "Use when..." activation clause present
- [ ] Description not truncated mid-sentence
- [ ] Progressive disclosure structure (3 tiers)
- [ ] "When to Use This Skill" section with 5-15 scenarios
- [ ] Core concepts section with 3-8 subsections
- [ ] Patterns or techniques with examples
- [ ] Best practices section
- [ ] Common pitfalls section
- [ ] Resources section (if applicable)
- [ ] Business terminology appropriate for domain
- [ ] No placeholder content or TODOs
- [ ] Minimum 100 lines of substantive content

## References

- **Anthropic Specification:** Agent Skills Specification v1.0
- **Official Repository:** github.com/anthropics/skills
- **Source Framework:** wshobson/agents (47 skills across 15 plugins)
- **Skills Catalog:** /agents/docs/agent-skills.md
- **Validation Rules:** validation-rules.md in this plugin
- **Template:** skill-template.md in this plugin
