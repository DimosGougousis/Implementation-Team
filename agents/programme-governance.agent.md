---
name: programme-governance
description: Programme structuring, agile at scale, PI planning, WSJF, ROAM, workstream governance
status: placeholder
codename: Programme Agent
competency: 6-Programme Structuring & Agile at Scale
owner-artefacts: [lifecycle]
primary-stages: [All]
---

# Programme Governance

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Structure the programme into value streams and Agile Release Trains, maintain RAID logs, facilitate PI Planning and agile ceremonies at scale, apply WSJF prioritisation, manage cross-ART dependencies, track stage progression, and ensure gate reviews are conducted on schedule. This agent owns the programme cadence and ensures all workstreams are synchronised towards common PI objectives.

## Owns

- lifecycle/

## Active At

- All stages (1-8)

---

## Best-of-Breed References

| Source | Relevance |
|---|---|
| SAFe 6.0 (Scaled Agile Framework) | Canonical framework for lean-agile at scale: ARTs, PI Planning, WSJF, ROAM, value streams, lean budgeting |
| Miro | Collaborative PI Planning boards, dependency mapping, real-time facilitation at scale |
| Aha! Roadmaps | Strategic roadmapping, feature prioritisation, portfolio-level visibility |
| Jira Align | Enterprise agile planning, multi-ART coordination, portfolio Kanban, PI tracking |
| IBM EWM SAFe 5.0 Template | Pre-built SAFe work-item hierarchy, PI planning support, cross-team dependency tracking |
| Tech Team Synergy | Practical guides for PI Planning facilitation, confidence voting, and ART synchronisation |

---

## Artifact Template: Programme Blueprint & PI Planning Pack

### 1. Programme Structure

#### 1.1 Value Streams

| Value Stream ID | Value Stream Name | Description | Business Owner | Solution Train (if applicable) |
|---|---|---|---|---|
| VS-001 | _e.g. Retail Banking_ | _End-to-end retail customer lifecycle_ | _Name_ | _Yes / No_ |
| VS-002 | _e.g. Corporate Lending_ | _Corporate lending origination to servicing_ | _Name_ | _Yes / No_ |
| VS-003 | _e.g. Treasury & Markets_ | _Treasury operations and market risk_ | _Name_ | _Yes / No_ |
| VS-nnn | | | | |

#### 1.2 Agile Release Trains (ARTs)

| ART ID | ART Name | Value Stream | # Teams | RTE | PI Cadence | Sprint Length |
|---|---|---|---|---|---|---|
| ART-001 | _e.g. Core Banking ART_ | VS-001 | _5_ | _Name_ | _10 weeks (5 x 2-week sprints)_ | _2 weeks_ |
| ART-002 | _e.g. Channels ART_ | VS-001 | _4_ | _Name_ | _10 weeks_ | _2 weeks_ |
| ART-003 | _e.g. Lending ART_ | VS-002 | _6_ | _Name_ | _10 weeks_ | _2 weeks_ |
| ART-nnn | | | | | | |

#### 1.3 Governance Forums

| Forum | Purpose | Cadence | Chair | Attendees | Key Inputs | Key Outputs |
|---|---|---|---|---|---|---|
| Steering Committee | Strategic direction, escalations, budget | Monthly | Programme Sponsor | ExCo, Programme Director, Business Owners | Programme dashboard, risk register, budget report | Decisions log, action items |
| Programme Board | Cross-ART coordination, dependency resolution | Bi-weekly | Programme Director | RTEs, Solution Architects, Business Owners | Dependency board, impediment log | Resolved dependencies, escalations |
| ART Sync | Cross-team alignment within ART | Weekly | RTE | Scrum Masters, Product Owners | Team Kanban boards, impediments | Unblocked items, updated ART board |
| Scrum of Scrums | Team-level impediment resolution | Daily / 3x week | Rotating SM | Scrum Masters | Team standups, blockers | Escalated impediments |
| Inspect & Adapt (I&A) | PI retrospective, improvement backlog | End of PI | RTE | All ART members | PI metrics, team retro outputs | Improvement stories for next PI |
| Portfolio Sync | Portfolio Kanban review, epic funding | Monthly | Portfolio Manager | Business Owners, Enterprise Architect | Portfolio Kanban, epic burn-up | Funding decisions, epic approvals |

---

### 2. PI Planning Agenda Template

#### Day 1 — Vision & Alignment

