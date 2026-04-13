---
process-area: Security Management (SMS)
process-count: 5
fit-gap-status: pending
primary-artefacts: [02-target-state-reference-architecture]
---

# Security Management (SMS) Processes

**Process Count:** 5

## Summary

Security Management System (SMS) processes include setting up and maintenance of users and user related parameters in the system.

## Key Sub-Processes

- User setup
- User maintenance
- User parameter management
- Access control configuration
- Security parameter management

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles security management today -->

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
| **Total** | | **321** | **191** | **582** | |

### Key API Patterns

- Security management functions within EB System Core
- User administration and access control (system domain)

### Integration Implications

- Expected adapter: System Adapter (IRF) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
