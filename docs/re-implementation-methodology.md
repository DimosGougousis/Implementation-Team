# Re-Implementation Methodology — Temenos Transact

**Date:** 2026-04-13
**Status:** Draft
**Scope:** Defines the implementation methodology for Temenos Transact re-implementation programmes (migrating from a legacy core banking system), distinguishing re-implementation from greenfield BIAN-aligned implementation.

---

## 1. Why Re-Implementation Is Not Greenfield

A greenfield implementation builds from scratch. A re-implementation replaces a running system. This creates seven fundamental differences that the methodology must address:

| # | Greenfield | Re-Implementation |
|---|---|---|
| 1 | No existing data | Millions of records to migrate, cleanse, reconcile |
| 2 | No existing integrations | Dozens of live integrations to rebuild or retire |
| 3 | No existing processes | Established processes with institutional knowledge and workarounds |
| 4 | No users in production | Users with muscle memory, training debt, and resistance |
| 5 | No legacy to decommission | Legacy system must run in parallel, then be safely retired |
| 6 | Clean slate for decisions | Every decision has a "what we do today" baseline to compare against |
| 7 | No regulatory history | Existing regulatory reports, audit trails, and compliance obligations must be preserved |

**Implication:** The methodology must add pre-stages, parallel workstreams, and extended gates that greenfield doesn't need.

---

## 2. Re-Implementation Lifecycle (Augmented 8-Stage)

The existing 8-stage lifecycle is retained but augmented with **pre-work**, **parallel workstreams**, and **extended gates** specific to re-implementation.

### 2.1 Lifecycle Overview

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        RE-IMPLEMENTATION LIFECYCLE                       │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  PRE-WORK (before Stage 1)                                              │
│  ├── Legacy System Inventory                                            │
│  ├── Data Estate Assessment                                             │
│  ├── Integration Landscape Mapping                                      │
│  └── Business Process Documentation (As-Is)                             │
│                                                                         │
│  STAGE 1: Discovery                                                     │
│  ├── Current-state deep dive (legacy system, data, integrations)        │
│  ├── Strategic objectives and business case                             │
│  ├── Re-implementation approach decision (big bang / phased / parallel) │
│  └── GATE 1: Scope + Approach Confirmed                                 │
│                                                                         │
│  STAGE 2: Fit-Gap & Process Redesign                                    │
│  ├── Fit-gap against Transact capabilities                              │
│  ├── Process redesign: adopt / adapt / abandon                          │
│  ├── Data migration strategy (domains, waves, quality thresholds)       │
│  ├── Integration rebuild vs retire decisions                            │
│  └── GATE 2: Fit-Gap + Migration Strategy Approved                      │
│                                                                         │
│  STAGE 3: Solution Architecture                                         │
│  ├── Target-state architecture (Transact + integrations)                │
│  ├── ADRs for all significant decisions                                 │
│  ├── Data migration architecture (ETL, mapping, transformation)         │
│  ├── Integration architecture (API contracts, event channels)           │
│  ├── Parallel-run strategy (if applicable)                              │
│  └── GATE 3: Architecture + Migration Design Approved                   │
│                                                                         │
│  STAGE 4: Build & Configure                                             │
│  ├── Transact configuration per fit-gap register                        │
│  ├── Customisation development per ADRs                                 │
│  ├── Integration development and testing                                │
│  ├── ETL development and unit testing                                   │
│  ├── Legacy system freeze planning                                      │
│  └── GATE 4: Build Complete + Migration Tooling Ready                   │
│                                                                         │
│  STAGE 5: Testing                                                       │
│  ├── Unit + Integration + SIT + Performance + UAT                       │
│  ├── Data migration rehearsal 1 (full dress rehearsal)                  │
│  ├── Reconciliation testing (source vs target)                          │
│  ├── Parallel-run testing (if applicable)                               │
│  ├── Legacy decommission testing                                        │
│  └── GATE 5: UAT Sign-Off + Rehearsal 1 Passed                          │
│                                                                         │
│  STAGE 6: Data Migration & Reconciliation                               │
│  ├── Data cleansing (final pass)                                        │
│  ├── Migration rehearsal 2 (production-scale)                           │
│  ├── Reconciliation validation (100% match or documented exceptions)    │
│  ├── Legacy data archive preparation                                    │
│  ├── Regulatory data preservation verification                          │
│  └── GATE 6: Rehearsal 2 Passed + Reconciliation Clean                  │
│                                                                         │
│  STAGE 7: Cutover                                                       │
│  ├── Legacy system freeze                                               │
│  ├── Final data extraction and migration                                │
│  ├── Reconciliation and validation                                      │
│  ├── Transact go-live                                                   │
│  ├── Legacy system read-only transition                                 │
│  └── GATE 7: Go-Live Confirmed + Legacy Safe                            │
│                                                                         │
│  STAGE 8: Hypercare & Legacy Decommission                               │
│  ├── Intensive hypercare (4-8 weeks)                                    │
│  ├── Legacy system parallel-run (if applicable)                         │
│  ├── Legacy system decommission                                         │
│  ├── Data archive access verification                                   │
│  ├── BAU handover                                                       │
│  └── GATE 8: Steady State + Legacy Decommissioned                       │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

