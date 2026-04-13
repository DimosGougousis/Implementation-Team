---
process-area: Corporate Banking
process-count: 238
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Corporate Banking Processes

**Process Count:** 238

## Summary

Corporate Banking processes support Corporate Current and Deposit Accounts, Corporate Loans, Project Loans, Syndicated Lending, Correspondent Banking, Trade Finance & Guarantees, Factoring & Forfaiting Processes and Supply Chain Finance.

## Key Sub-Processes

- Corporate Current and Deposit Accounts
- Corporate Loans
- Project Loans
- Syndicated Lending
- Correspondent Banking
- Trade Finance & Guarantees
- Factoring & Forfaiting
- Supply Chain Finance

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles corporate banking today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Facility Product | FL | 2,177 | 6 | 0 | holdings |
| Letters of Credit | LC | 693 | 0 | 0 | holdings |
| Collateral | CO | 29 | 4 | 0 | holdings |
| Limits | LI | 256 | 0 | 0 | holdings |
| Contingent Liability | CONLIB | 118 | 0 | 0 | holdings |
| **Total** | | **3,273** | **10** | **0** | |

### Key API Patterns

- Facility/syndicated lending via FL module (holdings domain)
- Trade finance (L/C, guarantees) via LC module
- Collateral management and limits via CO/LI modules

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
