# API Register

Full catalogue of APIs in the target-state architecture.

> **Source:** Temenos R25AMR API Catalog
> **Catalog Date:** 2026-04-12
> **Total Active APIs:** 26,689 (IRF: 19,255 / Publisher: 4,381 / PSD2: 3,053)
> **Total Deprecated:** 1,021
> **Full Catalog:** `docs/reference-data/temenos-r25amr-api-catalog.xlsx`

## Transact API Summary

### Coverage by API Sheet

| Sheet | Active | Deprecated | Total | Primary Use |
|---|---|---|---|---|
| IRF | 19,255 | 623 | 19,878 | Internal integration & back-office |
| Publisher | 4,381 | 68 | 4,449 | External data publishing & notifications |
| PSD2 | 3,053 | 330 | 3,383 | Open banking / regulatory (PSD2) |
| **Total** | **26,689** | **1,021** | **27,710** | |

### Domain × Method Matrix — IRF (19,255 active)

| Domain | GET | POST | PUT | DELETE | Total |
|---|---|---|---|---|---|
| holdings | 5,086 | 3,313 | 3,273 | 227 | 11,899 |
| order | 1,447 | 947 | 738 | 138 | 3,270 |
| party | 946 | 394 | 478 | 100 | 1,918 |
| product | 694 | 170 | 110 | 0 | 974 |
| reference | 507 | 172 | 142 | 28 | 849 |
| system | 90 | 31 | 48 | 5 | 174 |
| settings | 23 | 20 | 30 | 13 | 86 |
| enterprise | 53 | 3 | 3 | 0 | 59 |
| meta | 16 | 4 | 0 | 0 | 20 |
| userAdministration | 4 | 0 | 0 | 0 | 4 |

### Domain × Method Matrix — Publisher (4,381 active)

| Domain | GET | POST | PUT | DELETE | Total |
|---|---|---|---|---|---|
| order | 1,447 | 947 | 738 | 138 | 3,270 |
| reference | 507 | 172 | 142 | 28 | 849 |
| system | 90 | 31 | 48 | 5 | 174 |
| settings | 23 | 20 | 30 | 13 | 86 |

### Domain × Method Matrix — PSD2 (3,053 active)

| Domain | GET | POST | PUT | DELETE | Total |
|---|---|---|---|---|---|
| party | 1,060 | 418 | 562 | 121 | 2,161 |
| system | 360 | 124 | 192 | 20 | 696 |
| holdings | 81 | 0 | 0 | 0 | 81 |
| order | 9 | 48 | 12 | 9 | 78 |
| reference | 28 | 0 | 0 | 0 | 28 |
| userAdministration | 4 | 0 | 0 | 0 | 4 |

### Top 30 Modules by API Count

| Module | Description | IRF | Publisher | PSD2 | Total | Primary Domains |
|---|---|---|---|---|---|---|
| AA | Arrangement Architecture | 2,548 | 6 | 4 | 2,558 | holdings, product |
| ST | System Tables | 1,164 | 319 | 771 | 2,254 | party, reference |
| FL | Facility Product | 2,177 | 6 | 0 | 2,183 | holdings, order |
| SC | Securities | 920 | 360 | 34 | 1,314 | holdings, reference |
| PP | Payment Suite | 637 | 636 | 0 | 1,273 | order, settings |
| RF | Request To Pay | 577 | 577 | 0 | 1,154 | order |
| USCORE | US Core | 595 | 135 | 380 | 1,110 | party, order |
| EB | System Core | 321 | 191 | 582 | 1,094 | system, party |
| PI | Payment Initiation | 473 | 473 | 0 | 946 | order, settings |
| AL | Arrangement Lending | 770 | 1 | 0 | 771 | holdings, product |
| AC | Accounts | 632 | 63 | 3 | 698 | holdings, order |
| LC | Letters of Credit | 693 | 0 | 0 | 693 | holdings |
| AR | AA Retail accounts | 689 | 2 | 0 | 691 | holdings, product |
| USRETL | US Retail | 446 | 186 | 48 | 680 | order, holdings |
| IS | Islamic Banking | 499 | 20 | 0 | 519 | holdings, order |
| ACHFRM | US - ACH (Feature) | 240 | 240 | 0 | 480 | order |
| AD | Arrangement Deposits | 466 | 0 | 0 | 466 | holdings |
| TA | Fixed Assets Management | 438 | 0 | 0 | 438 | holdings |
| MD | Misc. Deals | 425 | 0 | 0 | 425 | holdings |
| PY | Party | 176 | 0 | 176 | 352 | party |
| PZ | PSD2 Account Information | 7 | 0 | 321 | 328 | party, holdings |
| USRTGS | FEDWIRE Processing | 158 | 126 | 32 | 316 | order, party |
| CABASE | Australian Clearing-upload | 216 | 19 | 49 | 284 | holdings, party |
| LNTRAD | Loan redraw (Feature) | 281 | 0 | 0 | 281 | holdings |
| LI | Limits | 256 | 0 | 0 | 256 | holdings, product |
| USIRAC | Fixed Assets Management | 181 | 73 | 0 | 254 | order, holdings |
| AS | Argentina - Teller (Feature) | 226 | 0 | 0 | 226 | holdings |
| USREGS | US Regulations (Generic) | 96 | 46 | 50 | 192 | party, order |
| GMCBAR | General Ledger Rollup | 182 | 7 | 0 | 189 | holdings, product |
| PO | Cash Pooling | 109 | 71 | 0 | 180 | order, holdings |

