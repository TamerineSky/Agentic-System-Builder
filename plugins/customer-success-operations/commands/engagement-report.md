---
description: Customer engagement health report with interaction analysis, disengagement detection, and optimization recommendations
argument-hint: [portfolio/account-id] [period]
version: "1.0.0"
tags: [engagement, activity, relationship]
model: sonnet
---

# Engagement Report Command

Comprehensive engagement analysis with activity tracking and relationship health assessment.

## Context
Engagement predicts retention (highly engaged 95%+ retention vs. disengaged 40% retention) and expansion (45% vs. 2% expansion rate).

## Requirements
$ARGUMENTS

## Instructions

### 1. Define Scope
Analyze engagement for $1 (specific account or portfolio) over $2 period (monthly, quarterly).

### 2. Track Engagement Activities
Count and categorize interactions: CSM touchpoints (calls, meetings, emails sent/received), customer responses (response rate, time-to-respond), business reviews (QBRs completed, attendance, participation quality), training/enablement (sessions attended, certifications), product engagement (logins, feature usage, in-app activity), community participation (forum posts, events attended).

### 3. Calculate Engagement Scores
Score dimensions (0-100): Frequency (activity volume vs. benchmark), Quality (response rates, meeting participation, strategic vs. tactical), Breadth (stakeholder count, multi-department reach, executive involvement), Product (feature adoption, power user activity). Compute overall engagement score: weighted average.

### 4. Identify Engagement Patterns
Classify accounts: Highly engaged (80-100, proactive, multi-threaded), Moderately engaged (60-79, responsive, tactical), Low engaged (40-59, declining, single-threaded), Disengaged (0-39, unresponsive, at-risk).

### 5. Detect Disengagement Signals
Flag warning signs: 3+ unanswered outreach attempts, 2+ canceled meetings without reschedule, Response time degrading (24h → 72h+), QBR declined or no-show, Executive sponsor MIA, Usage decline concurrent with engagement drop.

### 6. Recommend Optimization
By engagement tier: Highly engaged (reduce frequency, focus on expansion/advocacy), Moderately engaged (increase strategic content, executive engagement), Low engaged (re-engagement campaign, value demonstration), Disengaged (escalation, save play, or offboard decision).

## Output Format
- Engagement score summary (overall and by dimension)
- Activity metrics (touchpoints, response rates, meeting participation)
- Stakeholder mapping (breadth, executive involvement)
- Engagement trending (current vs. previous periods)
- Disengagement warnings (red flags identified)
- Engagement pattern classification
- Optimization recommendations (cadence, content, channels)
- Target engagement score and improvement plan

## Success Criteria
- Analysis completed in 15-20 minutes (single account), 1-2 hours (portfolio)
- All engagement dimensions scored with evidence
- Disengagement signals clearly flagged
- Stakeholder breadth assessed
- Specific optimization actions provided
- Target engagement levels defined
