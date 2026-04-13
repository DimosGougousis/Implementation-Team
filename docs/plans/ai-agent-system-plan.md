# AI Agent System — Build Plan

**Date:** 2026-04-12
**Status:** Draft
**Scope:** Defines the architecture, skills, interactions, and build sequence for the 11 AI agents in the Implementation Team OS.

---

## 1. Agent Architecture

### 1.1 Design Principles

1. **Artefact-First** — Agents produce and maintain files in `artefacts/`. They don't hold state internally; the repo is the source of truth.
2. **Stage-Aware** — Agents know which lifecycle stage the programme is in and adjust their behaviour accordingly.
3. **Skill-Based** — Each agent has a defined set of skills (markdown files in `.claude/skills/`) that teach it how to perform specific tasks.
4. **Collaborative** — Agents hand off work to each other through artefacts. E.g., fit-gap-analyst produces the register; design-authority reviews it for ADR implications.
5. **Evidence-Based** — Agents produce deliverables with measurable quality signals, not opinions.

### 1.2 Agent Anatomy

Each agent consists of:

```
agents/<agent-name>.agent.md     # Agent definition (YAML frontmatter + markdown)
.claude/skills/<skill-name>.md   # Skill files (one per capability)
artefacts/<folder>/              # Artefacts the agent owns/produces
```

### 1.3 Agent Definition Template

```yaml
---
name: <agent-name>
description: <one-liner>
status: placeholder | active | deprecated
codename: <friendly-name>
competency: <N>-<Competency Name>
owner-artefacts: [<folder-list>]
primary-stages: [<stage-list>]
skills: [<skill-list>]
tools: [<tool-list>]
---

# <Agent Name>

## Intent
<paragraph>

## Skills
| Skill | Description | Stage(s) |
|---|---|---|

## Owns
- artefacts/<folder>/

## Collaborates With
| Agent | Handoff | Direction |
|---|---|---|

## Active At
- Stage N: <name>
```

---

## 2. Agent Interaction Model

### 2.1 Stage-Based Handoffs

```
Stage 1: Discovery
├── process-analyst: Documents as-is processes
├── design-authority: Initial target-state architecture
└── integration-orchestrator: Stakeholder mapping

Stage 2: Fit-Gap & Process Design
├── fit-gap-analyst: Scores requirements, tracks budget
├── process-analyst: Redesigns processes (adopt/adapt/abandon)
├── data-migration-lead: Begins data profiling
└── integration-architect: Maps integration landscape

Stage 3: Solution Architecture
├── design-authority: Authors ADRs, finalises architecture
├── integration-architect: Designs API/event contracts
├── test-strategist: Defines test strategy framework
├── operating-model: Begins operating model design
└── fit-gap-analyst: Links gaps to ADRs

Stage 4: Build & Configure
├── design-authority: Reviews design conformance
├── integration-architect: Validates implementations
├── fit-gap-analyst: Tracks budget consumption
└── programme-governance: Manages RAID, DORA metrics

Stage 5: Testing
├── test-strategist: Executes test phases, tracks KPIs
├── data-migration-lead: Conducts Rehearsal 1
├── cutover-manager: Begins cutover planning
└── design-authority: Updates ADRs from test findings

Stage 6: Data Migration
├── data-migration-lead: Conducts Rehearsal 2, achieves quality gates
├── cutover-manager: Finalises runbook with migration timing
└── integration-orchestrator: Coordinates vendor support

Stage 7: Cutover
├── cutover-manager: Executes runbook, manages go/no-go
├── integration-orchestrator: Coordinates war room comms
└── dashboard-reporting: Reports go-live status

Stage 8: Hypercare
├── operating-model: Finalises support tiers, incident mgmt
├── dashboard-reporting: Tracks hypercare metrics
├── programme-governance: Conducts retrospective
└── integration-orchestrator: Manages BAU handover
```

### 2.2 Cross-Agent Collaboration Matrix

