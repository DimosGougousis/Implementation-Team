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
│   └── directives/
│       ├── approval-gates.md          # Built in programme-governance workshop (Phase 1)
│       ├── change-control.md          # Built in programme-governance workshop (Phase 1)
│       ├── escalation-matrix.md       # Built in programme-governance workshop (Phase 1)
│       ├── design-authority-process.md# Built in design-authority workshop (Phase 2)
│       └── customisation-governance.md# Built in fit-gap-analyst workshop (Phase 2)
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
│   ├── SKILLS-INVENTORY.md            # Master skills list: all 72/83 skills with agent, stage, status
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

## 9. Agent Hand-off Protocol

Defines how artefacts move between agents during programme execution. Without this protocol, hand-offs are ad-hoc and untracked.

### Hand-off Lifecycle

```
┌─────────────────┐     ┌──────────────────┐     ┌──────────────────┐     ┌───────────────────┐
│ 1. Trigger      │────▶│ 2. Source Agent   │────▶│ 3. Target Agent  │────▶│ 4. Status Update  │
│    Event        │     │    Writes Artefact│     │    Reads & Acks  │     │    in STAGE-STATUS│
└─────────────────┘     └──────────────────┘     └──────────────────┘     └───────────────────┘
```

### Step 1: Trigger Event

A hand-off is initiated when one of the following occurs:

| Trigger | Example |
|---|---|
| Stage gate passed | Discovery gate approved → fit-gap-analyst receives target-state-architecture |
| Artefact completed | ADR signed off → integration-architect receives design constraints |
| Downstream dependency | Fit-gap register finalised → design-authority receives customisation list |
| Scheduled milestone | Sprint boundary → dashboard-reporting pulls latest metrics |

### Step 2: Source Agent Writes Artefact

The source agent:
1. Completes or updates the artefact in `pipeline/active/<programme>/artefacts/`
2. Adds a hand-off entry to the artefact's frontmatter:

```yaml
---
hand-off:
  from: <source-agent>
  to: <target-agent>
  date: YYYY-MM-DD
  artefact: <relative-path>
  trigger: <trigger-event>
  status: pending-acknowledgement
---
```

3. Appends a row to `STAGE-STATUS.md` hand-off log:

```markdown
## Hand-off Log
| Date | From | To | Artefact | Trigger | Status |
|---|---|---|---|---|---|
| YYYY-MM-DD | fit-gap-analyst | design-authority | fit-gap-register.md | Stage 2 gate passed | ⏳ Pending |
```

### Step 3: Target Agent Reads & Acknowledges

The target agent:
1. Reads the artefact and validates it meets their input requirements
2. Updates the hand-off status to `acknowledged` in the artefact frontmatter
3. Updates the row in `STAGE-STATUS.md`:

```markdown
| YYYY-MM-DD | fit-gap-analyst | design-authority | fit-gap-register.md | Stage 2 gate passed | ✅ Acknowledged |
```

4. If the artefact is insufficient, the target agent:
   - Sets status to `rejected` with a reason
   - Creates a blocking issue in the programme's RAID log
   - Notifies programme-governance for escalation

### Step 4: Status Updated in STAGE-STATUS.md

The `STAGE-STATUS.md` hand-off log serves as the single source of truth for all inter-agent transfers. Programme-governance reviews this log at each gate to verify all expected hand-offs completed.

### Hand-off Rules

| Rule | Description |
|---|---|
| No implicit hand-offs | Every transfer must be logged in STAGE-STATUS.md |
| Acknowledgement required | Target agent must explicitly acknowledge within 1 sprint |
| Rejection triggers escalation | Rejected hand-offs go to programme-governance |
| Cross-cutting artefacts | Jointly-owned artefacts require acknowledgement from all owners |
| Gate prerequisite | All stage-entry hand-offs must be acknowledged before gate review |

### Hand-off Matrix (Default)

| Source Agent | Target Agent | Artefact | Trigger |
|---|---|---|---|
| fit-gap-analyst | design-authority | fit-gap-register.md | Stage 2 gate |
| fit-gap-analyst | integration-architect | customisation-list | Stage 2 gate |
| design-authority | integration-architect | adr-register.md | ADR signed |
| integration-architect | data-migration-lead | integration-register.md | Stage 3 gate |
| integration-architect | test-strategist | api-contracts/ | Stage 3 gate |
| data-migration-lead | cutover-manager | migration-strategy.md | Stage 6 gate |
| test-strategist | cutover-manager | entry-exit-criteria.md | Stage 5 gate |
| cutover-manager | operating-model | runbook.md | Stage 7 gate |
| *any agent* | dashboard-reporting | *any artefact* | Milestone |

## 10. Workshop Playbook

Repeatable structure for each of the 11 agent workshops. Ensures consistency across all workshops and prevents agents being shipped without tested skills.

