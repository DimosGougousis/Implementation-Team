# Module & API Cross-Reference

Master mapping of Temenos Transact R25AMR modules to business process areas, with API counts per integration surface.

**Source:** `docs/reference-data/temenos-r25amr-api-catalog.xlsx`
**Total Unique Modules:** 128
**Total APIs:** 27,710 (IRF: 19,878 + Publisher: 4,449 + PSD2: 3,383)

---

## Master Mapping Table

| # | Process Area | Module Codes | Total APIs | Key Domains |
|---|---|---|---|---|
| 01 | Customer Relationship Management | CR, CZ, PY, CK | 555 | party, holdings |
| 02 | Retail Banking | AA, AR, AD, AL, AC, RS | 5,078 | holdings, product |
| 03 | Corporate Banking | FL, LC, CO, LI, CONLIB | 3,349 | holdings, order |
| 04 | Transactional | FT, PP, PI, BU, DD, DB, RF, BY | 2,721 | order, reference |
| 05 | Treasury | MM, FX, FR, DX, MD, ND, RP, TY, CW | 694 | order, holdings |
| 06 | Private Wealth Management | FD, PM, SC | 969 | order, holdings |
| 07 | Online Channels | AO, EB, T1, T2, PW | 1,449 | system, holdings |
| 08 | Security Management | EB (security subset) | ~200 | system |
| 09 | Financial Accounting | AC, BF, ACCCSM | 771 | holdings, reference |
| 10 | Core Parameters | EB, ST | 3,588 | system, reference |
| 11 | Islamic Banking | IS | 519 | holdings |
| 12 | Regionalized Solutions | USCORE, USRETL, USRTGS, CABASE, CALEND, etc. | 2,400+ | holdings, system |
| 13 | Digital Engagement | T1, T2, AO | 53 | system |
| 14 | Regulatory & Compliance | FA, MIFID2, USREGS, EV | 297 | system, reference |
| 15 | Financial Crime | CR (AML subset), CZ | 38 | party |
| 16 | Fund Accounting | SC, SE | 1,329 | order, holdings |
| 17 | Temenos Digital | EB, T1, T2 | 1,332 | system, holdings |
| 18 | Temenos Banking Solution | AA, AR, AD, AL | 4,630 | holdings, product |
| 19 | Business Banking | AA, FL, AL | 5,620 | holdings |
| 20 | Enterprise Services | IF, IL, IY, RR, DW, EB | 1,392 | system, reference |
| 21 | Financial Risk Management | LI, PV, LMSCOL | 290 | holdings |
| 22 | Platform Based Approach | IF, EB, OA | 1,339 | system |

---

## Module Detail Index

