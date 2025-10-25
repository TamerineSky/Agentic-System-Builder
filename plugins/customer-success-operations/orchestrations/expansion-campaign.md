# Expansion Campaign Orchestration

**Purpose:** Systematic multi-agent workflow for identifying, qualifying, and executing targeted expansion campaigns to drive net revenue retention and customer lifetime value.

**Frequency:** Quarterly or bi-annual campaign cycles

**Duration:** 12-week campaign (2 weeks planning, 8 weeks execution, 2 weeks retrospective)

**Participants:** CS Leadership, CSMs, Sales/AEs, Marketing, Product

---

## Multi-Agent Workflow

### Phase 1: Campaign Planning and Targeting (Weeks 1-2)

**Week 1: Opportunity Identification**

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Portfolio-wide expansion analysis
- Scan entire customer base for expansion potential
- Calculate expansion propensity scores (0-100)
- Conduct whitespace analysis (seats, tiers, products, geographies)
- Quantify total expansion pipeline and potential ARR
- Segment opportunities by type (seat expansion, tier upgrade, cross-sell)

**Agent:** `customer-segmentation-analyst` (Sonnet)
**Task:** Campaign segmentation and targeting
- Define target segments for campaign (e.g., "Healthy Mid-Market with <50% feature adoption")
- Analyze segment characteristics and patterns
- Identify common expansion triggers and signals
- Size opportunity within target segment
- Benchmark expansion rates by segment

**Outputs:**
- Total expansion opportunity inventory ($ARR potential)
- Target segment definition (criteria, size, characteristics)
- Opportunity type breakdown (seats, tiers, cross-sell %)
- Expansion propensity distribution (high/medium/low)

**Week 2: Campaign Design and Resource Allocation**

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Expansion playbook and campaign strategy
- Design campaign flow (sequencing, touchpoints, timing)
- Create expansion playbooks by opportunity type
- Develop value messaging and positioning
- Build ROI calculators and business case templates
- Define success criteria and conversion targets

