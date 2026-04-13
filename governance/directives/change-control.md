# Change Control Directive

Defines the change request process for post-go-live changes and programme-stage changes.

## Change Types

| Type | Description | Approval | Lead Time | Example |
|---|---|---|---|---|
| Standard | Pre-approved, low-risk, repeatable | Automated | 1 day | Config change, report update |
| Normal | Requires review and assessment | CAB | 5 days | New integration, module config |
| Emergency | Urgent fix for production issue | Emergency CAB | 4 hours | Production outage fix |

## Change Advisory Board (CAB)

| Role | Member | Voting |
|---|---|---|
| Chair | Head of Technology / Programme Lead | Yes |
| Business Rep | Business Sponsor / Head of Banking Ops | Yes |
| Technical Lead | Application Lead | Yes |
| Security | Security Lead | Yes |
| Vendor | Temenos Account Manager | Advisory |

## Change Lifecycle

```
Request → Assess → Approve → Schedule → Implement → Verify → Close
              ↓
          Reject / Defer
```

## Change Request Template

| Field | Required |
|---|---|
| Change ID | Auto-generated |
| Requester | Yes |
| Date | Yes |
| Type | Standard / Normal / Emergency |
| Description | Yes |
| Business Justification | Yes |
| Impact Assessment | Yes (scope, cost, timeline, risk) |
| Rollback Plan | Yes |
| Test Plan | Yes |
| Approval | CAB / Emergency CAB |

## Change Windows

| Window | Day | Time | Risk Level |
|---|---|---|---|
| Standard | Saturday | 02:00–06:00 | Low–Medium |
| Emergency | Any | As needed | High (with approval) |

## Programme-Stage Change Control

During Stages 1–7, changes follow the ADR process (see `design-authority-process.md`). Post-go-live (Stage 8+), changes follow this directive.

## Rollback Requirements

Every change must include:
- Rollback procedure (step-by-step)
- Rollback time estimate
- Verification steps post-rollback
- Data backup confirmation (if data-modifying)
