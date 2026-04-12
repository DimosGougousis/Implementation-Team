# Implementation Team OS — Design Specification

**Date:** 2026-04-11
**Author:** Dimos Gougousis
**Repo:** https://github.com/DimosGougousis/Implementation-Team
**Local Path:** `C:\Users\dimos\Implementation\`
**Status:** Draft

---

## 1. Problem Statement

The proposed Implementation Team repo structure has domain folders and agents but fails to capture:

1. **Delivery Stages** — No explicit 8-stage Temenos lifecycle with formal stage gates tracking programme progression.
2. **Contribution & Value to the Bank** — No mechanism to demonstrate personal deliverables, decisions influenced, risks mitigated, and value created at each stage, targeting Steering Committee / CTO audiences.
3. **Concrete Deliverable Files** — Artefacts were represented as single template files, not as folders containing the constituent outputs actually produced (API registers, event channel maps, SLA matrices, etc.).

## 2. Design Decisions

| Decision | Choice | Rationale |
|---|---|---|
| Architecture | Approach C — Matrix | Separates stage gates (progression), artefact folders (content), and contribution log (value). Clean many-to-many mapping. |
| Lifecycle model | 8-stage Temenos standard | Discovery → Fit-Gap & Process Design → Solution Architecture → Build & Configure → Testing → Data Migration → Cutover → Hypercare |
| Tracking | Per-programme folders | Each programme gets STAGE-STATUS.md + CONTRIBUTION-LOG.md + stages/ + artefacts/ |
| Value audience | Steering Committee / CTO | Executive-level: strategic value, risk mitigation, cost avoidance, programme health |
| Agents | Placeholders only | Name + one-liner stubs. Each agent workshopped individually later. |
| Artefact templates | Rich folders with deliverable files | Each of the 8 artefacts is a folder with ~5-8 constituent output files |
| Scope | Minimal skeleton + rich artefact templates | Folder tree, root CLAUDE.md, agent placeholder list, lifecycle framework, artefact folders. No .github CI, no full agent definitions. |
| Independence | Fully independent from Product Office | Separate repo, separate governance, separate workspace entry. Cross-repo links via markdown only. |

## 3. CV Competency → Artefact → Stage Mapping

| # | CV Competency | Primary Artefact | Primary Stages | Updated At |
|---|---|---|---|---|
| 1 | ADRs & Traceability | Architecture Decision Records | 3-Solution Architecture | 4, 5, 6 |
| 2 | Target-State Architecture & Systems Thinking | Target-State Reference Architecture | 1-Discovery, 3-Solution Architecture | 4 |
| 3 | Fit-Gap Analysis & Customisation Governance | Fit-Gap Register & Customisation Budget | 2-Fit-Gap & Process Design | 3, 4 |
| 4 | RESTful & Event-Driven Integration Design | Integration Dependency Map | 3-Solution Architecture | 4, 5 |
| 5 | Data Migration & Quality Assurance | Data Quality Scorecard | 6-Data Migration | 2, 5 |
| 6 | Acceptance Criteria & Automated Evaluations | Test Strategy & KPI Dashboard | 5-Testing | 3 |
| 7 | Programme Structuring & Agile at Scale | Cutover Runbook & Rehearsal Log | 7-Cutover | 5, 6 |
| 8 | Post-Transformation Operating Model Design | Post-Go-Live Operating Model | 8-Hypercare | 3 |
| 9 | Stakeholder & Vendor Orchestration | Cross-cutting | All stages | CONTRIBUTION-LOG.md |
| 10 | Business Process Alignment & Redesign | Cross-cutting | 1, 2, 3 | CONTRIBUTION-LOG.md |

## 4. Repo Structure

```
Implementation/
├── CLAUDE.md                          # Lean entry point
├── AGENTS.md                          # Non-Claude mirror
├── README.md                          # Human onboarding
├── .gitignore
│
├── governance/
│   ├── framework.md                   # Adapted for implementation programmes
│   └── directives/                    # Placeholder — populated when agents workshopped
│
├── agents/
│   ├── CLAUDE.md                      # Agent registry: name + one-liner + status:placeholder
│   ├── fit-gap-analyst.agent.md
│   ├── integration-architect.agent.md
│   ├── data-migration-lead.agent.md
│   ├── test-strategist.agent.md
│   ├── cutover-manager.agent.md
│   ├── design-authority.agent.md
│   ├── programme-governance.agent.md
│   ├── operating-model.agent.md
│   ├── dashboard-reporting.agent.md
│   └── integration-orchestrator.agent.md
│
├── artefacts/
│   ├── CLAUDE.md                      # "These are the gold-standard deliverables"
│   │
│   ├── 01-architecture-decision-records/
│   │   ├── CLAUDE.md
│   │   ├── _template.md               # ADR template (Context, Decision, Options Rejected, Consequences)
│   │   ├── adr-register.md            # Master index: ADR# → title → status → date → linked requirement
│   │   ├── traceability-matrix.md     # Requirement → ADR → implementation mapping
│   │   └── decisions/
│   │       └── .gitkeep
│   │
│   ├── 02-target-state-reference-architecture/
│   │   ├── CLAUDE.md
│   │   ├── business-capability-map.md # Bank capabilities → Transact packaged business capabilities
│   │   ├── api-register.md            # Full API catalogue (Transact APIs, custom, third-party)
│   │   ├── event-channels.md          # Topics, producers, consumers, schemas
│   │   ├── infrastructure-stack.md    # Servers, middleware, DB, network
│   │   ├── component-model.md         # Logical component diagram (Mermaid)
│   │   ├── security-architecture.md   # Auth, encryption, key management, network zones
│   │   └── technology-standards.md    # Approved tech stack, version matrix
│   │
│   ├── 03-fit-gap-register/
│   │   ├── CLAUDE.md
│   │   ├── fit-gap-register.md        # Master register: module → requirement → Fit/Gap/Partial → score
│   │   ├── customisation-budget.md    # Hard ceiling tracker: budget consumed vs remaining
│   │   ├── customisation-requests/
│   │   │   └── _template.md           # Request, justification, cost, risk, alternatives, decision
│   │   ├── module-assessments/
│   │   │   └── _template.md           # Per Transact module assessment
│   │   └── workshop-notes/
│   │       └── _template.md
│   │
│   ├── 04-integration-dependency-map/
│   │   ├── CLAUDE.md
│   │   ├── integration-register.md    # All system-to-system touchpoints
│   │   ├── dependency-graph.md        # Directed graph (Mermaid) with protocol, SLA, owner
│   │   ├── api-contracts/
│   │   │   └── _template.md           # Per-integration: endpoint, payload, auth, SLA
│   │   ├── event-contracts/
│   │   │   └── _template.md           # Per-event: topic, schema, producer, consumer, retry
│   │   ├── adapter-strategy.md        # Temenos fulfilment service model, middleware patterns
│   │   ├── sla-matrix.md              # System x system SLA grid
│   │   └── owner-matrix.md            # System x owner x support contact
│   │
│   ├── 05-data-quality-scorecard/
│   │   ├── CLAUDE.md
│   │   ├── quality-scorecard.md       # Domain-by-domain quality metrics
│   │   ├── profiling-results/
│   │   │   └── _template.md
│   │   ├── cleansing-rules/
│   │   │   └── _template.md
│   │   ├── mapping-specifications/
│   │   │   └── _template.md           # Source → Transact domain field mappings
│   │   ├── quality-gates.md           # Per-milestone gating thresholds
│   │   ├── migration-strategy.md      # End-to-end migration approach
│   │   └── rehearsal-results/
│   │       └── _template.md
│   │
│   ├── 06-test-strategy-kpi-dashboard/
│   │   ├── CLAUDE.md
│   │   ├── test-strategy.md           # Four-phase: Unit → Integration → SIT/Perf → UAT
│   │   ├── entry-exit-criteria.md     # Per-phase gates
│   │   ├── kpi-dashboard.md           # Defect density, pass rate, cycle time
│   │   ├── defect-taxonomy.md         # Severity/priority classification, SLA per category
│   │   ├── test-data-strategy.md      # Sourcing, masking, refresh
│   │   ├── environment-matrix.md      # Test environments: purpose, data, access, refresh
│   │   └── test-cycles/
│   │       └── _template.md
│   │
│   ├── 07-cutover-runbook/
│   │   ├── CLAUDE.md
│   │   ├── runbook.md                 # Minute-by-minute cutover script
│   │   ├── rollback-triggers.md       # Conditions that trigger rollback
│   │   ├── go-nogo-criteria.md        # Decision framework
│   │   ├── communication-plan.md      # Who gets told what, when
│   │   ├── rehearsal-log.md           # Per-rehearsal results with timing deltas
│   │   ├── rehearsals/
│   │   │   └── _template.md
│   │   └── checklist.md               # Pre-cutover readiness checklist
│   │
│   └── 08-post-go-live-operating-model/
│       ├── CLAUDE.md
│       ├── target-operating-model.md  # Run-state structure: org chart, responsibilities
│       ├── support-tiers.md           # L1/L2/L3 definitions, escalation paths, SLAs
│       ├── incident-management.md     # Incident classification, response process
│       ├── change-management.md       # Post-go-live change request process
│       ├── upgrade-cadence.md         # Temenos release adoption plan
│       ├── hypercare-plan.md          # Stabilisation → steady-state handover
│       └── continuous-improvement.md  # Improvement backlog, feedback loops
│
├── lifecycle/
│   ├── CLAUDE.md                      # Stage overview, gate framework
│   ├── overview.md                    # Visual lifecycle + stage→artefact matrix
│   └── gates/
│       ├── 01-discovery.gate.md
│       ├── 02-fit-gap-process-design.gate.md
│       ├── 03-solution-architecture.gate.md
│       ├── 04-build-configure.gate.md
│       ├── 05-testing.gate.md
│       ├── 06-data-migration.gate.md
│       ├── 07-cutover.gate.md
│       └── 08-hypercare.gate.md
│
├── pipeline/
│   ├── CLAUDE.md
│   ├── _template/
│   │   ├── STAGE-STATUS.md            # Current stage, gate matrix, dates
│   │   ├── CONTRIBUTION-LOG.md        # Value per stage + artefact
│   │   ├── stages/
│   │   │   ├── 01-discovery-gate.md
│   │   │   ├── 02-fit-gap-gate.md
│   │   │   ├── 03-architecture-gate.md
│   │   │   ├── 04-build-gate.md
│   │   │   ├── 05-testing-gate.md
│   │   │   ├── 06-migration-gate.md
│   │   │   ├── 07-cutover-gate.md
│   │   │   └── 08-hypercare-gate.md
│   │   └── artefacts/
│   │       ├── adrs/
│   │       ├── target-state-architecture.md
│   │       ├── fit-gap-register.md
│   │       ├── integration-dependency-map.md
│   │       ├── data-quality-scorecard.md
│   │       ├── test-strategy-kpi-dashboard.md
│   │       ├── cutover-runbook.md
│   │       └── operating-model.md
│   ├── active/
│   └── archive/
│
├── analytics/
│   └── CLAUDE.md
│
├── team/
│   └── directory.md
│
├── .claude/
│   ├── CLAUDE.md
│   ├── skills/                        # Placeholder — built when agents workshopped
│   ├── commands/
│   │   ├── new-programme.md           # /new-programme <name>
│   │   └── impl-status.md            # /impl-status (read-only dashboard)
│   └── plans/
│
└── .vscode/
    └── settings.json
