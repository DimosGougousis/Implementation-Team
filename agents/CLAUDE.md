# Agent Registry

All agents are **placeholders** pending individual workshops. Each agent is mapped to a core competency with full artifact templates, best-of-breed references, and required skills defined.

## Competency → Agent → Artefact Mapping

| # | Competency | Agent | Codename | Primary Artefact | Active Stages |
|---|---|---|---|---|---|
| 1 | Target-State Architecture & Systems Thinking | design-authority | Architect Agent | 02-target-state-reference-architecture/ | 3, 4, 5, 6 |
| 2 | RESTful & Event-Driven Integration Design | integration-architect | Integration Agent | 04-integration-dependency-map/ | 3, 4, 5 |
| 3 | Acceptance Criteria & Automated Evaluations | test-strategist | Quality Agent | 06-test-strategy-kpi-dashboard/ | 3, 5 |
| 4 | Stakeholder & Vendor Orchestration | integration-orchestrator | Orchestration Agent | pipeline/ (coordination) | All |
| 5 | Fit-Gap Analysis & Customisation Governance | fit-gap-analyst | Governance Agent | 03-fit-gap-register/ | 2, 3, 4 |
| 6 | Programme Structuring & Agile at Scale | programme-governance | Programme Agent | lifecycle/ | All |
| 7 | Data Migration & Quality Assurance | data-migration-lead | Data Agent | 05-data-quality-scorecard/ | 2, 5, 6 |
| 8 | Architecture Decision Records & Traceability | design-authority | Decision Agent | 01-architecture-decision-records/ | 3, 4, 5, 6 |
| 9 | Business Process Alignment & Redesign | process-analyst | Process Agent | business-processes/ | 1, 2, 3 |
| 10 | Post-Transformation Operating Model Design | operating-model | Operating Model Agent | 08-post-go-live-operating-model/ | 3, 8 |
| — | Cutover specialisation (Competency 6) | cutover-manager | Cutover Agent | 07-cutover-runbook/ | 5, 6, 7 |
| — | Cross-cutting reporting | dashboard-reporting | Reporting Agent | analytics/, pipeline/*/STAGE-STATUS.md | All |

**Notes:**
- `design-authority` covers TWO competencies (1 and 8) — Target-State Architecture and ADRs.
- `02-target-state-reference-architecture/` is cross-cutting — owned jointly by design-authority and integration-architect. Resolved during agent workshops.
- `process-analyst` is the 11th agent, added to cover Competency 9 (Business Process Alignment & Redesign).

## Agent Skills Cross-Reference Matrix

This matrix shows which skills are **shared** across agents, enabling efficient skill reuse:

| Skill | Architect | Integration | Quality | Orchestration | Governance | Programme | Data | Decision | Process | Op. Model | Cutover | Reporting |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Systems Thinking** | * | * | | | | * | | * | | * | | |
| **TOGAF / EA Frameworks** | * | | | | | | | * | | * | | |
| **API / Schema Design** | * | * | | | | | | | | | | |
| **BDD / Gherkin** | | | * | | | | | | | | | |
| **RACI / DACI** | | | | * | | * | | | | * | | |
| **Trade-off Analysis** | * | * | | | * | | | * | | * | | |
| **Data Quality** | | | * | | | | * | | | | | |
| **Process Modelling (BPMN)** | | | | | * | | | | * | * | | |
| **Risk Assessment** | * | | | * | * | * | * | * | | * | * | |
| **Technical Writing** | * | * | * | | | | | * | * | | | * |
| **Metrics / KPI Design** | | | * | * | | * | * | | * | * | | * |
| **Change Management** | | | | * | | | | | * | * | * | |
| **Financial / Business Case** | | | | | * | * | | | | * | | |

## Recommended Toolchain per Agent

| Agent | Primary Tools |
|---|---|
| **design-authority** (Architect + Decision) | Structurizr (C4), draw.io, TOGAF Metamodel, AWS Well-Architected Tool, Markdown + Git |
| **integration-architect** (Integration) | Swagger/OpenAPI Editor, AsyncAPI Studio, Kafka Schema Registry, Postman |
| **test-strategist** (Quality) | Cucumber/SpecFlow, Playwright, axe-core, k6, TestQuality |
| **integration-orchestrator** (Orchestration) | Smartsheet/Jira, Power/Interest Grid builder, Scorecard dashboards |
| **fit-gap-analyst** (Governance) | SAP Solution Manager, Excel/Notion scoring matrices, Jira workflow |
| **programme-governance** (Programme) | Jira Align, Miro (PI boards), Aha! Roadmaps, Azure DevOps |
| **data-migration-lead** (Data) | dbt, Great Expectations, Apache Spark, AWS Glue/ADF, SQL validation |
| **process-analyst** (Process) | Lucidchart/Visio (BPMN 2.0), Miro (SIPOC), Signavio, Celonis |
| **operating-model** (Operating Model) | PowerPoint/Miro (one-pager), org.design tools, financial modelling (Excel) |
| **cutover-manager** (Cutover) | Runbook automation, communication tools, monitoring dashboards |
| **dashboard-reporting** (Reporting) | Markdown dashboards, Mermaid charts, Excel/PowerBI, report templates |
