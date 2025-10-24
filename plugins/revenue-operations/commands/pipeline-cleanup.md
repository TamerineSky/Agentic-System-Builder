---
description: Identify pipeline hygiene issues including stale deals, overdue close dates, and qualification gaps with cleanup recommendations
argument-hint: [team-name] [age-threshold]
version: "1.0.0"
tags: [pipeline, hygiene, cleanup]
model: haiku
---

# Pipeline Cleanup Command

Systematic pipeline hygiene assessment identifying deals to disqualify, update, or accelerate.

## Context
Clean, accurate pipeline is essential for forecast reliability and rep productivity focus.

## Requirements
$ARGUMENTS

## Instructions

### 1. Identify Pipeline Hygiene Issues
For $1 team with deals older than $2 threshold: Stale deals (age >90 days), overdue close dates, low activity (no touches in 21+ days), poor qualification (BANT/MEDDIC incomplete), unrealistic amounts or probabilities.

### 2. Categorize Deals
**Close or Disqualify:** Aged >120 days, no activity >30 days, no clear path forward
**Update Required:** Close date overdue, stage/probability misaligned, contact info outdated
**Accelerate:** Good deals moving too slowly, need executive engagement or urgency creation
**Maintain:** Healthy deals, no action needed

### 3. Generate Cleanup Plan
Deal-by-deal recommendations with rationale, estimated time to clean, impact on forecast and pipeline metrics.

### 4. Automation Opportunities
Rules to prevent future hygiene issues (auto-close inactive deals, required fields for stage advancement, close date validations).

## Output Format
- Pipeline hygiene score (0-100)
- Issue summary: Count and value of deals in each category
- Deal-by-deal cleanup list with recommendations
- Aggregate impact: Pipeline value before/after cleanup, forecast changes
- Automation recommendations to prevent recurrence
- Rep-specific cleanup priorities
- Timeline for cleanup completion (typically 2 weeks)

## Success Criteria
- Analysis completed in 1-2 hours
- All hygiene issues identified and categorized
- Cleanup recommendations specific per deal
- Pipeline impact quantified
- Rep buy-in on disqualifications
- Cleanup completed within 2 weeks
- Automated rules implemented to prevent recurrence
- Clean pipeline maintained ongoing (monthly reviews)
