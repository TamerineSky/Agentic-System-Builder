# A/B Testing Methodology Skill

## Overview
Master rigorous A/B testing methodology to make data-driven marketing decisions and continuously improve campaign performance.

## Skill Objectives
- Design statistically valid A/B tests
- Calculate required sample sizes and test durations
- Analyze test results for statistical significance
- Avoid common testing pitfalls and biases
- Build systematic testing programs

## When to Use This Skill
- Testing marketing hypotheses (creative, messaging, offers)
- Optimizing landing pages and conversion paths
- Improving email performance
- Validating major changes before full rollout
- Building data-driven marketing culture

## A/B Testing Fundamentals

### Test Design Framework
```
1. Hypothesis Formation:
   - Observation: "Our landing page has 15% conversion rate"
   - Hypothesis: "Changing headline to focus on ROI will increase CVR to 18%"
   - Prediction: "Version B will outperform Version A by 20%"

2. Variable Selection:
   - Test ONE variable at a time (headline, CTA, image, etc.)
   - Control all other variables
   - Clear before/after comparison

3. Success Metrics:
   - Primary metric: Conversion rate (most important)
   - Secondary metrics: Click rate, engagement, bounce rate
   - Guardrail metrics: Don't harm (page load time, brand perception)

4. Test Parameters:
   - Traffic split: 50/50 (or 90/10 for cautious rollouts)
   - Test duration: Minimum 1-2 weeks (cover full week cycle)
   - Sample size: Calculated based on statistical power
   - Confidence level: 95% (industry standard)
```

### Statistical Significance Basics
```
Key Concepts:

Null Hypothesis (H0): No difference between A and B
Alternative Hypothesis (H1): B is different from A

P-Value:
- Probability that observed difference occurred by chance
- p < 0.05 → Statistically significant (reject null hypothesis)
- p ≥ 0.05 → Not significant (cannot reject null hypothesis)

Confidence Level:
- 95% confidence = 5% chance result is due to chance
- Higher confidence (99%) requires larger sample size

Statistical Power:
- Probability of detecting a real difference if it exists
- Standard: 80% power
- Higher power requires larger sample size

Type I Error (False Positive):
- Declaring winner when there's no real difference
- Controlled by confidence level (5% at 95% confidence)

Type II Error (False Negative):
- Missing a real difference
- Controlled by statistical power
```

## Sample Size Calculation

### Formula for Proportions (Conversion Rate)
```
Required Sample Size Per Variation:

n = (Z_α/2 + Z_β)² × (p1(1-p1) + p2(1-p2)) / (p1 - p2)²

Where:
- Z_α/2 = 1.96 (for 95% confidence)
- Z_β = 0.84 (for 80% power)
- p1 = baseline conversion rate
- p2 = expected improved conversion rate
- (p1 - p2) = minimum detectable effect

Example:
Baseline CVR: 10%
Target CVR: 12% (20% relative improvement)
Confidence: 95%
Power: 80%

n = (1.96 + 0.84)² × (0.10×0.90 + 0.12×0.88) / (0.10 - 0.12)²
n ≈ 3,842 per variation
Total needed: 7,684 visitors

With 1,000 visitors/day: ~8 days test duration
```

### Sample Size Tables (Quick Reference)
```
Baseline CVR: 10%
Minimum Detectable Effect | Sample Size per Variation
5% relative (10% → 10.5%)  | 31,000
10% relative (10% → 11%)   | 7,800
20% relative (10% → 12%)   | 3,840
30% relative (10% → 13%)   | 1,730
50% relative (10% → 15%)   | 640

Key Insight: Detecting small improvements requires massive sample sizes
```

## Test Execution Best Practices

### Test Setup
```
Pre-Launch Checklist:
□ Hypothesis clearly documented
□ Success metrics defined
□ Sample size calculated
□ Test duration estimated
□ Both variations created and QA'd
□ Tracking/analytics verified working
□ Random traffic assignment confirmed
□ Stakeholders informed of test

Common Tools:
- Google Optimize (free A/B testing)
- Optimizely (enterprise platform)
- VWO (Visual Website Optimizer)
- Unbounce (landing page testing)
- Native ad platform testing (Google Ads, Meta)
```