| Module Code | Module Name | IRF | Publisher | PSD2 | Total | Process Areas |
|---|---|---|---|---|---|---|
| AA | Arrangement Architecture | 2,646 | 6 | 4 | 2,656 | 02, 18, 19 |
| AB | Arrangement Bundle | 31 | 0 | 0 | 31 | — |
| AC | Accounts | 633 | 63 | 9 | 705 | 02, 09 |
| ACCCSM | Generic Accounting Interface | 45 | 45 | 0 | 90 | 09 |
| ACFAMS | Accounting Families | 24 | 8 | 8 | 40 | — |
| ACHFRM | Accounting Framework | 241 | 241 | 0 | 482 | — |
| AD | Arrangement Disbursement | 472 | 0 | 0 | 472 | 02, 18 |
| AL | Arrangement Lending | 776 | 1 | 0 | 777 | 02, 18, 19 |
| AO | Account Opening | 45 | 0 | 0 | 45 | 07, 13 |
| AR | Arrangement Repayment | 725 | 2 | 0 | 727 | 02, 18 |
| AS | Arrangement Sweep | 244 | 0 | 0 | 244 | — |
| BU | Bulk Payments | 55 | 55 | 0 | 110 | 04 |
| BY | Bypass | 52 | 1 | 51 | 104 | 04 |
| CABASE | CA Base | 216 | 19 | 49 | 284 | 12 |
| CAEBPS | CA EB Payments | 21 | 17 | 4 | 42 | — |
| CAEFPA | CA EB FP Accounts | 22 | 14 | 8 | 44 | — |
| CALEND | Calendar | 4 | 0 | 0 | 4 | 12 |
| CK | Cheques | 45 | 0 | 40 | 85 | 01 |
| CO | Correspondent Banking | 29 | 4 | 4 | 37 | 03 |
| CONLIB | Contract Library | 118 | 0 | 0 | 118 | 03 |
| CR | Customer Relationship | 24 | 0 | 24 | 48 | 15 |
| CQ | Cheque Processing | 93 | 10 | 42 | 145 | — |
| CW | Cross-Currency Swaps | 1 | 0 | 0 | 1 | 05 |
| CZ | Customer Onboarding | 14 | 0 | 14 | 28 | 01, 15 |
| DD | Direct Debits | 62 | 62 | 0 | 124 | 04 |
| DE | Delivery | 76 | 19 | 44 | 139 | — |
| DM | Document Management | 31 | 1 | 12 | 44 | — |
| DW | Data Warehouse | 7 | 5 | 20 | 32 | 20 |
| DX | Derivatives | 89 | 67 | 3 | 159 | 05 |
| EB | Enterprise Backbone | 391 | 213 | 710 | 1,314 | 07, 08, 10, 17, 20, 22 |
| ENTPRI | Enterprise Pricing | 77 | 1 | 0 | 78 | — |
| EV | Events | 1 | 1 | 4 | 6 | 14 |
| FA | Financial Accounting | 28 | 0 | 28 | 56 | 14 |
| FD | Fiduciary | 26 | 16 | 0 | 42 | 06 |
| FIXAMT | Fixed Amounts | 140 | 3 | 3 | 146 | — |
| FL | Foreign Lending | 2,181 | 6 | 0 | 2,187 | 03, 19 |
| FR | Forward Rate Agreements | 26 | 0 | 0 | 26 | 05 |
| FT | Funds Transfer | 71 | 71 | 6 | 148 | 04 |
| FX | Foreign Exchange | 57 | 31 | 0 | 88 | 05 |
| GMCBAR | GMC Banking | 182 | 7 | 0 | 189 | — |
| IF | Integration Framework | 4 | 4 | 16 | 24 | 20, 22 |
| IL | Integration Logging | 30 | 25 | 0 | 55 | 20 |
| IM | Intermediary | 25 | 0 | 25 | 50 | — |
| IN | Interest | 53 | 53 | 0 | 106 | 04 |
| IS | Islamic Banking | 499 | 20 | 0 | 519 | 11 |
| IY | Integration Messaging | 12 | 0 | 0 | 12 | 20 |
| LC | Letters of Credit | 741 | 0 | 0 | 741 | 03 |
| LI | Limits | 282 | 0 | 0 | 282 | 21 |
| LMSCOL | Limits Collateral | 6 | 0 | 3 | 9 | 21 |
| LNTRAD | Loan Trading | 281 | 0 | 0 | 281 | — |
| MD | Money Market Deposits | 425 | 0 | 0 | 425 | 05 |
| MIFID2 | MiFID II | 3 | 0 | 3 | 6 | 14 |
| MM | Money Market | 21 | 0 | 0 | 21 | 05 |
| ND | Negotiable Deposits | 14 | 0 | 0 | 14 | 05 |
| OA | Online Administration | 5 | 5 | 20 | 30 | 22 |
| PI | Payments Initiation | 478 | 478 | 3 | 959 | 04 |
| PM | Portfolio Management | 8 | 0 | 0 | 8 | 06 |
| PO | Payment Orders | 109 | 71 | 0 | 180 | — |
| PP | Payment Processing | 643 | 642 | 0 | 1,285 | 04 |
| PV | Present Value | 4 | 0 | 2 | 6 | 21 |
| PW | Password/Web | 27 | 12 | 63 | 102 | 07 |
| PX | PSD2 Extended | 3 | 3 | 129 | 135 | — |
| PZ | PSD2 Core | 7 | 0 | 423 | 430 | — |
| QA | Quality Assurance | 73 | 73 | 0 | 146 | — |
| RC | Receivables | 36 | 0 | 0 | 36 | — |
| RD | Retail Deposits | 95 | 79 | 0 | 174 | — |
| RF | Reference Data | 577 | 577 | 0 | 1,154 | 04 |
| RP | Repurchase Agreements | 18 | 0 | 0 | 18 | 05 |
| RR | Regulatory Reporting | 12 | 12 | 24 | 48 | 20 |
| RS | Retail Savings | 16 | 16 | 0 | 32 | 02 |
| SC | Securities | 930 | 360 | 35 | 1,325 | 06, 16 |
| SE | Securities Settlement | 4 | 0 | 3 | 7 | 16 |
| SSMBRL | SMS Berlin | 219 | 0 | 0 | 219 | — |
| ST | Standing Orders | 1,174 | 320 | 780 | 2,274 | 10 |
| TA | Trade Finance | 438 | 0 | 0 | 438 | — |
| T1 | Temenos Digital 1 | 4 | 0 | 4 | 8 | 07, 13, 17 |
| T2 | Temenos Digital 2 | 14 | 1 | 5 | 20 | 07, 13, 17 |
| TY | Tax | 60 | 35 | 12 | 107 | 05 |
| USCORE | US Core | 598 | 135 | 383 | 1,116 | 12 |
| USIRAC | US Interest Accrual | 181 | 73 | 0 | 254 | 12 |
| USRETL | US Retail | 446 | 186 | 48 | 680 | 12 |
| USRTGS | US RTGS | 171 | 139 | 32 | 342 | 12 |
| USREGS | US Regulations | 96 | 46 | 50 | 192 | 12, 14 |

