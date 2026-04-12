# Acceptance Criteria & Automated Evaluations — Reference Guide

**CV Competency:** Acceptance Criteria & Automated Evaluations
**Primary Artefact:** artefacts/06-test-strategy-kpi-dashboard/
**Primary Stage:** 5 — Testing
**Updated At:** 3

---

## What This Competency Covers

The ability to define structured test strategies with clear phase gates, establish measurable KPIs for test effectiveness, classify defects consistently, and manage test environments and data to support rigorous acceptance criteria.

## Key Skills

- Designing four-phase test strategies (Unit → Integration → SIT/Perf → UAT)
- Defining entry/exit criteria per phase with objective pass/fail gates
- Tracking KPIs: pass rate, defect density, cycle time, automation coverage
- Classifying defects with severity/priority taxonomy and SLAs
- Managing test environments with clear purpose, data, and access policies
- Designing test data strategies with masking and refresh processes

## When to Apply

| Stage | Activity |
|---|---|
| 3 — Solution Architecture | Define test strategy framework and entry/exit criteria |
| 5 — Testing | Execute all test phases, track KPIs, manage defects |

## Deliverables

| File | Purpose |
|---|---|
| `test-strategy.md` | Four-phase: Unit → Integration → SIT/Perf → UAT |
| `entry-exit-criteria.md` | Per-phase gates |
| `kpi-dashboard.md` | Defect density, pass rate, cycle time |
| `defect-taxonomy.md` | Severity/priority classification, SLA per category |
| `test-data-strategy.md` | Sourcing, masking, refresh |
| `environment-matrix.md` | Test environments: purpose, data, access, refresh |
| `test-cycles/` | Per-cycle result templates |

## Quality Signals

- Entry/exit criteria are objective and measurable (not subjective)
- KPI dashboard shows trend data across sprints/cycles
- Defect taxonomy has clear severity definitions with examples
- Test data strategy addresses PII masking and refresh cadence
- Environment matrix covers all environments with dependency mapping

## Steering Committee Value

A structured test strategy with measurable KPIs gives the Steering Committee confidence that quality is being tracked objectively, not just reported anecdotally. Exit criteria provide clear evidence for gate reviews.

## CV Narrative

> "I defined the four-phase test strategy with X entry/exit criteria gates, tracked Y KPIs across Z test cycles, and achieved a UAT pass rate of X% with zero Critical defects at sign-off."