```

## 5. Stage Gate Template

Each gate file in `lifecycle/gates/` follows this structure:

```markdown
---
stage: <number>
name: <stage name>
artefacts-created: [list]
artefacts-updated: [list]
---

# Stage <N>: <Name>

## Purpose
What this stage achieves in the programme.

## Entry Criteria
- [ ] Prerequisite 1 (from previous gate)
- [ ] Prerequisite 2

## Key Activities
1. Activity with your role and contribution
2. ...

## Artefacts Produced / Updated
| Artefact | Action | What Changes |
|---|---|---|
| Target-State Architecture | Created / Updated | Description |

## Exit Criteria (Gate)
- [ ] Gate criterion 1
- [ ] Gate criterion 2

## Steering Committee Checkpoint
What is reported at this gate.

## Your Contribution at This Stage
What you personally deliver, decisions you influence, risks you mitigate.
Maps to CV competencies exercised.
```

## 6. CONTRIBUTION-LOG.md Template

Per-programme value evidence document targeting Steering Committee / CTO:

```markdown
# Contribution Log — <Programme Name>

## Executive Summary
One-paragraph value statement: what you delivered, key decisions influenced,
risks mitigated, cost avoided.

## Contribution by Stage

### Stage 1: Discovery
| Date | Contribution | Artefact(s) | CV Competency | Value to Bank |
|---|---|---|---|---|
| YYYY-MM-DD | Led stakeholder workshops... | Target-State Architecture | Systems Thinking | Aligned 5 departments... |

