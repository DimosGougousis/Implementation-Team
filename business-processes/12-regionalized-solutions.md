---
process-area: Regionalized Solutions
process-count: 268
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture, 14-regulatory-reporting-compliance]
---

# Regionalized Solution Processes

**Process Count:** 268

## Summary

Regionalized Solution Processes cater to features that are specific to a particular country/region.

- **United Kingdom:** Customer Relationship Management, Financial Services Compensation Scheme (FSCS), Continuity of Access (COA), CRS, BACS Clearing, Clear Bank Interface and ISA/JISA accounts/deposits service offerings.
- **United States:** Customer Relationship Management, Retail and Corporate service offerings.
- **India:** Corporate service offerings.
- **Australia:** Retail and Open banking service offerings.
- **Peru:** Retail and Corporate service offerings.
- **Argentina:** Retail and Corporate service offerings.
- **Colombia:** Retail service offerings.
- **Mexico:** Retail and Corporate service offerings.
- **Hong Kong:** Retail service offerings.
- **New Zealand:** Retail service offerings.
- **Global:** Retail and Corporate service offerings.

## Key Sub-Processes (by Region)

| Region | Coverage | Key Features |
|---|---|---|
| United Kingdom | CRM, Retail, Compliance | FSCS, COA, CRS, BACS, Clear Bank, ISA/JISA |
| United States | CRM, Retail, Corporate | |
| India | Corporate | |
| Australia | Retail, Open Banking | |
| Peru | Retail, Corporate | |
| Argentina | Retail, Corporate | |
| Colombia | Retail | |
| Mexico | Retail, Corporate | |
| Hong Kong | Retail | |
| New Zealand | Retail | |
| Global | Retail, Corporate | |

## Fit-Gap Status

| Region | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: which regional features are relevant -->

## Target State (Transact)
<!-- Map to Transact regionalized packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| US Core | USCORE | 595 | 135 | 380 | party |
| US Retail | USRETL | 446 | 186 | 48 | order |
| FEDWIRE Processing | USRTGS | 158 | 126 | 32 | order |
| Australian Clearing-upload | CABASE | 216 | 19 | 49 | holdings |
| US - ACH (Feature) | ACHFRM | 240 | 240 | 0 | order |
| Argentina - Teller (Feature) | AS | 226 | 0 | 0 | holdings |
| Argentina - Taxes (Feature) | ARTAXS | 74 | 0 | 0 | holdings |
| Peru - Taxes | PETAXS | 18 | 0 | 0 | holdings |
| Colombia - Account and deposit regulations | COACCT | 13 | 0 | 0 | holdings |
| Finland - Invoicing capability (Fininvoice) | FIXAMT | 140 | 3 | 3 | holdings |
| Fixed Assets Management | USIRAC | 181 | 73 | 0 | order |
| US Regulations (Generic) | USREGS | 96 | 46 | 50 | party |
| Australian Clearing-upload | CACARD | 30 | 7 | 0 | holdings |
| Australian Clearing-upload | CAEBPS | 21 | 17 | 4 | order |
| Australian Clearing-upload | CADEPO | 21 | 2 | 0 | holdings |
| Australian Clearing-upload | CAEFPA | 22 | 14 | 8 | order |
| Srilanka clearing directory upload | CAPLND | 18 | 0 | 0 | holdings |
| Srilanka clearing directory upload | CAONBK | 13 | 0 | 0 | holdings |
| RPSCHQ Cheque Clearing Directory | CARGPL | 54 | 16 | 0 | holdings |
| NSF Decision and Queue Management | NSFDES | 13 | 13 | 44 | system |
| Clearing Accessibility | CA | 10 | 10 | 0 | order |
| Finland - Lending | FILEND | 18 | 0 | 0 | holdings |
| Canada - Customer Messages/Notes | NACUST | 6 | 6 | 0 | reference |
| **Total** | | **2,629** | **913** | **618** | |

### Key API Patterns

- US market: ACH, FEDWIRE, retail banking via USCORE/USRETL/USRTGS/ACHFRM
- Australian clearing and NPP via CABASE/CA* modules
- Regional tax and compliance via ARTAXS/PETAXS/COACCT modules

### Integration Implications

- Expected adapter: Multiple region-specific adapters (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
