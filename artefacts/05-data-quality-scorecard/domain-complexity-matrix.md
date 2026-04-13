# Domain Complexity Matrix

Maps data domains to complexity, volume, regulatory requirements, and migration priority.

**Stage:** 2
**Owner:** data-migration-lead
**Gate Input:** Gate 2 (Fit-Gap + Migration Strategy Approved)

## Complexity Scoring

| Score | Meaning | Implication |
|---|---|---|
| 1 — Low | Simple mapping, few transformations | Standard ETL, minimal cleansing |
| 2 — Medium | Moderate mapping, some business logic | Custom ETL, cleansing rules needed |
| 3 — High | Complex mapping, significant transformations | Extensive ETL, multiple rehearsals |
| 4 — Very High | Cross-domain dependencies, regulatory constraints | Dedicated workstream, parallel-run consideration |

## Domain Matrix

| Domain | Complexity | Volume | Records (est.) | Regulatory | Priority | Migration Wave | Notes |
|---|---|---|---|---|---|---|---|
| Customers / Parties | High | High | | KYC/AML | Critical | Wave 1 | First to migrate — dependency for all others |
| Accounts | High | High | | Audit trail | Critical | Wave 1 | Core domain — financial integrity |
| Transactions / History | Medium | Very High | | Retention (7-10y) | High | Wave 2 | Archive strategy for historical data |
| Products / Parameters | Medium | Low | | None | Early | Wave 0 | Config dependency — migrate first |
| Limits / Collateral | High | Medium | | Regulatory | High | Wave 1 | Risk domain — regulatory scrutiny |
| Standing Orders / Mandates | Low | Medium | | None | Medium | Wave 2 | Operational — can be migrated later |
| Securities / Holdings | Very High | Medium | | Regulatory | Critical | Wave 1 | If applicable — complex instruments |
| Loans / Facilities | High | High | | Regulatory | Critical | Wave 1 | Financial domain — balance reconciliation |
| General Ledger | High | Medium | | Audit | Critical | Wave 1 | Financial integrity — balance reconciliation |

## Migration Wave Plan

| Wave | Domains | Timing | Dependencies | Risk |
|---|---|---|---|---|
| Wave 0 | Products, Parameters | Stage 4 | None | Low |
| Wave 1 | Customers, Accounts, Limits, Loans, GL, Securities | Stage 6 | Wave 0 complete | High |
| Wave 2 | Transactions, Standing Orders | Stage 6–7 | Wave 1 complete | Medium |
| Archive | Historical transactions (> 5 years) | Stage 7–8 | Regulatory approval | Medium |

## Risk Factors

| Domain | Risk Factor | Mitigation |
|---|---|---|
| Transactions | Volume too large for cutover window | Archive historical, migrate recent only |
| Securities | Complex instrument types | Dedicated securities workstream |
| GL | Balance reconciliation critical | Parallel-run for GL balances |
| Customers | KYC data quality poor | Extended cleansing phase |
