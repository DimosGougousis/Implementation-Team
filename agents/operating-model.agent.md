---
name: operating-model
description: Post-go-live target operating model, support tiers, upgrade cadence, continuous improvement
status: placeholder
codename: Operating Model Agent
competency: 10-Post-Transformation Operating Model Design
owner-artefacts: [08-post-go-live-operating-model]
primary-stages: [3, 8]
---

# Operating Model

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Design the post-go-live target operating model including organisational structure (L1-L3), value stream ownership, support tiers with escalation paths, incident and change management processes, Temenos upgrade cadence, continuous improvement mechanisms, and the hypercare-to-steady-state handover plan. Ensure the TOM is stress-tested against real scenarios and anchored to measurable performance targets.

## Owns

- artefacts/08-post-go-live-operating-model/

## Active At

- Stage 3: Solution Architecture (TOM design, future-state org structure, sourcing model)
- Stage 8: Hypercare (TOM activation, handover, steady-state transition)

---

## Best-of-Breed References

| Source | Relevance |
|---|---|
| Umbrex "Busy Consultant's Guide to TOM Design" (19 chapters) | Comprehensive methodology covering all TOM dimensions: strategy link, design principles, value streams, macro-structure, technology, sourcing, performance, change roadmap |
| Umbrex Carve-Out Playbook | Practical guidance for standing up new operating models during separations; applicable to transformation stand-up |
| Art of Service TOM Toolkit (981 requirements, RDMAICS) | Structured requirements library for TOM design; RDMAICS lifecycle (Recognise, Define, Measure, Analyse, Improve, Control, Sustain) |
| McKinsey Operating Model Framework | Organisation design principles, spans & layers, role clarity, decision rights |
| Deloitte Target Operating Model Approach | Industry-standard TOM methodology with 8 design dimensions; financial services specialisation |
| BCG Operating Model Design | Value-driven operating model design; capability-based planning, digital operating model patterns |

---

## Artifact Template: Target Operating Model Blueprint

---

### ONE-PAGE TOM SUMMARY

#### 1. Strategy & Value Link

| Strategic Objective | TOM Contribution | Measure | Target |
|---|---|---|---|
| Cost reduction | Automation of manual processes; shared services consolidation | Cost-to-income ratio reduction | _15% reduction within 18 months_ |
| Revenue enablement | Faster time-to-market for new products via platform capabilities | Product launch cycle time | _From 12 months to 4 months_ |
| Risk reduction | Integrated controls framework; automated compliance monitoring | Regulatory findings per audit | _Zero critical findings_ |
| Customer experience | Omni-channel journey redesign; real-time servicing | Net Promoter Score (NPS) | _NPS >= 45_ |
| Employee engagement | Clear role definitions; career pathways; modern tooling | Employee engagement score | _Top quartile (>= 75%)_ |

---

#### 2. Design Principles

| # | Principle | Implication |
|---|---|---|
| DP-01 | Customer-journey-led | Organisation structured around customer journeys, not functional silos; journey owners accountable for end-to-end experience |
| DP-02 | Platform-first | Invest in reusable platform capabilities (APIs, shared services) before point solutions; avoid duplication |
| DP-03 | Data as a product | Each data domain has a product owner; data quality is a production KPI, not an afterthought |
| DP-04 | Automate by default | Manual processes are the exception; every repetitive process must have an automation business case assessed |
| DP-05 | Build for resilience | Active-active architecture; no single points of failure in people, process, or technology; chaos engineering practices |
| DP-06 | Continuous improvement | Kaizen embedded in BAU; improvement ideas measured, prioritised (WSJF), and tracked through a visible backlog |
| DP-07 | Cloud-native where possible | Prefer managed cloud services over on-premise; design for elasticity, observability, and infrastructure-as-code |
| DP-08 | Secure by design | Security and compliance built into every process and system; shift-left on security testing and threat modelling |

---

#### 3. Value Streams & Ownership

