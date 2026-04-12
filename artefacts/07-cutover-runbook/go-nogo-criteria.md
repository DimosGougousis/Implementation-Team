# Go / No-Go Criteria

Decision framework for cutover approval.

## Mandatory Criteria (all must be ✅)

| # | Criterion | Evidence | Met? |
|---|---|---|---|
| 1 | UAT sign-off obtained | Sign-off document | |
| 2 | All Critical defects resolved | Defect tracker | |
| 3 | All High defects resolved or mitigated | Defect tracker + mitigation plan | |
| 4 | Data migration rehearsal 2 passed | Rehearsal results | |
| 5 | Performance benchmarks met | Performance test report | |
| 6 | Rollback tested successfully | Rehearsal results | |
| 7 | Cutover rehearsal completed | Rehearsal log | |
| 8 | Communication plan approved | Comms plan sign-off | |
| 9 | Support team trained and ready | Training records | |
| 10 | Infrastructure provisioned and tested | Environment matrix | |

## Advisory Criteria (should be ✅, exceptions documented)

| # | Criterion | Evidence | Met? |
|---|---|---|---|
| 1 | All Medium defects resolved | Defect tracker | |
| 2 | Documentation complete | Doc review | |
| 3 | Training materials delivered | Training records | |
| 4 | Monitoring and alerting configured | Ops runbook | |

## Decision Matrix

| Mandatory ✅ | Advisory ✅ | Decision |
|---|---|---|
| All 10 | All 4 | **GO** |
| All 10 | ≥ 2 | **GO** with conditions |
| All 10 | < 2 | **GO** with risk acceptance |
| < 10 | Any | **NO-GO** |

## Decision Record

| Attribute | Value |
|---|---|
| Date | |
| Decision | GO / NO-GO |
| Decided By | |
| Conditions | |
| Next Review | |
