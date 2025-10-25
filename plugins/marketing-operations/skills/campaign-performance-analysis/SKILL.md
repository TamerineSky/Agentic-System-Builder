# Campaign Performance Analysis Skill

## Overview
Master comprehensive campaign performance analysis to measure effectiveness, identify optimization opportunities, and improve marketing ROI.

## Skill Objectives
- Analyze campaign performance across all channels and metrics
- Conduct A/B testing and multivariate testing
- Identify top-performing campaigns and optimization opportunities
- Benchmark campaigns against targets and historical performance
- Provide data-driven optimization recommendations

## When to Use This Skill
- Evaluating campaign effectiveness and ROI
- Comparing performance across campaigns, channels, or time periods
- Identifying which campaign elements drive results
- Optimizing ongoing campaigns for better performance
- Planning future campaigns based on historical learnings

## Key Performance Metrics

### Awareness Metrics
- **Impressions**: Number of times ad/content was displayed
- **Reach**: Unique users who saw campaign
- **Frequency**: Average impressions per user
- **Share of Voice**: % of total category impressions
- **Brand Lift**: Increase in brand awareness/consideration

### Engagement Metrics
- **Click-Through Rate (CTR)**: Clicks / Impressions × 100%
- **Engagement Rate**: (Likes + Comments + Shares) / Reach × 100%
- **View-Through Rate**: Video views / Impressions
- **Completion Rate**: % who watched entire video
- **Time on Page**: Average time spent with content
- **Bounce Rate**: % who left without interacting

### Conversion Metrics
- **Conversion Rate**: Conversions / Clicks × 100%
- **Cost Per Click (CPC)**: Total Spend / Clicks
- **Cost Per Lead (CPL)**: Total Spend / Leads
- **Cost Per Acquisition (CPA)**: Total Spend / Customers
- **Lead Quality**: % of leads that become MQLs/SQLs
- **Win Rate**: % of opportunities that close

### ROI Metrics
- **Return on Ad Spend (ROAS)**: Revenue / Ad Spend
- **Return on Investment (ROI)**: (Revenue - Cost) / Cost × 100%
- **Customer Lifetime Value (LTV)**: Total revenue per customer
- **LTV:CAC Ratio**: Customer value / acquisition cost
- **Payback Period**: Time to recover acquisition cost

## Campaign Analysis Framework

### 1. Campaign Setup Analysis
```
Campaign Structure Review:
├── Campaign Objectives
│   ├── Primary goal (awareness, leads, sales, etc.)
│   ├── Target metrics (CTR, CPL, ROAS, etc.)
│   └── Success criteria
├── Targeting & Segmentation
│   ├── Audience definitions
│   ├── Geo-targeting
│   ├── Demographic filters
│   └── Behavioral targeting
├── Budget & Bidding
│   ├── Total budget allocation
│   ├── Daily budget pacing
│   ├── Bid strategy (manual, automated)
│   └── Budget distribution across ad sets
└── Creative Assets
    ├── Ad copy variations
    ├── Visual assets (images, videos)
    ├── Landing pages
    └── Call-to-action (CTA)
```

### 2. Performance Evaluation
```
Campaign Performance Scorecard:
├── Reach & Awareness
│   ├── Impressions: [actual] vs [target]
│   ├── Reach: [actual] vs [target]
│   ├── Frequency: [actual] vs [optimal]
│   └── Assessment: [On target / Below / Above]
├── Engagement
│   ├── CTR: [actual] vs [benchmark]
│   ├── Engagement Rate: [actual] vs [benchmark]
│   ├── Video Completion: [actual] vs [target]
│   └── Assessment: [On target / Below / Above]
├── Conversion
│   ├── Conversion Rate: [actual] vs [target]
│   ├── Leads: [actual] vs [target]
│   ├── CPL: [actual] vs [target]
│   └── Assessment: [On target / Below / Above]
└── ROI
    ├── ROAS: [actual] vs [target]
    ├── Revenue: [actual] vs [target]
    ├── ROI: [actual] vs [target]
    └── Overall: [Success / Needs Optimization / Underperforming]
```

