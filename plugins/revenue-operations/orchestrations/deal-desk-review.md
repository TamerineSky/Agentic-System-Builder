# Deal Desk Review Orchestration

**Purpose:** Structured review and approval workflow for non-standard deals including pricing exceptions, custom terms, and strategic approvals.

**Frequency:** As needed (typically 5-10 per week for growing companies)

**Duration:** 24-48 hours from submission to decision

**Participants:** Deal Desk, Sales Rep, Sales Manager, Finance, Legal (as needed), Executive Sponsor (for strategic deals)

---

## Multi-Agent Workflow

### Stage 1: Deal Submission and Initial Triage (2-4 hours)

**Trigger:** Sales rep submits deal for approval via CRM workflow

**Agent:** `sales-ops-automator` (Haiku)
**Task:** Automated validation and routing
- Check submission completeness (all required fields)
- Validate discount level against approval matrix
- Route to appropriate approvers based on deal attributes
- Send acknowledgment to rep with expected timeline
- Flag SLA violations or urgent requests

**Deal Desk Analyst:** Initial review
- Confirm deal economics and margin calculation
- Validate customer information and creditworthiness
- Check for policy exceptions or red flags
- Categorize urgency and complexity

**Outputs:**
- Deal categorized (standard/non-standard/strategic)
- Initial approval routing assigned
- SLA timer started

### Stage 2: Risk and Business Analysis (4-8 hours)

**Agent:** `deal-risk-analyzer` (Sonnet)
**Task:** Deal risk assessment
- Analyze deal structure and terms
- Identify customer risk factors (size, industry, credit)
- Assess implementation and delivery risks
- Flag contract term concerns (length, payment terms, SLAs)
- Calculate risk-adjusted value

**Agent:** `revenue-forecaster` (Sonnet)
**Task:** Deal economics modeling
- Calculate true net revenue (after discounts, fees)
- Model payment schedule and cash impact
- Assess customer lifetime value
- Compare to standard deal economics
- Quantify cost of concessions

**Deal Desk Analyst:** Competitive and strategic context
- Research customer and competitive situation
- Assess strategic value (reference account, market entry, competitive displacement)
- Document business justification for exceptions
- Prepare recommendation

**Outputs:**
- Risk assessment report
- Deal economics model
- Business case summary
- Approval recommendation

### Stage 3: Approval Workflow (4-24 hours)

**Standard Deals (within policy):**
- Manager approval (auto-approved if <10% discount)
- Deal Desk approval for documentation
- Contracts generated and sent
- **Timeline:** 4-8 hours

**Non-Standard Deals (exceptions required):**
- Manager approval
- Director/VP Sales approval
- Finance approval (if >20% discount or custom payment terms)
- Legal review (if custom contract terms)
- Deal Desk coordination and documentation
- **Timeline:** 24-48 hours

**Strategic Deals (significant exceptions):**
- Sales leadership approval (VP/CRO)
- CFO approval (if material financial impact)
- CEO approval (if >$1M ARR or major strategic customer)
- Executive committee review (if policy-breaking precedent)
- Board notification (if material to quarterly plan)
- **Timeline:** 48-72 hours

**Agent:** `sales-ops-automator` (Haiku)
**Task:** Workflow automation and tracking
- Route to next approver automatically
- Send reminders for pending approvals (SLA management)
- Escalate stalled approvals
- Update deal status in CRM
- Notify rep of progress and decisions

**Outputs:**
- Approval/rejection decision with rationale
- Approved deal terms documented
- Contract ready for signature
- CRM updated with final deal structure

### Stage 4: Documentation and Learning (1-2 hours)

**Deal Desk:** Finalization and documentation
- Document final approved terms
- Update approval precedent database
- Note any policy exceptions granted
- Archive deal package for audit

**Quarterly Review:** (Deal Desk + Sales Ops + Finance)
- Analyze deal approval patterns
- Identify frequent exception requests (policy update candidates)
- Review approval times and bottlenecks
- Assess impact of exceptions on margins
- Recommend policy or process refinements

**Outputs:**
- Deal fully documented and archived
- Precedent database updated
- Quarterly insights for policy improvement

---

## Approval Matrix

| Deal Attribute | Manager | Director | VP Sales | Finance | Legal | CFO/CEO |
|---|---|---|---|---|---|---|
| Discount 0-10% | ✓ | | | | | |
| Discount 11-20% | ✓ | ✓ | | | | |
| Discount 21-30% | ✓ | ✓ | ✓ | ✓ | | |
| Discount >30% | ✓ | ✓ | ✓ | ✓ | | ✓ |
| Custom Payment Terms | ✓ | ✓ | | ✓ | | |
| Custom Contract | ✓ | ✓ | | | ✓ | |
| Strategic Customer | ✓ | ✓ | ✓ | | | ✓ (if >$1M) |
| Multi-Year (>3 years) | ✓ | ✓ | | ✓ | ✓ | |

---

## SLA Targets

- Standard Deals: 8 hours to approval
- Non-Standard Deals: 24 hours to decision
- Strategic Deals: 48 hours to decision
- Urgent Deals (quarter-end): Expedited review (4-12 hours)

---

## Success Metrics

- SLA adherence >90%
- Approval cycle time trending down
- Rep satisfaction with process >85%
- Deal approval rate >75% (if too high, approvals not rigorous enough)
- Margin protection (exceptions don't erode margins >2%)
- No material audit findings on deal approvals
- Policy exception rate trending down (policies adapting to business needs)

---

## Escalation Paths

**Stalled Approval:**
- After 50% of SLA elapsed: Automated reminder to approver
- After 75% of SLA elapsed: Escalate to approver's manager
- After 100% of SLA elapsed: Executive escalation + visibility to sales leadership

**Approval Conflict:**
- Finance rejects but Sales pushes: VP Sales + CFO align
- Legal concerns but business urgency: Legal + CRO + CFO align
- Policy precedent concern: Deal Desk lead + Sales Ops + Finance align

**Urgent Requests:**
- Rep can flag as urgent with justification
- Deal Desk can expedite routing
- After-hours approvals available for critical deals
- Executive on-call for strategic deals

---

## Automation and Tooling

- CRM workflow for submission and routing (Salesforce Flow)
- Approval tracking dashboard (real-time status visibility)
- Auto-escalation for SLA violations
- Contract generation automation (standard terms)
- Deal package assembly (all docs in one folder)
- Email/Slack notifications at key milestones
- Reporting and analytics on deal desk metrics
