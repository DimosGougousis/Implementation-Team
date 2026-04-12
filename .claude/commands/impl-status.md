# /impl-status

Read-only dashboard showing all active programmes.

## Usage
```
/impl-status
```

## What It Does
1. Scans `pipeline/active/*/STAGE-STATUS.md`
2. Renders a summary dashboard:
   - Programme name and current stage
   - Gate status (In Progress / Passed / Pending)
   - Artefact completion matrix
   - Gate history summary

## Output Format

```
## Implementation Status Dashboard

| Programme | Stage | Gate Status | ADRs | Ref Arch | Fit-Gap | Int Map | DQ | Test | Cutover | Op Model |
|---|---|---|---|---|---|---|---|---|---|---|
| programme-a | 3. Architecture | 🔄 Active | Created | Updated | Updated | Created | - | Framework | - | Started |
| programme-b | 5. Testing | 🔄 Active | Updated | - | - | Updated | - | Created | - | - |
```
