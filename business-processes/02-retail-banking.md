---
process-area: Retail Banking
process-count: 166
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Retail Banking Processes

**Process Count:** 166

## Summary

Retail Banking processes cover a range of service offerings such as Savings & Current Accounts, Deposits, Consumer Loans, Mortgages, Teller Transactions - including Cash, Currency Exchange, Travellers Cheques etc. Complete end-to-end processing is supported, from account opening/loan origination, establishing lending arrangement, setting up of sweeps/standing orders, and account/contract maintenance and closure.

## Key Sub-Processes

- Savings & Current Accounts
- Deposits
- Consumer Loans
- Mortgages
- Teller Transactions (Cash, Currency Exchange, Travellers Cheques)
- Account opening / Loan origination
- Lending arrangement setup
- Sweeps / Standing orders
- Account / Contract maintenance and closure

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles retail banking today -->

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
| AA Retail accounts. | AR | 689 | 2 | 0 | holdings |
| Arrangement Deposits | AD | 466 | 0 | 0 | holdings |
| Arrangement Lending | AL | 770 | 1 | 0 | holdings |
| Accounts | AC | 632 | 63 | 3 | holdings |
| Retail Sweeping | RS | 10 | 10 | 0 | order |
| Loan redraw (Feature) | LNTRAD | 281 | 0 | 0 | holdings |
| Multi Currency Account Product | MCYAAR | 67 | 0 | 0 | holdings |
| Generic Product Services | RETACC | 58 | 0 | 0 | holdings |
| Account switch (Feature) | ACSWIT | 74 | 0 | 0 | holdings |
| Arrangement Bundle | AB | 30 | 0 | 0 | holdings |
| **Total** | | **5,625** | **82** | **7** | |

### Key API Patterns

- Arrangement lifecycle (create/amend/close) via AA module (holdings domain)
- Retail account operations via AR module
- Deposit and lending products via AD/AL modules

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
