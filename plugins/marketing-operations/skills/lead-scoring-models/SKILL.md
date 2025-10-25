# Lead Scoring Models Skill

## Overview
Master lead scoring model development, implementation, and optimization to identify high-quality leads and improve sales efficiency.

## Skill Objectives
- Design effective lead scoring models (rule-based, predictive, hybrid)
- Calibrate scoring thresholds for MQL and SQL qualification
- Build predictive models using machine learning
- Validate and optimize scoring accuracy
- Integrate scoring with sales processes

## When to Use This Skill
- Designing or refining lead scoring criteria
- Identifying which leads sales should prioritize
- Improving MQL to SQL conversion rates
- Building predictive conversion models
- Optimizing lead routing and qualification

## Lead Scoring Model Types

### 1. Rule-Based Demographic Scoring
```
Explicit Data Scoring (40 points max):

Job Title/Role (0-15 points):
- C-Level (CEO, CTO, CFO): 15
- VP/SVP: 12
- Director: 10
- Manager: 7
- Individual Contributor: 3

Company Size (0-15 points):
- Enterprise (1000+ employees): 15
- Mid-Market (100-999): 10
- Small Business (10-99): 5
- Micro (<10): 2

Industry (0-10 points):
- Target Industry A: 10
- Adjacent Industry B: 6
- Other Industries: 0
```

### 2. Rule-Based Behavioral Scoring
```
Implicit Data Scoring (60 points max):

Website Engagement (0-25 points):
- Pricing Page Visit: 15
- Product Demo Page: 12
- Features Page: 8
- Case Studies: 7
- Multiple Blog Visits (3+): 5

Content Engagement (0-20 points):
- Whitepaper Download: 12
- Webinar Registration: 10
- Webinar Attendance: 15
- Ebook Download: 8
- Newsletter Signup: 4

High-Intent Actions (0-15 points):
- Contact Sales Form: 15
- Free Trial Signup: 15
- Demo Request: 15
- Live Chat Initiated: 10
```

### 3. Predictive Lead Scoring
```
Machine Learning Approach:

Training Data:
- Historical leads with known outcomes (converted/not converted)
- Features: Demographics, firmographics, behavioral signals
- Time window: Last 12-24 months of data

Features (Example):
- Demographic: Job title, seniority, function
- Firmographic: Company size, industry, revenue, tech stack
- Behavioral: Page views, content downloads, email clicks
- Engagement: Email open rate, visit frequency, recency
- Source: Lead source channel (organic, paid, referral)

Model Selection:
- Logistic Regression: Simple, interpretable, fast
- Random Forest: Handles non-linear relationships, feature importance
- Gradient Boosting (XGBoost): High accuracy, captures complex patterns
- Neural Networks: Maximum flexibility, requires large dataset

Output:
- Probability score 0-100: Likelihood of conversion
- Score tier: A (80-100), B (60-79), C (40-59), D (0-39)
- Recommended action: Immediate sales contact, nurture, disqualify
```

### 4. Negative Scoring (Disqualifiers)
```
Score Deductions:

Email Domain (-10 to -20):
- Free email (@gmail, @yahoo): -10
- Competitor domain: -20
- Academic/EDU: -15

Role/Title (-5 to -15):
- Student: -15
- Job seeker: -10
- Consultant (if B2C product): -10

Engagement (-5 to -15):
- Unsubscribed from email: -10
- Bounced email: -15
- Marked as spam: -20

Data Quality (-5 to -10):
- Incomplete profile: -5
- Invalid/fake data: -10
```

## Lead Scoring Development Process

### Step 1: Define Ideal Customer Profile (ICP)
```
1. Analyze best customers:
   - Pull list of customers with highest LTV
   - Pull list of fastest-closing deals
   - Pull list of most successful implementations

2. Identify common attributes:
   - Company size: What size companies buy most?
   - Industry: Which industries are best fit?
   - Role: What job titles buy?
   - Geography: Where are best customers located?
   - Tech stack: What technologies do they use?

3. Document ICP criteria:
   - Must-haves: Required attributes (e.g., company size >50)
   - Nice-to-haves: Preferred attributes (e.g., target industry)
   - Disqualifiers: Attributes that predict failure (e.g., students)
```

