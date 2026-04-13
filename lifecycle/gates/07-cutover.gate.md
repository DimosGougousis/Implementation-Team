---
stage: 7
name: Cutover
artefacts-created: [07-cutover-runbook]
artefacts-updated: []
---

# Stage 7: Cutover

## Purpose
Execute the cutover runbook, manage the go/no-go decision, transition to production, and confirm go-live success.

## Entry Criteria
- [ ] Data Migration gate passed
- [ ] Go/no-go criteria documented and assessed
- [ ] Cutover rehearsal completed
- [ ] Rollback tested
- [ ] Legacy freeze plan reviewed and approved
- [ ] Communication plan approved
- [ ] War room booked and participants confirmed

## Key Activities
1. Conduct final go/no-go review
2. Execute legacy system freeze (see `artefacts/07-cutover-runbook/legacy-freeze-plan.md`)
3. Execute cutover runbook (minute-by-minute)
4. Execute final data extraction and migration
5. Execute reconciliation (source vs target)
6. Execute integration activation and smoke tests
7. Enable user access and verify
8. Transition legacy to read-only
9. Monitor post-cutover stability
10. Confirm go-live success

## Artefacts Produced / Updated

| Artefact | Action | What Changes |
|---|---|---|
| Cutover Runbook | Created | Final runbook with actual timings, rehearsal log |

## Exit Criteria (Gate)
- [ ] Go/no-go decision approved
- [ ] Legacy system frozen (writes disabled)
- [ ] Cutover executed per runbook
- [ ] Data migration completed and validated
- [ ] Reconciliation clean (or exceptions documented)
- [ ] All integrations active and verified
- [ ] Smoke tests passed
- [ ] User access enabled
- [ ] Legacy system in read-only mode
- [ ] Post-cutover stability confirmed (T+4h)
- [ ] Steering Committee notified of go-live

## Steering Committee Checkpoint
Present: go-live confirmation, cutover execution summary, post-cutover stability, hypercare plan.

## Your Contribution at This Stage
- Lead go/no-go decision process
- Manage cutover execution in war room
- Coordinate communication across all stakeholder groups
- CV competencies: Programme Structuring, Stakeholder Orchestration
