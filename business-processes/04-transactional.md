---
process-area: Transactional
process-count: 496
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture, 04-integration-dependency-map]
---

# Transactional Processes

**Process Count:** 496

## Summary

Transactional processes consist of Payments and Cheque Processing/Clearing. These are normally performed at Back Office as they are of high volume and operationally intensive in nature.

## Key Sub-Processes

- Payments processing
- Cheque processing / Clearing
- Back office operations
- High-volume transaction handling

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles transactional processing today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Funds Transfer | FT | 71 | 71 | 0 | order |
| Payment Suite | PP | 637 | 636 | 0 | order |
| Payment Initiation | PI | 473 | 473 | 0 | order |
| BulkPaymentInitiation | BU | 50 | 50 | 0 | order |
| Direct Debits | DD | 62 | 62 | 0 | order |
| Debit Collection | DB | 7 | 7 | 0 | order |
| Request To Pay | RF | 577 | 577 | 0 | order |
| Payments Beneficiary | BY | 52 | 1 | 51 | party |
| CARDS AND CHEQUES | CQ | 93 | 10 | 42 | party |
| IBAN | IN | 53 | 53 | 0 | reference |
| Centralised Pymt Reference Dir | RD | 95 | 79 | 0 | reference |
| **Total** | | **2,170** | **2,019** | **93** | |

### Key API Patterns

- Payment initiation and processing via PP/PI modules (order domain)
- Funds transfer and bulk payments via FT/BU modules
- Direct debits and request-to-pay via DD/RF modules

### Integration Implications

- Expected adapter: Order Adapter (IRF/Publisher) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
