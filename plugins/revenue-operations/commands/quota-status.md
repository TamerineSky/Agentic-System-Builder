---
description: Generate quota attainment status report showing individual, team, and organizational progress with pacing analysis and projections
argument-hint: [period] [level]
version: "1.0.0"
tags: [quota, attainment, performance]
model: haiku
---

# Quota Status Command

Real-time quota attainment reporting with pacing and projections.

## Context
Regular quota tracking enables early intervention for at-risk reps and recognition of top performers.

## Requirements
$ARGUMENTS

## Instructions

### 1. Collect Performance Data
For $1 period at $2 level (rep/team/company): Gather quota targets, actual closed revenue, days elapsed/remaining, historical attainment rates.

### 2. Calculate Core Metrics
- Current attainment % (actual / quota)
- Expected attainment at this point (% through period)
- Ahead/behind pace
- Daily/weekly run rate required to hit quota
- Projected end-of-period attainment

### 3. Performance Distribution
Group by attainment brackets: On Track (90-110%), At Risk (70-90%), Critical (<70%), Exceeding (>110%)

### 4. Generate Action Items
For at-risk: Pipeline gaps, deal acceleration needs, coaching priorities
For on-track: Maintain momentum recommendations
For exceeding: Stretch goals, mentorship opportunities

## Output Format
- Executive dashboard: Overall attainment %, on-track count, at-risk count
- Rep-level scorecard: Attainment, pace, projection, status
- Performance distribution chart
- At-risk list with gap analysis
- Leaderboard (top performers)
- Weekly action plan by performance bracket

## Success Criteria
- Report generated in <15 minutes
- All reps categorized by status
- Projections calculated with assumptions stated
- Action items specific and time-bound
- Trend vs. prior periods shown