### Running the Test
```
During Test:
□ Monitor daily for tracking issues
□ Check for even traffic split (should be ~50/50)
□ Don't peek at results and stop early!
□ Let test run to completion (planned sample size)
□ Watch for external factors (news, seasonality, outages)

Red Flags:
- Traffic split not 50/50 (check randomization)
- Conversion rate anomalies (tracking broken?)
- Sudden traffic spike or drop (investigate cause)
- Major external event affecting all variants
```

### Result Analysis
```
Statistical Significance Testing:

1. Calculate conversion rates:
   - Variation A: 100 conversions / 1,000 visitors = 10% CVR
   - Variation B: 130 conversions / 1,000 visitors = 13% CVR

2. Calculate statistical significance:
   - Use chi-square test or Z-test for proportions
   - Calculate p-value
   - If p < 0.05 → Significant
   - If p ≥ 0.05 → Not significant

3. Calculate confidence intervals:
   - Variation A: 10% ± 1.8% (95% CI)
   - Variation B: 13% ± 2.0% (95% CI)
   - If CIs don't overlap → likely significant

4. Check practical significance:
   - Is 3% absolute (30% relative) lift meaningful?
   - What's the revenue impact?
   - Is it worth implementing?

Winner Declaration:
□ Statistical significance achieved (p < 0.05)
□ Practical significance (meaningful business impact)
□ No anomalies or data quality issues
□ Confidence intervals don't overlap (additional check)
```

## Common Testing Scenarios

### Landing Page Tests
```
High-Impact Elements to Test:

1. Headline:
   - Feature-focused vs. benefit-focused
   - Question vs. statement
   - Length (short vs. long)

2. Call-to-Action:
   - Button text ("Sign Up" vs. "Start Free Trial")
   - Button color (contrast vs. brand color)
   - Button size and placement

3. Hero Image/Video:
   - Product screenshot vs. lifestyle image
   - Video vs. static image
   - People vs. no people

4. Social Proof:
   - Customer logos vs. testimonials
   - Number placement (above vs. below fold)
   - Format (text vs. badges)

5. Form Fields:
   - Number of fields (3 vs. 5 vs. 7)
   - Field labels (top vs. inline)
   - Required vs. optional fields

Test Priority: CTA > Headline > Form > Image
```

### Email Tests
```
Common Email A/B Tests:

Subject Line:
- Length (short vs. long)
- Emoji vs. no emoji
- Personalization (first name) vs. generic
- Question vs. statement
- Urgency/scarcity vs. value-focused

Preview Text:
- Complementary vs. repetitive of subject
- Length variations

From Name:
- Company name vs. person name
- CEO vs. team member

Send Time:
- Morning vs. afternoon vs. evening
- Tuesday vs. Thursday (traditionally high)
- Business hours vs. personal time

Content:
- Text-only vs. HTML
- Short vs. long copy
- Single CTA vs. multiple CTAs
- Image-heavy vs. text-heavy

Sample Size Note: Email tests often have large samples
(thousands to millions), making significance easier to achieve
```

### Ad Creative Tests
```
Ad Testing Variables:

Headline:
- Feature vs. benefit
- Question vs. statement
- Specific number vs. general claim

Image:
- Product shot vs. lifestyle
- People vs. no people
- Bright vs. dark

Ad Copy:
- Long vs. short
- Feature-list vs. story
- Social proof vs. straight sell

CTA:
- "Learn More" vs. "Get Started" vs. "Try Free"
- Generic vs. specific

Audience:
- Broad vs. narrow targeting
- Lookalike audiences
- Interest-based vs. behavior-based

Test in Platform:
- Google Ads: Campaign experiments
- Meta Ads: A/B test tool
- LinkedIn: Campaign splitting
```

## Advanced Testing Concepts

### Multivariate Testing (MVT)
```
Test Multiple Variables Simultaneously:

Example: Test headline (2 options) × image (2 options) × CTA (2 options)
= 2 × 2 × 2 = 8 combinations

Combinations:
1. Headline A + Image A + CTA A
2. Headline A + Image A + CTA B
3. Headline A + Image B + CTA A
... (8 total)

Pros:
- Test interactions between elements
- Find optimal combination faster

Cons:
- Requires 8x sample size of A/B test
- Complex analysis
- Hard to isolate individual element impact

When to Use:
- High traffic volume (>100K visitors/month)
- Multiple elements to optimize
- Sufficient testing sophistication
```

