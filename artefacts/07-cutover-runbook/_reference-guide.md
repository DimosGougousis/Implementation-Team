# Programme Structuring & Agile at Scale — Reference Guide

**CV Competency:** Programme Structuring & Agile at Scale
**Primary Artefact:** artefacts/07-cutover-runbook/
**Primary Stage:** 7 — Cutover
**Updated At:** 5, 6

---

## What This Competency Covers

The ability to structure complex implementation programmes with clear governance, cadences, and delivery frameworks that scale across multiple workstreams, vendors, and stakeholder groups — from programme charter through to release management and continuous improvement.

## Key Skills

- Defining programme charter and objectives (OKRs)
- Mapping value streams and product taxonomies
- Designing org models and roles (ARTs / Tribes / Squads)
- Establishing cadences and ceremonies (PI Planning, Scrums of Scrums, System Demos)
- Structuring backlogs with flow policies (DoR / DoD)
- Building delivery roadmaps and dependency management plans
- Maintaining risk/RAID logs and decision logs
- Managing release management and change control processes
- Tracking metrics and reporting (DORA, flow efficiency, predictability)
- Aligning tooling, integrations, budgeting, and vendor management
- Leading people and change management

## When to Apply

| Stage | Activity |
|---|---|
| 1 — Discovery | Define programme charter, OKRs, and org model |
| 2 — Fit-Gap | Establish cadences, ceremonies, and backlog structure |
| 3 — Solution Architecture | Build delivery roadmap, dependency management, risk/RAID |
| 4 — Build & Configure | Execute PI Planning, manage flow, track DORA metrics |
| 5 — Testing | System demos, defect flow management, predictability tracking |
| 6 — Data Migration | Release management for migration waves |
| 7 — Cutover | Change control, go/no-go governance |
| 8 — Hypercare | Steady-state handover, continuous improvement |

## Programme Charter & Objectives

### OKR Template

| Objective | Key Result | Target | Current | Owner |
|---|---|---|---|---|
| Deliver Transact on time | Go-live by [date] | [date] | | Programme Lead |
| Deliver within budget | Customisation spend ≤ £X | £X | £ | Finance Lead |
| Achieve quality targets | UAT pass rate ≥ 95% | 95% | % | Test Lead |
| Enable business adoption | User training complete | 100% | % | Change Lead |

## Value Streams & Product Taxonomy

| Value Stream | Products | Workstream | Owner |
|---|---|---|---|
| Retail Banking | Accounts, Payments, Lending | WS-1 | |
| Corporate Banking | Trade Finance, Cash Management | WS-2 | |
| Channels | Internet, Mobile, API | WS-3 | |
| Core Platform | Transact Config, Data, Integration | WS-4 | |

## Org Model & Roles

| Role | Responsibility | Reports To |
|---|---|---|
| Programme Lead | Overall delivery, Steering Committee | CTO |
| Workstream Lead | Workstream delivery, team coordination | Programme Lead |
| Product Owner | Backlog prioritisation, acceptance | Workstream Lead |
| Scrum Master | Ceremony facilitation, impediment removal | Workstream Lead |
| System Architect | Technical decisions, cross-WS alignment | Programme Lead |

### Scaling Model

| Model | Use Case | Structure |
|---|---|---|
| ART (Agile Release Train) | Cross-workstream delivery | 5–12 teams, shared cadence |
| Tribe | Domain-aligned delivery | Multiple squads, shared mission |
| Squad | Feature team | 5–9 people, end-to-end ownership |

## Cadences & Ceremonies

| Ceremony | Frequency | Duration | Participants | Purpose |
|---|---|---|---|---|
| PI Planning | Quarterly | 2 days | All teams | Plan next increment, align dependencies |
| Scrum of Scrums | 2x weekly | 30 min | Scrum Masters | Cross-team impediment resolution |
| System Demo | Bi-weekly | 1 hour | Stakeholders | Show integrated increment |
| Inspect & Adapt | Quarterly | Half day | All teams | Retrospective + improvement |
| Daily Standup | Daily | 15 min | Squad | Coordination, blockers |
| Sprint Review | Per sprint | 1 hour | Squad + PO | Demo, accept/reject |

## Backlog Structure & Flow Policies

### Definition of Ready (DoR)
- [ ] User story has clear acceptance criteria
- [ ] Dependencies identified and resolved
- [ ] Estimated by the team
- [ ] Fits within a single sprint

### Definition of Done (DoD)
- [ ] Code complete and peer reviewed
- [ ] Unit tests pass (≥ 80% coverage)
- [ ] Integration tests pass
- [ ] Documentation updated
- [ ] Deployed to SIT environment

### Flow Policies

| Policy | Rule |
|---|---|
| WIP Limit | Max 3 stories per developer |
| Blocked | Escalate after 24 hours |
| Carry-over | Requires PO approval and re-estimation |

## Delivery Roadmap & Dependency Management

### Roadmap Structure

