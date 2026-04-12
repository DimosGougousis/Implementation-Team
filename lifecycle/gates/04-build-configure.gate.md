---
stage: 4
name: Build & Configure
artefacts-created: []
artefacts-updated: [01-architecture-decision-records, 02-target-state-reference-architecture, 03-fit-gap-register, 04-integration-dependency-map]
---

# Stage 4: Build & Configure

## Purpose
Implement Transact configuration, customisations, and integrations according to the approved architecture. Track progress against the customisation budget and update artefacts as decisions evolve.

## Entry Criteria
- [ ] Solution Architecture gate passed
- [ ] All ADRs approved
- [ ] Development environments provisioned
- [ ] Build team onboarded

## Key Activities
1. Configure Transact modules per fit-gap register
2. Implement approved customisations per ADRs
3. Build and test integrations per dependency map
4. Track customisation budget consumption
5. Update ADRs as new decisions emerge
6. Conduct code reviews and design conformance checks
7. Prepare test environments and data

## Artefacts Produced / Updated

| Artefact | Action | What Changes |
|---|---|---|
| Architecture Decision Records | Updated | New decisions, superseded ADRs |
| Target-State Reference Architecture | Updated | API register, event channels refined |
| Fit-Gap Register | Updated | Implementation status per requirement |
| Integration Dependency Map | Updated | API contracts, event contracts populated |

## Exit Criteria (Gate)
- [ ] All modules configured
- [ ] All approved customisations implemented
- [ ] All integrations built and unit tested
- [ ] Customisation budget within threshold
- [ ] Code reviews complete
- [ ] Test environments ready
- [ ] Steering Committee briefed on build status

## Steering Committee Checkpoint
Present: build progress, customisation budget status, integration readiness, risks, test readiness.

## Your Contribution at This Stage
- Conduct design conformance reviews
- Track customisation budget and escalate thresholds
- Update ADRs for emerging decisions
- Validate integration implementations against contracts
- CV competencies: ADRs & Traceability, Customisation Governance