| Value Stream | Journey Owner | Key Processes | Key KPIs |
|---|---|---|---|
| Customer Onboarding | _Head of Customer Experience_ | KYC/AML checks, account opening, product origination, welcome journey | Onboarding cycle time, straight-through rate, abandonment rate |
| Lending & Credit | _Head of Lending_ | Credit assessment, loan origination, disbursement, servicing, collections | Decision turnaround time, approval rate, NPL ratio |
| Payments & Transfers | _Head of Payments_ | Domestic payments, international transfers, standing orders, direct debits | Payment STP rate, failure rate, processing time |
| Treasury & Markets | _Head of Treasury_ | FX dealing, money market, position management, regulatory reporting | P&L accuracy, position reconciliation time, regulatory submission timeliness |
| Customer Servicing | _Head of Operations_ | Account maintenance, enquiries, complaints, statements, closures | First-contact resolution, average handling time, complaint resolution time |
| Risk & Compliance | _Chief Risk Officer_ | Credit risk monitoring, AML monitoring, regulatory reporting, audit | Risk event frequency, false positive rate, report accuracy |

---

#### 4. Macro-Structure & Key Roles

**Organisation Design (L1-L3):**

```
L1: Chief Operating Officer
├── L2: Head of Customer Experience
│   ├── L3: Onboarding Manager
│   ├── L3: Digital Channels Manager
│   └── L3: Customer Insights Lead
├── L2: Head of Operations
│   ├── L3: Payments Operations Manager
│   ├── L3: Lending Operations Manager
│   └── L3: Back-Office Processing Manager
├── L2: Head of Technology
│   ├── L3: Platform Engineering Lead
│   ├── L3: Application Support Lead
│   └── L3: Infrastructure & Cloud Lead
├── L2: Head of Data & Analytics
│   ├── L3: Data Engineering Manager
│   ├── L3: Data Governance Lead
│   └── L3: BI & Reporting Manager
└── L2: Head of Change & Transformation
    ├── L3: Portfolio Manager
    ├── L3: Business Analysis Lead
    └── L3: Release Manager
```

**Governance Forums:**

| Forum | Purpose | Cadence | Chair | Key Attendees |
|---|---|---|---|---|
| Operating Model Review Board | Strategic TOM oversight, cross-dimension alignment | Quarterly | COO | L2 heads, CRO, CFO |
| Change Advisory Board (CAB) | Change approval, release coordination | Weekly | Head of Technology | Release Manager, App Support, Business Owners |
| Service Review | SLA performance, incident trends, improvement actions | Monthly | Head of Operations | Support leads, journey owners |
| Data Governance Council | Data quality, policy, stewardship | Monthly | Head of Data | Data domain owners, compliance |
| Risk & Controls Committee | Operational risk, control effectiveness, audit findings | Monthly | CRO | Risk owners, Internal Audit, Compliance |
| Continuous Improvement Forum | Improvement backlog prioritisation, kaizen tracking | Bi-weekly | Head of Change | L3 leads, improvement champions |

**Critical Roles:**

| Role | Accountability | Reporting Line |
|---|---|---|
| Journey Owner | End-to-end customer journey performance and improvement | Head of Customer Experience |
| Platform Engineering Lead | Temenos platform stability, upgrades, API management | Head of Technology |
| Application Support Lead (L2/L3) | Incident resolution, root cause analysis, knowledge base | Head of Technology |
| Data Domain Owner | Data quality, stewardship, and governance for assigned domain | Head of Data & Analytics |
| Release Manager | Release planning, CAB coordination, deployment orchestration | Head of Change |
| Service Desk Manager (L1) | First-contact resolution, ticket triage, SLA adherence | Head of Operations |

---

