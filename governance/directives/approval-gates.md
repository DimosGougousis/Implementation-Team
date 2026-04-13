# Approval Gates Directive

Defines who approves gate passage, escalation thresholds, and conditional pass criteria for the 8-stage Temenos Transact implementation lifecycle.

## Gate Authority

| Gate | Primary Approver | Secondary Approver | Escalation |
|---|---|---|---|
| 1 — Discovery | Programme Lead | Business Sponsor | Steering Committee |
| 2 — Fit-Gap | Programme Lead | Design Authority | Steering Committee |
| 3 — Architecture | Design Authority | Programme Lead | Steering Committee |
| 4 — Build | Programme Lead | Technical Lead | Steering Committee |
| 5 — Testing | Test Manager | Programme Lead | Steering Committee |
| 6 — Migration | Data Migration Lead | Programme Lead | Steering Committee |
| 7 — Cutover | Steering Committee | Programme Lead | CTO |
| 8 — Hypercare | Programme Lead | Business Sponsor | Steering Committee |

## Gate Decisions

| Decision | Definition | Action |
|---|---|---|
| **Pass** | All exit criteria met | Proceed to next stage |
| **Conditional Pass** | ≤ 2 minor items outstanding, mitigation plan documented | Proceed with tracked remediation |
| **Fail** | Exit criteria not met, no acceptable mitigation | Remediate and re-present at next gate review |

## Conditional Pass Rules

- Maximum 2 conditional passes in a row — third consecutive requires Steering Committee escalation
- Conditional items must have an owner, due date, and mitigation plan
- Conditional items must be resolved before the next gate review
- All conditional passes recorded in STAGE-STATUS.md gate history

## Gate Review Process

1. Programme lead completes all exit criteria checklist items
2. Artefacts reviewed against gate template
3. Gate review meeting with primary and secondary approvers
4. Decision recorded in STAGE-STATUS.md with date, attendees, key issues
5. If Conditional Pass: remediation items logged with owner and due date
6. If Fail: root cause documented, remediation plan agreed, re-review scheduled

## Escalation Thresholds

| Trigger | Escalation Level |
|---|---|
| Gate fails twice | Steering Committee |
| Conditional pass 3x in a row | Steering Committee |
| Stage duration exceeds plan by > 25% | Programme Lead → Steering Committee |
| Budget consumed > 75% before Stage 5 | Steering Committee |
| Critical risk identified with no mitigation | Immediate Steering Committee |
