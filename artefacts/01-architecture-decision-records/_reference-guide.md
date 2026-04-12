# ADRs & Traceability — Reference Guide

**CV Competency:** ADRs & Traceability
**Primary Artefact:** artefacts/01-architecture-decision-records/
**Primary Stage:** 3 — Solution Architecture
**Updated At:** 4, 5, 6

---

## What This Competency Covers

The ability to capture significant architectural decisions with full context, maintain a structured decision log, and trace decisions back to requirements and forward to implementation artefacts.

## Key Skills

- Writing clear, actionable Architecture Decision Records (ADRs)
- Evaluating options with explicit trade-off analysis
- Maintaining a decision register with status tracking
- Building traceability matrices linking requirements → decisions → implementation
- Governing customisation decisions through the ADR process

## When to Apply

| Stage | Activity |
|---|---|
| 3 — Solution Architecture | Author initial ADRs for all significant decisions |
| 4 — Build & Configure | Update ADRs as new decisions emerge during build |
| 5 — Testing | Revise ADRs based on test-discovered issues |
| 6 — Data Migration | Revise ADRs based on migration-discovered constraints |

## Deliverables

| File | Purpose |
|---|---|
| `_template.md` | ADR template (Context, Decision, Options Rejected, Consequences) |
| `adr-register.md` | Master index: ADR# → title → status → date → linked requirement |
| `traceability-matrix.md` | Requirement → ADR → implementation mapping |
| `decisions/` | Individual ADR files (ADR-001.md, ADR-002.md, ...) |

## Quality Signals

- Every significant decision has an ADR (no "tribal knowledge" gaps)
- ADR status is current (no stale "Proposed" decisions from months ago)
- Traceability matrix has no orphaned requirements or unlinked ADRs
- Options considered section shows genuine alternatives, not straw men

## Steering Committee Value

ADRs demonstrate rigorous decision-making, reduce rework by documenting rationale, and provide an audit trail for regulatory and governance reviews.

## CV Narrative

> "I authored X ADRs across the programme, each with explicit trade-off analysis and traceability to business requirements. My decisions prevented £Ym in unnecessary customisations and provided a clear audit trail for the Steering Committee."