### Workshop Sequence

Agents are workshopped in dependency order:

| Phase | Agents | Rationale |
|---|---|---|
| Phase 1 — Foundation | programme-governance, dashboard-reporting | Governance and reporting must exist before domain agents produce artefacts |
| Phase 2 — Core Domain | fit-gap-analyst, design-authority, integration-architect | These agents produce artefacts that downstream agents depend on |
| Phase 3 — Execution | data-migration-lead, test-strategist, cutover-manager | Consume artefacts from Phase 2 agents, produce execution artefacts |
| Phase 4 — Wrap-up | operating-model, integration-orchestrator | Consume final artefacts, produce steady-state outputs |

### Workshop Steps (Per Agent)

Each workshop follows this 5-step structure:

#### Step 1: Review Agent Spec
- Read the agent placeholder file (`agents/<name>.agent.md`)
- Clarify scope: what artefacts does this agent own? At which stages is it active?
- Identify upstream dependencies (which agents hand off to this agent?)
- Identify downstream consumers (which agents receive from this agent?)
- **Output:** Updated agent spec with confirmed scope, inputs, outputs

#### Step 2: Define Skill Acceptance Criteria
- List all skills this agent needs (target: 6-9 MVP skills per agent)
- For each skill, write:
  - **Name:** Verb-noun format (e.g., `write-adr`, `score-customisation`)
  - **Trigger:** When is this skill invoked?
  - **Inputs:** What artefacts/data does the skill consume?
  - **Outputs:** What artefacts/data does the skill produce?
  - **Acceptance criteria:** 3-5 testable conditions that prove the skill works
  - **Example:** A worked example with sample inputs and expected outputs
- **Output:** Skill definitions added to agent file + SKILLS-INVENTORY.md updated

#### Step 3: Write 1 Skill End-to-End
- Pick the most representative skill for this agent
- Implement it fully: prompt, tools, examples, error handling
- Validate it produces correct output for the worked example from Step 2
- **Output:** One fully implemented skill in `.claude/skills/<skill-name>/SKILL.md`

#### Step 4: Test with a Sample Programme
- Create a test programme in `pipeline/active/test-<agent>/`
- Run the implemented skill against realistic sample data
- Verify:
  - Artefact is produced in the correct location
  - Artefact matches the template structure in `artefacts/`
  - Hand-off protocol is followed (if applicable)
  - SKILLS-INVENTORY.md status updated
- **Output:** Test programme with artefacts, pass/fail documented

#### Step 5: Document
- Update agent file with full definition (skills, scope, tools, examples)
- Update SKILLS-INVENTORY.md: set skill statuses to ✅
- Update `agents/CLAUDE.md` registry: status changed from `placeholder` to `active`
- Record workshop notes in agent file under `## Workshop Log`
- **Output:** Agent fully documented and activated

### Workshop Checklist (Per Agent)

```markdown
## Workshop: <agent-name>
**Date:** YYYY-MM-DD
**Facilitator:** <name>

### Pre-workshop
- [ ] Agent placeholder reviewed
- [ ] Upstream dependencies identified
- [ ] Downstream consumers identified

### Step 1: Review Agent Spec
- [ ] Scope confirmed
- [ ] Inputs/outputs documented
- [ ] Cross-cutting ownership resolved

### Step 2: Define Skill Acceptance Criteria
- [ ] N skills listed (target: 6-9)
- [ ] Each skill has: name, trigger, inputs, outputs, acceptance criteria, example
- [ ] SKILLS-INVENTORY.md updated

### Step 3: Write 1 Skill End-to-End
- [ ] Skill selected: <name>
- [ ] SKILL.md created
- [ ] Worked example passes

### Step 4: Test with Sample Programme
- [ ] Test programme created: pipeline/active/test-<agent>/
- [ ] Artefact produced correctly
- [ ] Template structure matched
- [ ] Hand-off validated (if applicable)

### Step 5: Document
- [ ] Agent file updated with full definition
- [ ] SKILLS-INVENTORY.md statuses updated
- [ ] agents/CLAUDE.md registry updated
- [ ] Workshop log entry added
```

### Agent Activation Success Criteria

An agent is considered **activated** (status: `active`) only when ALL of the following are met:

| # | Criterion | Evidence Required | Verified By |
|---|---|---|---|
| 1 | **All skills have examples** | Each skill in the agent file has at least 1 worked example with sample inputs and expected outputs | Workshop facilitator |
| 2 | **At least 1 artefact produced from a test programme** | `pipeline/active/test-<agent>/` contains a real artefact matching the template in `artefacts/` | Automated check or peer review |
| 3 | **Hand-off to downstream agent validated** | A hand-off entry exists in the test programme's STAGE-STATUS.md with status `✅ Acknowledged` from the downstream agent (or N/A if no downstream) | Programme-governance |
| 4 | **SKILLS-INVENTORY.md updated** | All of the agent's skills show status `✅ Complete` in the inventory | Automated check |
| 5 | **Agent file is not a placeholder** | `agents/<name>.agent.md` contains full definition (skills, scope, tools, examples) — not just a stub | Peer review |

