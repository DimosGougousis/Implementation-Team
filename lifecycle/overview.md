# Lifecycle Overview

Visual lifecycle and stage-to-artefact mapping.

## Lifecycle Flow

```mermaid
graph LR
    D[1. Discovery] --> FG[2. Fit-Gap]
    FG --> SA[3. Architecture]
    SA --> BC[4. Build]
    BC --> T[5. Testing]
    T --> DM[6. Migration]
    DM --> C[7. Cutover]
    C --> H[8. Hypercare]
```

## Gate Decisions

```mermaid
graph TD
    S1[Stage 1] --> G1{Gate 1}
    G1 -->|Pass| S2[Stage 2]
    G1 -->|Fail| F1[Remediate]
    F1 --> S1
    S2 --> G2{Gate 2}
    G2 -->|Pass| S3[Stage 3]
    G2 -->|Fail| F2[Remediate]
    F2 --> S2
    S3 --> G3{Gate 3}
    G3 -->|Pass| S4[Stage 4]
    G3 -->|Fail| F3[Remediate]
    F3 --> S3
    S4 --> G4{Gate 4}
    G4 -->|Pass| S5[Stage 5]
    G4 -->|Fail| F4[Remediate]
    F4 --> S4
    S5 --> G5{Gate 5}
    G5 -->|Pass| S6[Stage 6]
    G5 -->|Fail| F5[Remediate]
    F5 --> S5
    S6 --> G6{Gate 6}
    G6 -->|Pass| S7[Stage 7]
    G6 -->|Fail| F6[Remediate]
    F6 --> S6
    S7 --> G7{Gate 7}
    G7 -->|Pass| S8[Stage 8]
    G7 -->|Fail| F7[Rollback]
    S8 --> G8{Gate 8}
    G8 -->|Pass| DONE[Steady State]
```

## Stage Summaries

### Stage 1: Discovery
Understand the bank's current state, strategic objectives, and programme scope. Produce the initial target-state reference architecture.

### Stage 2: Fit-Gap & Process Design
Assess each Transact module against business requirements. Score gaps, track customisation budget, and begin data quality profiling.

### Stage 3: Solution Architecture
Author ADRs, finalise the target-state architecture, create the integration dependency map, and define the test strategy framework.

### Stage 4: Build & Configure
Implement Transact configuration, customisations, and integrations. Update all artefacts as decisions evolve.

### Stage 5: Testing
Execute four-phase testing (Unit → Integration → SIT/Perf → UAT). Track KPIs and manage defects to gate criteria.

### Stage 6: Data Migration
Execute data profiling, cleansing, mapping, and rehearsals. Achieve quality gate thresholds for go-live.

### Stage 7: Cutover
Execute the cutover runbook, manage go/no-go decision, and transition to production.

### Stage 8: Hypercare
Stabilise the platform, transfer knowledge to BAU, and achieve steady-state operating model.
