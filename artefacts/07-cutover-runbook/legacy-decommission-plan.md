# Legacy Decommission Plan

Phased retirement of the legacy core banking system after Transact go-live.

**Stage:** 7–8
**Owner:** programme-governance
**Gate Input:** Gate 8 (Steady State + Legacy Decommissioned)

## Decommission Phases

| Phase | Timing | Duration | Activities | Exit Criteria |
|---|---|---|---|---|
| **Read-Only** | Stage 7 (cutover day) | Day 1 | Legacy access revoked for writes, read-only for reference | All writes redirected to Transact |
| **Parallel Run** | Stage 8 (weeks 1–4) | 4 weeks | Legacy available for reconciliation queries, no business processing | Reconciliation clean, no business dependency |
| **Archive** | Stage 8 (weeks 4–8) | 4 weeks | Data extracted to archive (regulatory-compliant), access controls applied | Archive verified, regulatory sign-off |
| **Decommission** | Post-hypercare | 2 weeks | Infrastructure shut down, licences terminated, contracts closed | All systems offline, contracts closed |

## Decommission Checklist

### Read-Only Transition (Day 1)
- [ ] All business processing migrated to Transact
- [ ] All integrations redirected or retired
- [ ] Legacy write access revoked
- [ ] Legacy read-only access granted to authorised users
- [ ] Monitoring active for legacy system

### Parallel Run (Weeks 1–4)
- [ ] Legacy available for reconciliation queries
- [ ] No business processing on legacy
- [ ] Daily reconciliation between legacy and Transact
- [ ] Issues logged and resolved
- [ ] Parallel run exit criteria defined

### Archive (Weeks 4–8)
- [ ] Data extracted to regulatory-compliant archive
- [ ] Archive access controls applied
- [ ] Historical transaction data accessible for audit
- [ ] Regulatory data preservation verified
- [ ] Archive access tested by authorised users

### Decommission (Post-Hypercare)
- [ ] Legacy infrastructure shut down
- [ ] Legacy licences terminated
- [ ] Legacy vendor contracts closed
- [ ] Cost savings realised and reported
- [ ] Decommission completion report produced

## Archive Requirements

| Data Type | Retention Period | Access Method | Regulatory Requirement |
|---|---|---|---|
| Transaction history | 7–10 years | Read-only archive query | Audit trail |
| Customer records | 7 years post-relationship | Read-only archive query | KYC/AML |
| Account records | 10 years | Read-only archive query | Audit trail |
| GL entries | 10 years | Read-only archive query | Financial audit |
| Audit logs | 7 years | Read-only archive query | Regulatory |

## Cost Savings

| Item | Monthly Cost | Annual Saving |
|---|---|---|
| Legacy licences | £ | £ |
| Legacy infrastructure | £ | £ |
| Legacy support contract | £ | £ |
| **Total** | **£** | **£** |
