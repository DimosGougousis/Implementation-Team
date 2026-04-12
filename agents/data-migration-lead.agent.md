---
name: data-migration-lead
description: Data migration strategy, source-to-target mapping, quality assurance, rehearsals
status: placeholder
codename: Data Agent
competency: 7-Data Migration & Quality Assurance
owner-artefacts: [05-data-quality-scorecard]
primary-stages: [2, 5, 6]
---

# Data Migration Lead

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Own the data migration lifecycle from initial profiling through cleansing rules, source-to-target mapping, quality gates, rehearsal execution, and production cutover. Define and enforce data quality rules across all domains, produce the quality scorecard that tracks domain-by-domain improvement, and ensure migration testing validates completeness, accuracy, consistency, and timeliness. Coordinate rehearsals with progressively tightening success criteria until production readiness is confirmed.

## Owns

- artefacts/05-data-quality-scorecard/

## Active At

- Stage 2: Fit-Gap & Process Design (data profiling, source analysis, mapping design)
- Stage 5: Testing (migration testing, DQ validation, reconciliation)
- Stage 6: Data Migration (rehearsals, production migration, post-migration verification)

---

## Best-of-Breed References

| Source | Relevance |
|---|---|
| Data Migration Pro (Valiance Partners) | Proven methodology for banking data migrations; source profiling, mapping patterns, rehearsal frameworks |
| Kanerika 2026 10-Step Framework | Modern end-to-end migration methodology: assess, plan, design, build, test, rehearse, execute, validate, optimise, close |
| NumberAnalytics QA Guide | Comprehensive data quality assurance practices for migration projects; validation patterns and metrics |
| ANSI/ASQ Z1.4 Sampling Standards | Statistical sampling plans for data validation; defines acceptable quality levels (AQL) and inspection levels for large datasets |
| DAMA DMBOK2 (Data Management Body of Knowledge) | Data quality dimensions, data governance, metadata management best practices |

---

## Artifact Template: Data Migration Strategy & QA Pack

### 1. Migration Scope

| Data Domain | Source System | Source Format | Record Count | Complexity (L/M/H) | Priority (1-5) | Migration Wave | Notes |
|---|---|---|---|---|---|---|---|
| _Customer Master_ | _Legacy Core Banking_ | _DB2 tables_ | _2,500,000_ | H | 1 | Wave 1 | _Complex hierarchy, multiple address types_ |
| _Accounts_ | _Legacy Core Banking_ | _DB2 tables_ | _4,100,000_ | H | 1 | Wave 1 | _Multi-currency, linked accounts_ |
| _General Ledger_ | _SAP ERP_ | _SAP extract (CSV)_ | _12,000,000_ | M | 2 | Wave 1 | _Chart of accounts mapping required_ |
| _Loans_ | _Lending Platform_ | _Oracle DB_ | _800,000_ | H | 1 | Wave 2 | _Amortisation schedules, collateral links_ |
| _Standing Orders_ | _Payment Hub_ | _XML messages_ | _350,000_ | M | 3 | Wave 2 | _Recurrence rules transformation_ |
| _Transaction History_ | _Data Warehouse_ | _Flat files_ | _150,000,000_ | L | 4 | Wave 3 | _Volume-driven; archive vs active split_ |
| _Documents / Images_ | _ECM System_ | _Binary + metadata_ | _5,000,000_ | M | 5 | Wave 3 | _Large binary objects; storage migration_ |
| _Domain nnn_ | | | | | | | |

**Complexity criteria:**
- **High**: Complex transformations, multiple source systems, referential integrity dependencies, business logic in mapping
- **Medium**: Moderate transformations, single source, some conditional logic
- **Low**: Direct 1:1 mapping, minimal transformation, high-volume but simple structure

---

### 2. Source-to-Target Mapping

