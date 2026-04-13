---
stage: 6
name: Data Migration
artefacts-created: [05-data-quality-scorecard]
artefacts-updated: [01-architecture-decision-records, 07-cutover-runbook]
---

# Stage 6: Data Migration

## Purpose
Execute data profiling, cleansing, mapping, and rehearsals. Achieve quality gate thresholds for all domains and prepare for cutover.

## Entry Criteria
- [ ] Testing gate passed
- [ ] Data migration strategy approved
- [ ] Mapping specifications complete
- [ ] Cleansing rules implemented
- [ ] Migration environment ready

## Key Activities
1. Execute data cleansing per cleansing rules
2. Validate mapping specifications
3. Conduct Rehearsal 1 — measure and remediate
4. Conduct Rehearsal 2 — achieve quality gates
5. Update quality scorecard with final metrics
6. Finalise cutover runbook with migration timing
7. Prepare reconciliation scripts
8. Verify regulatory data preservation (audit trail, KYC/AML, retention)
9. Prepare legacy data archive (regulatory-compliant)
10. Validate reconciliation strategy (record counts, balances, referential integrity)
8. Verify regulatory data preservation (audit trail, KYC/AML, retention)
9. Prepare legacy data archive (regulatory-compliant)
10. Validate reconciliation strategy (record counts, balances, referential integrity)

## Artefacts Produced / Updated

| Artefact | Action | What Changes |
|---|---|---|
| Data Quality Scorecard | Created | Final quality scorecard, rehearsal results |
| Architecture Decision Records | Updated | Migration-discovered decisions |
| Cutover Runbook | Updated | Migration timing, rehearsal log |

## Exit Criteria (Gate)
- [ ] All data domains cleansed
- [ ] Rehearsal 1 completed with acceptable results
- [ ] Regulatory data preservation verified
- [ ] Legacy data archive prepared
- [ ] Rehearsal 2 completed — all quality gates passed
- [ ] Reconciliation scripts tested
- [ ] Migration timing validated against cutover window
- [ ] Regulatory data preservation verified
- [ ] Legacy data archive prepared
- [ ] Steering Committee approved migration readiness

## Steering Committee Checkpoint
Present: data quality metrics, rehearsal results, migration timing, risks, go-live readiness.

## Your Contribution at This Stage
- Lead data quality assessment and remediation
- Review rehearsal results and quality gate compliance
- Validate migration timing against cutover window
- CV competencies: Data Migration & Quality Assurance
