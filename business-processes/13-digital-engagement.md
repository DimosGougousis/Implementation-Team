---
process-area: Digital Engagement
process-count: 22
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture, 04-integration-dependency-map]
---

# Digital Engagement Processes

**Process Count:** 22

## Summary

Digital Engagement processes caters to designing, planning and executing results-driven communications (Campaigns) across a variety of Online Channels (Internet and Mobile Banking) and Offline Channels (Email, Secure Message, SMS). Managing real time communication with Customers through Digital Channels is achieved through Digital Engagement User Agents Interfaces (front end applications - Campaign Management User Agent Interface and Campaign Administration User Agent Interface).

## Key Sub-Processes

- Campaign design, planning and execution
- Online Channel communications (Internet Banking, Mobile Banking)
- Offline Channel communications (Email, Secure Message, SMS)
- Real-time customer communication management
- Campaign Management User Agent Interface
- Campaign Administration User Agent Interface

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles digital engagement today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| TEMENOS CONNECT ONBOARDING | T1 | 4 | 0 | 4 | userAdministration |
| TCIB Common | T2 | 14 | 1 | 5 | party |
| Online Services | AO | 44 | 0 | 0 | holdings |
| **Total** | | **62** | **1** | **9** | |

### Key API Patterns

- Digital onboarding via T1 (Temenos Connect Onboarding)
- Common digital banking features via T2 (TCIB Common)
- Online self-service via AO module

### Integration Implications

- Expected adapter: System Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