### Sequential Testing
```
Test Series Approach:

Week 1-2: Test headline (find winner)
Week 3-4: Test CTA with winning headline
Week 5-6: Test image with winning headline + CTA
Week 7-8: Test form with all winning elements

Pros:
- Builds on learnings
- Simpler analysis
- Works with lower traffic

Cons:
- Takes longer (serial, not parallel)
- Doesn't test element interactions
- Assumes elements independent
```

### Bayesian Testing
```
Alternative to Frequentist (Traditional) A/B Testing:

Frequentist:
- Fixed sample size
- P-value significance threshold
- Yes/no answer (significant or not)

Bayesian:
- Continuous probability assessment
- Can stop early if high confidence
- Probabilistic answer ("95% chance B is better")

When to Use Bayesian:
- Low traffic sites (can stop earlier)
- Need flexibility on duration
- Want probabilistic interpretation

Tools: VWO, Optimizely (both offer Bayesian option)
```

## Common Pitfalls & How to Avoid

### Peeking Problem
```
Mistake: Checking results daily and stopping when significant

Why It's Bad:
- Early in test, randomness can show false positive
- "Peeking" multiple times increases false positive rate
- Ruins statistical validity

Solution:
- Calculate sample size upfront
- Run test to completion
- Use sequential testing methods if must monitor (Bayesian or proper alpha spending)
```

### Too Many Variants
```
Mistake: Testing A vs B vs C vs D vs E

Why It's Bad:
- Splits traffic too thin (takes forever to reach significance)
- Multiple comparison problem (increased false positives)

Solution:
- Limit to 2-3 variants maximum
- Use multivariate testing framework if testing many combinations
- Consider sequential testing (test B vs A, then winner vs C)
```

### Testing Too Small Changes
```
Mistake: Testing button color when CVR is 2%

Why It's Bad:
- Minor changes require huge sample sizes to detect
- Unlikely to have business impact even if significant

Solution:
- Prioritize high-impact changes (headline, offer, page layout)
- Test big, bold differences first
- Use minimum detectable effect calculator (need 20%+ lift for reasonable sample size)
```

### Ignoring Seasonality
```
Mistake: Running test during Black Friday vs. normal period

Why It's Bad:
- Different user behavior skews results
- Can't generalize to normal conditions

Solution:
- Test across full week (Mon-Sun)
- Avoid major holidays or events
- If must test during event, note limited generalizability
```

## Building a Testing Program

### Testing Roadmap
```
Month 1: Foundation
- Audit current conversion funnel
- Identify biggest drop-off points
- Set up testing tools
- Train team on methodology

Month 2-3: Quick Wins
- Test high-impact, easy changes
- Landing page headline/CTA tests
- Email subject line tests
- Build testing muscle

Month 4-6: Systematic Testing
- Develop hypothesis backlog
- Prioritize by impact × effort
- Run 2-4 tests per month
- Document all learnings

Month 7-12: Optimization
- Test refinements based on learnings
- Multivariate tests (if traffic supports)
- Segment-specific testing
- Share learnings across org
```

### Learning Documentation
```
Test Results Template:

Test Name: [Descriptive name]
Hypothesis: [What we expected]
Variations: [A vs B description]
Duration: [Start - end dates]
Sample Size: [Visitors per variation]
Results:
- Variation A: X% CVR
- Variation B: Y% CVR
- Lift: Z% (relative)
- P-value: [value]
- Conclusion: [Significant/Not significant]
Insight: [Why did it win/lose?]
Action: [Implement/abandon/retest]
Apply to: [Other areas where this learning applies]
```

## Tools & Resources

**Testing Platforms:**
- Google Optimize (free)
- Optimizely (enterprise)
- VWO (mid-market)
- Unbounce (landing pages)

**Sample Size Calculators:**
- Optimizely Sample Size Calculator
- Evan Miller's A/B Test Calculator
- VWO A/B Test Duration Calculator

**Significance Calculators:**
- Optimizely's Stat Engine
- AB Test Guide Calculator
- Neil Patel's Significance Calculator

## Success Metrics

- **Tests Run**: Number of tests completed per quarter
- **Win Rate**: % of tests with statistically significant winner
- **Conversion Lift**: Cumulative improvement from winning tests
- **Revenue Impact**: $ attributed to testing program
- **Testing Velocity**: Time from hypothesis to implementation

Remember: Not all tests will have winners. "No difference" is a valid and valuable result. It tells you that change doesn't matter, so focus efforts elsewhere. The goal is learning, not just winning.