### 2.2 What's Different from Greenfield

| Stage | Greenfield | Re-Implementation Addition |
|---|---|---|
| Pre-Work | None | Legacy inventory, data estate assessment, integration landscape, as-is process documentation |
| 1 — Discovery | Scope + target-state | + Current-state deep dive, re-implementation approach decision, legacy complexity assessment |
| 2 — Fit-Gap | Capability scoring | + Process redesign (adopt/adapt/abandon), data migration strategy, integration retire/rebuild decisions |
| 3 — Architecture | Target-state design | + Data migration architecture, parallel-run strategy, legacy decommission design |
| 4 — Build | Config + customisation | + ETL development, legacy freeze planning |
| 5 — Testing | 4-phase testing | + Migration rehearsal 1, reconciliation testing, parallel-run testing, legacy decommission testing |
| 6 — Data Migration | (folded into cutover) | **Full dedicated stage** — cleansing, rehearsal 2, reconciliation, archive prep, regulatory preservation |
| 7 — Cutover | Runbook execution | + Legacy freeze, final migration, reconciliation, legacy read-only transition |
| 8 — Hypercare | Stabilisation + handover | + Legacy parallel-run, decommission, data archive access verification |

---

## 3. Parallel Workstreams

Re-implementation requires workstreams that run in parallel across stages, not just sequentially.

### 3.1 Workstream Model

```
WS-1: Transact Configuration     ████████████████████████████░░░░░░░░░░░░░░
WS-2: Data Migration             ░░░░████████████████████████████████████░░
WS-3: Integration Rebuild        ░░░░░░░░████████████████████████░░░░░░░░░░
WS-4: Process Redesign           ████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░
WS-5: Legacy Decommission        ░░░░░░░░░░░░░░░░░░░░░░░░░░░░████████████░░
WS-6: Change Management          ██████████████████████████████████████████
         Stage:    1      2      3      4      5      6      7      8
```

### 3.2 Workstream Definitions

| Workstream | Stages | Owner | Key Deliverables |
|---|---|---|---|
| WS-1: Transact Configuration | 2, 3, 4, 5 | design-authority + fit-gap-analyst | Fit-gap register, ADRs, configured modules |
| WS-2: Data Migration | 2, 3, 4, 5, 6, 7 | data-migration-lead | Migration strategy, mapping specs, ETL, rehearsals, reconciliation |
| WS-3: Integration Rebuild | 2, 3, 4, 5 | integration-architect | Integration register, API contracts, rebuilt integrations |
| WS-4: Process Redesign | 1, 2, 3 | process-analyst | As-is processes, target-state processes, BPMN diagrams |
| WS-5: Legacy Decommission | 5, 6, 7, 8 | programme-governance | Decommission plan, archive strategy, read-only transition |
| WS-6: Change Management | 1–8 | integration-orchestrator | Stakeholder map, training plan, comms plan, adoption metrics |

---

## 4. Data Migration — The Critical Path

Data migration is the #1 risk in re-implementation. It deserves its own methodology layer.

### 4.1 Migration Approach Decision

| Approach | When to Use | Risk | Duration |
|---|---|---|---|
| **Big Bang** | Single entity, < 5M accounts, 48h cutover window acceptable | Highest | Shortest |
| **Phased** | Multiple entities, > 5M accounts, or regulatory constraints | Medium | Longest |
| **Parallel Run** | High-risk domains, regulatory requirement for dual-running | Lowest (operationally) | Longest (cost) |
| **Trickle** | Real-time coexistence required during transition | Medium | Indefinite |

### 4.2 Data Migration Sub-Stages

