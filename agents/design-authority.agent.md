---
name: design-authority
description: Target-state architecture, ADRs, design conformance, customisation governance
status: placeholder
codenames: [Architect Agent, Decision Agent]
competencies: [1-Target-State Architecture & Systems Thinking, 8-Architecture Decision Records & Traceability]
owner-artefacts: [01-architecture-decision-records, 02-target-state-reference-architecture]
primary-stages: [3, 4, 5, 6]
---

# Design Authority

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Author and maintain Architecture Decision Records, define and evolve the target-state reference architecture across all layers (business, application, data, technology, security), enforce design conformance against that target state, govern customisation requests through the ADR process, perform current-vs-target gap analysis, produce implementation roadmaps, and maintain the traceability matrix linking requirements to decisions to implementations to test evidence.

## Owns

- artefacts/01-architecture-decision-records/
- artefacts/02-target-state-reference-architecture/

## Active At

- Stage 3: Solution Architecture (primary -- target-state definition, initial ADRs)
- Stage 4: Build & Configure (design conformance reviews, change ADRs)
- Stage 5: Testing (architecture verification, traceability sign-off)
- Stage 6: Data Migration (data architecture conformance, migration ADRs)

---

## Competency 1: Target-State Architecture & Systems Thinking

### Best-of-Breed References

| Reference | Relevance |
|---|---|
| TOGAF ADM (Phase B-D) | Structured method for Business, Information Systems, and Technology Architecture |
| Visual Paradigm | UML/ArchiMate modelling and architecture documentation tooling |
| NeoArc Studio | Cloud-native architecture diagramming with C4 and dependency mapping |
| AWS Well-Architected Framework | Six-pillar lens for evaluating cloud architecture quality |

### Artifact Template: Target-State Architecture Report

