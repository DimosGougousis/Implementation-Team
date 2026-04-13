# Missing Items — Implementation Team OS

**Date:** 2026-04-13
**Audit Scope:** Design spec (Section 10 deferred items) + Re-implementation methodology gaps + Agent skill build plan (83 skills)

---

## Summary

| Category | Missing | Priority |
|---|---|---|
| Governance Directives | 5 files | High — needed before any real programme |
| Agent Skills | 83 skill files | High — agents are stubs without them |
| Re-Implementation Templates | 6 files | High — methodology defined but templates missing |
| Commands | 4 commands | Medium — spec says "additional commands deferred" |
| CI/CD & Repo Hygiene | 3 files | Low — spec explicitly defers |
| Cross-Repo Integration | 1 file | Low — spec explicitly defers |

---

## 1. Governance Directives (5 files)

**Location:** `governance/directives/` (directory exists, currently empty)
**Priority:** High — these define how the programme actually governs itself

| # | File | Purpose | Referenced By |
|---|---|---|---|
| 1.1 | `governance/directives/approval-gates.md` | Who approves gate passage, escalation thresholds, conditional pass criteria | All gate files |
| 1.2 | `governance/directives/design-authority-process.md` | ADR review process, design conformance checks, architecture review board cadence | design-authority agent |
| 1.3 | `governance/directives/change-control.md` | Change request process (standard/normal/emergency), CAB composition, approval matrix | operating-model agent, cutover-manager |
| 1.4 | `governance/directives/escalation-matrix.md` | Escalation levels, triggers, contacts, response SLAs | integration-orchestrator, all gate files |
| 1.5 | `governance/directives/customisation-governance.md` | Customisation decision criteria, budget enforcement, ADR linkage, approval workflow | fit-gap-analyst, design-authority |

---

## 2. Agent Skills (83 files)

**Location:** `.claude/skills/` (directory exists, currently empty)
**Priority:** High — agents are placeholders without skills

| Agent | Skills | Count |
|---|---|---|
| design-authority | write-adr, build-capability-map, design-component-model, define-security-architecture, maintain-adr-register, build-traceability-matrix, review-design-conformance, evaluate-customisation-request, define-nfr-requirements, assess-current-vs-target-gap | 10 |
| integration-architect | build-integration-register, design-api-contract, design-event-contract, create-dependency-graph, define-adapter-strategy, build-sla-matrix, build-owner-matrix, design-security-contract, plan-observability | 9 |
| test-strategist | define-test-strategy, set-entry-exit-criteria, build-kpi-dashboard, classify-defects, design-test-data-strategy, manage-environment-matrix, write-bdd-scenarios, define-nfr-acceptance | 8 |
| integration-orchestrator | map-stakeholders, build-communication-plan, manage-vendor-relationships, run-steering-committee, manage-escalations, coordinate-cross-system-cascade, build-raci-matrix | 7 |
| fit-gap-analyst | run-fit-gap-workshop, score-requirements, evaluate-customisation-trade-off, track-customisation-budget, produce-module-assessment, enforce-governance-approvals | 6 |
| programme-governance | define-programme-charter, design-cadences-ceremonies, manage-raid-log, track-dora-metrics, manage-release-process, build-delivery-roadmap, track-flow-metrics, facilitate-pi-planning, prioritise-wsjf | 9 |
| data-migration-lead | design-migration-strategy, profile-source-data, define-cleansing-rules, create-mapping-specification, set-quality-gates, execute-rehearsal, build-quality-scorecard, build-migration-runbook | 8 |
| process-analyst | map-current-state-process, design-target-state-process, create-bpmn-diagram, assess-process-impact, link-process-to-fit-gap, generate-process-flow, build-business-rules-catalogue | 7 |
| operating-model | design-operating-model, define-support-tiers, design-incident-management, design-change-management, plan-upgrade-cadence, manage-hypercare, build-continuous-improvement, run-stress-test-scenarios | 8 |
| cutover-manager | write-cutover-runbook, define-rollback-triggers, build-go-nogo-framework, execute-cutover-rehearsal, manage-war-room, build-readiness-checklist, build-cutover-communication-plan | 7 |
| dashboard-reporting | build-programme-dashboard, generate-executive-summary, track-artefact-completion, calculate-programme-health, render-mermaid-charts, generate-risk-heatmap, produce-steering-committee-pack | 7 |
| **Total** | | **83** |

---

## 3. Re-Implementation Templates (6 files)

**Priority:** High — methodology is defined in `docs/re-implementation-methodology.md` but templates don't exist

