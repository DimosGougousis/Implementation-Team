# Design Authority Process

Defines the ADR review process, design conformance checks, and architecture review board cadence.

## Architecture Review Board (ARB)

| Attribute | Detail |
|---|---|
| Chair | Design Authority |
| Members | Programme Lead, Technical Lead, Integration Architect, Workstream Leads |
| Cadence | Weekly during Stages 3–4, fortnightly during Stages 5–6 |
| Quorum | Chair + 2 members |
| Output | ADR decisions, design conformance reports |

## ADR Lifecycle

```
Draft → Review → Accepted / Rejected / Deferred
                    ↓
              Implemented → Verified → Closed
```

| Status | Definition | Who Sets |
|---|---|---|
| Draft | ADR written, not yet reviewed | Author |
| Review | Presented to ARB for review | Author |
| Accepted | Approved by ARB, can be implemented | ARB Chair |
| Rejected | ARB rejected, alternative needed | ARB Chair |
| Deferred | Decision postponed to a future date | ARB Chair |
| Implemented | Change implemented per ADR | Technical Lead |
| Verified | Implementation verified against ADR | Design Authority |
| Closed | ADR complete, no further action | Design Authority |
| Superseded | Replaced by a newer ADR | ARB Chair |

## ADR Review Rules

- All ADRs must be reviewed by ARB before implementation
- ADRs affecting > 1 workstream require full ARB quorum
- ADRs affecting a single workstream can be approved by ARB Chair + 1 member
- Emergency ADRs (production issues) can be approved by Programme Lead, ratified at next ARB

## Design Conformance Checks

| Check | Frequency | Owner | Output |
|---|---|---|---|
| Code review against ADRs | Per PR | Technical Lead | Conformance pass/fail |
| Architecture diagram update | Per sprint | Design Authority | Updated component model |
| Customisation audit | Per sprint | Design Authority | Customisation register |
| Technology standards compliance | Per release | Design Authority | Compliance report |

## Customisation Governance Link

Every customisation must have:
1. A fit-gap register entry with score ≥ 3
2. An ADR with options considered and trade-off analysis
3. Budget approval from the customisation budget tracker
4. ARB acceptance before implementation begins
