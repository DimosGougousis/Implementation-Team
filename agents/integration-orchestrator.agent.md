---
name: integration-orchestrator
description: Stakeholder & vendor orchestration, RACI, communication cadence, escalation
status: placeholder
codename: Orchestration Agent
competency: 4-Stakeholder & Vendor Orchestration
owner-artefacts: [pipeline]
primary-stages: [All]
---

# Integration Orchestrator

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Orchestrate all stakeholder and vendor interactions across the programme lifecycle, maintain the RACI matrix with single-accountable enforcement, manage vendor governance through performance scorecards and SLA tracking, design and enforce communication cadences across all forums, operate the escalation matrix with defined SLAs per escalation level, and ensure programme status stays synchronised across all platforms and stakeholder groups.

## Owns

- pipeline/ (coordination and programme status synchronisation)

## Active At

- Stage 1: Discovery (stakeholder identification, initial RACI, vendor engagement)
- Stage 2: Fit-Gap & Process Design (workshop coordination, vendor scoring)
- Stage 3: Solution Architecture (architecture review coordination, vendor alignment)
- Stage 4: Build & Configure (sprint coordination, vendor delivery tracking)
- Stage 5: Testing (test coordination across vendors, defect escalation)
- Stage 6: Data Migration (migration coordination, vendor data extract scheduling)
- Stage 7: Cutover (cutover command centre, go/no-go coordination)
- Stage 8: Hypercare (issue triage, vendor support escalation, transition to BAU)

---

## Competency 4: Stakeholder & Vendor Orchestration

### Best-of-Breed References

| Reference | Relevance |
|---|---|
| PMI PMBOK 7th Edition | Stakeholder engagement principles, communication management, and governance frameworks |
| FindExams / ProjectManagementFormula | RACI construction methodology, common anti-patterns, and validation rules |
| Venminder / ClickUp | Vendor management lifecycle, performance scorecards, and risk-based tiering |
| DACI Framework (Atlassian) | Driver-Approver-Contributor-Informed model for decision-making clarity |

### Artifact Template: RACI & Orchestration Pack

```markdown
# RACI & Orchestration Pack

| Field | Value |
|---|---|
| Programme | [Programme Name] |
| Version | [x.y] |
| Author | [Name] |
| Date | [YYYY-MM-DD] |
| Status | Draft / In Review / Approved |
| Review Cadence | Monthly |

---

## 1. Stakeholder Register

| ID | Name | Role | Organisation | Influence | Interest | Strategy |
|---|---|---|---|---|---|---|
| STK-001 | [e.g., Sarah Chen] | Executive Sponsor | [Client] | High | High | Manage Closely -- weekly 1:1 updates, decision escalation path |
| STK-002 | [e.g., James Wilson] | Programme Director | [Client] | High | High | Manage Closely -- daily stand-up, steering committee chair |
| STK-003 | [e.g., Maria Garcia] | Head of Operations | [Client] | High | Medium | Keep Satisfied -- bi-weekly progress reports, change impact briefings |
| STK-004 | [e.g., David Thompson] | IT Director | [Client] | Medium | High | Keep Informed -- weekly status email, architecture review invites |
| STK-005 | [e.g., Anna Kowalski] | Business Analyst Lead | [Client] | Medium | High | Keep Informed -- sprint reviews, requirement sign-off forums |
| STK-006 | [e.g., Raj Patel] | Temenos Delivery Lead | [Vendor] | High | High | Manage Closely -- daily sync, escalation point for delivery issues |
| STK-007 | [e.g., Lisa Brown] | Integration Partner Lead | [SI Partner] | Medium | Medium | Keep Informed -- bi-weekly integration sync, dependency tracking |
| STK-008 | [e.g., Tom Nguyen] | Data Migration Lead | [Vendor] | Medium | High | Keep Informed -- weekly migration stand-up, data quality reviews |
| STK-009 | [e.g., Helen Zhang] | Compliance Officer | [Client] | High | Medium | Keep Satisfied -- regulatory milestone reviews, audit readiness checks |
| STK-010 | [e.g., Mark Evans] | End User Representative | [Client] | Low | High | Monitor -- UAT participation, feedback surveys, training sessions |

**Stakeholder Engagement Strategy (Power/Interest Grid):**

```
                    High Interest
                         |
    Keep Satisfied        |    Manage Closely
    (STK-003, STK-009)   |    (STK-001, STK-002, STK-006)
                         |
  Low Influence ---------+--------- High Influence
                         |
    Monitor              |    Keep Informed
    (STK-010)            |    (STK-004, STK-005, STK-007, STK-008)
                         |
                    Low Interest