| From → To | Handoff | Artefact |
|---|---|---|
| process-analyst → fit-gap-analyst | As-is processes inform gap scoring | business-processes/ → 03-fit-gap-register/ |
| fit-gap-analyst → design-authority | Gaps requiring ADRs | 03-fit-gap-register/ → 01-architecture-decision-records/ |
| design-authority → integration-architect | Architecture decisions affect integration design | 01-architecture-decision-records/ → 04-integration-dependency-map/ |
| integration-architect → test-strategist | Integration contracts define test scope | 04-integration-dependency-map/ → 06-test-strategy-kpi-dashboard/ |
| data-migration-lead → cutover-manager | Migration timing feeds cutover runbook | 05-data-quality-scorecard/ → 07-cutover-runbook/ |
| cutover-manager → operating-model | Cutover experience informs operating model | 07-cutover-runbook/ → 08-post-go-live-operating-model/ |
| dashboard-reporting ← ALL | All agents feed status updates | */ → analytics/, pipeline/*/STAGE-STATUS.md |

---

## 3. Skill Definitions

### 3.1 Skill File Structure

Each skill is a markdown file in `.claude/skills/`:

```markdown
# <Skill Name>

**Agent:** <agent-name>
**Stage(s):** <stage-list>

## When to Use
<description of when this skill applies>

## Inputs
- <required context/artefacts>

## Process
1. <step-by-step>
2. ...

## Outputs
- <artefacts produced/updated>

## Quality Signals
- <how to verify the skill was applied well>

## Examples
<example inputs and outputs>
```

### 3.2 Skill Inventory by Agent

#### design-authority (8 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `write-adr` | Author ADRs with context, options, trade-offs, consequences |
| 2 | `build-capability-map` | Map bank capabilities to Transact PBCs |
| 3 | `design-component-model` | Create C4/Mermaid component diagrams |
| 4 | `define-security-architecture` | Auth, encryption, key management, network zones |
| 5 | `maintain-adr-register` | Track ADR status, link to requirements, detect staleness |
| 6 | `build-traceability-matrix` | Requirement → ADR → implementation mapping |
| 7 | `review-design-conformance` | Check implementation against approved architecture |
| 8 | `evaluate-customisation-request` | Score customisation vs workaround vs accept-gap |

#### integration-architect (7 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `build-integration-register` | Catalogue all system-to-system touchpoints |
| 2 | `design-api-contract` | RESTful contract: endpoint, payload, auth, SLA, versioning |
| 3 | `design-event-contract` | Event channel: topic, schema, producer, consumer, retry, DLQ |
| 4 | `create-dependency-graph` | Mermaid directed graph with protocol, SLA, owner |
| 5 | `define-adapter-strategy` | Temenos fulfilment service model, middleware patterns |
| 6 | `build-sla-matrix` | System × system SLA grid (Gold/Silver/Bronze) |
| 7 | `build-owner-matrix` | System × owner × support contact mapping |

#### test-strategist (7 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `define-test-strategy` | Four-phase: Unit → Integration → SIT/Perf → UAT |
| 2 | `set-entry-exit-criteria` | Objective, measurable gate criteria per phase |
| 3 | `build-kpi-dashboard` | Defect density, pass rate, cycle time, automation coverage |
| 4 | `classify-defects` | Severity/priority taxonomy with SLAs |
| 5 | `design-test-data-strategy` | Sourcing, masking, refresh cadence |
| 6 | `manage-environment-matrix` | Test environments: purpose, data, access, refresh |
| 7 | `write-bdd-scenarios` | Gherkin acceptance criteria for UAT |

#### integration-orchestrator (6 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `map-stakeholders` | Power/interest grid, influence analysis, RACI |
| 2 | `build-communication-plan` | Who gets told what, when, via which channel |
| 3 | `manage-vendor-relationships` | Vendor SLAs, escalation paths, contract alignment |
| 4 | `run-steering-committee` | Agenda, pack, action tracking, follow-up |
| 5 | `manage-escalations` | Escalation path, conflict resolution, decision logging |
| 6 | `coordinate-cross-system-cascade` | Jira/Slack/Drive notification orchestration |

#### fit-gap-analyst (6 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `run-fit-gap-workshop` | Facilitate structured workshops with business SMEs |
| 2 | `score-requirements` | Fit/Partial/Gap scoring with weighted criteria |
| 3 | `evaluate-customisation-trade-off` | Customise vs workaround vs accept-gap analysis |
| 4 | `track-customisation-budget` | Hard ceiling tracker with escalation thresholds |
| 5 | `produce-module-assessment` | Per-module assessment report with recommendations |
| 6 | `enforce-governance-approvals` | Customisation decision criteria, approval workflow |

#### programme-governance (7 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `define-programme-charter` | OKRs, scope, success criteria, org model |
| 2 | `design-cadences-ceremonies` | PI Planning, Scrums of Scrums, System Demos |
| 3 | `manage-raid-log` | Risks, Assumptions, Issues, Dependencies |
| 4 | `track-dora-metrics` | Deployment frequency, lead time, change failure rate, MTTR |
| 5 | `manage-release-process` | Release types, change control, approval gates |
| 6 | `build-delivery-roadmap` | Quarterly milestones, dependency management |
| 7 | `track-flow-metrics` | Flow efficiency, cycle time, throughput, predictability |

#### data-migration-lead (7 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `design-migration-strategy` | Big bang / phased / trickle approach |
| 2 | `profile-source-data` | Field-level profiling: nulls, distincts, formats, duplicates |
| 3 | `define-cleansing-rules` | Standardise, deduplicate, enrich, default with before/after |
| 4 | `create-mapping-specification` | Source → Transact field mappings with transformation logic |
| 5 | `set-quality-gates` | Per-milestone thresholds (completeness, accuracy, consistency) |
| 6 | `execute-rehearsal` | Run migration rehearsal, measure timing, validate quality |
| 7 | `build-quality-scorecard` | Domain-by-domain quality metrics with trend tracking |

#### process-analyst (6 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `map-current-state-process` | Document how the bank does things today |
| 2 | `design-target-state-process` | Redesign for Transact standard functionality |
| 3 | `create-bpmn-diagram` | BPMN 2.0 swimlane diagrams |
| 4 | `assess-process-impact` | People, training, operations impact analysis |
| 5 | `link-process-to-fit-gap` | Connect process redesign to fit-gap scores |
| 6 | `generate-process-flow` | Mermaid swimlane flow from process library |

#### operating-model (7 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `design-operating-model` | Org chart, roles, responsibilities, handover plan |
| 2 | `define-support-tiers` | L1/L2/L3 scope, escalation paths, SLAs |
| 3 | `design-incident-management` | Severity classification, response process, post-incident review |
| 4 | `design-change-management` | Standard/normal/emergency change paths, CAB process |
| 5 | `plan-upgrade-cadence` | Temenos release adoption: major/SP/patch/hotfix |
| 6 | `manage-hypercare` | Phase progression, exit criteria, metrics tracking |
| 7 | `build-continuous-improvement` | Feedback loops, improvement backlog, KPIs |

#### cutover-manager (6 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `write-cutover-runbook` | Minute-by-minute script with owners and verification |
| 2 | `define-rollback-triggers` | Automatic and manual rollback thresholds |
| 3 | `build-go-nogo-framework` | Mandatory vs advisory criteria, decision matrix |
| 4 | `execute-cutover-rehearsal` | Run rehearsal, measure timing deltas, log issues |
| 5 | `manage-war-room` | War room coordination, escalation, status updates |
| 6 | `build-readiness-checklist` | Data, testing, infra, integration, people readiness |

#### dashboard-reporting (5 skills)

| # | Skill | Description |
|---|---|---|
| 1 | `build-programme-dashboard` | Aggregate STAGE-STATUS.md across active programmes |
| 2 | `generate-executive-summary` | Steering Committee / CTO one-pager |
| 3 | `track-artefact-completion` | Stage × artefact matrix with status indicators |
| 4 | `calculate-programme-health` | RAG status from gate history, defect trends, budget burn |
| 5 | `render-mermaid-charts` | Generate Mermaid diagrams for reports |

**Total: 12 agents, 74 skills**

---

## 4. Build Sequence

### Phase 1: Foundation (Weeks 1–2)
- [ ] Finalise agent definitions (YAML frontmatter for all 12 agents)
- [ ] Create skill file templates in `.claude/skills/`
- [ ] Define agent-to-skill mapping in `agents/CLAUDE.md`

### Phase 2: Core Agents (Weeks 3–6)
- [ ] Workshop and build `design-authority` (8 skills)
- [ ] Workshop and build `fit-gap-analyst` (6 skills)
- [ ] Workshop and build `integration-architect` (7 skills)
- [ ] Workshop and build `data-migration-lead` (7 skills)

### Phase 3: Delivery Agents (Weeks 7–10)
- [ ] Workshop and build `test-strategist` (7 skills)
- [ ] Workshop and build `cutover-manager` (6 skills)
- [ ] Workshop and build `process-analyst` (6 skills)
- [ ] Workshop and build `operating-model` (7 skills)

### Phase 4: Coordination Agents (Weeks 11–12)
- [ ] Workshop and build `programme-governance` (7 skills)
- [ ] Workshop and build `integration-orchestrator` (6 skills)
- [ ] Workshop and build `dashboard-reporting` (5 skills)

### Phase 5: Integration & Testing (Weeks 13–14)
- [ ] End-to-end agent collaboration testing
- [ ] Handoff validation between agents
- [ ] Skill refinement based on test results
- [ ] Documentation and onboarding materials

---

## 5. Technical Approach

### 5.1 Agent Implementation Options

| Approach | Pros | Cons | Recommendation |
|---|---|---|---|
| **Claude Skills (current)** | Native to Claude, markdown-based, low friction | Limited to Claude ecosystem | ✅ Start here |
| **MCP Servers** | Tool integration, external APIs, stateful | More complex, requires hosting | Phase 2 |
| **LangGraph Agents** | Full autonomy, tool use, state management | Significant engineering effort | Phase 3 |
| **CrewAI / AutoGen** | Multi-agent orchestration, delegation | Framework dependency | Evaluate |

### 5.2 Recommended Stack

```
┌─────────────────────────────────────────────────┐
│                  User Interface                   │
│         (VS Code + Claude Chat + Commands)        │
├─────────────────────────────────────────────────┤
│              Agent Orchestration                  │
│    (Claude reads agent.md + skill.md files)      │
├─────────────────────────────────────────────────┤
│                  Artefact Layer                   │
│    (Markdown files in artefacts/, pipeline/)     │
├─────────────────────────────────────────────────┤
│                  Data Layer                       │
│    (Git repo, Excel references, API catalogs)    │
└─────────────────────────────────────────────────┘
```

### 5.3 Agent Activation

When a user invokes an agent (e.g., "run the fit-gap analyst for module AA"):

1. Claude reads `agents/fit-gap-analyst.agent.md` for context
2. Claude reads the relevant skill files (e.g., `.claude/skills/score-requirements.md`)
3. Claude reads the current state from `artefacts/03-fit-gap-register/`
4. Claude executes the skill process
5. Claude writes outputs to the artefact files
6. Claude updates `pipeline/active/<programme>/STAGE-STATUS.md`

---

## 6. Governance Directives (Build with Agents)

These files should be built during agent workshops:

| File | Built By | When |
|---|---|---|
| `governance/directives/approval-gates.md` | programme-governance | Phase 4 |
| `governance/directives/design-authority-process.md` | design-authority | Phase 2 |
| `governance/directives/change-control.md` | operating-model | Phase 3 |
| `governance/directives/escalation-matrix.md` | integration-orchestrator | Phase 4 |
| `governance/directives/customisation-governance.md` | fit-gap-analyst | Phase 2 |

---

## 7. Success Criteria

| Metric | Target |
|---|---|
| Agent definitions complete | 12/12 |
| Skills defined | 74/74 |
| Skills with examples | 74/74 |
| Agent collaboration tested | All handoffs validated |
| Governance directives complete | 5/5 |
| User can invoke any agent via natural language | 100% |
| Artefact quality meets template standards | Spot-check pass |
