---
process-area: Business Banking
process-count: 34
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Business Banking Processes

**Process Count:** 34

## Summary

Business Banking processes cover a range of service offerings such as Accounts, Deposits, Loans, Asset Finance products that serve the needs of the Small Medium Enterprise (SME) segment.

## Key Sub-Processes

- SME Accounts
- SME Deposits
- SME Loans
- Asset Finance products
- SME-specific service offerings

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles business banking today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Arrangement Architecture | AA | 2,548 | 6 | 4 | holdings |
| Facility Product | FL | 2,177 | 6 | 0 | holdings |
| Arrangement Lending | AL | 770 | 1 | 0 | holdings |
| **Total** | | **5,495** | **13** | **4** | |

### Key API Patterns

- SME/business lending via FL/AL modules (holdings domain)
- Business arrangement management via AA module

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
