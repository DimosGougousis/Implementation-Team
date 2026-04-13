---
process-area: Enterprise Services
process-count: 157
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture, 04-integration-dependency-map]
---

# Enterprise Services Processes

**Process Count:** 157

## Summary

Enterprise Services Processes cover two main service areas:

- **Retail Enterprise Services (RES):** Opening and closing of Accounts, Term Deposits, Transferring funds, maintenance, closure of Accounts/Term Deposits, Multi-Currency Accounts and lending with payment capabilities.
- **Business and Corporate Enterprise Service (BCES):** Opening and closing of Accounts, Term Deposits, Transferring funds, maintenance, Payments, closure of Accounts/Term Deposits, Cash Management, Trade Finance & Guarantees and lending.

## Key Sub-Processes

| Service | Capabilities |
|---|---|
| RES | Accounts, Term Deposits, Funds Transfer, Multi-Currency, Lending with payments |
| BCES | Accounts, Term Deposits, Funds Transfer, Payments, Cash Management, Trade Finance, Guarantees, Lending |

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: which enterprise services are relevant -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Integration Framework | IF | 4 | 4 | 16 | system |
| IBM Integration Bus Adapter | IL | 30 | 25 | 0 | reference |
| ISO XML Messages | IY | 12 | 0 | 0 | enterprise |
| Relational Replication | RR | 11 | 11 | 24 | system |
| Data Warehousing | DW | 7 | 5 | 20 | system |
| System Core | EB | 321 | 191 | 582 | system |
| Delivery | DE | 71 | 14 | 44 | party |
| **Total** | | **456** | **250** | **686** | |

### Key API Patterns

- Integration framework and inflow design via IF module
- ISO XML messaging via IY module
- Data warehousing and replication via DW/RR modules

### Integration Implications

- Expected adapter: System Adapter + Reference Adapter (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
