# Customisation Governance Directive

Defines customisation decision criteria, budget enforcement, ADR linkage, and approval workflow.

## Core Principle

**Adopt before Adapt before Customise.** Every customisation must prove that configuration and process change cannot meet the requirement.

## Decision Criteria

| Criterion | Weight | Scoring |
|---|---|---|
| Business criticality | 30% | 1 (nice-to-have) → 5 (regulatory/legal) |
| Configuration alternative exists | 25% | 1 (no alternative) → 5 (full config solution) |
| Process change alternative exists | 20% | 1 (no alternative) → 5 (full process solution) |
| Upgrade impact | 15% | 1 (no impact) → 5 (breaks upgrade path) |
| Cost (effort × risk) | 10% | 1 (trivial) → 5 (massive) |

## Decision Outcomes

| Outcome | Criteria | Approval |
|---|---|---|
| **Accept as-is** | Score 1–2, configuration meets need | Fit-Gap Analyst |
| **Configure** | Score 3, minor config change | Fit-Gap Analyst |
| **Customise (minor)** | Score 4, moderate customisation, within budget | Design Authority + ADR |
| **Customise (major)** | Score 5, significant customisation, within budget | ARB + ADR + Budget approval |
| **Reject** | Exceeds budget, or breaks upgrade path | Steering Committee |
| **Workaround** | Customisation rejected, business accepts manual process | Business Sponsor |

## Budget Enforcement

| Threshold | Action |
|---|---|
| 50% consumed | Programme Lead review |
| 75% consumed | Steering Committee alert |
| 90% consumed | Mandatory re-prioritisation — no new customisations without Steering Committee approval |
| 100% consumed | No further customisations without CTO approval |

## ADR Linkage

Every customisation with score ≥ 3 requires:
1. ADR with context, options considered, trade-off analysis
2. ARB review and acceptance
3. Budget allocation from customisation budget tracker
4. Traceability matrix entry linking requirement → ADR → implementation

## Customisation Request Workflow

```
Request → Score (Fit-Gap Analyst) → ADR (Design Authority) → ARB Review → Approve/Reject
                                                                          ↓
                                                                    Budget Check
                                                                          ↓
                                                                    Implement → Verify → Close
```

## Anti-Patterns

| Anti-Pattern | Reality |
|---|---|
| "We need everything we have today" | Challenge every requirement — is it still needed? |
| "It's just a small change" | Small changes compound — track everything |
| "The vendor said it's standard" | Verify — check the fit-gap register |
| "We'll sort it out later" | Later = never — decide now, document now |
