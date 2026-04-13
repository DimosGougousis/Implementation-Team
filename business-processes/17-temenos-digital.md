---
process-area: Temenos Digital
process-count: 46
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture, 04-integration-dependency-map]
---

# Temenos Digital Processes

**Process Count:** 46

## Summary

Temenos Digital Processes covers customer on-boarding, retail and corporate services such as managing account, beneficiary, cheques, lending etc.

## Key Sub-Processes

- Customer on-boarding (digital)
- Account management
- Beneficiary management
- Cheque management
- Lending services
- Retail digital services
- Corporate digital services

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles digital banking today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| System Core | EB | 321 | 191 | 582 | system |
| TEMENOS CONNECT ONBOARDING | T1 | 4 | 0 | 4 | userAdministration |
| TCIB Common | T2 | 14 | 1 | 5 | party |
| **Total** | | **339** | **192** | **591** | |

### Key API Patterns

- Digital banking platform via EB System Core
- Temenos Connect digital channels via T1/T2 modules

### Integration Implications

- Expected adapter: System Adapter (IRF/PSD2) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
