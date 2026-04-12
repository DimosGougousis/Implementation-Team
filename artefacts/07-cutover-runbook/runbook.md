# Cutover Runbook

Minute-by-minute cutover script for go-live execution.

## Cutover Window

| Attribute | Value |
|---|---|
| Date | YYYY-MM-DD |
| Start Time | HH:MM |
| End Time | HH:MM |
| Duration | X hours |
| War Room | Location / Virtual link |

## Pre-Cutover (T-24h to T-0)

| Time | Step | Owner | Duration | Status |
|---|---|---|---|---|
| T-24h | Final rehearsal review | | | |
| T-24h | Confirm go/no-go criteria met | | | |
| T-12h | Freeze source system changes | | | |
| T-4h | Final data extract | | | |
| T-2h | War room setup, comms check | | | |
| T-1h | Final go/no-go decision | | | |

## Cutover Execution (T-0)

| Time | Step | Owner | Duration | Verification | Status |
|---|---|---|---|---|---|
| T+0 | Announce cutover start | | 5 min | Comms sent | |
| T+5 | Disable source system access | | 10 min | Access revoked | |
| T+15 | Final data extraction | | 60 min | Record count match | |
| T+75 | Data transformation | | 90 min | Quality checks pass | |
| T+165 | Data load to Transact | | 120 min | Load report clean | |
| T+285 | Data validation | | 60 min | Reconciliation pass | |
| T+345 | Integration activation | | 30 min | Smoke tests pass | |
| T+375 | Application smoke test | | 30 min | Key scenarios pass | |
| T+405 | Enable user access | | 15 min | Login verified | |
| T+420 | Announce go-live complete | | 5 min | Comms sent | |

## Post-Cutover (T+0 to T+24h)

| Time | Step | Owner | Duration | Status |
|---|---|---|---|---|
| T+1h | Monitor error rates | | Continuous | |
| T+2h | First business transaction verification | | 30 min | |
| T+4h | Integration health check | | 30 min | |
| T+8h | End-of-day processing test | | 60 min | |
| T+24h | Hypercare handover | | 60 min | |