| Map ID | Source System | Source Table | Source Field | Data Type (Source) | Target Table | Target Field | Data Type (Target) | Transformation Rule | Validation Rule | Notes |
|---|---|---|---|---|---|---|---|---|---|---|
| MAP-001 | Legacy Core | CUST_MASTER | CUST_ID | VARCHAR(20) | CUSTOMER | @ID | VARCHAR(25) | Prefix with branch code: `BR001-{CUST_ID}` | NOT NULL, unique | Branch prefix from lookup table |
| MAP-002 | Legacy Core | CUST_MASTER | CUST_NAME | VARCHAR(100) | CUSTOMER | SHORT.NAME | VARCHAR(35) | Truncate to 35 chars; title-case | NOT NULL | Truncation logged for review |
| MAP-003 | Legacy Core | CUST_MASTER | DOB | DATE (YYYYMMDD) | CUSTOMER | DATE.OF.BIRTH | DATE (YYYYMMDD) | Direct map; validate age >= 18 | NOT NULL, valid date | Age validation for retail customers |
| MAP-004 | Legacy Core | CUST_MASTER | ADDR_LINE_1 | VARCHAR(200) | CUSTOMER | STREET | VARCHAR(35) | Truncate; split multi-line to STREET + ADDRESS fields | NOT NULL | Multi-value field splitting |
| MAP-005 | Legacy Core | ACCT_MASTER | ACCT_NO | VARCHAR(16) | ACCOUNT | @ID | VARCHAR(19) | Map via account number translation table | NOT NULL, unique | Translation table maintained by ops |
| MAP-006 | Legacy Core | ACCT_MASTER | CCY_CODE | CHAR(3) | ACCOUNT | CURRENCY | CHAR(3) | Direct map; validate against ISO 4217 | Valid ISO 4217 | Reject if invalid currency |
| MAP-007 | Legacy Core | ACCT_MASTER | BALANCE | DECIMAL(18,2) | ACCOUNT | WORKING.BALANCE | DECIMAL(18,2) | Direct map; reconcile to GL | NOT NULL | Reconciliation checkpoint |
| MAP-nnn | | | | | | | | | | |

**Mapping conventions:**
- Each mapping carries a unique MAP-ID for traceability
- Transformation rules use pseudo-code or SQL expressions
- Validation rules define post-load checks
- Unmapped source fields documented separately with justification

---

### 3. Data Quality Rules — Pre-Migration

| Rule ID | Domain | Rule Description | DQ Dimension | Threshold | Action if Fail | Priority |
|---|---|---|---|---|---|---|
| DQR-001 | Customer | Customer ID must be non-null and unique across source | Completeness, Uniqueness | 100% | Reject record; escalate to source team | Critical |
| DQR-002 | Customer | Date of birth must be valid date and age >= 0 | Accuracy | 99.5% | Flag for manual review | High |
| DQR-003 | Customer | Email format must match RFC 5322 pattern | Validity | 95% | Cleanse or null; log count | Medium |
| DQR-004 | Customer | Country code must exist in ISO 3166-1 reference | Consistency | 100% | Map to default or reject | Critical |
| DQR-005 | Accounts | Account balance must reconcile to GL within tolerance | Accuracy | 100% (tolerance: 0.01) | Halt migration; investigate | Critical |
| DQR-006 | Accounts | Currency code must be valid ISO 4217 | Validity | 100% | Reject record | Critical |
| DQR-007 | Accounts | Account status must map to valid target status | Consistency | 100% | Map to default; log exceptions | High |
| DQR-008 | GL | Debits must equal credits per posting date | Consistency | 100% | Halt migration; reconcile | Critical |
| DQR-009 | Loans | Loan maturity date must be >= disbursement date | Accuracy | 100% | Reject record; escalate | Critical |
| DQR-010 | All | No orphan records (FK references must resolve) | Referential Integrity | 100% | Reject or defer; log | Critical |
| DQR-011 | All | No duplicate records by natural key | Uniqueness | 100% | De-duplicate; log action | High |
| DQR-012 | All | Mandatory fields per domain must be populated | Completeness | 99% | Cleanse or reject | High |
| DQR-nnn | | | | | | |

**DQ Dimensions:**
- **Completeness** — Are all required fields populated?
- **Accuracy** — Does the data correctly represent the real-world entity?
- **Consistency** — Is the data consistent across related fields and systems?
- **Uniqueness** — Are there no unintended duplicates?
- **Validity** — Does the data conform to defined formats and reference data?
- **Timeliness** — Is the data current as of the agreed extraction point?

---

### 4. Migration Testing Strategy

#### 4.1 Pre-Migration Testing Checklist

- [ ] Source data profiling completed for all domains
- [ ] Data quality baseline measured and documented
- [ ] Source-to-target mapping reviewed and signed off by business
- [ ] Transformation rules unit-tested with sample data
- [ ] Referential integrity dependencies mapped and load order confirmed
- [ ] Cleansing rules applied and re-profiled
- [ ] Extraction scripts tested against source (full volume)
- [ ] Target environment provisioned and schema validated
- [ ] Rollback procedure documented and tested

#### 4.2 Post-Migration Testing

