---
description: Analyze specific deal risk factors across engagement, competitive, organizational, and timeline dimensions with mitigation strategies
argument-hint: [deal-id]
version: "1.0.0"
tags: [deal-analysis, risk, mitigation]
model: sonnet
---

# Deal Risk Analysis Command

Comprehensive risk assessment for specific opportunity with actionable mitigation plan.

## Context
Early risk identification enables proactive intervention to save at-risk deals before they slip or are lost.

## Requirements
$ARGUMENTS

## Instructions

### 1. Gather Deal Intelligence
For deal $1: Extract all CRM data (stage, value, contacts, activities, notes, history), identify stakeholders, review activity patterns, check for competitive mentions.

### 2. Calculate Multi-Dimensional Risk Score
**Engagement Risk:** Activity levels, response rates, stakeholder breadth, economic buyer access
**Competitive Risk:** Competitor presence, pricing pressure, POC comparisons
**Organizational Risk:** Champion stability, budget status, company changes
**Timeline Risk:** Deal age, stage velocity, close date slips
**Process Risk:** Qualification completeness, legal/security/procurement status

Aggregate to overall score (0-100, higher = more risk)

### 3. Identify Root Causes
Map risk signals to underlying issues (e.g., low activity → lack of urgency or disengagement)

### 4. Develop Mitigation Plan
Prioritized actions with owners, timelines, and success metrics. Include escalation criteria.

## Output Format
- Risk score and category breakdown (engagement, competitive, organizational, timeline, process)
- Top 3 critical risk factors with evidence
- Root cause analysis
- Prioritized 5-7 mitigation actions with owners and deadlines
- Historical pattern comparison (similar deals outcomes)
- Updated win probability and forecast category recommendation

## Success Criteria
- Risk analysis completed within 30 minutes
- All risk dimensions scored with evidence
- Specific, actionable mitigation steps identified
- Rep and manager aligned on priority actions
- Follow-up checkpoints scheduled
