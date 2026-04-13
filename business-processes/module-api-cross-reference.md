---
purpose: Cross-reference between Temenos R25AMR modules and business process areas
source: Temenos R25AMR API Catalog (docs/reference-data/temenos-r25amr-api-catalog.xlsx)
last-updated: 2026-04-12
---

# Module-to-Business Process Cross-Reference

> Source: Temenos R25AMR API Catalog | Total Active APIs: 26,689 (IRF: 19,255 / Publisher: 4,381 / PSD2: 3,053)

## Master Mapping Table

| # | Business Process Area | Module Codes | Est. APIs | Key Domains |
|---|---|---|---|---|
| 01 | Customer Relationship Management | CR, CZ, PY, CK | ~468 | party |
| 02 | Retail Banking | AA, AR, AD, AL, AC, RS | 5,204 | holdings, product |
| 03 | Corporate Banking | FL, LC, CO, LI, CONLIB | 3,283 | holdings, order |
| 04 | Transactional | FT, PP, PI, BU, DD, DB, RF, BY | 3,857 | order |
| 05 | Treasury | MM, FX, FR, DX, MD, ND, RP, TY, CW | 756 | holdings, reference |
| 06 | Private Wealth Management | FD, PM, SC | 1,363 | holdings, reference |
| 07 | Online Channels | AO, EB, T1, T2, PW | 1,266 | system, holdings |
| 08 | Security Management | EB (security subset) | — | system |
| 09 | Financial Accounting Parameters | AC, BF, ACCCSM | 809 | holdings, order |
| 10 | Core Parameters | EB, ST | 3,348 | system, reference, party |
| 11 | Islamic Banking | IS | 519 | holdings |
| 12 | Regionalized Solutions | USCORE, USRETL, USRTGS, CABASE, CALEND, AS, ARTAXS, PETAXS, COACCT, FIXAMT, CACARD, CAEBPS, CADEPO, CAEFPA, CAPLND, CAONBK, CARGPL, NACUST, FILEND | 2,711 | holdings, order, party |
| 13 | Digital Engagement | T1, T2, AO | 72 | userAdministration, holdings |
| 14 | Regulatory Reporting & Compliance | FA, MIFID2, USREGS, EV | 256 | party, reference |
| 15 | Financial Crime Mitigation | CR (AML subset), CZ | 66 | party |
| 16 | Fund Accounting | SC, SE | 1,319 | holdings, reference |
| 17 | Temenos Digital | EB, T1, T2 | 1,122 | system, party |
| 18 | Temenos Banking Solution | AA, AR, AD, AL | 4,476 | holdings, product |
| 19 | Business Banking | AA, FL, AL | 5,512 | holdings, order, product |
| 20 | Enterprise Services | IF, IL, IY, RR, DW, EB | 1,263 | system, reference |
| 21 | Financial Risk Management | LI, PV, LMSCOL | 271 | holdings, party |
| 22 | Platform Based Approach | IF, EB, OA | 1,148 | system, reference |

> **Note:** A module may appear in multiple business process areas. API counts are not additive across rows.

## Module Detail Index