```markdown
# Target-State Architecture Report

| Field | Value |
|---|---|
| Programme | [Programme Name] |
| Version | [x.y] |
| Author | [Name] |
| Date | [YYYY-MM-DD] |
| Status | Draft / In Review / Approved |
| Classification | Confidential / Internal |

---

## 1. Executive Summary

[One-page summary of the target-state architecture vision, key design decisions, and
strategic alignment. State the primary architectural goals, the transformation scope,
and the expected business outcomes.]

---

## 2. Business Context & Strategic Drivers

[Describe the business strategy, market drivers, regulatory requirements, and
organisational goals that shape the architecture. Include:]

- **Strategic objectives** the architecture must enable
- **Regulatory / compliance** constraints (e.g., PSD2, GDPR, Basel III)
- **Market pressures** driving the transformation timeline
- **Technology debt** or legacy constraints requiring remediation
- **Key stakeholders** and their architectural concerns

---

## 3. Current-State Architecture Summary

| Layer | Current State | Key Pain Points |
|---|---|---|
| Business | [Current business capabilities, processes, org structure] | [Pain points: manual processes, capability gaps, etc.] |
| Application | [Current application landscape, monoliths, integrations] | [Pain points: tight coupling, vendor lock-in, etc.] |
| Data | [Current data stores, flows, quality issues] | [Pain points: silos, duplication, poor lineage, etc.] |
| Technology | [Current infrastructure, hosting, networking] | [Pain points: scalability limits, end-of-life, etc.] |
| Security | [Current security posture, IAM, perimeter model] | [Pain points: gaps in zero-trust, audit findings, etc.] |

---

## 4. Target-State Architecture

### 4.1 Business Architecture

[Describe the target business capabilities, value streams, and organisational alignment.]

**Capability Map (L0-L2):**

| L0 Domain | L1 Capability | L2 Sub-Capability | Target Maturity |
|---|---|---|---|
| [e.g., Customer Management] | [e.g., Onboarding] | [e.g., Digital KYC] | [e.g., Optimised] |
| [e.g., Customer Management] | [e.g., Onboarding] | [e.g., Risk Scoring] | [e.g., Managed] |
| [e.g., Product Management] | [e.g., Product Catalogue] | [e.g., Dynamic Pricing] | [e.g., Defined] |
| [e.g., Payments] | [e.g., Payment Processing] | [e.g., Real-Time Payments] | [e.g., Optimised] |
| ... | ... | ... | ... |

### 4.2 Application Architecture

[Describe the target application landscape, decomposition strategy, and integration
approach.]

- **Decomposition strategy:** Microservices / modular monolith / hybrid
- **API strategy:** API-first design, internal vs external API gateway
- **Front-end strategy:** Micro-frontends / SPA / hybrid
- **Service mesh:** Sidecar proxy model for inter-service communication
- **Async messaging:** Event-driven backbone for decoupled workflows

### 4.3 Data Architecture

[Describe the target data landscape, governance model, and data flow patterns.]

- **Data domains:** Domain-oriented ownership (data mesh / data fabric)
- **Master data management:** Golden source identification per entity
- **Data governance:** Stewardship model, data quality rules, lineage tracking
- **Analytics platform:** Lakehouse / warehouse architecture for BI and ML
- **Data integration:** CDC, streaming, batch ETL patterns

### 4.4 Technology Architecture

[Describe the target infrastructure, platform services, and operational model.]

- **Cloud strategy:** Multi-cloud / hybrid / single-cloud provider
- **Infrastructure as Code:** Terraform / Pulumi / CloudFormation
- **Container orchestration:** Kubernetes (EKS / AKS / GKE)
- **Observability stack:** Metrics (Prometheus), Logs (ELK/Loki), Traces (Jaeger/Tempo)
- **CI/CD pipeline:** GitOps model with automated quality gates
- **DR/BCP:** RPO/RTO targets, failover architecture

### 4.5 Security Architecture

[Describe the target security architecture and zero-trust posture.]

- **Zero-trust model:** Never trust, always verify -- identity-centric perimeter
- **Identity & Access Management:** Centralised IdP, RBAC/ABAC, MFA
- **Network security:** Microsegmentation, east-west traffic encryption
- **Application security:** SAST/DAST in pipeline, dependency scanning
- **Data security:** Encryption at rest (AES-256) and in transit (TLS 1.3)
- **Secrets management:** Vault / cloud-native secrets manager
- **Compliance:** Continuous compliance monitoring and audit trail

---

## 5. Current vs Target Gap Analysis

| Component | Current State | Target State | Gap Description | Priority |
|---|---|---|---|---|
| [e.g., Core Banking] | [Monolithic T24 Classic] | [Transact on cloud-native stack] | [Migration to containerised deployment] | [High] |
| [e.g., Integration Layer] | [Point-to-point, FTP-based] | [API gateway + event broker] | [Replace file-based with real-time APIs] | [Critical] |
| [e.g., Data Platform] | [On-prem Oracle DW] | [Cloud lakehouse with streaming] | [Migrate and modernise analytics] | [Medium] |
| [e.g., IAM] | [Local AD, no MFA] | [Cloud IdP, zero-trust, MFA] | [Implement centralised identity] | [High] |
| [e.g., Monitoring] | [Basic Nagios alerts] | [Full observability stack] | [Deploy metrics, logs, traces] | [Medium] |
| ... | ... | ... | ... | ... |

---

## 6. Architecture Principles

| # | Principle | Rationale |
|---|---|---|
| 1 | API-First Design | All capabilities exposed as versioned APIs to enable composability and partner integration |
| 2 | Cloud-Native by Default | Leverage managed services for scalability, resilience, and reduced operational overhead |
| 3 | Data as a Product | Each domain owns and publishes its data with defined contracts and SLAs |
| 4 | Security by Design | Security controls embedded at every layer, not bolted on after the fact |
| 5 | Loose Coupling, High Cohesion | Services own their data and communicate via well-defined interfaces |
| 6 | Automate Everything | Infrastructure, testing, deployment, and compliance checks are automated |
| 7 | Design for Failure | Assume components will fail; build resilience through redundancy and graceful degradation |
| 8 | Observable by Default | Every service emits metrics, logs, and traces from day one |
| 9 | Minimise Customisation | Prefer configuration and standard extension points over custom code |
| 10 | Evolutionary Architecture | Architecture supports incremental change through fitness functions and modularity |

---

## 7. Implementation Roadmap

| Wave | Scope | Timeline | Dependencies |
|---|---|---|---|
| Wave 1 -- Foundation | Cloud landing zone, CI/CD pipeline, IAM, observability stack | Q1-Q2 | Cloud account provisioning, security baseline approval |
| Wave 2 -- Core Platform | Core banking migration, API gateway, event broker | Q2-Q4 | Wave 1 complete, vendor contract signed |
| Wave 3 -- Integration | Channel integration, partner APIs, data migration | Q3-Q5 | Wave 2 core services live, API contracts agreed |
| Wave 4 -- Advanced | Analytics platform, ML models, advanced automation | Q5-Q6 | Wave 3 data flows operational |
| Wave 5 -- Optimisation | Performance tuning, cost optimisation, DR testing | Q6-Q7 | All waves stable in production |

---

## 8. Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| [e.g., Vendor lock-in to single cloud] | Medium | High | [Multi-cloud abstraction layer, portable IaC] |
| [e.g., Data migration data loss] | Low | Critical | [Dual-run period, reconciliation framework, rollback plan] |
| [e.g., Skills gap in cloud-native] | High | Medium | [Training programme, embedded cloud architects, pair programming] |
| [e.g., Integration complexity explosion] | Medium | High | [API governance, contract testing, dependency mapping] |
| [e.g., Regulatory non-compliance] | Low | Critical | [Continuous compliance checks, regulatory sandbox testing] |

---

## Appendices

### Appendix A: C4 Diagrams

[Include or reference the following C4 diagrams:]

- **System Context (C1):** Shows the system in scope and its relationships to users
  and external systems
- **Container (C2):** Shows the high-level technology choices and how containers
  communicate
- **Component (C3):** Shows the internal components of each container (for key
  containers)
- **Code (C4):** Shows class-level detail (only where architecturally significant)

> Diagrams to be maintained in Structurizr DSL at: `docs/architecture/structurizr/`

### Appendix B: Technology Radar

| Quadrant | Adopt | Trial | Assess | Hold |
|---|---|---|---|---|
| Languages & Frameworks | [e.g., Java 21, Spring Boot 3] | [e.g., Kotlin, Quarkus] | [e.g., Rust for infra] | [e.g., Java 8] |
| Platforms | [e.g., Kubernetes, PostgreSQL] | [e.g., Dapr, CockroachDB] | [e.g., Wasm runtimes] | [e.g., on-prem VMs] |
| Tools | [e.g., Terraform, ArgoCD] | [e.g., Backstage, Crossplane] | [e.g., Radius] | [e.g., Jenkins] |
| Techniques | [e.g., GitOps, trunk-based dev] | [e.g., eBPF observability] | [e.g., AI-assisted code review] | [e.g., long-lived branches] |

### Appendix C: Non-Functional Requirements Catalogue

| NFR ID | Category | Requirement | Target | Measurement Method |
|---|---|---|---|---|
| NFR-001 | Performance | API response time (P95) | < 200ms | APM tooling |
| NFR-002 | Performance | Batch processing throughput | > 10,000 txn/sec | Load test results |
| NFR-003 | Availability | System uptime | >= 99.95% | Monitoring dashboard |
| NFR-004 | Scalability | Concurrent users | 50,000+ | Load test results |
| NFR-005 | Security | Authentication | MFA + OAuth 2.0 | Pen test report |
| NFR-006 | Recoverability | RTO | < 4 hours | DR test results |
| NFR-007 | Recoverability | RPO | < 1 hour | DR test results |
| NFR-008 | Compliance | Data residency | In-country | Cloud config audit |
| ... | ... | ... | ... | ... |
```

