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
- [ ] Communication plan approved
- [ ] War room booked and participants confirmed

## Key Activities
1. Conduct final go/no-go review
2. Execute cutover runbook (minute-by-minute)
3. Monitor data migration execution
4. Execute integration activation and smoke tests
5. Enable user access and verify
6. Monitor post-cutover stability
7. Confirm go-live success

## Artefacts Produced / Updated

| Artefact | Action | What Changes |
|---|---|---|
| Cutover Runbook | Created | Final runbook with actual timings, rehearsal log |

## Exit Criteria (Gate)
- [ ] Go/no-go decision approved
- [ ] Cutover executed per runbook
- [ ] Data migration completed and validated
- [ ] All integrations active and verified
- [ ] Smoke tests passed
- [ ] User access enabled
- [ ] Post-cutover stability confirmed (T+4h)
- [ ] Steering Committee notified of go-live

## Steering Committee Checkpoint
Present: go-live confirmation, cutover execution summary, post-cutover stability, hypercare plan.

## Your Contribution at This Stage
- Lead go/no-go decision process
- Manage cutover execution in war room
- Coordinate communication across all stakeholder groups
- CV competencies: Programme Structuring, Stakeholder Orchestration