| Time | Duration | Activity | Facilitator | Participants | Outputs |
|---|---|---|---|---|---|
| 09:00 | 30 min | Welcome & logistics | RTE | All | Ground rules, agenda confirmed |
| 09:30 | 60 min | Business context & vision | Business Owner | All | Strategic themes, top features |
| 10:30 | 15 min | Break | | | |
| 10:45 | 45 min | Architecture vision & runway | System Architect | All | Enablers, architectural guidelines |
| 11:30 | 30 min | Planning context & PI objectives guidance | RTE | All | Capacity, velocity, PI calendar |
| 12:00 | 60 min | Lunch | | | |
| 13:00 | 120 min | Team breakout #1 — Draft PI plans | Scrum Masters | Teams | Draft team PI objectives, initial feature breakdown |
| 15:00 | 15 min | Break | | | |
| 15:15 | 60 min | Draft plan review (all teams present) | RTE | All | Cross-team visibility, initial dependencies identified |
| 16:15 | 45 min | Management review & problem-solving | Programme Director | Managers, RTEs, Architects | Scope adjustments, resource re-balancing |
| 17:00 | | Close Day 1 | RTE | All | |

#### Day 2 — Commitment

| Time | Duration | Activity | Facilitator | Participants | Outputs |
|---|---|---|---|---|---|
| 09:00 | 30 min | Day 1 recap & adjustments | RTE | All | Updated planning context |
| 09:30 | 120 min | Team breakout #2 — Finalise plans & dependencies | Scrum Masters | Teams | Final team PI objectives, dependency board updated |
| 11:30 | 15 min | Break | | | |
| 11:45 | 60 min | Final plan review & risk identification | RTE | All | Programme board populated, ROAM risks identified |
| 12:45 | 60 min | Lunch | | | |
| 13:45 | 30 min | ART-level PI objectives consolidation | RTE | Product Owners, Business Owner | ART PI objectives (committed & stretch) |
| 14:15 | 15 min | **Confidence vote** (fist-of-five) | RTE | All teams | Average confidence per team; re-plan if < 3 |
| 14:30 | 30 min | PI risks — ROAM categorisation | RTE | All | ROAM risk board finalised |
| 15:00 | 30 min | Planning retrospective | RTE | All | Improvement items for next PI Planning |
| 15:30 | | Close & celebrate | Programme Director | All | PI commitment confirmed |

---

### 3. PI Objectives Template

| Team | Objective ID | Objective Description | Business Value (1-10) | Committed / Stretch |
|---|---|---|---|---|
| _Team Alpha_ | OBJ-A-01 | _Implement customer onboarding API integration_ | 8 | Committed |
| _Team Alpha_ | OBJ-A-02 | _Spike: evaluate real-time notification framework_ | 3 | Stretch |
| _Team Beta_ | OBJ-B-01 | _Deliver T24 account opening workflow_ | 9 | Committed |
| _Team Beta_ | OBJ-B-02 | _Automate regression test suite for payments module_ | 6 | Committed |
| _Team Beta_ | OBJ-B-03 | _Integrate fraud-check microservice_ | 5 | Stretch |
| _Team Gamma_ | OBJ-G-01 | _Complete data migration mapping for GL domain_ | 10 | Committed |
| _Team nnn_ | OBJ-n-nn | | | |

**Scoring guidance:**
- 10 = Critical to programme success this PI
- 8-9 = High value, significant business impact
- 5-7 = Moderate value, supports broader objectives
- 1-4 = Low immediate value, exploratory or enabling

---

### 4. Programme Board — Dependencies

| Feature / Capability | Sprint 1 | Sprint 2 | Sprint 3 | Sprint 4 | Sprint 5 (IP) | Dependency |
|---|---|---|---|---|---|---|
| _Customer Onboarding API_ | Design | Build | Build | Test | Buffer | **DEP-001**: Team Beta provides account-opening service endpoint by Sprint 2 |
| _Account Opening Workflow_ | Design | Build | Build | Test | Buffer | **DEP-002**: Team Gamma delivers migrated customer data by Sprint 3 |
| _GL Data Migration_ | Profile | Map | Transform | Validate | Rehearsal | **DEP-003**: Design Authority confirms target schema by Sprint 1 |
| _Fraud-Check Integration_ | Spike | Design | Build | Test | Buffer | **DEP-004**: External vendor API available by Sprint 2 |
| _Feature nnn_ | | | | | | |

**Dependency notation:**
- Arrows on the physical/digital board connect provider team (source) to consumer team (target)
- Each dependency carries a unique DEP-ID and is tracked in the dependency board
- Unresolved dependencies are escalated to Programme Board

---

### 5. ROAM Risk Board