### Required Skills

| Skill Area | Specific Skills |
|---|---|
| Domain Knowledge | TOGAF/Zachman frameworks, cloud architecture patterns (multi-tier, serverless, event-driven), C4 model for software architecture |
| Systems Thinking | Dependency mapping across layers, feedback loop identification, emergent behaviour analysis, architecture fitness functions |
| Technical Depth | Microservices design patterns, Kubernetes orchestration, Infrastructure as Code (Terraform/Pulumi), service mesh (Istio/Linkerd) |
| Analysis | Gap analysis methodology, non-functional requirement quantification, technology radar evaluation, total cost of ownership modelling |
| Communication | PlantUML/Mermaid diagram authoring, multi-level abstraction (board vs engineering), architecture storytelling, workshop facilitation |
| Reasoning | Trade-off analysis (CAP theorem, consistency vs availability), what-if scenario modelling, risk-weighted decision making, architecture debt assessment |

### Toolchain

| Tool | Purpose |
|---|---|
| Structurizr | C4 architecture diagrams as code (DSL) |
| draw.io / diagrams.net | Ad-hoc architecture and flow diagrams |
| TOGAF Metamodel | Enterprise architecture layer alignment and artefact mapping |
| AWS Well-Architected Tool | Cloud architecture review against six pillars |

