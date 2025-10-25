# Weekly At-Risk Account Review Orchestration

**Purpose:** Systematic weekly review process for identifying, prioritizing, and actioning at-risk customer accounts to prevent churn.

**Frequency:** Weekly (every Monday morning)

**Duration:** 90-120 minutes

**Participants:** CS Leadership, CS Managers, CSMs (for their accounts)

---

## Multi-Agent Workflow

### Phase 1: Risk Identification (30 minutes)

**Agent:** `churn-predictor` (Sonnet)
**Task:** Generate weekly at-risk account list
- Apply churn prediction model to entire customer base
- Identify accounts with risk score >60 or velocity declining
- Segment by risk tier (critical, high, medium)
- Flag new entrants to at-risk list (changes from last week)
- Calculate total at-risk ARR and expected churn impact

**Agent:** `customer-health-scorer` (Sonnet)
**Task:** Health score trending analysis
- Identify accounts with health decline >10 points in 7 days
- Flag dimension-specific warnings (usage drops, engagement gaps, sentiment issues)
- Highlight stakeholder changes and organizational signals
- Compare current week vs. prior week at-risk population

**Outputs:**
- At-risk account list (top 25 accounts by risk × ARR)
- New risks identified this week (requires immediate attention)
- Health degradation alerts (declining trends)
- Total portfolio risk summary (ARR at risk, count by tier)

### Phase 2: Root Cause Analysis (20 minutes)

**Agent:** `customer-health-scorer` (Sonnet)
**Task:** Deep-dive into top 10 at-risk accounts
- For each account: Identify primary risk drivers (usage, engagement, sentiment, financial)
- Provide evidence (metrics, events, behavior changes)
- Assess recovery difficulty (easy/moderate/hard save)
- Estimate time-to-churn if no intervention

**Agent:** `csm-performance-analyzer` (Haiku)
**Task:** CSM capacity and coverage analysis
- For each at-risk account: Identify assigned CSM, current workload
- Flag capacity constraints (CSM with >4 red accounts)
- Identify potential portfolio rebalancing needs
- Assess intervention resource requirements

**Outputs:**
- Root cause summary for top 10 accounts
- Risk driver patterns (common themes across at-risk accounts)
- CSM capacity assessment (overload warnings)
- Resource needs for intervention (CSM time, exec involvement, budget)

### Phase 3: Intervention Planning (25 minutes)

**Agent:** `churn-predictor` (Sonnet)
**Task:** Develop account-specific save strategies
- Match risk profile to intervention playbook (critical = exec escalation, high = intensive CSM, medium = proactive plan)
- Assign priority and urgency (immediate 24-48h, urgent 1 week, standard 2-4 weeks)
- Calculate save probability and expected value (ROI analysis)
- Recommend resource allocation (CSM, manager, exec, product team)

**Review Discussion:** (CS Leadership + Managers)
- Review top 10 at-risk accounts and recommended interventions
- Assign ownership and accountability (CSM, manager, exec sponsor)
- Approve resource allocation (save play budget, executive time)
- Set success criteria and checkpoint dates (weekly follow-up)

**Outputs:**
- Intervention plans for top 10 accounts (specific actions, owners, timelines)
- Resource commitments (CSM time, executive escalations, budget approvals)
- Success metrics and checkpoints (health score targets, engagement goals)
- Escalation pathways (when to involve execs, product team)

### Phase 4: Action Assignment and Tracking (15 minutes)

**Agent:** `csm-performance-analyzer` (Haiku)
**Task:** Create CSM action items and tracking
- Generate CSM-specific action lists (accounts, tasks, deadlines)
- Update CRM/CS platform with risk flags and intervention plans
- Schedule follow-up touchpoints (CSM calls, manager check-ins)
- Set up alerts and reminders (trigger-based notifications)

**Review Meeting Close:**
- Confirm all critical accounts have assigned owners
- Verify all immediate actions scheduled (24-48h items)
- Set next week's review agenda (follow-up on this week's actions)
- Document decisions and commitments

**Outputs:**
- CSM action item lists (what, when, who for each at-risk account)
- CRM/CS platform updates (risk flags, health alerts, intervention status)
- Calendar holds (CSM calls, exec escalations, manager check-ins)
- Next week's follow-up agenda

---

## Success Metrics

**Process Metrics:**
- Meeting completed on time (90-120 min max)
- All critical accounts (red tier) reviewed and assigned
- 100% of intervention actions have owners and due dates
- CRM/CS platform updated same day

**Outcome Metrics:**
- 50-60% of at-risk accounts (medium/high risk) prevented from churning
- Average time from risk identification to intervention: <7 days
- Health score improvement for intervened accounts: +15 points avg (60 days)
- Churn rate for at-risk accounts: <35% (vs. 75% without intervention)

---

## Key Handoffs

**Pre-Meeting:** CSMs review their at-risk accounts, prepare context and updates
**During Meeting:** CS Leadership approves resource allocation (budget, executive time)
**Post-Meeting:** CSMs execute intervention plans, managers monitor progress
**Throughout Week:** Daily stand-ups or slack updates on critical account progress
**Following Week:** Review outcomes, celebrate saves, learn from failures

---

## Best Practices

1. **Start on Time:** Respect calendar, move details to offline discussions
2. **Data-Driven:** Use health scores and churn models, not gut feel
3. **Action-Oriented:** Every at-risk account leaves with specific next steps
4. **Ownership:** Clear accountability (named owner for every account/action)
5. **Follow-Through:** Weekly review of prior week's commitments
6. **Learn and Iterate:** Track save play success rates, refine approaches
7. **Celebrate Wins:** Recognize CSMs who successfully recover at-risk accounts
8. **Executive Engagement:** Don't wait until last minute, involve execs early (high-risk accounts)

---

## Meeting Agenda Template

**0:00-0:10 (10 min):** Portfolio risk overview (churn-predictor summary)
**0:10-0:20 (10 min):** New at-risk accounts this week (health degradation alerts)
**0:20-0:40 (20 min):** Prior week follow-up (outcomes, saves, losses, learnings)
**0:40-1:15 (35 min):** Deep-dive on top 10 critical accounts (review + intervention planning)
**1:15-1:25 (10 min):** Resource allocation decisions (budget, executive time)
**1:25-1:30 (5 min):** Action assignment and next steps

**Total: 90 minutes**

---

## Tools and Systems

**Data Sources:**
- Customer health scores (Gainsight, Totango, ChurnZero)
- Churn prediction model outputs (risk scores, probabilities)
- CRM data (renewal dates, ARR, account details)
- Product usage analytics (feature adoption, login frequency)
- Support data (tickets, escalations, CSAT)

**Meeting Tools:**
- Shared dashboard (real-time at-risk account view)
- Collaboration tool (Slack channel for daily updates)
- Task management (Asana, Jira for action tracking)
- Calendar (automated meeting invites, reminders)

---

## Variations by Company Size

**Startup/Small (<100 customers):**
- Frequency: Bi-weekly (every other Monday)
- Duration: 30-45 minutes
- Scope: Review all yellow/red accounts (typically 5-15)

**Mid-Market (100-500 customers):**
- Frequency: Weekly
- Duration: 60-90 minutes
- Scope: Top 20 at-risk accounts by ARR × risk score

**Enterprise (>500 customers):**
- Frequency: Weekly
- Duration: 90-120 minutes
- Scope: Top 25-30 accounts, segment-specific deep-dives
- Additional: Daily 15-min stand-ups for critical accounts