| Test Type | Method | Coverage | Tool | Pass Criteria | Owner |
|---|---|---|---|---|---|
| Record Count Reconciliation | Compare source extract count to target load count per domain | 100% of domains | SQL queries | Counts match exactly (zero variance) | Data Migration Lead |
| Field-Level Validation | Sample records validated field-by-field against source | Statistical sample (ANSI Z1.4, Level II, AQL 1.0%) | Great Expectations / SQL | All sampled records pass all field validations | QA Analyst |
| Referential Integrity | Verify all FK relationships resolve in target | 100% of FK relationships | SQL queries | Zero orphan records | Data Migration Lead |
| Balance Reconciliation | Compare aggregated balances (accounts, GL) source vs target | 100% of financial domains | SQL / Excel | Variance within tolerance (0.01 per domain) | Finance / Data Lead |
| Business Rule Validation | Verify derived/calculated fields in target | Key business rules per domain | Automated test scripts | All rules pass | Business Analyst |
| Transformation Verification | Verify transformations applied correctly on sample | Statistical sample per transformation rule | SQL / Python scripts | All transformations correct on sample | Data Migration Lead |
| Negative Testing | Attempt to load known-bad records; verify rejection | Key rejection scenarios per domain | ETL tool logs | All bad records rejected with correct error codes | QA Analyst |
| Performance / Volume | Measure load times at full production volume | Full volume | ETL tool metrics | Load completes within cutover window allocation | Data Migration Lead |

#### 4.3 UAT Checklist

- [ ] Business users can locate and view migrated customer records
- [ ] Account balances match expected values for UAT sample set
- [ ] Transaction history displays correctly for selected accounts
- [ ] Standing orders and direct debits trigger on expected dates (in test cycle)
- [ ] Loan amortisation schedules calculate correctly post-migration
- [ ] Reports and statements generate with migrated data
- [ ] Downstream system feeds (e.g., regulatory reporting) produce correct output
- [ ] Business sign-off obtained for each data domain

#### 4.4 Production Migration Verification Checklist

- [ ] Record count reconciliation passed for all domains
- [ ] Financial balance reconciliation passed (accounts, GL, loans)
- [ ] Referential integrity verified — zero orphan records
- [ ] Data quality scorecard meets minimum thresholds for all domains
- [ ] Sample spot-checks completed by business users (minimum 50 records per domain)
- [ ] Downstream system integration verified (feeds, reports, APIs)
- [ ] Rollback window confirmed and rollback procedure ready
- [ ] Migration completion certificate signed by Data Migration Lead and Business Owner
- [ ] Post-migration monitoring dashboards active

---

### 5. Data Quality Scorecard

| Domain | Completeness (%) | Accuracy (%) | Consistency (%) | Uniqueness (%) | Validity (%) | Timeliness (%) | Overall (%) | Status | Trend |
|---|---|---|---|---|---|---|---|---|---|
| Customer Master | _98.5_ | _97.2_ | _99.1_ | _99.9_ | _96.8_ | _100_ | _98.6_ | PASS | Improving |
| Accounts | _99.8_ | _99.5_ | _99.9_ | _100_ | _99.7_ | _100_ | _99.8_ | PASS | Stable |
| General Ledger | _100_ | _99.9_ | _100_ | _100_ | _100_ | _100_ | _100_ | PASS | Stable |
| Loans | _97.0_ | _96.5_ | _98.2_ | _99.8_ | _97.1_ | _100_ | _98.1_ | AT RISK | Improving |
| Standing Orders | _99.2_ | _98.8_ | _99.5_ | _100_ | _99.0_ | _100_ | _99.4_ | PASS | Stable |
| Transaction History | _99.9_ | _99.7_ | _99.8_ | _99.9_ | _99.9_ | _95.0_ | _99.0_ | PASS | Stable |
| Documents | _95.0_ | _94.0_ | _97.0_ | _99.5_ | _93.0_ | _100_ | _96.4_ | AT RISK | Improving |
| _Domain nnn_ | | | | | | | | | |

**Scoring:**
- Overall = weighted average of all six dimensions (equal weight unless domain-specific weighting agreed)
- PASS: Overall >= 98%
- AT RISK: Overall 95-97.9%
- FAIL: Overall < 95%
- Trend: Improving / Stable / Declining (compared to previous measurement cycle)

---

### 6. Migration Runbook

