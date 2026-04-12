# Fit-Gap Analysis & Customisation Governance — Reference Guide

**CV Competency:** Fit-Gap Analysis & Customisation Governance
**Primary Artefact:** artefacts/03-fit-gap-register/
**Primary Stage:** 2 — Fit-Gap & Process Design
**Updated At:** 3, 4

---

## What This Competency Covers

The ability to systematically assess Temenos Transact modules against business requirements, score gaps objectively, govern customisation decisions through a budget framework, and produce evidence-based recommendations to stakeholders.

## Key Skills

- Facilitating structured fit-gap workshops with business stakeholders
- Scoring requirements on a consistent scale (Fit / Partial / Gap)
- Evaluating customisation vs workaround vs accept-gap trade-offs
- Tracking and enforcing a customisation budget with escalation thresholds
- Producing module assessment reports with clear recommendations

## When to Apply

| Stage | Activity |
|---|---|
| 2 — Fit-Gap & Process Design | Conduct workshops, score requirements, establish budget |
| 3 — Solution Architecture | Link gaps to ADRs, refine scoring based on architecture |
| 4 — Build & Configure | Track budget consumption, reassess gaps during build |

## Deliverables

| File | Purpose |
|---|---|
| `fit-gap-register.md` | Master register: module → requirement → Fit/Gap/Partial → score |
| `customisation-budget.md` | Hard ceiling tracker: budget consumed vs remaining |
| `customisation-requests/` | Individual customisation request forms |
| `module-assessments/` | Per Transact module assessment reports |
| `workshop-notes/` | Fit-gap workshop session notes |

## Quality Signals

- Every requirement has a score with documented rationale
- Customisation budget has clear escalation thresholds (50%, 75%, 90%, 100%)
- Workshop notes capture decisions and action items
- Module assessments provide clear accept/configure/customise recommendations
- No "shadow customisations" outside the register

## Steering Committee Value

Fit-gap analysis quantifies the customisation scope and cost, enabling informed trade-off decisions. Budget tracking prevents scope creep and demonstrates fiscal discipline.

## CV Narrative

> "I led fit-gap workshops across X Transact modules, scoring Y requirements and identifying Z customisations. My governance framework prevented £Xm in unnecessary customisations by enforcing a hard budget ceiling with escalation thresholds."
