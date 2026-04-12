# Implementation Team

Operating system for Temenos Transact implementation programmes.

## What This Repo Does

- Tracks programme delivery through an 8-stage Temenos lifecycle (Discovery → Hypercare)
- Provides rich artefact templates for all major deliverables (ADRs, architecture, fit-gap, integration, data migration, testing, cutover, operating model)
- Logs personal contribution and value delivered at each stage (Steering Committee / CTO audience)
- Manages agent-assisted workflows via placeholder agent definitions

## Getting Started

1. Review `lifecycle/overview.md` for the stage model
2. Browse `artefacts/` for deliverable templates
3. Run `/new-programme <name>` to create a new programme pipeline
4. Run `/impl-status` to see all active programmes

## Repo Structure

```
Implementation/
├── CLAUDE.md              # Entry point for AI assistants
├── AGENTS.md              # Non-Claude mirror
├── README.md              # You are here
├── governance/            # Framework and directives
├── agents/                # Agent definitions (placeholders)
├── artefacts/             # 8 artefact template folders
├── lifecycle/             # 8-stage lifecycle + gates
├── pipeline/              # Per-programme tracking
├── analytics/             # KPIs and reporting
├── team/                  # Team directory
├── .claude/               # Claude-specific config, skills, commands
└── .vscode/               # VS Code settings
```

## Lifecycle Stages

| Stage | Name | Key Artefacts |
|---|---|---|
| 1 | Discovery | Target-State Architecture |
| 2 | Fit-Gap & Process Design | Fit-Gap Register, Data Quality Scorecard |
| 3 | Solution Architecture | ADRs, Integration Map, Test Strategy |
| 4 | Build & Configure | All artefacts updated |
| 5 | Testing | Test Strategy & KPI Dashboard |
| 6 | Data Migration | Data Quality Scorecard |
| 7 | Cutover | Cutover Runbook |
| 8 | Hypercare | Post-Go-Live Operating Model |