| Step | Activity | Owner | Duration (est.) | Start Time | End Time | Verification | Rollback Procedure | Status |
|---|---|---|---|---|---|---|---|---|
| 1 | Freeze source systems (cut-off) | Business Operations | 30 min | T+0:00 | T+0:30 | Confirm no new transactions post-freeze | Lift freeze; resume normal operations | Pending |
| 2 | Final delta extraction from source | Data Migration Lead | 60 min | T+0:30 | T+1:30 | Row count matches expected delta | Re-extract; if fails, abort migration | Pending |
| 3 | Apply cleansing rules to delta | Data Engineer | 45 min | T+1:30 | T+2:15 | DQ rules pass on delta extract | Revert to pre-cleansed extract | Pending |
| 4 | Load Wave 1 (Customer, Accounts, GL) | Data Migration Lead | 120 min | T+2:15 | T+4:15 | Record counts reconciled; FK integrity verified | Truncate target tables; restore from backup | Pending |
| 5 | Balance reconciliation — Wave 1 | Finance + Data Lead | 60 min | T+4:15 | T+5:15 | All balances within tolerance | Escalate; if unresolvable, trigger rollback | Pending |
| 6 | Load Wave 2 (Loans, Standing Orders) | Data Migration Lead | 90 min | T+5:15 | T+6:45 | Record counts reconciled; FK integrity verified | Truncate Wave 2 tables; revert to Wave 1 state | Pending |
| 7 | Balance reconciliation — Wave 2 | Finance + Data Lead | 45 min | T+6:45 | T+7:30 | Loan balances reconciled | Escalate; if unresolvable, trigger rollback | Pending |
| 8 | Load Wave 3 (History, Documents) | Data Migration Lead | 180 min | T+7:30 | T+10:30 | Record counts reconciled; spot-check sample | Truncate Wave 3 tables; acceptable to proceed without if needed | Pending |
| 9 | Post-migration DQ scorecard | QA Analyst | 60 min | T+10:30 | T+11:30 | All domains meet minimum thresholds | Flag domains below threshold; assess severity | Pending |
| 10 | Downstream system verification | Integration Lead | 60 min | T+11:30 | T+12:30 | Feeds, reports, APIs return expected results | Disable downstream feeds; troubleshoot | Pending |
| 11 | Business spot-checks (UAT sample) | Business Users | 90 min | T+12:30 | T+14:00 | Business sign-off per domain | Extend verification window or trigger rollback | Pending |
| 12 | Go/No-Go decision | Programme Director | 30 min | T+14:00 | T+14:30 | All verification steps passed; sign-off obtained | Full rollback to pre-migration backup | Pending |
| 13 | Unfreeze source / enable target | Business Operations | 30 min | T+14:30 | T+15:00 | Target system accepting transactions | Re-freeze; investigate | Pending |
| 14 | Post-migration monitoring (24h) | Support Team | 24 hours | T+15:00 | T+39:00 | No critical issues in first 24 hours | Rollback within 24h window if critical issues | Pending |

---

## Required Skills

### Data Engineering
- ETL/ELT design patterns (batch, micro-batch, streaming)
- Source-to-target mapping and data lineage documentation
- Data profiling and source system analysis
- Schema transformation and data type mapping
- Load order management and referential integrity sequencing

### Data Quality
- DQ dimensions (completeness, accuracy, consistency, uniqueness, validity, timeliness)
- Cleansing rule design and automated remediation
- DQ measurement and scoring frameworks
- Root cause analysis for data quality issues
- Data stewardship and data ownership models

### Testing
- Automated data validation (row counts, checksums, field-level)
- Reconciliation frameworks (financial, volumetric, referential)
- ANSI/ASQ Z1.4 sampling plans (inspection levels, AQL, lot sizing)
- Statistical sampling design for large-volume validation
- UAT facilitation for data migration

### Migration Patterns
- Big bang vs phased vs parallel migration strategies
- Delta/incremental migration design
- Cutover planning and timing estimation
- Rollback procedures and point-of-no-return definition
- Rehearsal planning with progressive tightening

### Tooling
- SQL (complex queries, reconciliation scripts, data profiling)
- Python / PySpark (transformation scripts, data quality checks, automation)
- Great Expectations (expectation suites, data docs, validation pipelines)
- Cloud ETL (AWS Glue, Azure Data Factory, GCP Dataflow)
- dbt (data transformation, testing, documentation)

### Compliance
- GDPR data migration requirements (consent, right to erasure, data minimisation)
- PII masking and tokenisation in non-production environments
- Audit trail design for migration activities
- Data retention policies and archival during migration
- Regulatory reporting continuity during migration window

---

## Toolchain

| Tool | Purpose |
|---|---|
| dbt | Data transformation, automated testing, documentation, lineage |
| Great Expectations | Data quality validation, expectation suites, data docs, automated DQ pipelines |
| Apache Spark / PySpark | Large-volume data processing, transformation, profiling |
| AWS Glue / Azure Data Factory | Cloud-native ETL orchestration, scheduling, monitoring |
| SQL (various engines) | Data profiling, reconciliation queries, validation scripts |
| Python | Scripting for transformation, cleansing, automation, reporting |
| Excel | Reconciliation worksheets, DQ scorecard reporting, stakeholder communication |
