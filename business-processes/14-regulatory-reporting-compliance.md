---
process-area: Regulatory Reporting and Compliance
process-count: 66
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Regulatory Reporting and Compliance Processes

**Process Count:** 66

## Summary

Regulatory Reporting Processes cover the creation of FATCA/CRS report setup, creation, generation and checking of reports. It also caters to customer personal data definition, searching and protection. Processes involved in loan management and restructuring have also been included.

## Key Sub-Processes

- FATCA report setup and generation
- CRS report setup and generation
- Report creation and checking
- Customer personal data definition
- Customer data searching and protection
- Loan management compliance
- Loan restructuring compliance

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles regulatory reporting today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| FATCA | FA | 26 | 0 | 26 | party |
| MiFID II for Transact only clients | MIFID2 | 3 | 0 | 3 | party |
| US Regulations (Generic) | USREGS | 96 | 46 | 50 | party |
| Evidence Management | EV | 1 | 1 | 4 | reference |
| PSD2 Account Information | PZ | 7 | 0 | 321 | party |
| PSD2 Account Information | QA | 73 | 73 | 0 | order |
| PSD2 Payments | PX | 3 | 3 | 84 | order |
| **Total** | | **209** | **123** | **488** | |

### Key API Patterns

- PSD2 account information and payments via PZ/PX modules
- FATCA reporting via FA module (party domain)
- MiFID II compliance via MIFID2 module

### Integration Implications

- Expected adapter: PSD2 Adapter + Party Adapter (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