### Activation Gate

```markdown
## Agent Activation Gate — <agent-name>

**Date:** YYYY-MM-DD
**Workshop completed:** [link to workshop checklist]

### Done Definition
- [ ] All skills have examples (criterion 1)
- [ ] At least 1 artefact from test programme (criterion 2)
- [ ] Hand-off validated (criterion 3)
- [ ] SKILLS-INVENTORY.md updated (criterion 4)
- [ ] Agent file fully defined (criterion 5)

**Decision:** ACTIVATED / NEEDS WORK
**Signed off by:** <name>
```

### Governance Directive Integration

Each directive is a deliverable of its owning agent's workshop:

| Directive | Owning Agent | Workshop Phase |
|---|---|---|
| approval-gates | programme-governance | Phase 1 |
| design-authority-process | design-authority | Phase 2 |
| change-control | programme-governance | Phase 1 |
| escalation-matrix | programme-governance | Phase 1 |
| customisation-governance | fit-gap-analyst | Phase 2 |

Directives are produced during Step 1 (Review Agent Spec) of the owning agent's workshop and placed in `governance/directives/`.

## 11. Scope Decision: MVP (72 Skills) vs Full (83 Skills)

Flagged in WS-3 but not previously reflected in the build plan. This decision must be made **before** workshops begin, as it affects workshop scope, timeline, and agent definitions.

### The Decision

| Option | Skills | Agents Affected | Workshop Impact |
|---|---|---|---|
| **A: MVP (72 skills)** | 6-9 skills per agent, core capabilities only | All 10 agents | Standard 5-step workshop per agent |
| **B: Full (83 skills)** | +11 gap skills across agents | 8 agents gain 1-2 extra skills | Extended workshop, additional acceptance criteria |

### Gap Skills Inventory (11 skills)

| # | Gap Skill | Agent | Rationale for Deferral |
|---|---|---|---|
| 1 | manage-vendor-escalation | programme-governance | Edge case — most programmes handle via existing escalation-matrix |
| 2 | automate-regression-suite | test-strategist | Tooling-dependent — requires CI pipeline (deferred to .github/) |
| 3 | generate-cost-benefit-analysis | dashboard-reporting | Nice-to-have — executive summary covers most needs |
| 4 | conduct-security-review | design-authority | Specialist skill — may warrant separate security agent later |
| 5 | plan-data-rehearsal | data-migration-lead | Covered partially by `design-migration-strategy` |
| 6 | negotiate-sla-terms | integration-architect | Commercial skill — usually handled by programme manager |
| 7 | create-training-materials | operating-model | Post-go-live — can be added in hypercare phase |
| 8 | manage-parallel-run | cutover-manager | Complex scenario — most programmes use big-bang or phased |
| 9 | orchestrate-cross-repo-links | integration-orchestrator | Depends on Product Office repo being mature |
| 10 | define-acceptance-matrix | test-strategist | Partially covered by `entry-exit-criteria` |
| 11 | audit-customisation-compliance | fit-gap-analyst | Overlaps with design-authority's `review-design-conformance` |

### Trade-off Analysis

| Factor | MVP (72) | Full (83) |
|---|---|---|
| **Delivery speed** | 11 workshops × 1 session = ~3 weeks | 11 workshops × 1.5 sessions = ~4.5 weeks |
| **Completeness** | Core capabilities covered | Edge cases and specialist scenarios covered |
| **Risk** | Low — proven core skills | Medium — some skills have unclear acceptance criteria |
| **Maintenance** | 72 skills to maintain | 83 skills to maintain (+15%) |
| **Deferred cost** | Gap skills added post-MVP if needed | Upfront investment, some may never be used |
| **Recommendation** | ✅ **Recommended** — ship fast, iterate | Consider only if specific programme demands it |

### Decision Record

```markdown
## Decision: MVP vs Full Skills

**Date:** YYYY-MM-DD
**Decision:** [MVP 72 / Full 83 / Hybrid: X of 11]
**Decided by:** <name>
**Rationale:** <why>

### If MVP:
- Gap skills logged in SKILLS-INVENTORY.md with status: ⏸️ Deferred
- Each gap skill tagged with trigger condition for activation
- Review scheduled at end of Phase 3 workshops

### If Full:
- Gap skills added to agent specs before workshops
- Extended workshop plan approved
- Additional acceptance criteria defined per gap skill
```

## 12. Commands (Minimal)

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

## 13. Skills Inventory

Master traceability file consolidating all skills across agents. Lives at `artefacts/SKILLS-INVENTORY.md`.

