---
process-area: Islamic Banking
process-count: 134
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Islamic Banking Processes

**Process Count:** 134

## Summary

Islamic Banking Processes cover the work flow of Islamic model such as Asset Request, Approval and Purchase of Islamic Assets. Further it covers the end-to-end processing of Asset/Commodity Sale under different products such as Fixed Profit, Variable Profit and Multi Structured. Also it covers the work flow of Vendor/Supplier Payment.

## Key Sub-Processes

- Asset Request workflow
- Asset Approval workflow
- Purchase of Islamic Assets
- Asset/Commodity Sale (Fixed Profit)
- Asset/Commodity Sale (Variable Profit)
- Asset/Commodity Sale (Multi Structured)
- Vendor/Supplier Payment workflow

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles Islamic banking today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Islamic Banking | IS | 499 | 20 | 0 | holdings |
| **Total** | | **499** | **20** | **0** | |

### Key API Patterns

- Islamic banking products (Murabaha, Ijara, etc.) via IS module
- Sharia-compliant arrangement lifecycle management

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
