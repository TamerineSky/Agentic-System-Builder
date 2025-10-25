# Lead Handoff Process Orchestration

## Overview
Automated workflow for qualifying, scoring, routing, and handing off leads from marketing to sales.

## Workflow Stages

### Stage 1: Lead Capture & Enrichment
**Agent**: lead-scoring-engine  
**Tasks**:
- Capture lead from form submission, content download, or event
- Enrich with demographic and firmographic data
- Validate data quality (email, company info)
- Initial categorization (persona, industry, company size)

**Inputs**: Lead form data, enrichment services (Clearbit, ZoomInfo)  
**Outputs**: Enriched lead record

---

### Stage 2: Lead Scoring
**Agent**: lead-scoring-engine  
**Tasks**:
- Calculate demographic/firmographic score (fit)
- Calculate behavioral score (intent)
- Apply negative scoring (disqualifiers)
- Assign total lead score (0-100)
- Classify lead tier (Cold, MEL, MQL, HQL)

**Inputs**: Lead data, behavioral history  
**Outputs**: Lead score, tier classification

---

### Stage 3: Lead Nurture or Fast-Track
**Decision Point**: Score threshold  

**If score < 60 (not yet MQL)**:
- Route to marketing nurture campaign
- Set up score monitoring (alert on increase)
- Schedule periodic re-evaluation
- **Agent**: content-performance-analyst recommends nurture content

**If score 60-79 (MQL)**:
- Proceed to qualification

**If score 80+ (HQL)**:
- Fast-track to sales (skip SDR, go to AE)
- SLA: Contact within 1 hour

---

### Stage 4: MQL Qualification (Score 60-79)
**Agent**: lead-scoring-engine  
**Tasks**:
- Assign to Sales Development Rep (SDR)
- Provide lead intelligence summary (score factors, recent activity)
- Set SLA for outreach (4 hours)
- Track qualification call outcome

**Inputs**: MQL record, activity history  
**Outputs**: Lead assigned to SDR, intelligence brief

---

### Stage 5: Sales Acceptance/Rejection
**Sales Action**: SDR reviews and accepts or rejects  

**If Rejected**:
- **Agent**: lead-scoring-engine captures rejection reason
- Update scoring model based on feedback
- Route back to nurture or disqualify
- Track rejection patterns for model calibration

**If Accepted**:
- Proceed to Stage 6

---

### Stage 6: SQL Conversion
**Agent**: lead-scoring-engine  
**Tasks**:
- Track SQL qualification (BANT or similar criteria met)
- Monitor opportunity creation
- Measure MQL → SQL conversion time
- Update lead scoring effectiveness metrics

**Inputs**: SDR qualification notes  
**Outputs**: SQL status, opportunity record

---

### Stage 7: Opportunity Handoff to Account Executive
**Agent**: campaign-roi-analyzer  
**Tasks**:
- Attribute opportunity to marketing sources
- Track multi-touch attribution
- Provide AE with campaign influence data
- Monitor opportunity progression

**Inputs**: Opportunity data, attribution data  
**Outputs**: Attributed opportunity, AE intelligence

---

### Stage 8: Performance Tracking & Feedback Loop
**Agents**: lead-scoring-engine + campaign-roi-analyzer  
**Tasks**:
- Track opportunity → closed-won conversion
- Calculate revenue attribution by campaign/channel
- Update lead scoring model based on outcomes
- Provide sales feedback to marketing
- Optimize MQL threshold based on conversion data

**Inputs**: Closed-won data  
**Outputs**: Performance metrics, scoring model updates

## Orchestration Flow

```
Lead Capture
    ↓
[lead-scoring-engine] → Enrichment + Scoring
    ↓
Decision: Score Tier?
    ├─ <60 (Cold/MEL) → Nurture Campaign
    ├─ 60-79 (MQL) → SDR Assignment
    └─ 80+ (HQL) → AE Direct Assignment
         ↓
    SDR Qualification
         ↓
    Decision: Accept/Reject?
    ├─ Reject → [lead-scoring-engine] → Capture feedback → Re-nurture or disqualify
    └─ Accept → SQL Conversion
                     ↓
                Opportunity Creation
                     ↓
            [campaign-roi-analyzer] → Attribution
                     ↓
                AE Handoff
                     ↓
            Closed-Won Tracking
                     ↓
    [lead-scoring-engine] → Model Update
```

## SLAs

| Lead Tier | Assignment Target | First Contact Target | Qualification Target |
|-----------|-------------------|---------------------|---------------------|
| HQL (80+) | Immediate (automated) | 1 hour | 4 hours |
| MQL (60-79) | 15 minutes | 4 hours | 24 hours |
| MEL (40-59) | N/A (nurture) | N/A | Monthly review |

## Quality Metrics

- **MQL Acceptance Rate**: Target >80%
- **MQL to SQL Conversion**: Target >40%
- **SQL to Opportunity**: Target >60%
- **Time to Contact**: Meet SLA >90% of time
- **Lead Scoring Accuracy**: Predicted vs. actual conversion within 15%

## Feedback Loops

### Daily
- Monitor MQL volume and acceptance rate
- Alert on SLA misses

### Weekly
- Review rejection reasons
- Identify scoring model issues
- Optimize lead routing

### Monthly
- Comprehensive lead quality review
- Scoring model calibration
- Sales/marketing alignment meeting

## System Integrations

- **Marketing Automation**: HubSpot, Marketo, Pardot (lead scoring, routing)
- **CRM**: Salesforce (opportunity tracking, sales feedback)
- **Enrichment**: Clearbit, ZoomInfo (data enrichment)
- **Communication**: Slack alerts for HQL leads

## Success Criteria

- MQL acceptance rate >80%
- MQL to SQL conversion >40%
- Average time to contact within SLA
- Lead scoring accuracy improving quarterly
- Sales satisfaction with lead quality trending positive
