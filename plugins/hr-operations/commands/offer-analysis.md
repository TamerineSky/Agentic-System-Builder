---
description: Offer acceptance rate analysis with competitiveness assessment
argument-hint: [period]
version: "1.0.0"
tags: [recruiting, offers, acceptance, competitiveness]
tool_access: [Read, Write, Bash]
model: haiku
---

# Offer Acceptance Analysis

Analyze offer acceptance rates, assess competitiveness, and identify factors affecting candidate acceptance decisions.

## Requirements
- **Period**: Analysis timeframe (e.g., "Q1 2024", "last 6 months")
- **Offer Data**: All offers extended with outcomes, compensation, source, timeline

## Instructions

### 1. Acceptance Rate Analysis
- Overall acceptance rate and trend
- By function, level, source
- Benchmark vs. target (85-90%)
- Identify patterns in declines

### 2. Decline Reason Analysis
- Categorize decline reasons (competing offer, compensation, timing, fit)
- Quantify impact of each factor
- Identify preventable vs. unpreventable declines

### 3. Compensation Competitiveness
- Compare offers to market data
- Analyze acceptance rate by offer competitiveness (P25, P50, P75, P90)
- Identify compensation-related declines
- Calculate cost of losing candidates to compensation

### 4. Time-to-Offer Impact
- Correlation between interview-to-offer time and acceptance
- Identify optimal offer timing
- Analyze impact of delays on acceptance

### 5. Improvement Recommendations
- Compensation adjustment recommendations
- Process improvements (faster offers, better candidate experience)
- Negotiation strategies and training
- Expected acceptance rate improvement

## Output Format
- Executive summary with acceptance rate trends
- Decline reason breakdown with examples
- Compensation competitiveness assessment
- Time-to-offer analysis and correlation
- Recommendations with projected impact

## Related Plugins
**Skills**: recruiting-analytics, compensation-benchmarking
**Agents**: recruiting-efficiency-analyst, compensation-analyst
**Commands**: /recruiting-metrics, /compensation-review