*Modules with < 10 total APIs and no process area mapping omitted for brevity. Full list in source Excel.*

---

## Unmapped Modules

Modules not assigned to any process area (typically internal, utility, or region-specific):

| Module Code | Module Name | Total APIs | Notes |
|---|---|---|---|
| AB | Arrangement Bundle | 31 | Internal arrangement utility |
| ACFAMS | Accounting Families | 40 | Accounting sub-module |
| ACHFRM | Accounting Framework | 482 | Accounting infrastructure |
| AS | Arrangement Sweep | 244 | Sweep configuration |
| CAEBPS | CA EB Payments | 42 | Channel-specific |
| CAEFPA | CA EB FP Accounts | 44 | Channel-specific |
| CQ | Cheque Processing | 145 | Cheque clearing |
| DE | Delivery | 139 | Message delivery |
| DM | Document Management | 44 | Document handling |
| ENTPRI | Enterprise Pricing | 78 | Pricing engine |
| FIXAMT | Fixed Amounts | 146 | Fee/fixed amount config |
| GMCBAR | GMC Banking | 189 | GMC integration |
| IM | Intermediary | 50 | Intermediary processing |
| LNTRAD | Loan Trading | 281 | Loan trading |
| PO | Payment Orders | 180 | Payment order management |
| PV | Present Value | 6 | Risk calculation |
| PX | PSD2 Extended | 135 | PSD2 extension |
| PZ | PSD2 Core | 430 | PSD2 core |
| QA | Quality Assurance | 146 | QA tooling |
| RC | Receivables | 36 | Receivables |
| RD | Retail Deposits | 174 | Retail deposits |
| SSMBRL | SMS Berlin | 219 | SMS Berlin interface |
| TA | Trade Finance | 438 | Trade finance |

---

## Integration Surface Summary

| Surface | Active APIs | Deprecated | Total | Key Domains |
|---|---|---|---|---|
| IRF | 19,255 | 623 | 19,878 | holdings (12K), order (3.3K), party (2K), product (974), reference (849) |
| Publisher | 4,381 | 68 | 4,449 | order (3.3K), reference (857), system (194) |
| PSD2 | 3,053 | 330 | 3,383 | party (2.4K), system (776) |
| **Total** | **26,689** | **1,021** | **27,710** | |