### 3. Segmentation Analysis
```
Performance by Dimension:
├── By Channel
│   ├── Paid Search: [metrics]
│   ├── Social (Meta, LinkedIn): [metrics]
│   ├── Display/Programmatic: [metrics]
│   └── Email: [metrics]
├── By Audience Segment
│   ├── Segment 1: [metrics]
│   ├── Segment 2: [metrics]
│   └── Segment N: [metrics]
├── By Creative Variation
│   ├── Creative A: [metrics]
│   ├── Creative B: [metrics]
│   └── Creative N: [metrics]
├── By Geography
│   ├── Region 1: [metrics]
│   ├── Region 2: [metrics]
│   └── Region N: [metrics]
└── By Device/Platform
    ├── Mobile: [metrics]
    ├── Desktop: [metrics]
    └── Tablet: [metrics]
```

## A/B Testing Methodology

### Test Design
```
1. Define Hypothesis:
   - What: Variable to test (headline, CTA, image, audience)
   - Why: Expected impact on performance
   - Prediction: Directional hypothesis (e.g., "Headline A will increase CTR by 15%")

2. Set Test Parameters:
   - Test duration: Minimum 7-14 days
   - Sample size: Sufficient for statistical significance
   - Traffic split: Usually 50/50 for A/B tests
   - Success metric: Primary KPI (CTR, conversion rate, CPA)

3. Control Variables:
   - Only one variable changes between variants
   - All other factors held constant
   - Random traffic assignment to variants

4. Statistical Significance:
   - Confidence level: Typically 95%
   - P-value threshold: < 0.05
   - Minimum detectable effect: 10-20% improvement
```

### Test Execution
```
1. Launch test variants simultaneously
2. Monitor performance daily
3. Check for:
   - Even traffic distribution
   - Data collection accuracy
   - External factors (seasonality, news events)
4. Let test run to completion (avoid early stopping)
5. Analyze results once sufficient data collected
```

### Test Analysis
```
Result Evaluation:
├── Statistical Significance
│   ├── Sample size per variant: [N]
│   ├── Conversion rate A: [X]% ± [margin of error]
│   ├── Conversion rate B: [Y]% ± [margin of error]
│   ├── P-value: [value]
│   └── Conclusion: [Significant / Not significant]
├── Practical Significance
│   ├── Absolute difference: [X]%
│   ├── Relative lift: [Y]%
│   ├── Revenue impact: $[amount]
│   └── Worth implementing: [Yes/No]
└── Winner Declaration
    ├── Winning variant: [A/B/Inconclusive]
    ├── Reason: [Why it won]
    └── Action: [Implement / Continue testing / Abandon]
```

## Campaign Optimization Process

### Step 1: Performance Diagnosis
```
Identify underperformance:
1. Compare actual vs. target metrics
2. Identify largest gaps
3. Determine stage of breakdown:
   - Low impressions → Targeting or budget issue
   - Low CTR → Creative or messaging issue
   - Low conversion rate → Landing page or offer issue
   - High CPA → Efficiency or targeting issue
```

### Step 2: Root Cause Analysis
```
For each underperforming metric, investigate:

Low CTR:
- Creative fatigue (high frequency, declining CTR over time)
- Poor ad relevance to audience
- Weak headline or visual
- Unclear value proposition
- Strong competition

Low Conversion Rate:
- Landing page misalignment with ad promise
- High friction (long forms, too many fields)
- Slow page load time
- Unclear CTA
- Weak offer or value proposition

High CPA:
- Targeting too broad or wrong audience
- Low-quality traffic
- Inefficient bidding strategy
- Poor ad/landing page alignment
- Budget too small for learning phase
```

### Step 3: Optimization Hypotheses
```
Formulate testable improvements:

Example Hypotheses:
1. "Reducing form fields from 8 to 4 will increase conversion rate by 25%"
2. "Showing product demo video will increase engagement by 40%"
3. "Narrowing audience to decision-makers will improve lead quality by 30%"
4. "Using urgency messaging will increase CTR by 15%"
```

### Step 4: Implementation & Testing
```
1. Prioritize optimizations by:
   - Expected impact (high/medium/low)
   - Effort to implement (easy/medium/hard)
   - Focus on high-impact, easy-to-implement first

2. Implement as A/B tests when possible
3. Change one variable at a time
4. Monitor daily for early warning signs
5. Let tests run to statistical significance
```