| Quarter | Milestone | Workstreams | Key Dependencies |
|---|---|---|---|
| Q1 | Discovery & Fit-Gap complete | WS-1, WS-2, WS-3, WS-4 | |
| Q2 | Architecture approved, Build starts | WS-4 → WS-1, WS-2 | Core platform first |
| Q3 | SIT complete, UAT starts | All | Integration readiness |
| Q4 | Go-Live | All | Data migration, cutover |

### Dependency Management

| Dependency | From | To | Type | Mitigation |
|---|---|---|---|---|
| | | | Hard / Soft | |

## Risk/RAID & Decision Logs

### RAID Template

| Type | Item | Owner | Status | Due | Notes |
|---|---|---|---|---|---|
| Risk | | | Open / Closed | | |
| Assumption | | | Validated / Invalid | | |
| Issue | | | Open / Closed | | |
| Dependency | | | Resolved / Pending | | |

### Decision Log

| ID | Decision | Date | Context | Decided By | ADR Ref |
|---|---|---|---|---|---|
| | | | | | |

## Release Management & Change Control

| Release Type | Frequency | Approval | Lead Time |
|---|---|---|---|
| PI Release | Quarterly | Steering Committee | 2 weeks |
| Sprint Release | Bi-weekly | Workstream Lead | 3 days |
| Hotfix | As needed | Programme Lead | 4 hours |

### Change Control Process

1. Change request submitted (standard / normal / emergency)
2. Impact assessment (scope, cost, timeline, risk)
3. Approval (CAB for normal, Programme Lead for standard, Steering Committee for emergency)
4. Schedule in release window
5. Implement, verify, close

## Metrics & Reporting

### DORA Metrics

| Metric | Target | Current | Trend |
|---|---|---|---|
| Deployment Frequency | ≥ weekly | | |
| Lead Time for Changes | ≤ 2 days | | |
| Change Failure Rate | ≤ 5% | | |
| Mean Time to Restore | ≤ 4 hours | | |

### Flow Efficiency

| Metric | Target | Current |
|---|---|---|
| Flow Efficiency | ≥ 40% | |
| Cycle Time | ≤ 5 days | |
| Throughput | ≥ 20 stories/sprint | |

### Predictability

| Metric | Target | Current |
|---|---|---|
| PI Predictability | ≥ 80% | |
| Sprint Commitment Met | ≥ 90% | |
| Carry-over Rate | ≤ 10% | |

## Tooling & Integrations

| Tool | Purpose | Integration |
|---|---|---|
| Jira | Backlog, tracking | Confluence, Bitbucket |
| Confluence | Documentation | Jira |
| Bitbucket / GitHub | Source control | CI/CD pipeline |
| Jenkins / Azure DevOps | CI/CD | Jira, Bitbucket |
| Slack / Teams | Communication | Jira notifications |

## Budgeting & Vendor Alignment

| Category | Budget | Spent | Remaining | Notes |
|---|---|---|---|---|
| Internal team | £ | £ | £ | |
| Temenos licences | £ | £ | £ | |
| SI partner | £ | £ | £ | |
| Infrastructure | £ | £ | £ | |
| Contingency | £ | £ | £ | |

### Vendor Alignment

| Vendor | Scope | Contract Type | Key Contact | SLA |
|---|---|---|---|---|
| Temenos | Product + support | Licence + support | | |
| SI Partner | Implementation | T&M / Fixed | | |

## People & Change

| Activity | Owner | Status | Due |
|---|---|---|---|
| Stakeholder impact assessment | Change Lead | | |
| Training needs analysis | Change Lead | | |
| Training delivery | Training Lead | | |
| Communication plan | Comms Lead | | |
| Resistance management | Change Lead | | |
| Adoption measurement | Change Lead | | |

## Quality Checklist

- [ ] Programme charter approved with clear OKRs
- [ ] Value streams and product taxonomy defined
- [ ] Org model and roles documented
- [ ] Cadences and ceremonies established
- [ ] Backlog structure with DoR/DoD in place
- [ ] Delivery roadmap with dependencies mapped
- [ ] RAID log maintained and reviewed regularly
- [ ] Release management and change control processes defined
- [ ] DORA and flow metrics tracked and reported
- [ ] Tooling integrated and team trained
- [ ] Budget tracked with vendor alignment confirmed
- [ ] People and change plan active

## Agent Skills

| Skill | Agent | Description |
|---|---|---|
| `run-pi-planning` | programme-governance | Facilitate PI Planning sessions |
| `track-dora-metrics` | dashboard-reporting | Calculate and report DORA metrics |
| `manage-raid-log` | programme-governance | Update RAID items, flag overdue |
| `sprint-health-check` | dashboard-reporting | Assess sprint predictability and flow |
| `release-readiness` | cutover-manager | Verify release criteria before deployment |

## CV Narrative

> "I structured a X-workstream Temenos Transact implementation programme using SAFe-aligned governance, establishing Y cadences and Z ceremonies across the delivery organisation. DORA metrics improved from X to Y over the programme lifecycle, and PI predictability reached Z% by the third increment."
