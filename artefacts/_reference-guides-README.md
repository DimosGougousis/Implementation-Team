# Reference Guides — Convention

Each CV competency mapped in the design spec has a reference guide that provides context on when and how to apply that competency during a Temenos Transact implementation.

## Placement

| Competency | File | Location |
|---|---|---|
| ADRs & Traceability | `_reference-guide.md` | `01-architecture-decision-records/` |
| Target-State Architecture & Systems Thinking | `_reference-guide.md` | `02-target-state-reference-architecture/` |
| Fit-Gap Analysis & Customisation Governance | `_reference-guide.md` | `03-fit-gap-register/` |
| RESTful & Event-Driven Integration Design | `_reference-guide.md` | `04-integration-dependency-map/` |
| Data Migration & Quality Assurance | `_reference-guide.md` | `05-data-quality-scorecard/` |
| Acceptance Criteria & Automated Evaluations | `_reference-guide.md` | `06-test-strategy-kpi-dashboard/` |
| Programme Structuring & Agile at Scale | `_reference-guide.md` | `07-cutover-runbook/` |
| Post-Transformation Operating Model Design | `_reference-guide.md` | `08-post-go-live-operating-model/` |
| Stakeholder & Vendor Orchestration | `stakeholder-and-vendor-orchestration.md` | `governance/` |
| Business Process Alignment & Redesign | `process-alignment-and-redesign.md` | `business-processes/` |

## Convention

- **8 primary competencies** → `_reference-guide.md` co-located inside their mapped artefact folder
- **2 cross-cutting competencies** → placed in `governance/` and `business-processes/` since these folders already exist for those topics
- Each guide follows the same structure: What It Covers, Key Skills, When to Apply, Deliverables, Quality Signals, Steering Committee Value, CV Narrative

## Why Co-Located?

Reference guides sit next to the deliverable templates they support. When you open an artefact folder, you see both the templates (what to produce) and the reference guide (how to produce it well).
