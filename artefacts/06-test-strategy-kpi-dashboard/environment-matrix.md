# Environment Matrix

Test environments: purpose, data, access, and refresh schedule.

## Environments

| Environment | Purpose | Data | Refresh | Access | URL |
|---|---|---|---|---|---|
| DEV | Unit testing, development | Synthetic | Static | Dev team | |
| SIT | Integration, system testing | Masked prod subset | Per sprint | Test + Integration | |
| PERF | Performance, load testing | Masked prod subset | Per perf test | Performance team | |
| UAT | User acceptance testing | Masked prod | Before UAT phase | Business users | |
| PRE-PROD | Final validation | Production mirror | Before cutover | Restricted | |

## Environment Dependencies

| Environment | Transact | Database | Middleware | External Systems |
|---|---|---|---|---|
| DEV | v | v | Mocked | Mocked |
| SIT | v | v | v | Stubs + Partial live |
| PERF | v | v | v | Stubs |
| UAT | v | v | v | Live (sandboxed) |
| PRE-PROD | v | v | v | Live |

## Refresh Schedule

| Environment | Schedule | Owner | Approval |
|---|---|---|---|
| DEV | On demand | Dev lead | — |
| SIT | Every sprint | Test manager | Programme lead |
| PERF | Before each perf test | Performance lead | Test manager |
| UAT | Before UAT phase | Test manager | Steering Committee |
