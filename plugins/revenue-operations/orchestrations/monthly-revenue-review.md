# Monthly Revenue Review Orchestration

**Purpose:** Comprehensive end-of-month revenue performance review combining forecast accuracy, pipeline health, quota attainment, and forward-looking planning.

**Frequency:** Monthly (within 3 business days of month end)

**Duration:** 3-4 hours total (2 hours prep, 2 hours review meeting)

**Participants:** VP Sales, Sales Directors, RevOps Lead, Finance Partner

---

## Multi-Agent Workflow

### Phase 1: Data Gathering and Analysis (Automated)

**Agent:** `quota-performance-tracker` (Haiku)
**Task:** Generate month-end quota attainment report
- Pull closed deals for the month
- Calculate attainment by rep, team, region, segment
- Identify top performers and at-risk reps
- Generate performance distribution and trends

**Output:** Quota Attainment Dashboard

**Agent:** `revenue-forecaster` (Sonnet)
**Task:** Analyze forecast accuracy for completed month
- Compare forecast (30/60/90 days out) to actuals
- Calculate MAPE and bias
- Identify largest variance contributors
- Document lessons learned

**Output:** Forecast Accuracy Report

**Agent:** `sales-pipeline-analyst` (Sonnet)
**Task:** Current pipeline health assessment for next month
- Calculate pipeline coverage for upcoming month
- Analyze stage distribution and velocity
- Identify at-risk deals
- Assess pipeline generation trends

**Output:** Pipeline Health Scorecard

### Phase 2: Synthesis and Insights (Hybrid)

**Agent:** `revenue-forecaster` (Sonnet)
**Task:** Generate next month forecast
- Apply ensemble methodologies
- Incorporate month-end pipeline snapshot
- Create conservative/base/upside scenarios
- Identify key assumptions and risks

**Output:** Next Month Revenue Forecast

**Agent:** `deal-risk-analyzer` (Sonnet)
**Task:** Top 20 deals risk assessment
- Score largest opportunities for upcoming month
- Identify mitigation actions needed
- Flag deals requiring executive engagement

**Output:** Deal Risk Register

### Phase 3: Action Planning (Collaborative)

**Facilitator:** RevOps Lead
**Inputs:** All reports from Phase 1 & 2

**Agenda:**
1. **Month Close Review** (30 min)
   - Actual vs. plan variance explanation
   - Top performers recognition
   - At-risk reps discussion and intervention plans

2. **Forecast Accuracy Review** (20 min)
   - MAPE trends and improvement opportunities
   - Methodology refinements needed
   - Rep forecast discipline review

3. **Forward-Looking Forecast** (40 min)
   - Next month forecast presentation (base/conservative/upside)
   - Key assumptions validation
   - Gap-to-goal analysis
   - Pipeline generation requirements

4. **Deal Reviews** (40 min)
   - Top 20 deals risk assessment
   - Executive sponsor assignments
   - Mitigation action assignments

5. **Action Item Review** (20 min)
   - Summary of decisions and commitments
   - Owner and deadline assignment
   - Next review date

**Outputs:**
- Monthly Business Review Deck (for executive/board distribution)
- Action Item Register with owners and deadlines
- Updated forecast submitted to finance
- Deal escalation list for executive engagement

---

## Success Metrics

- Review completed within 3 business days of month close
- All key metrics calculated and validated
- Forecast accuracy improving over time (target: <8% MAPE)
- Action items from prior month 80%+ completed
- Deal interventions initiated within 48 hours
- Executive alignment on forecast and priorities

---

## Automation Opportunities

- Scheduled report generation (all Phase 1 reports auto-run)
- Dashboard refresh automation
- Meeting deck auto-population
- Action item tracking integration (Asana, Jira)
- Email distribution of materials 24 hours pre-meeting
