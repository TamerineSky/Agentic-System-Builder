# Quarterly Business Review Preparation Orchestration

**Purpose:** Comprehensive multi-agent workflow for preparing strategic, value-focused quarterly business reviews that strengthen relationships, demonstrate ROI, and create expansion opportunities.

**Frequency:** Quarterly (4-6 weeks before QBR date)

**Duration:** 2-3 weeks preparation cycle per strategic account

**Participants:** CSM (owner), CS Manager, Account Executive (if expansion), Executive Sponsor (for strategic accounts)

---

## Multi-Agent Workflow

### Week 1: Data Gathering and Analysis

**Day 1-2: Account Health and Performance Review**

**Agent:** `customer-health-scorer` (Sonnet)
**Task:** Comprehensive health assessment
- Calculate current health score across all dimensions
- Analyze quarter-over-quarter health trends
- Identify health improvements and degradations
- Assess risk factors and positive indicators
- Benchmark against segment averages

**Agent:** `customer-segmentation-analyst` (Sonnet)
**Task:** Cohort and peer benchmarking
- Compare account to peer cohort (same industry, size, tenure)
- Identify performance gaps and leadership areas
- Provide context for usage and adoption metrics
- Generate comparative insights ("Top 10% in feature adoption")

**Outputs:**
- Health score report with trends
- Dimension-by-dimension analysis
- Peer benchmark comparison
- Strengths and improvement areas

**Day 3-4: Usage and Adoption Analysis**

**Agent:** `customer-health-scorer` (Sonnet)
**Task:** Product usage deep-dive
- Feature adoption analysis (breadth and depth)
- Power user identification and activity trends
- Department/team engagement breakdown
- Login frequency and session analytics
- Underutilized features and opportunities

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Whitespace and opportunity mapping
- Identify expansion potential (seats, tiers, modules)
- Map untapped departments and use cases
- Calculate expansion ARR opportunity
- Assess expansion propensity and readiness

**Outputs:**
- Usage analytics dashboard
- Adoption gap analysis
- Expansion opportunity brief
- Whitespace map

**Day 5: Business Outcomes and ROI**

**Agent:** `customer-health-scorer` (Sonnet)
**Task:** Value realization documentation
- Collect customer success stories and wins
- Quantify business impact (KPIs improved, efficiency gains)
- Calculate ROI and payback period
- Document qualitative value (testimonials, feedback)
- Gather competitive wins or displacement stories

**Outputs:**
- ROI calculation and documentation
- Success stories and case examples
- Business value summary
- Testimonial quotes

### Week 2: Content Creation and Stakeholder Preparation

**Day 6-8: QBR Presentation Development**

**Agent:** `customer-health-scorer` (Sonnet) + **CSM**
**Task:** Build executive presentation deck
- Slide 1: Executive summary (health, value delivered, priorities)
- Slides 2-3: Success metrics and business outcomes (quantified value)
- Slides 4-5: Usage and adoption trends (benchmarked against peers)
- Slides 6-7: Upcoming roadmap and innovation (aligned to customer goals)
- Slides 8-9: Strategic recommendations (next quarter priorities)
- Slide 10: Action items and mutual commitments

**Design Principles:**
- Visual (charts, graphs, minimal text)
- Quantified (numbers, metrics, ROI)
- Forward-looking (strategic, not just reporting backward)
- Engaging (discussion prompts, not lecture)
- Business language (outcomes, not features)
- Concise (30-40 min max, 10-12 slides)

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Expansion opportunity positioning (if applicable)
- Create expansion one-pager (opportunity, value, investment)
- Develop ROI model for expansion
- Prepare demo/trial plan for new features/modules
- Align expansion to business objectives

**Outputs:**
- QBR presentation deck (draft)
- Expansion opportunity brief
- Supporting data appendix
- Talking points and facilitation guide

**Day 9-10: Stakeholder Engagement and Prep**

**Agent:** `customer-health-scorer` (Sonnet)
**Task:** Stakeholder mapping and engagement plan
- Identify all QBR attendees (confirm stakeholders)
- Map stakeholder roles, priorities, and concerns
- Develop personalized engagement approach
- Create pre-QBR outreach plan

**CSM Actions:**
- Send QBR invitation with agenda (2-3 weeks before)
- Schedule pre-QBR call with champion/sponsor (1 week before)
- Solicit input on priorities and topics
- Confirm executive attendance and availability
- Share draft deck with champion for feedback

**Outputs:**
- QBR attendee list with roles
- Stakeholder map and engagement approach
- Pre-QBR champion call agenda
- Calendar confirmations

### Week 3: Refinement and Rehearsal

**Day 11-12: Content Refinement**

**CSM + CS Manager:**
**Task:** Review and polish QBR materials
- Incorporate champion feedback
- Refine metrics and storytelling
- Practice presentation delivery
- Anticipate questions and objections
- Prepare backup slides (optional deep-dives)

**Manager Review:**
- Validate content accuracy and messaging
- Ensure strategic focus (not tactical weeds)
- Confirm expansion positioning (if applicable)
- Approve final deck

**Outputs:**
- Final QBR presentation deck
- Backup slides and appendix
- Q&A preparation
- Executive brief (one-pager summary)

**Day 13: Pre-QBR Champion Call**

