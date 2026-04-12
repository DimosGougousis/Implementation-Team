# Rollback Triggers

Conditions that trigger a rollback during cutover.

## Automatic Rollback Triggers

| Trigger | Threshold | Action |
|---|---|---|
| Data load failure | > 5% record rejection | Halt and assess |
| Data validation failure | Any critical domain fails | Halt and assess |
| Integration smoke test failure | > 2 integrations fail | Halt and assess |
| Application smoke test failure | Core banking functions fail | Immediate rollback |
| Data corruption detected | Any occurrence | Immediate rollback |

## Manual Rollback Triggers

| Trigger | Decision Maker | Time Limit |
|---|---|---|
| Business cannot operate | Programme Lead | T+4h |
| Critical defect with no workaround | Programme Lead + Design Authority | T+2h |
| Performance unacceptable | Programme Lead | T+4h |
| Stakeholder escalation | Steering Committee | Any time |

## Rollback Procedure

| Step | Owner | Duration | Verification |
|---|---|---|---|
| 1. Announce rollback decision | Programme Lead | 5 min | Comms sent |
| 2. Disable Transact access | | 10 min | Access revoked |
| 3. Restore source system | | 60 min | System available |
| 4. Restore source data | | 120 min | Record count match |
| 5. Re-enable source system access | | 10 min | Login verified |
| 6. Verify source system operation | | 30 min | Key scenarios pass |
| 7. Announce rollback complete | Programme Lead | 5 min | Comms sent |

## Rollback Window

| Phase | Rollback Possible | Complexity |
|---|---|---|
| Pre-cutover | Yes | Low |
| Data load | Yes | Medium |
| Data validation | Yes | Medium |
| Integration activation | Yes | High |
| Post go-live (0–4h) | Yes | High |
| Post go-live (4–24h) | Risk-based decision | Very High |
| Post go-live (24h+) | No — forward fix only | N/A |
