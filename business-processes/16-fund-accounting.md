---
process-area: Fund Accounting
process-count: 69
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Fund Accounting Processes

**Process Count:** 69

## Summary

Fund Accounting Processes cover creation of Accounting Chart along with account definitions, structures, and transaction links. This structure is used as a basis for reporting and to produce financial statements.

## Key Sub-Processes

- Accounting Chart creation
- Account definitions
- Account structures
- Transaction links
- Financial reporting basis
- Financial statement production

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles fund accounting today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Securities | SC | 920 | 360 | 34 | holdings |
| SEAT AUTOMATED TOOL | SE | 3 | 0 | 2 | party |
| **Total** | | **923** | **360** | **36** | |

### Key API Patterns

- Fund accounting and NAV calculation via SC module
- Securities settlement and custody

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
