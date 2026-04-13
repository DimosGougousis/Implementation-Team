---
process-area: Temenos Banking Solution (TBS)
process-count: 75
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture, 04-integration-dependency-map]
---

# Temenos Banking Solution (TBS) Processes

**Process Count:** 75

## Summary

Temenos Banking Solution (TBS) Processes cover multiple fulfillment services:

- **Retail Lending Fulfillment Service (RFS):** Creation, disbursement, and repayment of Loans.
- **Retail Deposits Banking Service (RDBS):** Opening & closing of Accounts, Term Deposits, Transferring funds, maintenance, closure, Alerts, Multi-Currency Accounts and Multi-Company Groups.
- **Target Instant Payment System (TIPS) Service:** Outward remittance, inward credit transfers, and cancellation of payments.
- **Temenos Enterprise Pricing (TEP):** Creating package arrangements for pricing benefits, closing packages, updating negotiated price and capturing relationships for relationship pricing.
- **Buy Now Pay Later (BNPL):** Financing options for retail customers, from Customer registration, Loan creation to Loan cancellation and refund. Supports amendment and closure of Facilities and loans.

## Key Sub-Processes

| Service | Capabilities |
|---|---|
| RFS | Loan creation, disbursement, repayment |
| RDBS | Accounts, Term Deposits, Funds Transfer, Alerts, Multi-Currency |
| TIPS | Outward remittance, inward credit transfers, payment cancellation |
| TEP | Package arrangements, negotiated pricing, relationship pricing |
| BNPL | Customer registration, loan creation/cancellation, facility management |

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: which TBS services are relevant -->

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
| **Total** | | **4,473** | **9** | **4** | |

### Key API Patterns

- Core banking product suite via AA framework (holdings domain)
- Retail accounts, deposits, and lending as TBS components

### Integration Implications

- Expected adapter: Holdings Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
