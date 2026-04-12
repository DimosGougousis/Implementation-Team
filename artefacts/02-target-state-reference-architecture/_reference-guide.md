# Target-State Architecture & Systems Thinking — Reference Guide

**CV Competency:** Target-State Architecture & Systems Thinking
**Primary Artefact:** artefacts/02-target-state-reference-architecture/
**Primary Stages:** 1 — Discovery, 3 — Solution Architecture
**Updated At:** 4

---

## What This Competency Covers

The ability to design a coherent target-state architecture that maps business capabilities to technology components, defines integration patterns, and establishes security and infrastructure standards for a Temenos Transact implementation.

## Key Skills

- Mapping business capabilities to Transact packaged business capabilities
- Designing API-first and event-driven integration architectures
- Defining infrastructure topology and network zones
- Establishing security architecture (auth, encryption, key management)
- Creating logical component models with clear boundaries
- Setting technology standards and version matrices

## When to Apply

| Stage | Activity |
|---|---|
| 1 — Discovery | Produce initial target-state from current-state analysis |
| 3 — Solution Architecture | Finalise architecture with integration and security details |
| 4 — Build & Configure | Refine API register and event channels as build progresses |

## Deliverables

| File | Purpose |
|---|---|
| `business-capability-map.md` | Bank capabilities → Transact packaged business capabilities |
| `api-register.md` | Full API catalogue (Transact APIs, custom, third-party) |
| `event-channels.md` | Topics, producers, consumers, schemas |
| `infrastructure-stack.md` | Servers, middleware, DB, network |
| `component-model.md` | Logical component diagram (Mermaid) |
| `security-architecture.md` | Auth, encryption, key management, network zones |
| `technology-standards.md` | Approved tech stack, version matrix |

## Quality Signals

- Capability map covers all business domains with no gaps
- API register is complete and versioned
- Event channels have defined schemas and retry policies
- Security architecture addresses all threat vectors
- Component model is readable and shows clear boundaries

## Steering Committee Value

A well-defined target-state reduces integration risk, provides a clear technology roadmap, and enables accurate cost estimation and resource planning.

## CV Narrative

> "I designed the target-state architecture for a X-domain Temenos Transact implementation, mapping Y business capabilities to Transact modules and defining Z integrations across the enterprise estate. The architecture was approved by the Steering Committee with zero material objections."