**CSM:**
**Task:** Pre-align with champion/sponsor
- Walk through QBR agenda and content
- Solicit feedback and concerns
- Identify any sensitive topics or landmines
- Confirm attendees and logistics
- Preview expansion opportunity (if applicable)
- Set expectations for outcomes and next steps

**Outputs:**
- Champion alignment and buy-in
- Final adjustments to deck
- Attendee confirmations
- Success criteria agreed

**Day 14: Final Preparation**

**CSM:**
**Task:** QBR logistics and materials
- Send final deck to attendees (24 hours before)
- Prepare physical materials (if in-person)
- Test screen sharing and demos (if virtual)
- Review talking points and facilitation plan
- Confirm room setup or video link
- Brief any co-presenters (AE, Product, Exec)

**Outputs:**
- All logistics confirmed
- Materials distributed
- Technology tested
- Team aligned

---

## QBR Execution (Day of Meeting)

**Opening (5 min):**
- Welcome and introductions
- Agenda overview and objectives
- Engagement prompt (icebreaker or strategic question)

**Success Review (10 min):**
- Recap previous quarter goals and outcomes
- Highlight wins and achievements
- Quantify business value and ROI
- Share success stories

**Usage and Adoption Analysis (8 min):**
- Present usage trends and benchmarks
- Identify adoption strengths and gaps
- Discuss power users and champions
- Explore opportunities for expansion

**Roadmap Preview (8 min):**
- Upcoming features and releases
- Alignment to customer priorities
- Beta or early access opportunities
- Strategic product direction

**Strategic Recommendations (8 min):**
- Next quarter priorities and focus areas
- Quick wins and long-term initiatives
- Resources and support needed
- Expansion opportunities (if applicable)

**Action Items and Commitments (6 min):**
- Mutual action items and owners
- Success metrics and checkpoints
- Next QBR date and format
- Follow-up cadence

**Total: 45 minutes + 15 min Q&A/Discussion**

---

## Post-QBR Follow-Up

**Day 1 After QBR:**

**Agent:** `csm-performance-analyzer` (Haiku)
**Task:** Document and track outcomes
- Capture action items and commitments
- Update CRM/CS platform with QBR notes
- Record expansion opportunities
- Flag any concerns or risks surfaced

**CSM Actions:**
- Send thank-you email with action item recap
- Share QBR recording or materials (if requested)
- Schedule next touchpoint or follow-up
- Update account success plan

**Outputs:**
- QBR summary and action items
- CRM notes and follow-up tasks
- Expansion pipeline updates

**Week 1-2 After QBR:**

**CSM:**
- Execute on committed action items
- Follow up on customer commitments
- Progress expansion opportunity (if identified)
- Monitor health score for improvement

**Outputs:**
- Action items in progress
- Customer engagement maintained
- Expansion pipeline advancing

---

## Success Metrics

**Process Metrics:**
- QBR preparation completed 3+ days before meeting
- Champion pre-aligned (pre-QBR call completed)
- Executive attendance: 80%+ (confirms strategic importance)
- Meeting duration: On-time (45-60 min, not exceeding)

**Outcome Metrics:**
- Customer satisfaction with QBR: NPS 8+ (post-QBR survey)
- Action items completed (customer + vendor): 85%+ execution
- Expansion opportunity identified: 30-40% of QBRs
- Health score improvement post-QBR: +5 points avg (30 days)
- Relationship depth: New stakeholder engaged in 25% of QBRs

---

## Best Practices

1. **Make It Strategic:** Focus on business outcomes, not product features
2. **Quantify Value:** Use metrics, ROI, and tangible results
3. **Engage, Don't Present:** Ask questions, solicit feedback, have dialogue
4. **Be Forward-Looking:** Spend 60% on future, 40% on past review
5. **Prepare Champion:** Pre-align to ensure smooth meeting, no surprises
6. **Action-Oriented:** Leave with clear next steps and commitments
7. **Follow Through:** Execute on commitments to build trust
8. **Iterate:** Ask for feedback, improve QBR format over time

---

## QBR Variations by Account Tier

**Strategic Accounts (>$75K ARR):**
- Frequency: Quarterly
- Format: In-person or exec video call (60 min)
- Preparation: Full 3-week cycle
- Attendees: Executive sponsors, CSM, AE, Product (optional)
- Outcome: Strategic partnership, expansion planning

**Growth Accounts ($25K-75K ARR):**
- Frequency: Quarterly or semi-annual
- Format: Video call (45 min)
- Preparation: 2-week cycle
- Attendees: Stakeholders, CSM
- Outcome: Value reinforcement, moderate expansion

**Core Accounts ($10K-25K ARR):**
- Frequency: Semi-annual or annual
- Format: Video call (30 min) or digital QBR (recorded)
- Preparation: 1-week cycle (scaled template)
- Attendees: Champion, CSM
- Outcome: Retention, small expansion

---

## Tools and Templates

**Presentation Template:** Standard QBR deck (10-12 slides, branded)
**ROI Calculator:** Spreadsheet or tool for value quantification
**Action Item Tracker:** Template for post-QBR follow-up
**Stakeholder Map:** Visual representation of decision-makers and influencers
**Expansion One-Pager:** Brief for upsell/cross-sell opportunities
**QBR Scorecard:** Internal CSM prep checklist (quality assurance)