### Stage 2: Fit-Gap & Process Design
(same table format)

... (all 8 stages)

## Key Decisions Influenced
| Decision | Context | Your Recommendation | Outcome | ADR Ref |
|---|---|---|---|---|

## Risks Mitigated
| Risk | Severity | Your Action | Result |
|---|---|---|---|

## Cumulative Value Summary
| Metric | Value |
|---|---|
| Customisations prevented | N (saving £Xm) |
| ADRs authored | N |
| Gate reviews led | N |
| Data quality improvement | X% → Y% |
```

## 7. STAGE-STATUS.md Template

Programme status dashboard with artefact matrix:

```markdown
# Programme Status — <Name>

## Current Stage: <N — Name>
**Gate Status**: In Progress / Awaiting Gate Review / Passed
**Target Date**: YYYY-MM-DD

## Stage-Artefact Matrix

| Stage | Status | ADRs | Ref Arch | Fit-Gap | Int Map | DQ Score | Test KPI | Cutover | Op Model |
|---|---|---|---|---|---|---|---|---|---|
| 1. Discovery | ✅ Passed | - | Created | - | - | - | - | - | - |
| 2. Fit-Gap | ✅ Passed | - | - | Created | - | Started | - | - | - |
| 3. Architecture | 🔄 Active | Created | Updated | Updated | Created | - | Framework | - | Started |
| 4. Build | ⬜ Pending | | | | | | | | |
| 5. Testing | ⬜ Pending | | | | | | | | |
| 6. Migration | ⬜ Pending | | | | | | | | |
| 7. Cutover | ⬜ Pending | | | | | | | | |
| 8. Hypercare | ⬜ Pending | | | | | | | | |