### Step 2: Identify Behavioral Signals
```
1. Analyze conversion paths:
   - What actions do converters take before purchase?
   - Which content do they consume?
   - What's their engagement pattern?

2. Map high-intent actions:
   - Pricing page views
   - Demo requests
   - Free trial signups
   - Contact sales forms
   - Product comparison pages

3. Identify engagement patterns:
   - Email engagement (opens, clicks)
   - Website visit frequency
   - Content download types
   - Event/webinar attendance

4. Determine timing signals:
   - Recency: How recent was last engagement?
   - Frequency: How often do they engage?
   - Velocity: Are engagements accelerating?
```

### Step 3: Assign Point Values
```
Scoring Weight Assignment:

1. Start with equal weights:
   - Demographic: 40 points
   - Behavioral: 60 points

2. Assign points within categories based on predictive strength:
   - Analyze historical data: Which attributes correlate with conversion?
   - Sales input: What signals matter to sales team?
   - Test and iterate: Start conservative, adjust based on results

3. Example point allocation logic:
   - High predictive power + high frequency = high points
   - High predictive power + low frequency = medium points
   - Low predictive power = low points or exclude
```

### Step 4: Set Qualification Thresholds
```
Threshold Setting:

1. Analyze score distribution:
   - Plot histogram of all lead scores
   - Identify natural clustering or gaps

2. Calculate conversion rates by score tier:
   Score 0-20: 2% convert to customer
   Score 21-40: 5% convert
   Score 41-60: 12% convert
   Score 61-80: 25% convert
   Score 81-100: 45% convert

3. Set thresholds based on:
   - Sales capacity: Can sales handle all leads above threshold?
   - Conversion lift: Is there meaningful difference above/below threshold?
   - Historical MQL threshold: What worked before?

4. Common thresholds:
   - MQL: 60+ points (marketing qualified)
   - HQL: 80+ points (high quality, urgent)
   - MEL: 40-59 points (marketing engaged, nurture)
   - Cold: 0-39 points (unqualified or dormant)
```

### Step 5: Validate & Calibrate
```
Model Validation:

1. Backtest on historical data:
   - Apply scoring model to past 6-12 months of leads
   - Compare scores to actual outcomes (converted or not)
   - Calculate precision and recall:
     - Precision: % of high-scoring leads that converted
     - Recall: % of converters that scored high

2. A/B test if possible:
   - Control group: Old scoring model
   - Test group: New scoring model
   - Compare MQL to SQL conversion rate
   - Compare SQL to opportunity rate

3. Gather sales feedback:
   - MQL acceptance rate (sales agrees lead is qualified)
   - Rejection reasons (wrong title, wrong company size, etc.)
   - Quality assessment surveys

4. Calibrate scores:
   - If too many false positives: Increase threshold or adjust weights
   - If too many false negatives: Decrease threshold or adjust weights
   - If specific criteria over/under-predicting: Adjust point values
```

## Predictive Lead Scoring Implementation

### Data Preparation
```python
# Example feature engineering for predictive model

import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier

# 1. Load historical leads with outcomes
leads = pd.read_csv('historical_leads.csv')

# 2. Feature engineering
leads['days_since_first_touch'] = (pd.to_datetime('today') - pd.to_datetime(leads['created_date'])).dt.days
leads['email_engagement_rate'] = leads['email_opens'] / leads['emails_sent']
leads['pages_per_visit'] = leads['total_pageviews'] / leads['total_visits']
leads['has_high_intent_action'] = (leads['pricing_views'] > 0) | (leads['demo_requests'] > 0)

# 3. Encode categorical variables
leads = pd.get_dummies(leads, columns=['industry', 'company_size', 'job_function'])

# 4. Select features
features = ['days_since_first_touch', 'email_engagement_rate', 'pages_per_visit',
            'has_high_intent_action', 'total_visits', 'content_downloads', ...industry dummies...]

X = leads[features]
y = leads['converted']  # 1 if converted to customer, 0 if not

# 5. Train/test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 6. Train model
model = RandomForestClassifier(n_estimators=100, random_state=42)
model.fit(X_train, y_train)

# 7. Generate predictions (probability scores 0-1)
leads['conversion_probability'] = model.predict_proba(X)[:, 1]
leads['lead_score'] = (leads['conversion_probability'] * 100).round()

# 8. Evaluate model
from sklearn.metrics import roc_auc_score, precision_recall_curve
auc = roc_auc_score(y_test, model.predict_proba(X_test)[:, 1])
print(f"Model AUC: {auc:.3f}")
```

