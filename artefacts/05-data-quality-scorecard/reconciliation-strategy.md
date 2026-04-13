# Reconciliation Strategy

Source vs target reconciliation approach for data migration validation.

**Stage:** 5–7
**Owner:** data-migration-lead
**Gate Input:** Gate 6 (Rehearsal 2 Passed + Reconciliation Clean)

## Reconciliation Types

| Type | Description | Method | Tolerance |
|---|---|---|---|
| Record Count | Total records source vs target | Count comparison | 0 (exact match) |
| Balance | Financial balances source vs target | Sum comparison | 0.01 (rounding) |
| Referential Integrity | Parent-child relationships preserved | FK validation | 0 (exact match) |
| Field-Level | Key fields match between source and target | Sample comparison | 0 for mandatory, documented exceptions for optional |
| Business Validation | Key users verify critical data | Manual spot-check | Sign-off required |

## Reconciliation by Domain

| Domain | Record Count | Balance | Referential Integrity | Field-Level | Business Validation |
|---|---|---|---|---|---|
| Customers / Parties | ✅ | — | ✅ | ✅ | ✅ |
| Accounts | ✅ | ✅ | ✅ | ✅ | ✅ |
| Transactions | ✅ | ✅ | ✅ | Sample | — |
| Products | ✅ | — | ✅ | ✅ | — |
| Limits | ✅ | ✅ | ✅ | ✅ | ✅ |
| Standing Orders | ✅ | — | ✅ | ✅ | — |
| Securities | ✅ | ✅ | ✅ | ✅ | ✅ |
| Loans | ✅ | ✅ | ✅ | ✅ | ✅ |
| General Ledger | ✅ | ✅ | ✅ | ✅ | ✅ |

## Reconciliation Scripts

| Script | Purpose | Owner | Status |
|---|---|---|---|
| | | | |

## Exception Handling

| Exception Type | Threshold | Action |
|---|---|---|
| Record count mismatch | Any | Root cause, fix, re-extract |
| Balance mismatch > 0.01 | Any | Root cause, fix, re-extract |
| Orphaned records | Any | Root cause, fix or document |
| Missing mandatory fields | Any | Root cause, fix, re-extract |
| Optional field differences | Document | Log and accept |

## Reconciliation Report Template

| Metric | Source | Target | Delta | Status |
|---|---|---|---|---|
| Total Records | | | | ✅ / ❌ |
| Total Balance | | | | ✅ / ❌ |
| Orphaned Records | | | | ✅ / ❌ |
| Missing Mandatory Fields | | | | ✅ / ❌ |
