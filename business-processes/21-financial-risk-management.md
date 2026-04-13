---
process-area: Financial Risk Management
process-count: 19
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Financial Risk Management Processes

**Process Count:** 19

## Summary

Financial Risk Management illustrates various approaches or methodologies for risk management using reporting tools and techniques.

## Key Sub-Processes

- Risk management methodologies
- Risk reporting tools
- Risk analysis techniques
- Risk measurement approaches

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles financial risk management today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Limits | LI | 256 | 0 | 0 | holdings |
| Provisioning Module | PV | 4 | 0 | 2 | party |
| Lifecycle Management - Collections | LMSCOL | 6 | 0 | 3 | party |
| **Total** | | **266** | **0** | **5** | |

### Key API Patterns

- Credit limits and exposure management via LI module
- Provisioning and impairment via PV module
- Collections lifecycle management via LMSCOL module

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
