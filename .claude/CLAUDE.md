# Claude Configuration

## Skills
Placeholder — populated when agents are workshopped.

## Commands

### /new-programme <name>
Creates `pipeline/active/<name>/` with:
- STAGE-STATUS.md (from template, programme name filled in)
- CONTRIBUTION-LOG.md (from template, programme name filled in)
- stages/ (8 gate files, all status: pending)
- artefacts/ (8 placeholder files referencing the rich templates in artefacts/)

### /impl-status
Read-only dashboard that scans `pipeline/active/*/STAGE-STATUS.md` and renders:
- Programme list with current stage
- Artefact completion matrix
- Gate history summary