#### 5. Technology & Data Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     CHANNELS LAYER                          │
│  [Internet Banking] [Mobile App] [Branch] [API Partners]    │
├─────────────────────────────────────────────────────────────┤
│                   API GATEWAY / BFF                         │
├─────────────────────────────────────────────────────────────┤
│                  APPLICATION LAYER                          │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────────┐    │
│  │ Temenos T24  │ │  Payments    │ │  Lending Engine   │    │
│  │ Core Banking │ │  Hub         │ │                   │    │
│  └──────────────┘ └──────────────┘ └──────────────────┘    │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────────┐    │
│  │  Treasury    │ │  AML / KYC   │ │  Document Mgmt   │    │
│  │  System      │ │  Platform    │ │                   │    │
│  └──────────────┘ └──────────────┘ └──────────────────┘    │
├─────────────────────────────────────────────────────────────┤
│               INTEGRATION LAYER (ESB / iPaaS)               │
├─────────────────────────────────────────────────────────────┤
│                    DATA LAYER                               │
│  [Operational DB] [Data Warehouse] [Data Lake] [Reporting]  │
├─────────────────────────────────────────────────────────────┤
│               INFRASTRUCTURE (Cloud / On-Prem)              │
│  [Compute] [Storage] [Network] [Security] [Monitoring]      │
└─────────────────────────────────────────────────────────────┘
```

---

#### 6. Sourcing & Footprint

| Capability | Sourcing Model | Primary Location(s) | Rationale |
|---|---|---|---|
| Core Banking Operations | In-house | _HQ, Regional Hub_ | Core competency; regulatory proximity required |
| Application Development | Hybrid (in-house + SI partner) | _HQ, Nearshore_ | Retain architecture control; scale delivery via partner |
| Infrastructure & Cloud | Managed service (cloud provider) | _Cloud region(s)_ | Leverage hyperscaler scale, SLAs, and managed services |
| L1 Service Desk | Outsourced | _Offshore hub_ | Cost optimisation; follow-the-sun model |
| L2/L3 Application Support | In-house | _HQ, Regional Hub_ | Deep product knowledge required; incident resolution speed |
| Data Engineering | Hybrid (in-house + contractor) | _HQ_ | Retain data governance; augment for peak demand |
| Testing / QA | Hybrid (in-house + managed testing) | _HQ, Nearshore_ | Retain test strategy; scale execution via partner |
| Cybersecurity | Hybrid (in-house SOC + MSSP) | _HQ, SOC provider_ | 24/7 coverage; specialised threat intelligence via MSSP |
| Regulatory Reporting | In-house | _HQ_ | Regulatory accountability; cannot outsource compliance ownership |

---

#### 7. Performance & Risk Anchors

| KPI Category | Metric | Baseline (Current) | Target (Steady State) | Measurement Frequency |
|---|---|---|---|---|
| Availability | Core banking system uptime | _99.5%_ | _99.95%_ | Daily |
| Incident Management | Mean Time to Resolve (MTTR) — P1 incidents | _4 hours_ | _1 hour_ | Per incident |
| Incident Management | P1 incidents per month | _8_ | _< 2_ | Monthly |
| Change Management | Change success rate | _85%_ | _95%_ | Monthly |
| Customer Experience | Net Promoter Score (NPS) | _32_ | _>= 45_ | Quarterly |
| Payments | Straight-through processing rate | _88%_ | _98%_ | Daily |
| Data Quality | Overall DQ scorecard (weighted average) | _92%_ | _>= 98%_ | Monthly |
| Capacity | Peak transaction throughput | _500 TPS_ | _2,000 TPS_ | Load test quarterly |
| Cost | Cost per transaction | _$0.45_ | _$0.20_ | Monthly |
| People | Employee engagement score | _65%_ | _>= 75%_ | Annual |
| Compliance | Regulatory findings (critical/major) | _3 per year_ | _0 per year_ | Per audit |

---

#### 8. Change Roadmap Snapshot

| Wave | Timeline | Scope | Key Milestone | Dependencies |
|---|---|---|---|---|
| Wave 0 — Foundation | Months 1-3 (Hypercare) | Stabilise go-live; establish L1/L2/L3 support; activate monitoring | Hypercare exit criteria met | Go-live completion |
| Wave 1 — Optimise | Months 4-6 | Process optimisation; automation of top-10 manual processes; SLA baselining | Automation benefits realised (first tranche) | Stable production operations |
| Wave 2 — Enhance | Months 7-12 | Advanced analytics activation; continuous improvement framework embedded; first platform upgrade | First Temenos upgrade completed | Automation foundations |
| Wave 3 — Scale | Months 13-18 | Expanded digital channels; API partner onboarding; target operating metrics achieved | All TOM KPIs at target | Stable upgrade cadence |
| Wave 4 — Innovate | Months 19-24 | Innovation lab; AI/ML use cases in production; TOM review and refresh | TOM v2.0 design initiated | Mature operating model |

---

### DETAILED APPENDICES

---

#### Appendix A: Detailed Organisation Design

**L3 Organisation Charts:**
- Provide L3 org charts per L2 function (see Macro-Structure above for L1-L3 skeleton)
- Each L3 role includes: role title, grade, reporting line, direct reports, key accountabilities

**Spans & Layers Analysis:**

| Level | Role | Span of Control | Target Span | Action Required |
|---|---|---|---|---|
| L1 | COO | 5 direct reports | 5-7 | Within target |
| L2 | Head of Technology | 3 direct reports | 5-7 | Consider consolidation or additional L3 roles |
| L2 | Head of Operations | 3 direct reports | 5-7 | Consider consolidation or additional L3 roles |
| L3 | Platform Engineering Lead | 12 direct reports | 8-10 | Split into two sub-teams |
| L3 | Payments Operations Manager | 25 direct reports | 10-15 | Introduce team lead layer |

**RACI Matrix (Key Processes):**

| Process | COO | Head of Tech | Head of Ops | Journey Owner | Release Mgr | Support Lead |
|---|---|---|---|---|---|---|
| Incident Management (P1) | I | A | R | I | I | R |
| Change Management | I | A | C | C | R | I |
| Release Deployment | I | A | I | C | R | C |
| Problem Management | I | A | C | I | I | R |
| SLA Reporting | A | C | R | I | I | C |
| Continuous Improvement | A | C | C | R | I | C |
| Temenos Upgrade Planning | I | A | C | C | R | C |
| Data Quality Monitoring | I | C | C | I | I | R |

**Legend:** R = Responsible, A = Accountable, C = Consulted, I = Informed

---

#### Appendix B: People & Capability Plan

| Capability Family | Current FTE | Target FTE | Gap | Build / Buy / Borrow | Timeline | Notes |
|---|---|---|---|---|---|---|
| Core Banking SME (Temenos T24) | 8 | 12 | +4 | Build (2) + Buy (2) | Months 1-6 | Upskill existing + hire experienced |
| Platform Engineering (Cloud, DevOps) | 5 | 10 | +5 | Buy (3) + Borrow (2) | Months 1-3 | Contractor bridge while hiring |
| Application Support (L2/L3) | 10 | 15 | +5 | Build (3) + Buy (2) | Months 1-6 | Knowledge transfer from SI partner |
| Data Engineering | 3 | 6 | +3 | Buy (2) + Borrow (1) | Months 1-4 | Specialist hire + contractor |
| Service Desk (L1) | 0 | 20 | +20 | Borrow (20) | Month 1 | Outsourced; vendor ramp-up |
| Business Analysis | 6 | 4 | -2 | Redeploy | Months 4-6 | Transition to journey owner / product roles |
| Testing / QA | 8 | 5 | -3 | Redeploy | Months 4-6 | Shift to automation; redeploy manual testers |
| Cybersecurity | 2 | 4 | +2 | Buy (1) + Borrow (1) | Months 1-3 | MSSP augmentation |
| Change Management | 4 | 2 | -2 | Redeploy | Months 7-12 | Post-transformation wind-down |
| _Capability nnn_ | | | | | | |

**Build / Buy / Borrow definitions:**
- **Build** — Upskill existing staff through training, mentoring, and on-the-job development
- **Buy** — Hire permanent employees externally
- **Borrow** — Engage contractors, consultants, or outsourced providers for temporary or ongoing capacity

---

#### Appendix C: Risk & Controls Framework

| Risk Category | Risk Description | Owner | Likelihood (L/M/H) | Impact (L/M/H) | Key Control | Assurance Mechanism | Residual Risk |
|---|---|---|---|---|---|---|---|
| Operational | Core banking system outage impacting customer services | Head of Technology | M | H | Active-active architecture; automated failover; DR tested quarterly | Quarterly DR test; monthly availability reporting | Low |
| People | Key person dependency on Temenos SMEs | Head of Technology | H | H | Cross-training programme; documented runbooks; vendor support contract | Quarterly knowledge assessment; succession planning review | Medium |
| Cyber | Data breach or ransomware attack | CISO | M | H | Defence in depth; endpoint detection; SOC monitoring 24/7; incident response plan | Annual penetration testing; red team exercises; phishing simulations | Medium |
| Regulatory | Non-compliance with regulatory reporting requirements | CRO | L | H | Automated regulatory reporting; pre-submission validation; compliance calendar | Internal audit annual review; regulatory exam readiness | Low |
| Vendor | SI partner or outsourced provider underperformance | Head of Operations | M | M | SLA-backed contracts; monthly performance reviews; exit clauses | Monthly SLA dashboard; quarterly business reviews | Low |
| Data | Data quality degradation post-migration | Head of Data | M | M | Automated DQ monitoring; data stewardship model; quality dashboards | Monthly DQ scorecard; quarterly data governance council review | Low |
| Change | Failed or disruptive production changes | Release Manager | M | M | CAB approval; automated deployment pipeline; rollback capability; change freeze windows | Weekly change success rate tracking; post-implementation reviews | Low |
| Financial | Operating costs exceed budget | CFO | L | M | Lean budgeting; monthly cost tracking; variance analysis | Monthly finance review; quarterly reforecast | Low |

---

#### Appendix D: Business Case Summary

| Category | Year 1 | Year 2 | Year 3 | Total |
|---|---|---|---|---|
| **Investment** | | | | |
| Technology (platform, infrastructure, licences) | _($3.5M)_ | _($1.2M)_ | _($0.8M)_ | _($5.5M)_ |
| People (hiring, training, contractors) | _($2.0M)_ | _($1.0M)_ | _($0.5M)_ | _($3.5M)_ |
| Change management & communications | _($0.5M)_ | _($0.3M)_ | _($0.1M)_ | _($0.9M)_ |
| Contingency (15%) | _($0.9M)_ | _($0.4M)_ | _($0.2M)_ | _($1.5M)_ |
| **Total Investment** | **($6.9M)** | **($2.9M)** | **($1.6M)** | **($11.4M)** |
| **Cost Savings** | | | | |
| Process automation (manual effort reduction) | _$1.0M_ | _$2.5M_ | _$3.5M_ | _$7.0M_ |
| Shared services consolidation | _$0.5M_ | _$1.5M_ | _$2.0M_ | _$4.0M_ |
| Vendor rationalisation | _$0.0M_ | _$0.5M_ | _$1.0M_ | _$1.5M_ |
| Incident reduction (avoided cost) | _$0.2M_ | _$0.5M_ | _$0.8M_ | _$1.5M_ |
| **Total Cost Savings** | **$1.7M** | **$5.0M** | **$7.3M** | **$14.0M** |
| **Revenue Uplift** | | | | |
| Faster time-to-market (new product revenue) | _$0.0M_ | _$1.0M_ | _$2.5M_ | _$3.5M_ |
| Improved customer retention (reduced churn) | _$0.5M_ | _$1.0M_ | _$1.5M_ | _$3.0M_ |
| **Total Revenue Uplift** | **$0.5M** | **$2.0M** | **$4.0M** | **$6.5M** |
| | | | | |
| **Net Benefit** | **($4.7M)** | **$4.1M** | **$9.7M** | **$9.1M** |

**Key financial metrics:**
- Payback period: ~18 months
- 3-year ROI: 80%
- NPV (at 8% discount rate): $6.2M

---

#### Appendix E: Stress Test Results

**Stress Test Methodology:**
Apply "day in the life" scenarios against the proposed TOM to validate that the operating model can handle realistic operational demands, edge cases, and crisis situations.

| Scenario ID | Scenario Description | Dimension Tested | Expected Outcome | Actual Outcome | Pass/Fail | Remediation |
|---|---|---|---|---|---|---|
| ST-001 | P1 incident during peak trading hours (core banking down) | Incident management, escalation, communication | L1 detects within 5 min; L2 engaged within 15 min; L3 resolves within 60 min; comms sent to affected customers | _To be tested_ | _Pending_ | |
| ST-002 | Temenos quarterly upgrade with 200+ change items | Change management, release process, testing | CAB reviews within 1 week; regression testing completed in 3 days; deployment within maintenance window | _To be tested_ | _Pending_ | |
| ST-003 | Key Temenos SME resigns with 4 weeks notice | People, knowledge management, succession | Knowledge transfer completed; replacement identified; no service degradation | _To be tested_ | _Pending_ | |
| ST-004 | Regulatory exam with 48-hour data request | Data governance, reporting, compliance | All requested data produced within 24 hours; no findings | _To be tested_ | _Pending_ | |
| ST-005 | Outsourced L1 provider experiences 50% staff attrition | Vendor management, BCP, service continuity | Backup resources activated within 24 hours; SLAs maintained | _To be tested_ | _Pending_ | |
| ST-006 | Ransomware attack encrypts production file shares | Cybersecurity, incident response, DR | SOC detects within 15 min; containment within 1 hour; recovery from backup within 4 hours | _To be tested_ | _Pending_ | |
| ST-007 | Month-end processing volume 3x normal (quarter-end + regulatory) | Capacity, performance, prioritisation | System handles peak without degradation; all reports delivered on time | _To be tested_ | _Pending_ | |
| ST-008 | Two concurrent P1 incidents across different value streams | Incident management, resource allocation, prioritisation | Both incidents managed in parallel; no resource conflict; both resolved within SLA | _To be tested_ | _Pending_ | |

**Stress test cadence:**
- Initial: Pre-TOM activation (during Stage 8 Hypercare)
- Ongoing: Quarterly stress test rotation (2 scenarios per quarter)
- Trigger-based: After any significant TOM change or organisational restructure

---

## Required Skills

### TOM Design
- 8 design dimensions (strategy link, design principles, value streams, macro-structure, technology, sourcing, performance, change roadmap)
- Value stream mapping and journey-led organisation design
- Current-state assessment and gap analysis
- TOM maturity models and progressive activation

### Organisation Design
- Macro-structure selection (functional, divisional, matrix, platform-based)
- Spans and layers analysis and optimisation
- Role design and job family architecture
- RACI design for key processes
- Decision rights frameworks (RAPID, DACI)

### Strategy Translation
- Strategic intent decomposition into operating requirements
- Design principle formulation and implication mapping
- Alignment of TOM dimensions to strategic objectives
- Stakeholder engagement for strategy validation

### Financial Modelling
- Business case construction (investment, savings, revenue uplift, net benefit)
- Total Cost of Ownership (TCO) calculation
- Benefit quantification and tracking methodology
- Investment phasing and funding models
- Sensitivity analysis and scenario modelling

### Change Management
- Stakeholder mapping and engagement planning
- Communications planning for TOM transition
- Culture shift and behavioural change programmes
- Resistance management and adoption measurement
- Training needs analysis and delivery planning

### Stress Testing
- Scenario design (operational, crisis, capacity, people)
- "Day in the life" simulation methodology
- Capacity planning and peak load modelling
- Remediation tracking and re-testing
- Continuous validation cadence design

### Integration
- Cross-dimension contradiction identification and resolution
- End-to-end consistency checks across all TOM dimensions
- Transition architecture (bridge between current and target state)
- Dependency mapping between TOM components

---

## Toolchain

| Tool | Purpose |
|---|---|
| PowerPoint / Miro | One-page TOM summary, visual architecture diagrams, stakeholder presentations |
| Org design tools (e.g., Orgvue, Nakisa) | Organisation modelling, spans & layers analysis, scenario planning |
| Excel / Google Sheets | Financial modelling, business case, TCO analysis, FTE planning, DQ scorecards |
| Confluence / Wiki | Detailed TOM documentation, appendices, RACI matrices, process documentation |
| Visio / Lucidchart | Process maps, technology architecture diagrams, support escalation flows |
| ServiceNow | Incident, change, and problem management process implementation |
| Jira / Azure DevOps | Continuous improvement backlog, kaizen tracking, release management |
