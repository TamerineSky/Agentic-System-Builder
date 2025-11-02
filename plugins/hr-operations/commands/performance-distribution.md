---
description: Performance rating distribution analysis with calibration insights
argument-hint: [cycle] [org]
version: "1.0.0"
tags: [performance, calibration, ratings, distribution]
tool_access: [Read, Write, Bash]
model: sonnet
---

# Performance Distribution Analysis

Analyze performance rating distributions, support calibration sessions, detect bias, and validate rating consistency across the organization.

## Context
Fair and consistent performance ratings are critical for pay differentiation, promotion decisions, and employee trust. Calibration ensures standards are applied uniformly.

## Requirements
- **Cycle**: Performance cycle (e.g., "2024 Annual", "Q3 2024")
- **Organization**: Department or "all" for company-wide
- **Guidelines**: Target distribution (e.g., 10% Exceptional, 30% Exceeds, 50% Meets, 10% Below)
- **Prior Cycle**: Previous cycle data for trend analysis

## Instructions

### 1. Distribution Analysis
Overall company distribution:
- Actual vs. guideline distribution by rating level
- Variance analysis (teams above/below guideline)
- Year-over-year trends (rating inflation/deflation)
- Total employees rated and distribution percentages

### 2. Organizational Breakdown
By department/team:
- Manager-level distribution analysis
- Identify outlier managers (>50% top ratings or <20%)
- Team-by-team comparison tables
- Flag teams requiring calibration discussion

### 3. Demographic Fairness Analysis
Rating distribution by:
- Gender (M/F/Non-binary)
- Race/ethnicity
- Tenure cohorts (0-1yr, 1-3yr, 3-5yr, 5+yr)
- Level (IC vs. Manager vs. Director+)
Statistical tests for significant differences

### 4. Calibration Preparation
For calibration sessions:
- Pre-calibration manager summaries
- Peer comparisons (similar roles across teams)
- Exceptional and Below ratings requiring evidence
- Suggested adjustments to meet guidelines
- Manager rating tendencies (leniency, severity, central)

### 5. Performance-Outcome Correlation
Validate system effectiveness:
- Performance vs. merit increase correlation
- Performance vs. promotion rate correlation
- Performance vs. attrition correlation
- Identify disconnects (poor performers promoted, top performers leaving)

## Output Format
- Executive summary: Overall distribution vs. guidelines
- Org-level distribution table with variance analysis
- Manager outlier report for calibration focus
- Demographic fairness assessment
- Calibration session prep package (manager summaries, peer comparisons)
- Performance-outcome correlation analysis
- Recommended adjustments to meet distribution goals

## Success Criteria
- Distribution analyzed at company, org, and manager levels
- Outliers identified for calibration discussion
- Demographic fairness validated statistically
- Calibration prep materials ready for sessions
- Performance-outcome linkage validated
- Post-calibration follow-up analysis planned

## Related Plugins
**Skills**: performance-management, compensation-benchmarking
**Agents**: performance-analytics-agent, compensation-analyst
**Commands**: /compensation-review, /diversity-report
