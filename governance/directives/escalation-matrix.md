# Escalation Matrix

Defines escalation levels, triggers, contacts, and response SLAs for programme and operational issues.

## Escalation Levels

| Level | Role | Response SLA | Trigger |
|---|---|---|---|
| L1 | Workstream Lead | 15 min | Issue within workstream, can be resolved locally |
| L2 | Programme Lead | 30 min | Cross-workstream issue, or L1 unresolved after 30 min |
| L3 | Steering Committee | 2 hours | Programme-level risk, budget breach, gate failure |
| L4 | CTO | Immediate | Regulatory breach, data loss, security incident |

## Escalation Triggers

| Trigger | Level | Action |
|---|---|---|
| Technical issue within workstream | L1 | Workstream Lead resolves |
| Cross-workstream dependency blocked | L2 | Programme Lead coordinates |
| Gate review failed | L3 | Steering Committee decides |
| Stage duration > 125% of plan | L3 | Steering Committee review |
| Budget consumed > 75% before Stage 5 | L3 | Steering Committee alert |
| Budget consumed > 90% | L3 | Mandatory re-prioritisation |
| Critical defect in production | L2 → L3 | Programme Lead escalates if unresolved in 2h |
| Data loss or corruption | L4 | Immediate CTO notification |
| Security breach | L4 | Immediate CTO notification |
| Regulatory non-compliance | L3 → L4 | Steering Committee → CTO |
| Vendor SLA breach | L2 | Programme Lead engages vendor |
| Key resource unavailable > 1 week | L2 | Programme Lead backfill decision |

## Escalation Process

1. **Identify** — Issue classified against trigger list
2. **Notify** — Escalation sent to appropriate level with context
3. **Respond** — Escalation owner acknowledges within SLA
4. **Resolve** — Action plan agreed and executed
5. **Close** — Resolution documented, root cause recorded
6. **Learn** — Post-incident review for L3/L4 escalations

## Escalation Log

| Date | Issue | Level | Trigger | Owner | Resolution | Time to Resolve |
|---|---|---|---|---|---|---|
| | | | | | | |

## Contact Matrix

| Level | Name | Role | Email | Phone | Backup |
|---|---|---|---|---|---|
| L1 | | Workstream Lead | | | |
| L2 | | Programme Lead | | | |
| L3 | | Steering Committee Chair | | | |
| L4 | | CTO | | | |
