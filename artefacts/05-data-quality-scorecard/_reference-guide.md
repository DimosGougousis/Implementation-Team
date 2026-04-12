# Data Migration & Quality Assurance — Reference Guide

**CV Competency:** Data Migration & Quality Assurance
**Primary Artefact:** artefacts/05-data-quality-scorecard/
**Primary Stage:** 6 — Data Migration
**Updated At:** 2, 5

---

## What This Competency Covers

The ability to design and execute data migration strategies including profiling, cleansing, mapping, quality gating, and rehearsal execution, with measurable quality metrics tracked domain-by-domain.

## Key Skills

- Designing end-to-end migration strategies (big bang, phased, trickle)
- Profiling source data to identify quality issues
- Defining cleansing rules with before/after validation
- Creating source-to-target mapping specifications
- Establishing quality gates with per-milestone thresholds
- Executing and evaluating migration rehearsals

## When to Apply

| Stage | Activity |
|---|---|
| 2 — Fit-Gap & Process Design | Begin data quality profiling across source systems |
| 5 — Testing | Validate mapping specifications, test cleansing rules |
| 6 — Data Migration | Execute cleansing, rehearsals, achieve quality gates |

## Deliverables

| File | Purpose |
|---|---|
| `quality-scorecard.md` | Domain-by-domain quality metrics |
| `profiling-results/` | Data profiling output templates |
| `cleansing-rules/` | Data cleansing rule definitions |
| `mapping-specifications/` | Source → Transact domain field mappings |
| `quality-gates.md` | Per-milestone gating thresholds |
| `migration-strategy.md` | End-to-end migration approach |
| `rehearsal-results/` | Migration rehearsal result templates |

## Quality Signals

- Quality scorecard shows trend improvement from baseline to target
- Profiling results cover all domains with field-level detail
- Cleansing rules have before/after examples and impact metrics
- Mapping specifications cover all mandatory fields with transformation logic
- Quality gates have clear pass/fail thresholds with escalation paths
- Rehearsal results show timing deltas between runs

## Steering Committee Value

Data quality scorecards provide objective evidence of migration readiness. Rehearsal results demonstrate the programme can execute within the cutover window with acceptable quality.

## CV Narrative

> "I led the data migration for X domains, improving data quality from X% to Y% through Z cleansing rules. Two rehearsals validated the migration within the cutover window, with all quality gates passing on the second rehearsal."