```
DM-1: Data Estate Assessment (Stage 1-2)
├── Source system inventory (tables, records, relationships)
├── Data quality baseline (completeness, accuracy, consistency)
├── Data volume estimates per domain
├── Regulatory data requirements (retention, access, audit trail)
└── DELIVERABLE: Data Estate Report

DM-2: Migration Design (Stage 2-3)
├── Domain-by-domain migration strategy
├── Source-to-target mapping specifications
├── Transformation rules and business logic
├── Cleansing rules (standardise, deduplicate, enrich)
├── Quality gate thresholds per milestone
├── Reconciliation strategy (record counts, balances, referential integrity)
└── DELIVERABLE: Migration Design Document

DM-3: ETL Development (Stage 4)
├── Extract scripts (source system → staging)
├── Transform scripts (staging → Transact format)
├── Load scripts (Transact format → Transact DB)
├── Reconciliation scripts (source vs target comparison)
├── Cleansing rule implementation
└── DELIVERABLE: ETL Pipeline + Reconciliation Suite

DM-4: Rehearsal 1 (Stage 5)
├── Full dress rehearsal with production-scale data
├── Timing measurement (must fit cutover window)
├── Quality validation against gate thresholds
├── Issue identification and remediation
├── Reconciliation validation
└── DELIVERABLE: Rehearsal 1 Report

DM-5: Rehearsal 2 (Stage 6)
├── Second full rehearsal with remediated ETL
├── All quality gates must pass
├── Timing must be within cutover window
├── Reconciliation must be clean (or exceptions documented)
├── Regulatory data preservation verified
└── DELIVERABLE: Rehearsal 2 Report (Go/No-Go input)

DM-6: Final Migration (Stage 7)
├── Legacy system freeze
├── Final data extraction
├── Transformation and load
├── Reconciliation (100% match or documented exceptions)
├── Business validation (key users verify critical data)
└── DELIVERABLE: Migration Completion Report
```

### 4.3 Data Domains (Typical)

| Domain | Complexity | Volume | Regulatory | Migration Priority |
|---|---|---|---|---|
| Customers / Parties | High | High | KYC/AML | Critical — first to migrate |
| Accounts | High | High | Audit trail | Critical — core domain |
| Transactions / History | Medium | Very High | Retention (7-10 years) | High — archive strategy needed |
| Products / Parameters | Medium | Low | None | Early — config dependency |
| Limits / Collateral | High | Medium | Regulatory | High — risk domain |
| Standing Orders / Mandates | Low | Medium | None | Medium — operational |
| Securities / Holdings | Very High | Medium | Regulatory | Critical if applicable |
| Loans / Facilities | High | High | Regulatory | Critical — financial domain |
| General Ledger | High | Medium | Audit | Critical — financial integrity |

---

## 5. Legacy System Decommission

A re-implementation isn't complete until the legacy system is safely retired.

### 5.1 Decommission Phases

| Phase | Timing | Activities |
|---|---|---|
| **Read-Only** | Stage 7 (cutover day) | Legacy access revoked for writes, read-only for reference |
| **Parallel Run** | Stage 8 (weeks 1-4) | Legacy available for reconciliation queries, no business processing |
| **Archive** | Stage 8 (weeks 4-8) | Data extracted to archive (regulatory-compliant), access controls applied |
| **Decommission** | Post-hypercare | Legacy infrastructure shut down, licences terminated, contracts closed |

### 5.2 Decommission Checklist

- [ ] All business processing migrated to Transact
- [ ] All integrations redirected or retired
- [ ] Regulatory data archived with verified access
- [ ] Historical transaction data accessible for audit
- [ ] Legacy read-only access revoked
- [ ] Legacy infrastructure decommissioned
- [ ] Legacy licences terminated
- [ ] Legacy vendor contracts closed
- [ ] Cost savings realised and reported

---

## 6. Re-Implementation Project Plan Structure

### 6.1 Typical Timeline (18-24 months)

```
Month:  1  2  3  4  5  6  7  8  9  10 11 12 13 14 15 16 17 18 19 20 21 22 23 24
        ├──┤
        Pre-Work (legacy inventory, data assessment)
        
           ├────────┤
           Stage 1: Discovery
           
              ├─────────────┤
              Stage 2: Fit-Gap & Process Redesign
              
                       ├──────────────┤
                       Stage 3: Solution Architecture
                       
                                ├──────────────────────┤
                                Stage 4: Build & Configure
                                
                                                 ├──────────────┤
                                                 Stage 5: Testing
                                                 
                                                          ├────────┤
                                                          Stage 6: Data Migration
                                                          
                                                                   ├──┤
                                                                   Stage 7: Cutover
                                                                   
                                                                      ├────────┤
                                                                      Stage 8: Hypercare
```

