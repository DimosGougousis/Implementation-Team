# Test Data Strategy

Sourcing, masking, and refresh approach for test environments.

## Data Sources

| Source | Environment | Records | Refresh Frequency |
|---|---|---|---|
| Production copy | SIT, UAT | | Per sprint / on demand |
| Synthetic | DEV | | Static |
| Subset | PERF | | Per performance test |

## Masking Rules

| Field Type | Masking Method | Example |
|---|---|---|
| Name | Random replacement | John Smith → [RANDOM_NAME] |
| Account Number | Format-preserving encryption | 12345678 → 87654321 |
| National ID | Hash + salt | → [HASH] |
| Email | Domain replacement | → user@test.com |
| Phone | Random digits | → +44 7000 000000 |

## Refresh Process

1. Extract from source (production or previous environment)
2. Apply masking rules
3. Validate masked data (no PII leakage)
4. Load into target environment
5. Run data quality checks
6. Record in rehearsal-results/

## Access Control

| Environment | Access | Approval |
|---|---|---|
| DEV | Development team | Team lead |
| SIT | Test team, Integration team | Test manager |
| PERF | Performance team | Test manager |
| UAT | Business users | Programme lead |