---

## Competency 8: Architecture Decision Records & Traceability

### Best-of-Breed References

| Reference | Relevance |
|---|---|
| Michael Nygard (2011) | Original ADR format and philosophy -- lightweight, immutable decision capture |
| MADR (Markdown Any Decision Record) | Standardised ADR template with structured options and consequences |
| Jono Herrington CLI scaffolding | Command-line tooling for creating and managing ADRs with auto-numbering |
| ThoughtWorks Technology Radar | Technology evaluation framework informing ADR option analysis |

### Artifact Template: Architecture Decision Record

```markdown
# ADR-NNNN: [Decision Title]

| Field | Value |
|---|---|
| Status | Proposed / Accepted / Deprecated / Superseded by ADR-XXXX |
| Impact | High / Medium / Low |
| Driver | [Name of the person or team raising the decision] |
| Approver | [Name of the architecture authority or review board] |
| Created | [YYYY-MM-DD] |
| Outcome | [One-line summary of what was decided] |

---

## 1. Context and Problem Statement

[Describe the context in which this decision is being made. What is the architectural
challenge? What forces are at play? What constraints exist? Why does this decision
need to be made now?]

---

## 2. Decision Drivers

- **[Driver 1]:** [Specific constraint or requirement, e.g., "Must support 10,000
  concurrent connections"]
- **[Driver 2]:** [Specific constraint or requirement, e.g., "Vendor contract expires
  Q3 2026"]
- **[Driver 3]:** [Specific constraint or requirement, e.g., "Team has no experience
  with technology X"]
- **[Driver 4]:** [Specific constraint or requirement, e.g., "Regulatory requirement
  for data residency in UK"]
- **[Driver 5]:** [Specific constraint or requirement, e.g., "Budget ceiling of $500K
  for this component"]

---

## 3. Considered Options

### Option A: [Name]

- **How it works:** [Brief description of the approach]
- **Pros:**
  - [Pro 1]
  - [Pro 2]
  - [Pro 3]
- **Cons:**
  - [Con 1]
  - [Con 2]
- **Why not chosen / Why chosen:** [Explain the evaluation outcome for this option]

### Option B: [Name]

- **How it works:** [Brief description of the approach]
- **Pros:**
  - [Pro 1]
  - [Pro 2]
  - [Pro 3]
- **Cons:**
  - [Con 1]
  - [Con 2]
- **Why not chosen / Why chosen:** [Explain the evaluation outcome for this option]

### Option C: [Name]

- **How it works:** [Brief description of the approach]
- **Pros:**
  - [Pro 1]
  - [Pro 2]
- **Cons:**
  - [Con 1]
  - [Con 2]
  - [Con 3]
- **Why not chosen / Why chosen:** [Explain the evaluation outcome for this option]

---

## 4. Decision

We will use **[Option X]** for **[specific purpose / scope]** because **[primary
justification linking back to decision drivers]**.

---

## 5. Consequences

**Positive:**
- [Positive consequence 1]
- [Positive consequence 2]
- [Positive consequence 3]

**Negative:**
- [Negative consequence 1 -- and how it will be mitigated]
- [Negative consequence 2 -- and how it will be mitigated]

**Neutral:**
- [Neutral observation or trade-off acknowledged]

---

## 6. Related Decisions

- **ADR-NNNN:** [Title] -- [Relationship: depends on / supersedes / constrains /
  enables]
- **ADR-NNNN:** [Title] -- [Relationship]

---

## 7. Links

- [Requirement / Epic / Story ID]
- [Design document reference]
- [Spike / PoC results]
- [Meeting minutes / workshop output]
```

