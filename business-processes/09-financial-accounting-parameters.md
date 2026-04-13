---
process-area: Financial Accounting Parameters
process-count: 34
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Financial Accounting Parameter Processes

**Process Count:** 34

## Summary

Processes for maintaining parameters relating to financial accounting, accounting rules, set up of general ledger and financial reporting.

## Key Sub-Processes

- Financial accounting parameter maintenance
- Accounting rules configuration
- General ledger setup
- Financial reporting configuration

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles financial accounting parameters today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Accounts | AC | 632 | 63 | 3 | holdings |
| Balance Files | BF | 21 | 0 | 0 | holdings |
| Generic Accounting Interface | ACCCSM | 45 | 45 | 0 | order |
| General Ledger Rollup (Feature) | GMCBAR | 182 | 7 | 0 | holdings |
| General Ledger Rollup (Feature) | GMBBAL | 40 | 0 | 0 | holdings |
| General Ledger Rollup (Feature) | GMBBAR | 30 | 0 | 0 | holdings |
| **Total** | | **950** | **115** | **3** | |

### Key API Patterns

- Accounting entries and balance management via AC module
- General ledger rollup and reporting via GM* modules
- Generic accounting interface via ACCCSM module

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
