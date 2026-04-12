# RESTful & Event-Driven Integration Design — Reference Guide

**CV Competency:** RESTful & Event-Driven Integration Design
**Primary Artefact:** artefacts/04-integration-dependency-map/
**Primary Stage:** 3 — Solution Architecture
**Updated At:** 4, 5

---

## What This Competency Covers

The ability to design end-to-end integration architectures spanning RESTful APIs, event-driven channels, and batch interfaces, with clear contracts, SLAs, dependency mapping, and adapter strategies for Temenos Transact.

## Key Skills

- Mapping all system-to-system touchpoints in a dependency graph
- Designing RESTful API contracts with versioning and auth
- Defining event-driven channels with schemas and retry policies
- Establishing adapter strategies (Temenos fulfilment service model)
- Building SLA matrices and owner matrices for the integrated estate
- Applying patterns: request-reply, event-driven, batch, circuit breaker

## When to Apply

| Stage | Activity |
|---|---|
| 3 — Solution Architecture | Create integration register, dependency graph, contracts |
| 4 — Build & Configure | Refine contracts, validate implementations against specs |
| 5 — Testing | Validate integration test results against SLAs |

## Deliverables

| File | Purpose |
|---|---|
| `integration-register.md` | All system-to-system touchpoints |
| `dependency-graph.md` | Directed graph (Mermaid) with protocol, SLA, owner |
| `api-contracts/` | Per-integration API contract specifications |
| `event-contracts/` | Per-event contract specifications |
| `adapter-strategy.md` | Temenos fulfilment service model, middleware patterns |
| `sla-matrix.md` | System × system SLA grid |
| `owner-matrix.md` | System × owner × support contact |

## Quality Signals

- Every integration has a defined contract (API or event)
- Dependency graph shows all paths, not just direct connections
- SLA matrix covers all system pairs with realistic targets
- Adapter strategy addresses failure modes (retry, circuit breaker, DLQ)
- Owner matrix has named contacts, not just team names

## Steering Committee Value

A complete integration map de-risks the programme by making dependencies visible, enabling impact analysis for changes, and providing a clear ownership model for post-go-live support.

## CV Narrative

> "I designed the integration architecture for X system touchpoints across Y systems, defining Z API contracts and event channels with explicit SLAs. The dependency graph enabled the programme to identify and mitigate X critical-path risks before build."
