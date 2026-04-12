# Pipeline

Per-programme tracking for active and archived implementation programmes.

## Structure

```
pipeline/
├── _template/          # Templates for new programmes
│   ├── STAGE-STATUS.md
│   ├── CONTRIBUTION-LOG.md
│   ├── stages/         # 8 gate files
│   └── artefacts/      # 8 placeholder files
├── active/             # Current programmes
└── archive/            # Completed programmes
```

## Creating a New Programme

Run `/new-programme <name>` to scaffold:
1. Copy `_template/` to `active/<name>/`
2. Fill in programme name in STAGE-STATUS.md and CONTRIBUTION-LOG.md
3. All stages start as `pending`

## Programme Structure

Each programme folder contains:
- `STAGE-STATUS.md` — Current stage, gate matrix, dates
- `CONTRIBUTION-LOG.md` — Value per stage + artefact
- `stages/` — 8 gate files with programme-specific status
- `artefacts/` — 8 placeholder files referencing rich templates