### 6.2 Critical Path Items

| Item | Why Critical | Mitigation |
|---|---|---|
| Data quality | Poor source data delays everything | Start profiling in Pre-Work, not Stage 2 |
| Integration complexity | Unknown integrations cause scope creep | Integration landscape mapping in Pre-Work |
| Legacy freeze window | Business can't freeze for too long | Rehearse timing, plan phased freeze if needed |
| Regulatory data preservation | Cannot lose audit trail | Dedicated regulatory workstream, early validation |
| User adoption | Users resist change | Change management from Stage 1, not Stage 7 |
| Customisation scope | "We need everything we have today" | Hard budget ceiling, ADR governance from Stage 2 |

### 6.3 Risk Register (Re-Implementation Specific)

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Data quality worse than expected | High | High | Early profiling, extended cleansing, quality gates |
| Legacy system has undocumented integrations | High | High | Integration landscape mapping in Pre-Work |
| Cutover window too short for data volume | Medium | Critical | Rehearse twice, plan phased if needed |
| Regulatory data not preserved | Low | Critical | Dedicated regulatory workstream, archive strategy |
| Users revert to legacy workarounds | Medium | Medium | Training, change management, legacy decommission |
| Customisation budget exceeded | High | High | Hard ceiling, ADR governance, "adopt standard" bias |
| Parallel-run costs overrun | Medium | Medium | Time-box parallel-run, clear exit criteria |

---

## 7. How This Maps to the Existing Repo

The existing 8-stage lifecycle and artefact templates are **compatible** with this methodology. The additions are:

| Existing Repo Element | Re-Implementation Augmentation |
|---|---|
| `lifecycle/gates/01-discovery.gate.md` | Add Pre-Work criteria (legacy inventory, data estate, integration landscape) |
| `lifecycle/gates/02-fit-gap-process-design.gate.md` | Add process redesign (adopt/adapt/abandon), data migration strategy, integration retire/rebuild |
| `lifecycle/gates/05-testing.gate.md` | Add migration rehearsal 1, reconciliation testing, parallel-run testing |
| `lifecycle/gates/06-data-migration.gate.md` | Already migration-focused — augment with regulatory preservation, archive prep |
| `lifecycle/gates/07-cutover.gate.md` | Add legacy freeze, legacy read-only transition |
| `lifecycle/gates/08-hypercare.gate.md` | Add legacy parallel-run, decommission, archive verification |
| `pipeline/_template/STAGE-STATUS.md` | Add workstream tracking columns (WS-1 through WS-6) |
| `artefacts/05-data-quality-scorecard/` | Already migration-focused — augment with domain complexity matrix |
| `artefacts/07-cutover-runbook/` | Add legacy freeze steps, reconciliation steps, legacy read-only steps |

**No structural changes to the repo are needed** — the existing templates are flexible enough. The methodology document (this file) provides the re-implementation context that programme leads apply when filling in the templates.

---

## 8. Summary: What a Re-Implementation Project Plan Looks Like

A re-implementation project plan has these layers that a greenfield plan doesn't:

1. **Pre-Work** — Legacy system inventory, data estate assessment, integration landscape, as-is process documentation
2. **Parallel Workstreams** — Transact config, data migration, integration rebuild, process redesign, legacy decommission, change management — running concurrently across stages
3. **Data Migration as Critical Path** — 6 sub-stages (assess → design → build → rehearse → rehearse → execute), not a single stage
4. **Process Redesign Decisions** — Adopt standard / adapt / abandon for every process, not just "configure Transact"
5. **Integration Rebuild vs Retire** — Every existing integration needs a decision, not just "build new ones"
6. **Legacy Decommission** — Read-only → parallel run → archive → decommission, with regulatory data preservation
7. **Extended Hypercare** — Longer stabilisation, legacy parallel-run, decommission verification
8. **Re-Implementation Specific Risks** — Data quality, cutover window, regulatory preservation, user adoption, customisation scope

The existing Implementation Team OS provides the skeleton. This methodology provides the re-implementation muscle.
