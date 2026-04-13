---
process-area: Private Wealth Management
process-count: 319
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Private Wealth Management Processes

**Process Count:** 319

## Summary

Private Wealth Management processes covers the full life cycle of discretionary wealth management - from Asset Allocation & Portfolio Modeling, through Client Profiling, Maintenance/Review of portfolios, performance measurement and portfolio rebalancing. This process area also covers a range of processes related to Trading of Securities, Derivatives, Forex and Structured Products, as well as Mutual Funds, Fiduciary placements and administration processes such as Corporate Actions.

## Key Sub-Processes

- Asset Allocation & Portfolio Modeling
- Client Profiling
- Portfolio Maintenance / Review
- Performance Measurement
- Portfolio Rebalancing
- Securities Trading
- Derivatives Trading
- Forex Trading
- Structured Products
- Mutual Funds
- Fiduciary Placements
- Corporate Actions

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles wealth management today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Fiduciaries | FD | 26 | 16 | 0 | order |
| Position Management | PM | 7 | 0 | 0 | holdings |
| Securities | SC | 920 | 360 | 34 | holdings |
| **Total** | | **953** | **376** | **34** | |

### Key API Patterns

- Securities trading and settlement via SC module
- Portfolio/position management via PM module
- Fiduciary services via FD module

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