### Step 5: Learning Documentation
```
Campaign Learnings Template:
- Test: [What was tested]
- Hypothesis: [What we expected]
- Result: [What actually happened]
- Statistical Significance: [Yes/No, p-value]
- Impact: [% change in metric, $ impact]
- Insight: [Why it worked or didn't work]
- Action: [Implement / Scale / Abandon]
- Apply to: [Other campaigns where this applies]
```

## Common Analysis Patterns

### Campaign Health Check
```
Quick assessment framework:

✅ Healthy Campaign:
- CTR at or above benchmark
- Conversion rate meeting target
- CPA within acceptable range
- ROAS above target
- Positive ROI
- No budget pacing issues

⚠️ Needs Attention:
- CTR declining over time (creative fatigue)
- Conversion rate below target by 10-25%
- CPA 10-25% above target
- Budget under-pacing or over-pacing
- ROI slightly below target

🚨 Critical Issues:
- CTR < 50% of benchmark
- Conversion rate < 50% of target
- CPA > 50% above target
- Negative or very low ROI
- Technical issues (tracking broken)
```

### Comparative Analysis
```
Campaign Comparison Framework:

Same Period Comparison (Campaign A vs. Campaign B):
- Which drove more volume (impressions, clicks, leads)?
- Which was more efficient (CTR, CVR, CPA)?
- Which quality was better (MQL rate, SQL rate, deal size)?
- Which had better ROI?
- Why did one outperform the other?

Time Period Comparison (Q1 vs. Q2):
- How did performance change over time?
- Seasonal factors or market changes?
- What optimizations were implemented?
- Sustained improvements or temporary spikes?

Channel Comparison (Paid Search vs. Social):
- Which channel better for awareness vs. conversion?
- Cost efficiency differences?
- Audience quality differences?
- Optimal channel mix?
```

## Tools & Platforms

### Ad Platform Analytics
- **Google Ads**: Campaign performance, A/B testing, audience insights
- **Meta Ads Manager**: Facebook/Instagram campaign analytics
- **LinkedIn Campaign Manager**: B2B campaign performance
- **Microsoft Advertising**: Bing ads performance

### Analytics Platforms
- **Google Analytics 4**: Campaign tracking, conversion attribution
- **Adobe Analytics**: Advanced segmentation, journey analysis
- **HubSpot**: Campaign ROI, multi-touch attribution

### A/B Testing Tools
- **Optimizely**: Landing page and web testing
- **VWO**: A/B testing, multivariate testing
- **Google Optimize**: Free website testing
- **Unbounce**: Landing page builder with A/B testing

### Reporting & Visualization
- **Google Data Studio**: Campaign dashboards
- **Tableau**: Advanced campaign analytics
- **Looker**: Custom campaign reporting

## Best Practices

1. **Set Clear Goals**: Define success metrics before launch
2. **Benchmark Performance**: Compare to industry standards and historical data
3. **Segment Analysis**: Break down by audience, creative, device, geo
4. **Test Systematically**: Use A/B testing, not gut instinct
5. **Monitor Continuously**: Check performance daily, especially first week
6. **Optimize Iteratively**: Make small, testable improvements
7. **Document Learnings**: Build institutional knowledge
8. **Focus on ROI**: Balance efficiency (CPA) with volume (scale)

## Common Pitfalls

- **Declaring winners too early**: Not reaching statistical significance
- **Changing multiple variables**: Can't isolate what caused improvement
- **Ignoring lead quality**: Focusing only on cost per lead, not lead value
- **Over-optimizing for CTR**: High CTR but low conversion = wasted budget
- **Analysis paralysis**: Endless testing without implementing winners
- **Ignoring seasonality**: Comparing Q4 to Q1 without context

## Success Metrics

- **Performance Improvement**: Optimized campaigns showing measurable lift
- **ROI Increase**: Campaign ROI improving over time
- **Learning Velocity**: Number of tests run and insights generated
- **Scalability**: Ability to scale winning campaigns profitably
- **Repeatability**: Successful patterns applied to new campaigns

Remember: Campaign analysis is not just about reporting what happened—it's about understanding why it happened and what to do next to improve performance.