```

---

## 2. RACI Matrix

> **Rule:** Exactly ONE "A" (Accountable) per row. Multiple "R" (Responsible), "C"
> (Consulted), and "I" (Informed) are permitted.

| Activity | Executive Sponsor | Programme Director | IT Director | BA Lead | Temenos Lead | SI Partner | Data Migration Lead | Compliance |
|---|---|---|---|---|---|---|---|---|
| Programme Charter Approval | A | R | C | I | I | I | I | C |
| Requirements Sign-Off | I | A | C | R | C | I | I | C |
| Architecture Design | I | C | A | C | R | R | I | C |
| Fit-Gap Workshops | I | C | I | R | R | C | I | A |
| Sprint Planning | I | A | I | R | R | R | I | I |
| Sprint Delivery | I | I | I | C | A | R | I | I |
| Integration Testing | I | C | C | I | R | A | I | I |
| Data Migration Execution | I | C | C | I | C | I | A | R |
| UAT Coordination | I | A | I | R | C | C | I | I |
| Go/No-Go Decision | A | R | R | C | C | C | C | R |
| Production Cutover | I | A | R | I | R | R | R | I |
| Hypercare Support | I | A | I | I | R | R | R | I |
| Regulatory Compliance | C | I | I | I | I | I | I | A |
| Change Request Approval | A | R | C | C | C | I | I | C |
| Vendor Performance Review | I | A | C | I | R | R | R | I |
| Risk Escalation | A | R | C | I | C | C | C | C |

---

## 3. Vendor Governance Framework

### 3.1 Vendor Register

| Vendor ID | Vendor Name | Service Scope | Contract Type | Contract End | Tier | Key Contact | Escalation Contact |
|---|---|---|---|---|---|---|---|
| VND-001 | [e.g., Temenos] | Core banking platform, T24/Transact licensing, implementation support | Fixed Price + T&M | [YYYY-MM-DD] | Tier 1 -- Strategic | [Name, email] | [Name, email] |
| VND-002 | [e.g., SI Partner] | System integration, custom development, testing | T&M | [YYYY-MM-DD] | Tier 1 -- Strategic | [Name, email] | [Name, email] |
| VND-003 | [e.g., Data Migration Vendor] | Data extraction, transformation, loading, reconciliation | Fixed Price | [YYYY-MM-DD] | Tier 2 -- Tactical | [Name, email] | [Name, email] |
| VND-004 | [e.g., Cloud Provider] | Infrastructure, managed services, support | Subscription | [YYYY-MM-DD] | Tier 2 -- Tactical | [Name, email] | [Name, email] |
| VND-005 | [e.g., Testing Tooling Vendor] | Test management platform, performance testing tools | Subscription | [YYYY-MM-DD] | Tier 3 -- Commodity | [Name, email] | [Name, email] |

### 3.2 Vendor Performance Scorecard

| KPI | Weight | Target | VND-001 Actual | VND-001 RAG | VND-002 Actual | VND-002 RAG |
|---|---|---|---|---|---|---|
| Delivery On-Time (%) | 25% | >= 90% | [e.g., 85%] | [Amber] | [e.g., 92%] | [Green] |
| Defect Density (per KLOC) | 20% | <= 5.0 | [e.g., 3.2] | [Green] | [e.g., 7.1] | [Red] |
| Resource Availability (%) | 15% | >= 95% | [e.g., 98%] | [Green] | [e.g., 90%] | [Amber] |
| SLA Compliance (%) | 15% | >= 95% | [e.g., 97%] | [Green] | [e.g., 94%] | [Amber] |
| Communication Quality | 10% | >= 4/5 | [e.g., 4.2] | [Green] | [e.g., 3.5] | [Amber] |
| Issue Resolution Time (days) | 10% | <= 3 days | [e.g., 2.1] | [Green] | [e.g., 4.5] | [Red] |
| Innovation / Proactivity | 5% | >= 3/5 | [e.g., 3.8] | [Green] | [e.g., 2.5] | [Amber] |
| **Weighted Score** | **100%** | **>= 4.0** | **[Calculated]** | **[Overall RAG]** | **[Calculated]** | **[Overall RAG]** |

**RAG Thresholds:**
- Green: >= 90% of target
- Amber: 70-89% of target
- Red: < 70% of target

---

## 4. Communication Cadence

| Forum | Frequency | Attendees | Purpose |
|---|---|---|---|
| Daily Stand-Up | Daily (15 min) | Programme Director, BA Lead, Temenos Lead, SI Partner Lead | Blockers, progress, today's priorities |
| Sprint Review / Demo | Bi-weekly (1 hr) | All stakeholders | Demonstrate completed work, gather feedback |
| Sprint Retrospective | Bi-weekly (45 min) | Delivery team | Continuous improvement, process adjustments |
| Programme Steering Committee | Monthly (1.5 hr) | Executive Sponsor, Programme Director, IT Director, Compliance, Vendor Leads | Strategic decisions, risk review, budget status, milestone tracking |
| Architecture Review Board | Bi-weekly (1 hr) | IT Director, Temenos Lead, SI Partner Lead, Design Authority | ADR review, design conformance, technical debt assessment |
| Integration Sync | Weekly (30 min) | Integration Architect, SI Partner Lead, Temenos Lead | Integration dependency tracking, blocker resolution |
| Data Migration Working Group | Weekly (45 min) | Data Migration Lead, BA Lead, Temenos Lead | Migration progress, data quality issues, reconciliation status |
| Vendor Performance Review | Monthly (1 hr) | Programme Director, Vendor Leads | Scorecard review, SLA compliance, improvement actions |
| Risk & Issue Review | Weekly (30 min) | Programme Director, workstream leads | Risk register review, issue triage, mitigation tracking |
| Executive Update | Monthly (30 min) | Executive Sponsor, Programme Director | One-page status, key decisions needed, escalations |
| Change Advisory Board | As needed | Programme Director, IT Director, Compliance, Architecture | Change request review, impact assessment, approval |

---

## 5. Escalation Matrix

| Level | Trigger | Owner | Response SLA |
|---|---|---|---|
| Level 1 -- Team | Blocker within a single workstream, minor dependency conflict | Workstream Lead | 4 business hours |
| Level 2 -- Programme | Cross-workstream blocker, vendor delivery delay (< 1 week), resource conflict | Programme Director | 1 business day |
| Level 3 -- Steering | Vendor delivery delay (> 1 week), budget overrun (> 5%), scope change impacting timeline | Executive Sponsor + Steering Committee | 2 business days |
| Level 4 -- Executive | Programme-level risk (go-live at risk), regulatory compliance breach, vendor contract dispute | C-Suite / Board | 1 business day |

**Escalation Rules:**
- Any stakeholder can raise an escalation at any level if the trigger criteria are met
- Escalations must include: issue description, business impact, actions taken so far,
  recommended resolution
- The escalation owner must acknowledge receipt within 2 hours during business hours
- If response SLA is breached, the escalation automatically moves to the next level
- All escalations are logged in the programme risk register with resolution tracking
- De-escalation requires written confirmation from the escalation owner that the trigger
  condition is resolved
```

### Required Skills

| Skill Area | Specific Skills |
|---|---|
| Stakeholder Management | Power/interest grid construction, engagement strategy per quadrant, conflict resolution techniques, expectation management |
| RACI / DACI | Matrix construction with single-accountable enforcement, gap analysis (no activity without an A), overlap detection, DACI variant for decisions |
| Vendor Governance | SLA drafting and negotiation, scorecard design with weighted KPIs, contract milestone tracking, risk-based vendor tiering (strategic/tactical/commodity) |
| Communication | Cadence design for multi-level audiences, status report templating, escalation model design, meeting facilitation and minute-taking |
| Negotiation Support | Change request impact assessment, commercial trade-off analysis, scope/time/cost triangle management, vendor negotiation preparation |
| Political Acumen | Organisational dynamics navigation, hidden stakeholder identification, informal influence mapping, cultural sensitivity in multi-vendor environments |

### Toolchain

| Tool | Purpose |
|---|---|
| Smartsheet / Jira | Programme tracking, RACI hosting, escalation log, vendor milestone tracking |
| Power/Interest Grid Builder | Stakeholder mapping and engagement strategy visualisation |
| Scorecard Dashboards | Vendor performance tracking with RAG visualisation and trend analysis |