## Gate History
| Stage | Gate Date | Decision | Key Issues | Attendees |
|---|---|---|---|---|
```

## 8. Agent Placeholders

10 agents, each as a stub file:

```markdown
---
name: <agent-name>
description: <one-liner>
status: placeholder
owner-artefacts: [list of artefact folders this agent will own]
primary-stages: [list of stages this agent is active in]
---

# <Agent Name>

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent
<One paragraph describing what this agent will do>

## Owns
- artefacts/<folder>

## Active At
- Stage N: <name>
```

| Agent | Intent | Owns | Active Stages |
|---|---|---|---|
| fit-gap-analyst | Lead fit-gap workshops, score customisations | 03-fit-gap-register/ | 2, 3, 4 |
| integration-architect | E2E integration architecture, adapter strategy | 04-integration-dependency-map/ | 3, 4, 5 |
| data-migration-lead | Strategy, profiling, cleansing, rehearsals | 05-data-quality-scorecard/ | 2, 5, 6 |
| test-strategist | 4-phase test strategy, define KPIs and gates | 06-test-strategy-kpi-dashboard/ | 3, 5 |
| cutover-manager | Runbook, rehearsals, go/no-go | 07-cutover-runbook/ | 5, 6, 7 |
| design-authority | ADRs, design conformance, customisation governance | 01-architecture-decision-records/ | 3, 4, 5, 6 |
| programme-governance | Workstream structure, RAID, agile ceremonies | lifecycle/ | All |
| operating-model | Post-go-live run-state, support tiers, upgrade cadence | 08-post-go-live-operating-model/ | 3, 8 |
| dashboard-reporting | Implementation KPIs and executive summaries | analytics/, pipeline/*/STAGE-STATUS.md | All |
| integration-orchestrator | Cross-system cascade (Jira/Slack/Drive) | pipeline/ (coordination) | All |

**Note:** The `02-target-state-reference-architecture/` artefact is cross-cutting — owned jointly by design-authority and integration-architect. This will be resolved during agent workshops.

## 9. Commands (Minimal)

Two commands built now:

### `/new-programme <name>`
Creates `pipeline/active/<name>/` with:
- STAGE-STATUS.md (from template, programme name filled in)
- CONTRIBUTION-LOG.md (from template, programme name filled in)
- stages/ (8 gate files, all status: pending)
- artefacts/ (8 placeholder files referencing the rich templates in artefacts/)

### `/impl-status`
Read-only dashboard that scans `pipeline/active/*/STAGE-STATUS.md` and renders:
- Programme list with current stage
- Artefact completion matrix
- Gate history summary

## 10. What Is NOT Built Now

Deferred to agent workshops:
- Full agent definitions (skills, scope, examples, tools)
- Governance directives (approval-gates, design-authority-process, change-control, escalation-matrix, customisation-governance)
- Skills (run-fit-gap-workshop, write-adr, design-migration-strategy, etc.)
- Additional commands (fit-gap, design-review, migration-rehearsal, go-nogo)
- .github/ CI workflows
- CONTRIBUTING.md
- Cross-repo workspace integration with Product Office

## 11. Verification

After scaffold:
1. `tree` confirms structure matches this spec
2. Root CLAUDE.md lists all 10 agents with one-liners
3. All 8 artefact folders exist with their constituent deliverable files
4. All 8 gate definitions exist in lifecycle/gates/
5. pipeline/_template/ contains STAGE-STATUS.md, CONTRIBUTION-LOG.md, stages/, artefacts/
6. `/new-programme test` creates pipeline/active/test/ with correct structure
7. `/impl-status` renders empty dashboard
8. Git init succeeds, push to GitHub succeeds
