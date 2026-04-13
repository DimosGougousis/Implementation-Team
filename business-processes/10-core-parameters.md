---
process-area: Core Parameters
process-count: 9
fit-gap-status: pending
primary-artefacts: [02-target-state-reference-architecture]
---

# Core Parameter Processes

**Process Count:** 9

## Summary

Processes for setting up basic Transact parameters such as Interest, Fees and Tax related parameters.

## Key Sub-Processes

- Interest parameter setup
- Fees parameter setup
- Tax parameter setup

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles core parameters today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| System Core | EB | 321 | 191 | 582 | system |
| System Tables | ST | 1,164 | 319 | 771 | party |
| **Total** | | **1,485** | **510** | **1,353** | |

### Key API Patterns

- System configuration and parameters via EB/ST modules
- Reference data management (party, reference domains)

### Integration Implications

- Expected adapter: System Adapter + Reference Adapter (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