> See `business-processes/module-api-cross-reference.md` for the complete 128-module index.

### Representative APIs by Domain

#### holdings (11,899 active IRF APIs)

| API Name | Version | Method | Endpoint | Module | Status |
|---|---|---|---|---|---|
| holding-loans-arrangements | v1.0.0 | POST | /holdings/loans/personalLoans | AL | Active |
| holding-loans-arrangements | v1.0.0 | POST | /holdings/loans/commercialLoans | AL | Active |
| holding-loans-arrangements | v1.0.0 | POST | /holdings/loans/mortgages | AL | Active |
| holding-loans-arrangements | v1.0.0 | POST | /holdings/loans/creditLines | AL | Active |
| arrangements-balances | v2.0.0 | GET | /holdings/arrangements/{id}/consolidatedBalances | AA | Active |

#### order (3,270 active IRF APIs)

| API Name | Version | Method | Endpoint | Module | Status |
|---|---|---|---|---|---|
| order-accountTransfers | v1.0.0 | POST | /order/fundsMovement | FT | Active |
| order-accountTransfers | v1.0.0 | PUT | /order/fundsMovement/{fundsTransferId} | FT | Active |
| order-accountTransfers | v1.0.0 | GET | /order/fundsMovement/{debitAcct}/{creditAcct} | FT | Active |
| order-accountTransfers | v1.0.0 | GET | /order/transfers/bulkTransfers/{bulkTransferId} | FT | Active |
| order-accountTransfers | v1.0.0 | POST | /order/transfers/inwards | FT | Active |

#### party (1,918 active IRF APIs)

| API Name | Version | Method | Endpoint | Module | Status |
|---|---|---|---|---|---|
| customer-account-details | v1.0.0 | GET | /party/customers/accountDetails | SE | Active |
| participantList-service | v1.0.0 | GET | /party/participants | PW | Active |
| party-beneficiaries-service | v1.0.0 | PUT | /party/beneficiaries/{beneficiaryId} | BY | Active |
| party-beneficiaries-service | v1.0.0 | POST | /party/beneficiaries | BY | Active |
| party-beneficiaries-service | v1.0.0 | DELETE | /party/beneficiaries/{beneficiaryId} | BY | Active |

#### product (974 active IRF APIs)

| API Name | Version | Method | Endpoint | Module | Status |
|---|---|---|---|---|---|
| product-customers-service | v1.0.0 | GET | /product/customers/{id}/eligibleProducts | AA | Active |
| product-customers-service | v1.0.0 | GET | /product/periodicInterests/{id} | AA | Active |
| product-customers-service | v1.0.0 | GET | /product/interestCatalog/{id} | AA | Active |
| product-ca-product-service | v1.0.0 | GET | /product/ca/products | CABASE | Active |
| product-externalProducts | v1.0.0 | POST | /product/loans/mortgages/externalProducts/{id} | AA | Active |

#### reference (849 active IRF APIs)

| API Name | Version | Method | Endpoint | Module | Status |
|---|---|---|---|---|---|
| origination | v1.0.0 | GET | /reference/originationDefinitions | OA | Active |
| origination | v1.0.0 | GET | /reference/originationRoles | OA | Active |
| origination | v1.0.0 | GET | /reference/originationDefinitions/{id} | OA | Active |
| origination | v1.0.0 | GET | /reference/entityTypes/{id}/activities | OA | Active |

#### system (174 active IRF APIs)

| API Name | Version | Method | Endpoint | Module | Status |
|---|---|---|---|---|---|
| integration-inflowDesign | v1.0.0 | POST | /system/integrationInflowDesigns/{id} | IF | Active |
| integration-inflowDesign | v1.0.0 | PUT | /system/integrationInflowDesigns/{id} | IF | Active |
| integration-inflowDesign | v1.0.0 | GET | /system/integrationInflowDesigns | IF | Active |
| system-channels-service | v1.0.0 | PUT | /system/channels/parameters/{systemId} | EB | Active |

## Custom APIs

| API Name | Version | Endpoint | Auth | Owner | Status |
|---|---|---|---|---|---|
| _(populated per-programme — copy to pipeline/active/<prog>/artefacts/)_ | | | | | |

## Third-Party APIs

| API Name | Provider | Version | Endpoint | Auth | SLA |
|---|---|---|---|---|---|
| _(populated per-programme)_ | | | | | |

## Full Catalog Reference

The complete API catalog (26,689 active APIs across 128 modules) is maintained in:
- **Excel source:** `docs/reference-data/temenos-r25amr-api-catalog.xlsx`
- **Module index:** `business-processes/module-api-cross-reference.md`
- **Business process mapping:** Each `business-processes/NN-*.md` file has a `## Transact Module & API Coverage` section
