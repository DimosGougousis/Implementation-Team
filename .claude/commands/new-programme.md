# /new-programme

Creates a new programme pipeline from the template.

## Usage
```
/new-programme <programme-name>
```

## What It Does
1. Copies `pipeline/_template/` to `pipeline/active/<programme-name>/`
2. Replaces `<Programme Name>` placeholder with the actual name in:
   - STAGE-STATUS.md
   - CONTRIBUTION-LOG.md
   - All stage gate files
   - All artefact placeholder files
3. Sets all stages to `pending` status
4. Sets Stage 1 to `In Progress` in STAGE-STATUS.md

## Example
```
/new-programme barclays-transact-migration
```

Creates:
```
pipeline/active/barclays-transact-migration/
├── STAGE-STATUS.md
├── CONTRIBUTION-LOG.md
├── stages/
│   ├── 01-discovery-gate.md
│   ├── 02-fit-gap-gate.md
│   ├── ...
│   └── 08-hypercare-gate.md
└── artefacts/
    ├── adrs.md
    ├── target-state-architecture.md
    ├── ...
    └── operating-model.md
```