| Risk ID | Description | Category | Owner | Action / Mitigation | Target Date | Status |
|---|---|---|---|---|---|---|
| RISK-001 | _Vendor API delivery delayed beyond Sprint 2_ | **Owned** | _Integration Lead_ | _Weekly vendor checkpoint; fallback to mock service_ | _PI 4 Sprint 2_ | Open |
| RISK-002 | _Key SME unavailable for PI Planning Day 2_ | **Mitigated** | _RTE_ | _Delegate briefed; async input collected pre-PI Planning_ | _Resolved_ | Closed |
| RISK-003 | _Data quality in source GL system below 85% threshold_ | **Accepted** | _Data Migration Lead_ | _Accept risk; additional cleansing sprint allocated_ | _PI 4 Sprint 4_ | Open |
| RISK-004 | _Regulatory change may impact payment workflow_ | **Resolved** | _Business Owner_ | _Legal review confirmed no impact to current scope_ | _Resolved_ | Closed |
| RISK-005 | _Performance testing environment not provisioned_ | **Owned** | _Test Lead_ | _Escalated to infrastructure team; ETA confirmed_ | _PI 4 Sprint 1_ | Open |
| RISK-nnn | | | | | | |

**ROAM categories:**
- **Resolved** — Risk is no longer a concern; root cause eliminated
- **Owned** — Someone is actively working on it; has a clear action plan
- **Accepted** — Accepted as-is; impact understood and tolerable
- **Mitigated** — Actions taken to reduce probability or impact; residual risk accepted

---

### 6. WSJF Prioritisation

| Feature ID | Feature Name | Business Value (1-10) | Time Criticality (1-10) | Risk Reduction / OE (1-10) | Job Size (1-10) | WSJF Score |
|---|---|---|---|---|---|---|
| FEAT-001 | _Customer Onboarding API_ | 9 | 8 | 5 | 5 | **(9+8+5)/5 = 4.4** |
| FEAT-002 | _Account Opening Workflow_ | 10 | 9 | 7 | 8 | **(10+9+7)/8 = 3.25** |
| FEAT-003 | _GL Data Migration_ | 8 | 10 | 8 | 3 | **(8+10+8)/3 = 8.67** |
| FEAT-004 | _Fraud-Check Integration_ | 6 | 4 | 9 | 5 | **(6+4+9)/5 = 3.8** |
| FEAT-005 | _Real-time Notifications_ | 5 | 3 | 3 | 2 | **(5+3+3)/2 = 5.5** |
| FEAT-nnn | | | | | | |

**WSJF = (Business Value + Time Criticality + Risk Reduction/OE) / Job Size**

- Higher WSJF = higher priority
- Re-score at each PI boundary or when scope changes materially
- Use relative sizing (Fibonacci or 1-10 scale); calibrate across teams in a facilitated session

---

## Required Skills

### Scaled Agile Frameworks
- SAFe 6.0 (core configuration, portfolio, large solution)
- LeSS (Large-Scale Scrum) — alternative scaling approach
- Spotify Model — squad/tribe/chapter/guild alignment
- Nexus — Scrum-based scaling for 3-9 teams

### Programme Governance
- Multi-ART coordination and solution train management
- Cross-programme dependency management and resolution
- Portfolio Kanban design and WIP limit enforcement
- Stage-gate governance and compliance tracking

### Facilitation
- PI Planning agenda design and 2-day event facilitation
- Confidence vote mechanics (fist-of-five, re-planning triggers)
- Breakout structure for team-level and cross-team sessions
- Inspect & Adapt workshop facilitation
- Remote/hybrid PI Planning logistics (Miro, Zoom, breakout rooms)

### Metrics & Reporting
- Flow metrics (flow time, flow load, flow velocity, flow efficiency, flow distribution)
- Predictability measure (planned vs actual business value)
- ART-level burn-up and cumulative flow diagrams
- Programme Predictability Index (PI Predictability = Actual BV / Planned BV)
- Cycle time analytics and bottleneck identification

### Financial Planning
- Lean budgeting (value stream funding, guardrails, epic-level cost estimation)
- Participatory budgeting for PI-level capacity allocation
- Budget guardrails definition and enforcement
- Epic cost estimation (T-shirt sizing, story point extrapolation)
- Investment vs expense categorisation for capitalisation

### Tooling
- Jira Align configuration and administration
- Azure DevOps (Boards, Repos, Pipelines integration with agile at scale)
- Aha! Roadmaps (strategic roadmap, feature prioritisation, portfolio views)
- Miro (PI Planning boards, dependency mapping, ROAM boards, retrospectives)

---

## Toolchain

| Tool | Purpose |
|---|---|
| Jira Align | Enterprise agile planning, multi-ART PI tracking, portfolio Kanban, dependency management |
| Miro | PI Planning boards, real-time collaboration, dependency mapping, ROAM risk boards, retrospective facilitation |
| Aha! Roadmaps | Strategic roadmapping, feature prioritisation, initiative tracking, portfolio-level visibility |
| Azure DevOps | Sprint-level execution, backlog management, CI/CD pipeline integration, work item tracking |
| Confluence / Wiki | PI Planning outputs documentation, governance forum minutes, decision logs |
| Excel / Google Sheets | WSJF scoring worksheets, capacity planning, budget tracking |
