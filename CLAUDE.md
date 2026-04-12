# Implementation Team OS

> This repo is the operating system for Temenos Transact implementation programmes.
> It tracks delivery through an 8-stage lifecycle, captures contribution value, and provides rich artefact templates.

## Quick Start

- **New programme?** Run `/new-programme <name>` to scaffold a pipeline entry.
- **Check status?** Run `/impl-status` for a cross-programme dashboard.
- **Agents?** See `agents/CLAUDE.md` — all are placeholders pending workshops.

## Repo Structure

| Folder | Purpose |
|---|---|
| `governance/` | Framework and directives for programme governance |
| `agents/` | Agent definitions (placeholders until workshopped) |
| `business-processes/` | Core banking process reference library (22 areas, 2,485+ processes) |
| `artefacts/` | Gold-standard deliverable templates (8 artefact folders) |
| `lifecycle/` | 8-stage Temenos lifecycle with gate definitions |
| `pipeline/` | Per-programme tracking (active + archive) |
| `analytics/` | Implementation KPIs and reporting |
| `team/` | Team directory |

## Lifecycle Stages

1. Discovery
2. Fit-Gap & Process Design
3. Solution Architecture
4. Build & Configure
5. Testing
6. Data Migration
7. Cutover
8. Hypercare

## Conventions

- Gate files use the template in `lifecycle/gates/`.
- Programme folders use templates from `pipeline/_template/`.
- Artefact folders in `artefacts/` are read-only templates; programme-specific copies live in `pipeline/active/<programme>/artefacts/`.
- Agent files are stubs until individually workshopped.
