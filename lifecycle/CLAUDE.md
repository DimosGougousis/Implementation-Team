# Lifecycle Framework

The 8-stage Temenos Transact implementation lifecycle with formal gate reviews.

## Stages

| Stage | Name | Duration (typical) | Key Gate |
|---|---|---|---|
| 1 | Discovery | 2–4 weeks | Scope confirmed |
| 2 | Fit-Gap & Process Design | 4–8 weeks | All modules assessed |
| 3 | Solution Architecture | 4–6 weeks | Architecture approved |
| 4 | Build & Configure | 12–20 weeks | Code complete |
| 5 | Testing | 8–12 weeks | UAT sign-off |
| 6 | Data Migration | 4–8 weeks | Rehearsal 2 passed |
| 7 | Cutover | 1–2 weeks | Go-live complete |
| 8 | Hypercare | 4–8 weeks | Steady state achieved |

## Gate Framework

Each stage ends with a gate review. See `gates/` for individual gate definitions.

- **Pass** — All exit criteria met, proceed to next stage
- **Conditional Pass** — Minor items outstanding, proceed with mitigation plan
- **Fail** — Exit criteria not met, remediation required before re-review

## Stage → Artefact Matrix

| Stage | ADRs | Ref Arch | Fit-Gap | Int Map | DQ Score | Test KPI | Cutover | Op Model |
|---|---|---|---|---|---|---|---|---|
| 1. Discovery | - | Create | - | - | - | - | - | - |
| 2. Fit-Gap | - | - | Create | - | Start | - | - | - |
| 3. Architecture | Create | Update | Update | Create | - | Framework | - | Start |
| 4. Build | Update | Update | Update | Update | - | - | - | - |
| 5. Testing | Update | - | - | Update | - | Create | - | - |
| 6. Migration | Update | - | - | - | Create | - | - | - |
| 7. Cutover | - | - | - | - | - | - | Create | - |
| 8. Hypercare | - | - | - | - | - | - | - | Create |
