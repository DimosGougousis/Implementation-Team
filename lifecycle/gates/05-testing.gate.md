---
stage: 5
name: Testing
artefacts-created: [06-test-strategy-kpi-dashboard]
artefacts-updated: [01-architecture-decision-records, 04-integration-dependency-map, 07-cutover-runbook]
---

# Stage 5: Testing

## Purpose
Execute four-phase testing (Unit → Integration → SIT/Perf → UAT), track KPIs, manage defects to gate criteria, and achieve UAT sign-off.

## Entry Criteria
- [ ] Build & Configure gate passed
- [ ] Test environments provisioned and validated
- [ ] Test data loaded and masked
- [ ] Test cases documented and reviewed

## Key Activities
1. Execute Unit tests (development team)
2. Execute Integration tests (integration team)
3. Execute SIT and Performance tests (test team)
4. Execute UAT (business users)
5. Track KPIs: pass rate, defect density, cycle time
6. Manage defects through taxonomy
7. Begin cutover runbook development
8. Execute Data Migration Rehearsal 1 (full dress rehearsal)
9. Execute reconciliation testing (source vs target)
10. Execute parallel-run testing (if applicable)
11. Execute legacy decommission testing

## Artefacts Produced / Updated

| Artefact | Action | What Changes |
|---|---|---|
| Test Strategy & KPI Dashboard | Created | KPI dashboard, defect taxonomy, test cycles |
| Architecture Decision Records | Updated | Test-discovered decisions |
| Integration Dependency Map | Updated | Integration test results |
| Cutover Runbook | Started | Initial runbook, communication plan |

## Exit Criteria (Gate)
- [ ] All test phases completed
- [ ] UAT sign-off obtained
- [ ] All Critical defects resolved
- [ ] All High defects resolved or mitigated
- [ ] Performance benchmarks met
- [ ] Test exit criteria met for all phases
- [ ] Migration Rehearsal 1 completed with acceptable results
- [ ] Reconciliation testing passed
- [ ] Parallel-run testing passed (if applicable)
- [ ] Steering Committee approved test results

## Steering Committee Checkpoint
Present: test results summary, defect status, performance benchmarks, UAT sign-off, go-live readiness.

## Your Contribution at This Stage
- Define and track test KPIs
- Review test exit criteria compliance
- Manage defect triage and prioritisation
- Begin cutover planning
- CV competencies: Acceptance Criteria, Programme Structuring