| Module | Description | IRF | Publisher | PSD2 | Total | Primary Domains | Process Areas |
|---|---|---|---|---|---|---|---|
| AA | Arrangement Architecture | 2,548 | 6 | 4 | 2,558 | holdings, product | 02, 18, 19 |
| ST | System Tables | 1,164 | 319 | 771 | 2,254 | party, reference | 10 |
| FL | Facility Product | 2,177 | 6 | 0 | 2,183 | holdings, order | 03, 19 |
| SC | Securities | 920 | 360 | 34 | 1,314 | holdings, reference | 06, 16 |
| PP | Payment Suite | 637 | 636 | 0 | 1,273 | order, settings | 04 |
| RF | Request To Pay | 577 | 577 | 0 | 1,154 | order | 04 |
| USCORE | US Core | 595 | 135 | 380 | 1,110 | party, order | 12 |
| EB | System Core | 321 | 191 | 582 | 1,094 | system, party | 07, 08, 10, 17, 20, 22 |
| PI | Payment Initiation | 473 | 473 | 0 | 946 | order, settings | 04 |
| AL | Arrangement Lending | 770 | 1 | 0 | 771 | holdings, product | 02, 18, 19 |
| AC | Accounts | 632 | 63 | 3 | 698 | holdings, order | 02, 09 |
| LC | Letters of Credit | 693 | 0 | 0 | 693 | holdings | 03 |
| AR | AA Retail accounts. | 689 | 2 | 0 | 691 | holdings, product | 02, 18 |
| USRETL | US Retail | 446 | 186 | 48 | 680 | order, holdings | 12 |
| IS | Islamic Banking | 499 | 20 | 0 | 519 | holdings, order | 11 |
| ACHFRM | US - ACH (Feature) | 240 | 240 | 0 | 480 | order | 12 |
| AD | Arrangement Deposits | 466 | 0 | 0 | 466 | holdings | 02, 18 |
| TA | Fixed Assets Management | 438 | 0 | 0 | 438 | holdings | — |
| MD | Misc. Deals | 425 | 0 | 0 | 425 | holdings | 05 |
| PY | Party | 176 | 0 | 176 | 352 | party | 01 |
| PZ | PSD2 Account Information | 7 | 0 | 321 | 328 | party, holdings | 14 |
| USRTGS | FEDWIRE Processing | 158 | 126 | 32 | 316 | order, party | 12 |
| CABASE | Australian Clearing-upload | 216 | 19 | 49 | 284 | holdings, party | 12 |
| LNTRAD | Loan redraw (Feature) | 281 | 0 | 0 | 281 | holdings | 02 |
| LI | Limits | 256 | 0 | 0 | 256 | holdings, product | 03, 21 |
| USIRAC | Fixed Assets Management | 181 | 73 | 0 | 254 | order, holdings | 12 |
| AS | Argentina - Teller (Feature) | 226 | 0 | 0 | 226 | holdings | 12 |
| USREGS | US Regulations (Generic) | 96 | 46 | 50 | 192 | party, order | 12, 14 |
| GMCBAR | General Ledger Rollup (Feature) | 182 | 7 | 0 | 189 | holdings, product | 09 |
| PO | Cash Pooling | 109 | 71 | 0 | 180 | order, holdings | 05 |
| RD | Centralised Pymt Reference Dir | 95 | 79 | 0 | 174 | reference, holdings | 04 |
| DX | Derivatives | 88 | 66 | 3 | 157 | reference, holdings | 05 |
| FIXAMT | Finland - Invoicing (Feature) | 140 | 3 | 3 | 146 | holdings, party | 12 |
| QA | PSD2 Account Information | 73 | 73 | 0 | 146 | order | 14 |
| CQ | Cards and Cheques | 93 | 10 | 42 | 145 | party, holdings | 04 |
| FT | Funds Transfer | 71 | 71 | 0 | 142 | order | 04 |
| DE | Delivery | 71 | 14 | 44 | 129 | party, holdings | 20 |
| DD | Direct Debits | 62 | 62 | 0 | 124 | order | 04 |
| CONLIB | Contingent Liability | 118 | 0 | 0 | 118 | holdings | 03 |
| IN | IBAN | 53 | 53 | 0 | 106 | reference | 04 |
| BY | Payments Beneficiary | 52 | 1 | 51 | 104 | party, reference | 04 |
| TY | Treasury Frontoffice | 58 | 33 | 12 | 103 | reference, holdings | 05 |
| BU | BulkPaymentInitiation | 50 | 50 | 0 | 100 | order | 04 |
| PW | Process Workflow | 26 | 12 | 62 | 100 | system, party | 07 |
| ID | Description | 91 | 0 | 0 | 91 | holdings | — |
| ACCCSM | Generic Accounting Interface | 45 | 45 | 0 | 90 | order | 09 |
| PX | PSD2 Payments | 3 | 3 | 84 | 90 | order, party | 14 |
| FX | Forex | 57 | 31 | 0 | 88 | order, holdings | 05 |
| ACSWIT | Account switch (Feature) | 74 | 0 | 0 | 74 | holdings | 02 |
| ARTAXS | Argentina - Taxes (Feature) | 74 | 0 | 0 | 74 | holdings | 12 |
| CARGPL | RPSCHQ Cheque Clearing Directory | 54 | 16 | 0 | 70 | holdings, order | 12 |
| NSFDES | NSF Decision and Queue Management | 13 | 13 | 44 | 70 | system, reference | 12 |
| MCYAAR | Multi Currency Account Product | 67 | 0 | 0 | 67 | holdings | 02 |
| RETACC | Generic Product Services | 58 | 0 | 0 | 58 | holdings | 02 |
| IL | IBM Integration Bus Adapter | 30 | 25 | 0 | 55 | reference, holdings | 20 |
| FA | FATCA | 26 | 0 | 26 | 52 | party | 14 |
| CK | Consent Management | 25 | 0 | 25 | 50 | party | 01 |
| IM | Image Capture | 25 | 0 | 25 | 50 | party | — |
| SSMBRL | Fixed Assets Management | 48 | 0 | 0 | 48 | holdings | — |
| CR | Customer Relationship Management | 23 | 0 | 23 | 46 | party | 01, 15 |
| RR | Relational Replication | 11 | 11 | 24 | 46 | system, reference | 20 |
| AO | Online Services | 44 | 0 | 0 | 44 | holdings, product | 07, 13 |
| CAEFPA | Australian Clearing-upload | 22 | 14 | 8 | 44 | order, party | 12 |
| ENTPRI | Enterprise pricing | 43 | 1 | 0 | 44 | enterprise, reference | — |
| DM | Document Management | 30 | 1 | 12 | 43 | holdings, party | — |
| CAEBPS | Australian Clearing-upload | 21 | 17 | 4 | 42 | order, party | 12 |
| FD | Fiduciaries | 26 | 16 | 0 | 42 | order, holdings | 06 |
| GMBBAL | General Ledger Rollup (Feature) | 40 | 0 | 0 | 40 | holdings | 09 |
| CACARD | Australian Clearing-upload | 30 | 7 | 0 | 37 | holdings, reference | 12 |
| RC | Transaction Cycler | 36 | 0 | 0 | 36 | holdings | — |
| CO | Collateral | 29 | 4 | 0 | 33 | holdings, reference | 03 |
| ACFAMS | ACFundsAuthorisationMS Product | 22 | 2 | 8 | 32 | holdings, system | — |
| DW | Data Warehousing | 7 | 5 | 20 | 32 | system, meta | 20 |
| AB | Arrangement Bundle | 30 | 0 | 0 | 30 | holdings, product | 02 |
| GMBBAR | General Ledger Rollup (Feature) | 30 | 0 | 0 | 30 | holdings | 09 |
| OA | Origination Architecture | 5 | 5 | 20 | 30 | reference | 22 |
| FR | Forward Rate Agreements | 26 | 0 | 0 | 26 | holdings | 05 |
| IF | Integration Framework | 4 | 4 | 16 | 24 | system | 20, 22 |
| CADEPO | Australian Clearing-upload | 21 | 2 | 0 | 23 | holdings, order | 12 |
| BF | Balance Files | 21 | 0 | 0 | 21 | holdings | 09 |
| MM | Money Market | 21 | 0 | 0 | 21 | holdings | 05 |
| CA | Clearing Accessibility | 10 | 10 | 0 | 20 | order | 12 |
| CZ | Customer Data Protection | 10 | 0 | 10 | 20 | party | 01, 15 |
| RS | Retail Sweeping | 10 | 10 | 0 | 20 | order | 02 |
| T2 | TCIB Common | 14 | 1 | 5 | 20 | party, holdings | 07, 13, 17 |
| XP | Fixed Assets Management | 20 | 0 | 0 | 20 | holdings | — |
| CAPLND | Srilanka clearing directory upload | 18 | 0 | 0 | 18 | holdings | 12 |
| FILEND | Finland - Lending | 18 | 0 | 0 | 18 | holdings | 12 |
| PETAXS | Peru - Taxes | 18 | 0 | 0 | 18 | holdings | 12 |
| RP | Repo | 18 | 0 | 0 | 18 | holdings | 05 |
| Remaining 30+ modules | Various (< 18 APIs each) | — | — | — | ~290 | various | various |

## Unmapped Modules

The following modules are not assigned to a specific business process area (typically utility, legacy, or platform-internal):

- **TA** (Fixed Assets Management, 438 APIs) — assess during fit-gap
- **ID** (Description, 91 APIs)
- **SSMBRL** (Fixed Assets Management, 48 APIs)
- **IM** (Image Capture, 50 APIs)
- **ENTPRI** (Enterprise pricing, 44 APIs)
- **DM** (Document Management, 43 APIs)
- **RC** (Transaction Cycler, 36 APIs)
- **ACFAMS** (ACFundsAuthorisationMS Product, 32 APIs)
- **XP** (Fixed Assets Management, 20 APIs)
- Various small modules (< 20 APIs each)

> These should be reviewed during the fit-gap phase and assigned to the relevant process area or flagged as out-of-scope.
