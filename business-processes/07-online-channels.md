---
process-area: Online Channels
process-count: 116
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture, 04-integration-dependency-map]
---

# Online Channels Processes

**Process Count:** 116

## Summary

Online Channels processes covers user set up and maintenance associated with Personal, Corporate and Wealth Management customers. It also includes processes specific to Retail, Corporate and Wealth Management as well as Transactional online channels processes.

## Key Sub-Processes

- Personal banking online user setup & maintenance
- Corporate banking online user setup & maintenance
- Wealth Management online user setup & maintenance
- Retail online channel processes
- Corporate online channel processes
- Wealth Management online channel processes
- Transactional online channel processes

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles online channels today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Online Services | AO | 44 | 0 | 0 | holdings |
| System Core | EB | 321 | 191 | 582 | system |
| TEMENOS CONNECT ONBOARDING | T1 | 4 | 0 | 4 | userAdministration |
| TCIB Common | T2 | 14 | 1 | 5 | party |
| Process Workflow | PW | 26 | 12 | 62 | system |
| **Total** | | **409** | **204** | **653** | |

### Key API Patterns

- Channel orchestration via EB System Core
- Online services and onboarding via AO/T1 modules
- Process workflow management via PW module

### Integration Implications

- Expected adapter: System Adapter + Party Adapter (PSD2) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
