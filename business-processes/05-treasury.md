---
process-area: Treasury
process-count: 79
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Treasury Processes

**Process Count:** 79

## Summary

Treasury processes support a range of vanilla (FX, MM) as well as Derivative products (FRAs, SWAPS, CCY Swaps etc). Customer position analysis, formulation of trading strategy, trade initiation, execution and settlement etc. are covered.

## Key Sub-Processes

- Foreign Exchange (FX)
- Money Market (MM)
- Forward Rate Agreements (FRAs)
- Interest Rate Swaps (SWAPS)
- Cross-Currency Swaps (CCY Swaps)
- Customer position analysis
- Trading strategy formulation
- Trade initiation, execution and settlement

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles treasury today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Money Market | MM | 21 | 0 | 0 | holdings |
| Forex | FX | 57 | 31 | 0 | order |
| Forward Rate Agreements | FR | 26 | 0 | 0 | holdings |
| Derivatives | DX | 88 | 66 | 3 | reference |
| Misc. Deals | MD | 425 | 0 | 0 | holdings |
| NON-DELIVERY FORWARD | ND | 14 | 0 | 0 | holdings |
| Repo | RP | 18 | 0 | 0 | holdings |
| Treasury Frontoffice | TY | 58 | 33 | 12 | reference |
| CW - Cash Flow | CW | 1 | 0 | 0 | holdings |
| Cash Pooling | PO | 109 | 71 | 0 | order |
| **Total** | | **817** | **201** | **15** | |

### Key API Patterns

- Treasury front-office dealing via TY/FX/MM modules
- Derivatives and forward rate agreements via DX/FR modules
- Cash management and pooling via PO/CW modules

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) + Reference Adapter (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