```markdown
# Skills Inventory — Implementation Team OS

**Total Skills:** 72 (MVP) / 83 (with gap skills)
**Last Updated:** YYYY-MM-DD
**Status Legend:** ⬜ Not Started | 🔄 In Progress | ✅ Complete | ⏸️ Deferred

## Skills by Agent

| # | Skill | Agent | Stage(s) | Status | Acceptance Criteria Met | Notes |
|---|---|---|---|---|---|---|
| 1 | run-fit-gap-workshop | fit-gap-analyst | 2 | ⬜ | - | |
| 2 | score-customisation | fit-gap-analyst | 2, 3 | ⬜ | - | |
| 3 | write-adr | design-authority | 3, 4 | ⬜ | - | |
| 4 | review-design-conformance | design-authority | 4, 5 | ⬜ | - | |
| 5 | design-integration-architecture | integration-architect | 3 | ⬜ | - | |
| 6 | map-event-channels | integration-architect | 3, 4 | ⬜ | - | |
| 7 | define-api-contracts | integration-architect | 3, 4 | ⬜ | - | |
| 8 | design-migration-strategy | data-migration-lead | 6 | ⬜ | - | |
| 9 | profile-data-quality | data-migration-lead | 2, 5 | ⬜ | - | |
| 10 | define-cleansing-rules | data-migration-lead | 5, 6 | ⬜ | - | |
| ... | ... | ... | ... | ... | ... | |
| 72 | generate-executive-dashboard | dashboard-reporting | All | ⬜ | - | |
|---|---|---|---|---|---|---|
| 73 | *(gap)* manage-vendor-escalation | programme-governance | All | ⏸️ | - | Gap skill |
| 74 | *(gap)* automate-regression-suite | test-strategist | 5 | ⏸️ | - | Gap skill |
| ... | ... | ... | ... | ⏸️ | - | |
| 83 | *(gap)* orchestrate-cross-repo-links | integration-orchestrator | All | ⏸️ | - | Gap skill |

## Summary by Agent

| Agent | MVP Skills | Gap Skills | Complete | In Progress | Not Started |
|---|---|---|---|---|---|
| fit-gap-analyst | 8 | 1 | 0 | 0 | 8 |
| integration-architect | 9 | 1 | 0 | 0 | 9 |
| data-migration-lead | 7 | 1 | 0 | 0 | 7 |
| test-strategist | 6 | 2 | 0 | 0 | 6 |
| cutover-manager | 7 | 1 | 0 | 0 | 7 |
| design-authority | 8 | 1 | 0 | 0 | 8 |
| programme-governance | 8 | 2 | 0 | 0 | 8 |
| operating-model | 7 | 1 | 0 | 0 | 7 |
| dashboard-reporting | 6 | 1 | 0 | 0 | 6 |
| integration-orchestrator | 6 | 2 | 0 | 0 | 6 |
| **Total** | **72** | **11** | **0** | **0** | **72** |

## Summary by Stage

| Stage | Skills Active | Complete | Status |
|---|---|---|---|
| 1. Discovery | 5 | 0 | ⬜ |
| 2. Fit-Gap & Process Design | 12 | 0 | ⬜ |
| 3. Solution Architecture | 18 | 0 | ⬜ |
| 4. Build & Configure | 14 | 0 | ⬜ |
| 5. Testing | 10 | 0 | ⬜ |
| 6. Data Migration | 8 | 0 | ⬜ |
| 7. Cutover | 7 | 0 | ⬜ |
| 8. Hypercare | 6 | 0 | ⬜ |
| Cross-cutting (All) | 10 | 0 | ⬜ |
```

**Usage:** Updated after each agent workshop. Status changes from ⬜ → 🔄 → ✅ as skills are defined, acceptance criteria written, and tested with a sample programme. Gap skills remain ⏸️ until the E4 decision is made.

## 14. What Is NOT Built Now

Deferred to agent workshops:
- Full agent definitions (skills, scope, examples, tools)
- Skills (run-fit-gap-workshop, write-adr, design-migration-strategy, etc.)
- Additional commands (fit-gap, design-review, migration-rehearsal, go-nogo)
- .github/ CI workflows
- CONTRIBUTING.md
- Cross-repo workspace integration with Product Office

## 15. Verification

After scaffold:
1. `tree` confirms structure matches this spec
2. Root CLAUDE.md lists all 10 agents with one-liners
3. All 8 artefact folders exist with their constituent deliverable files + SKILLS-INVENTORY.md
4. All 8 gate definitions exist in lifecycle/gates/
5. pipeline/_template/ contains STAGE-STATUS.md, CONTRIBUTION-LOG.md, stages/, artefacts/
6. `/new-programme test` creates pipeline/active/test/ with correct structure
7. `/impl-status` renders empty dashboard
8. Git init succeeds, push to GitHub succeeds