### Artifact Template: ADR Traceability Matrix

```markdown
# ADR Traceability Matrix

| ADR ID | Decision Title | Status | Requirement IDs | Component(s) | Sprint/PI | Test Evidence |
|---|---|---|---|---|---|---|
| ADR-0001 | [e.g., Use PostgreSQL for account data] | Accepted | REQ-101, REQ-102 | account-service, data-layer | PI-2, Sprint 4 | IT-045, PT-012 |
| ADR-0002 | [e.g., Adopt event sourcing for transactions] | Accepted | REQ-201 | transaction-service, event-store | PI-2, Sprint 6 | IT-067, PT-023 |
| ADR-0003 | [e.g., API gateway for external consumers] | Accepted | REQ-301, REQ-302, REQ-303 | api-gateway, auth-service | PI-3, Sprint 1 | IT-089, ST-005 |
| ADR-0004 | [e.g., Use Terraform for IaC] | Accepted | NFR-008, NFR-009 | infrastructure | PI-1, Sprint 2 | OT-001 |
| ADR-0005 | [e.g., Reject GraphQL for public APIs] | Deprecated | REQ-301 | api-gateway | PI-2, Sprint 3 | N/A -- superseded by ADR-0003 |
| ... | ... | ... | ... | ... | ... | ... |
```

### File Structure Convention

```
docs/
  adr/
    0001-use-postgresql-for-account-data.md
    0002-adopt-event-sourcing-for-transactions.md
    0003-api-gateway-for-external-consumers.md
    0004-use-terraform-for-iac.md
    ...
    template.md          # ADR template (copy for new ADRs)
    TRACEABILITY.md      # ADR Traceability Matrix
```

- File naming: `NNNN-kebab-case-title.md`
- Numbering: Sequential, zero-padded to 4 digits
- Immutability: Accepted ADRs are never edited; they are superseded by new ADRs
- Status lifecycle: `Proposed` -> `Accepted` -> (`Deprecated` | `Superseded by ADR-XXXX`)

### Required Skills

| Skill Area | Specific Skills |
|---|---|
| Decision Frameworks | ADR authoring (Nygard/MADR format), trade-off analysis, option evaluation matrices, decision trees |
| Technical Breadth | Evaluate across databases, frameworks, cloud services, protocols, and architectural patterns to populate options objectively |
| Traceability | Requirement-to-decision-to-test mapping, impact analysis when decisions change, dependency chain maintenance |
| Writing | Concise technical writing, context preservation for future readers, immutable record discipline, audience-appropriate abstraction |
| Process | PR-based ADR review workflow, status lifecycle management, supersession chaining, architectural review board facilitation |
| Retrieval | Semantic search across ADR corpus, precedent-based recommendation, pattern detection across decisions |

### Toolchain

| Tool | Purpose |
|---|---|
| Markdown + Git | ADR authoring, version control, and immutable history via commits |
| CLI scaffolding script | Auto-number and create new ADR files from template (`adr new "title"`) |
| Semantic search | Full-text and embedding-based search across ADR corpus for precedent lookup |
