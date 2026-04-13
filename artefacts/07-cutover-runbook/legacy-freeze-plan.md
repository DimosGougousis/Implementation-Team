# Legacy Freeze Plan

Procedure for freezing the legacy core banking system prior to Transact go-live.

**Stage:** 7
**Owner:** cutover-manager
**Gate Input:** Gate 7 (Go-Live Confirmed + Legacy Safe)

## Freeze Timeline

| Time | Action | Owner | Verification |
|---|---|---|---|
| T-7 days | Announce freeze date to all stakeholders | Programme Lead | Comms sent |
| T-3 days | Final change freeze on legacy system | Technical Lead | Change log frozen |
| T-24h | Final data quality check on legacy | Data Migration Lead | Quality report clean |
| T-12h | Freeze legacy system for writes | Technical Lead | Write access revoked |
| T-4h | Final data extraction from legacy | Data Migration Lead | Extract complete |
| T-2h | War room setup, comms check | Cutover Manager | All participants confirmed |
| T-1h | Final go/no-go decision | Steering Committee | Decision recorded |

## Freeze Scope

| System | Freeze Type | Exceptions |
|---|---|---|
| Legacy core banking | Full write freeze | None |
| Legacy integrations | Redirect to Transact or disable | Monitoring only |
| Legacy reporting | Read-only | Historical queries only |
| Legacy batch jobs | Disable | End-of-day final run only |

## Communication Plan

| Audience | Message | Channel | Timing |
|---|---|---|---|
| All staff | Legacy freeze date confirmed | Email | T-7 days |
| Business users | Complete all pending transactions | Email + meeting | T-3 days |
| IT Operations | Freeze procedure and monitoring | Slack/Teams | T-24h |
| Steering Committee | Final readiness confirmation | Call | T-1h |
| Customers | Service transition notice (if applicable) | Website + email | T-7 days |

## Rollback from Freeze

If go/no-go decision is NO-GO after freeze:

| Step | Action | Owner | Duration |
|---|---|---|---|
| 1 | Announce rollback decision | Programme Lead | 5 min |
| 2 | Re-enable legacy write access | Technical Lead | 15 min |
| 3 | Restore legacy integrations | Integration Lead | 30 min |
| 4 | Re-enable legacy batch jobs | Technical Lead | 15 min |
| 5 | Verify legacy system operation | Technical Lead | 30 min |
| 6 | Announce rollback complete | Programme Lead | 5 min |

## Freeze Verification

- [ ] Legacy write access revoked for all users
- [ ] Legacy integrations disabled or redirected
- [ ] Legacy batch jobs disabled
- [ ] Final data extract completed and validated
- [ ] Monitoring active for legacy system
- [ ] Rollback procedure tested and ready