| # | File | Purpose | Referenced By |
|---|---|---|---|
| 3.1 | `artefacts/05-data-quality-scorecard/data-estate-report.md` | Source system inventory, table/record counts, data quality baseline, volume estimates | Pre-Work, Stage 1-2 |
| 3.2 | `artefacts/05-data-quality-scorecard/reconciliation-strategy.md` | Record count, balance, referential integrity reconciliation approach | Stage 5-7 |
| 3.3 | `artefacts/05-data-quality-scorecard/domain-complexity-matrix.md` | Domain × complexity × volume × regulatory × priority matrix | Stage 2 |
| 3.4 | `artefacts/07-cutover-runbook/legacy-decommission-plan.md` | Read-only → parallel run → archive → decommission phases, checklist | Stage 7-8 |
| 3.5 | `artefacts/07-cutover-runbook/legacy-freeze-plan.md` | Legacy system freeze procedure, timing, communication, rollback | Stage 7 |
| 3.6 | `lifecycle/pre-work/` (directory + template) | Pre-work checklist: legacy inventory, data estate, integration landscape, as-is processes | Before Stage 1 |

---

## 4. Commands (4 files)

**Location:** `.claude/commands/`
**Priority:** Medium — spec says "additional commands deferred to agent workshops"

| # | File | Purpose | Referenced By |
|---|---|---|---|
| 4.1 | `.claude/commands/fit-gap.md` | Run a fit-gap scoring session for a module | fit-gap-analyst |
| 4.2 | `.claude/commands/design-review.md` | Trigger an architecture design review | design-authority |
| 4.3 | `.claude/commands/migration-rehearsal.md` | Execute and log a migration rehearsal | data-migration-lead |
| 4.4 | `.claude/commands/go-nogo.md` | Run the go/no-go decision framework | cutover-manager |

---

## 5. CI/CD & Repo Hygiene (3 files)

**Priority:** Low — spec explicitly defers

| # | File | Purpose |
|---|---|---|
| 5.1 | `.github/workflows/lint.yml` | Markdown lint on PR |
| 5.2 | `.github/workflows/link-check.yml` | Validate internal links |
| 5.3 | `CONTRIBUTING.md` | Contribution guidelines |

---

## 6. Cross-Repo Integration (1 file)

**Priority:** Low — spec explicitly defers

| # | File | Purpose |
|---|---|---|
| 6.1 | `governance/cross-repo-links.md` | Links to Product Office repo, shared conventions |

---

## 7. Gate File Augments (8 files to edit)

**Priority:** High — re-implementation methodology requires gate changes but templates haven't been updated

| # | File | Augmentation Needed |
|---|---|---|
| 7.1 | `lifecycle/gates/01-discovery.gate.md` | Add Pre-Work entry criteria (legacy inventory, data estate, integration landscape) |
| 7.2 | `lifecycle/gates/02-fit-gap-process-design.gate.md` | Add process redesign (adopt/adapt/abandon), data migration strategy, integration retire/rebuild |
| 7.3 | `lifecycle/gates/05-testing.gate.md` | Add migration rehearsal 1, reconciliation testing, parallel-run testing |
| 7.4 | `lifecycle/gates/06-data-migration.gate.md` | Add regulatory data preservation, legacy archive prep |
| 7.5 | `lifecycle/gates/07-cutover.gate.md` | Add legacy freeze, legacy read-only transition |
| 7.6 | `lifecycle/gates/08-hypercare.gate.md` | Add legacy parallel-run, decommission, archive verification |
| 7.7 | `pipeline/_template/STAGE-STATUS.md` | Add workstream tracking columns (WS-1 through WS-6) |
| 7.8 | `lifecycle/overview.md` | Add re-implementation lifecycle diagram with pre-work and parallel workstreams |

---

## Execution Priority

| Priority | Items | Count | Effort |
|---|---|---|---|
| **P1 — Now** | Governance directives (1.1–1.5) | 5 files | Medium |
| **P1 — Now** | Re-implementation templates (3.1–3.6) | 6 files | Medium |
| **P1 — Now** | Gate file augments (7.1–7.8) | 8 edits | Medium |
| **P2 — Next** | Agent skills (2.1–2.83) | 83 files | High (workshop per agent) |
| **P2 — Next** | Commands (4.1–4.4) | 4 files | Low |
| **P3 — Later** | CI/CD (5.1–5.3) | 3 files | Low |
| **P3 — Later** | Cross-repo (6.1) | 1 file | Low |

**Total missing: 110 items** (5 + 83 + 6 + 4 + 3 + 1 + 8 edits)