### Model Maintenance
```
Ongoing Calibration:

1. Monthly monitoring:
   - Track MQL to SQL conversion rate
   - Monitor score distribution changes
   - Review sales feedback on lead quality

2. Quarterly retraining (for predictive models):
   - Retrain model on last 12 months of data
   - Compare new model accuracy to old model
   - Deploy new model if meaningfully better

3. Annual comprehensive review:
   - Re-validate ICP criteria
   - Analyze market changes affecting scoring
   - Consider new data sources or features
   - Rebuild scoring model from scratch if needed
```

## Integration with Sales Process

### Lead Routing
```
Automated Lead Assignment:

Score 80-100 (HQL):
→ Immediate assignment to sales rep
→ SLA: Contact within 1 hour
→ Priority in queue

Score 60-79 (MQL):
→ Assigned to sales development rep (SDR)
→ SLA: Contact within 4 hours
→ Qualification call scheduled

Score 40-59 (MEL):
→ Route to marketing nurture campaign
→ Lead scoring alerts on score increase
→ Periodic re-evaluation (monthly)

Score 0-39 (Cold):
→ Light-touch nurture (monthly newsletter)
→ Monitor for re-engagement
→ Consider retirement after 6-12 months dormant
```

### Sales Enablement
```
Lead Intelligence for Sales:

Lead Score Card:
├── Overall Score: 85/100 (HQL)
├── Score Breakdown:
│   ├── Fit Score: 38/40 (Excellent fit)
│   └── Engagement Score: 47/60 (High intent)
├── Top Scoring Factors:
│   ├── VP-level title (+12)
│   ├── Enterprise company (+15)
│   ├── Requested demo (+15)
│   ├── Visited pricing 3x (+15)
├── Recent Activity:
│   ├── Downloaded whitepaper (2 days ago)
│   ├── Attended webinar (5 days ago)
│   ├── Viewed pricing page (7 days ago)
└── Recommended Talking Points:
    ├── Follow up on demo request
    ├── Reference webinar content
    └── Discuss enterprise pricing
```

## Best Practices

1. **Start Simple**: Begin with rule-based scoring before jumping to ML
2. **Sales Collaboration**: Involve sales in defining criteria and thresholds
3. **Continuous Calibration**: Review and adjust quarterly at minimum
4. **Balance Fit and Intent**: Weight both who they are and what they do
5. **Time Decay**: Reduce points for old activity (engagement recency matters)
6. **Negative Scoring**: Use disqualifiers to filter out poor fits
7. **Transparent Scoring**: Sales should understand how scores are calculated
8. **Test Before Scaling**: Pilot new scoring models before full deployment

## Common Pitfalls

- **Over-weighting demographics**: Ignoring behavioral intent signals
- **Static models**: Not updating as buyer behavior changes
- **Too many points**: Score inflation makes it meaningless
- **No validation**: Never checking if high scorers actually convert
- **Ignoring sales feedback**: Scores say MQL, sales says unqualified
- **One-size-fits-all**: Same scoring for different products or segments

## Success Metrics

- **MQL to SQL Conversion**: Should increase with better scoring
- **SQL Acceptance Rate**: Sales accepting >80% of MQLs as qualified
- **Lead Response Time**: High scores get faster response
- **Win Rate by Score**: Higher scores correlate with higher win rates
- **Sales Productivity**: Reps spending time on high-probability leads

Remember: Lead scoring is not about perfection—it's about helping sales focus their limited time on the leads most likely to buy, while marketing continues to nurture those who aren't ready yet.