**CS Leadership:**
**Task:** Resource allocation and goal setting
- Set campaign targets (ARR goal, conversion rate, # of deals)
- Assign CSM and AE responsibilities (who owns what)
- Allocate budget (demos, trials, incentives, tools)
- Define quotas and compensation for expansion
- Establish campaign timeline and milestones

**Outputs:**
- Campaign strategy and playbooks
- Resource allocation (CSM time, AE support, budget)
- Targets and quotas (ARR goal, conversion rate)
- Campaign timeline and milestones
- Roles and responsibilities matrix

### Phase 2: Campaign Execution (Weeks 3-10)

**Weeks 3-4: Qualification and Outreach**

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Opportunity qualification and prioritization
- Apply BANT framework to each opportunity (Budget, Authority, Need, Timing)
- Score and rank opportunities (propensity × ARR potential × readiness)
- Create tiered target list (Tier 1: Close now, Tier 2: Develop, Tier 3: Nurture)
- Assign opportunities to CSMs/AEs based on capacity and fit

**Agent:** `customer-health-scorer` (Sonnet)
**Task:** Pre-campaign health check
- Verify health score >70 for all target accounts
- Flag any at-risk accounts (exclude from campaign or address first)
- Identify stakeholder changes or organizational signals
- Ensure accounts are "expansion-ready" (stable, satisfied)

**CSM Actions (Weeks 3-4):**
- Conduct discovery calls with target accounts
- Identify specific expansion triggers and needs
- Validate whitespace and opportunity sizing
- Confirm stakeholder interest and buying authority
- Schedule demos/workshops for qualified opportunities

**Outputs:**
- Qualified opportunity list (BANT-scored)
- Tier 1 targets (30-40 high-priority accounts)
- Discovery call summaries and notes
- Demo/workshop schedule
- CRM pipeline updates (opportunities created)

**Weeks 5-7: Demonstrations and Value Selling**

**CSM + AE Collaboration:**
**Task:** Execute expansion plays by type

**Seat Expansion Play:**
1. License audit and usage review
2. Department mapping (whitespace identification)
3. Business case: Productivity gain per additional user
4. Volume discount proposal
5. 2-week decision timeline

**Tier Upgrade Play:**
1. Current tier limitations audit
2. Premium feature demo and trial (30 days)
3. ROI calculator: Value of advanced features
4. Proposal aligned with annual planning
5. 30-60 day decision timeline

**Cross-Sell Play:**
1. Use case workshop and discovery
2. Pilot program (60 days)
3. Success metrics and outcomes
4. Expansion proposal post-pilot
5. 60-90 day decision timeline

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Campaign performance monitoring
- Track pipeline progression (stage movement)
- Identify stalled deals and obstacles
- Provide coaching for CSMs on struggling opportunities
- Recommend adjustments to campaign tactics

**Outputs:**
- Demos and trials launched (count, accounts)
- Proposals delivered (value, timing)
- Pipeline progression (stage advancement)
- Deal obstacles identified and addressed

**Weeks 8-10: Negotiation and Close**

**CSM + AE:**
**Task:** Close expansion deals
- Negotiate pricing and terms
- Address objections and concerns
- Secure executive sponsor approval (if needed)
- Execute contracts and close deals
- Celebrate wins with customers

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Pipeline forecasting and acceleration
- Forecast deal close timing and probability
- Identify at-risk deals (may slip or stall)
- Recommend acceleration tactics (discounts, urgency, incentives)
- Provide win/loss analysis as deals close

**Outputs:**
- Closed expansion deals (ARR, count)
- Pipeline forecast (expected revenue, timing)
- Win/loss reasons documented
- Slipped/lost deals analysis

### Phase 3: Campaign Wrap-Up and Learning (Weeks 11-12)

**Week 11: Performance Analysis**

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Campaign results and ROI analysis
- Calculate total expansion ARR closed
- Measure conversion rates (by tier, type, segment)
- Analyze average deal size and cycle time
- Compare actual vs. target performance
- Calculate campaign ROI (revenue vs. investment)

**Agent:** `customer-segmentation-analyst` (Sonnet)
**Task:** Segment and cohort performance analysis
- Compare expansion rates across segments
- Identify high-performing and low-performing cohorts
- Determine which opportunity types converted best
- Analyze propensity score accuracy (did high-propensity close?)

**Outputs:**
- Campaign performance dashboard (ARR, conversion, ROI)
- Segment performance breakdown
- Win/loss analysis by opportunity type
- Propensity model validation and refinement

**Week 12: Retrospective and Optimization**

**CS Leadership + Team:**
**Task:** Campaign retrospective and lessons learned
- What worked well? (Playbooks, messaging, tactics)
- What didn't work? (Low conversion areas, obstacles)
- What should we start/stop/continue?
- How can we improve next campaign?

**Agent:** `expansion-opportunity-identifier` (Sonnet)
**Task:** Playbook refinement and recommendations
- Update expansion playbooks based on learnings
- Refine propensity scoring model (improve accuracy)
- Identify new expansion triggers and signals
- Recommend improvements for next campaign cycle

**Outputs:**
- Campaign retrospective summary
- Updated expansion playbooks
- Refined propensity model
- Recommendations for next campaign
- Success stories and case studies

---

## Success Metrics

**Pipeline Metrics:**
- Expansion opportunities identified: 100-150 (target segment)
- Qualified opportunities (BANT): 60-80 (50-60% qualification rate)
- Tier 1 opportunities (high propensity): 30-40 accounts

**Conversion Metrics:**
- Overall conversion rate: 35-45% (qualified opps → closed)
- Tier 1 conversion rate: 60-70% (high propensity)
- Tier 2 conversion rate: 30-40% (medium propensity)
- Average deal size: $12K-18K (varies by segment)
- Average sales cycle: 45-75 days

**Revenue Metrics:**
- Total expansion ARR: $300K-500K (quarterly campaign)
- NRR impact: +4-6% portfolio NRR improvement
- Campaign ROI: 5-8x (revenue / campaign investment)

**Efficiency Metrics:**
- CSM time invested: 15-20 hours per closed deal
- Cost of acquisition: 15-20% of expansion ARR
- Time from opportunity to close: 60 days avg

---

## Campaign Variations by Opportunity Type

### Seat Expansion Campaign
**Target:** Accounts with <60% seat utilization, growing headcount
**Play:** License audit, department expansion, volume discounts
**Cycle:** 30-45 days (fast)
**Win Rate:** 60-70% (high propensity)

### Tier Upgrade Campaign
**Target:** Accounts hitting usage limits, requesting advanced features
**Play:** ROI analysis, feature trials, premium value demonstration
**Cycle:** 60-90 days (moderate)
**Win Rate:** 45-55% (medium propensity)

### Cross-Sell Campaign
**Target:** Healthy accounts with adjacent product needs
**Play:** Use case workshops, pilots, bundled pricing
**Cycle:** 60-120 days (longer)
**Win Rate:** 35-45% (lower propensity, newer motion)

---

## Key Handoffs and Collaboration

**CS → Sales:**
- Handoff: Qualified opportunities >$50K or complex deals
- Collaboration: Joint discovery, demos, proposals
- Split: 50/50 credit or commission share (aligned incentives)

**CS → Marketing:**
- Marketing support: Case studies, ROI calculators, campaign emails
- Content: Expansion-focused webinars, content, templates
- Automation: Email sequences, in-app messaging, nurture campaigns

**CS → Product:**
- Product input: Feature requests from expansion conversations
- Beta access: Offer early access to features driving upgrades
- Roadmap alignment: Position upcoming features in expansion discussions

---

## Best Practices

1. **Target Healthy Accounts:** Expansion from satisfied customers (health >70)
2. **Align to Business Needs:** Lead with customer value, not product features
3. **Proactive Outreach:** Don't wait for customers to ask, identify and propose
4. **Multi-Threading:** Engage multiple stakeholders for larger deals
5. **Quick Wins First:** Prioritize Tier 1 opportunities for early momentum
6. **Learn and Iterate:** Use campaign data to refine next cycle
7. **Celebrate Wins:** Recognize CSMs for expansion success
8. **Customer-First:** Expansion should feel like value-add, not sales pitch

---

## Tools and Templates

**Campaign Management:**
- Opportunity tracking spreadsheet or CRM pipeline
- Campaign performance dashboard (Tableau, Looker)
- CSM activity tracker (touchpoints, progress)

**Sales Enablement:**
- ROI calculator templates (by opportunity type)
- Expansion one-pagers (value propositions)
- Demo scripts and use case libraries
- Proposal templates (pricing, terms)
- Contract amendment templates

**Communication:**
- Email templates (outreach, follow-up, proposals)
- Slack channel for campaign coordination
- Weekly campaign stand-up meetings
- Win/loss tracking and sharing

---

## Expected Outcomes

**Quarterly Campaign Results:**
- Expansion ARR: $400K
- Deals Closed: 25-30
- Average Deal Size: $13K
- Conversion Rate: 40%
- NRR Impact: +5% portfolio-wide
- Campaign ROI: 6x

**Annual Impact (4 campaigns/year):**
- Total Expansion ARR: $1.6M
- NRR: 115-120% (from 110% baseline)
- Customer LTV: +22% improvement
- CSM Quota Attainment: 85%+ hit expansion targets
