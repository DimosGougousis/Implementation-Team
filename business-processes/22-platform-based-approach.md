---
process-area: Platform Based Approach
process-count: 275
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture, 04-integration-dependency-map]
---

# Platform Based Approach Processes

**Process Count:** 275

## Summary

The platform-based approach processes provides a comprehensive and detailed understanding of user journeys within Transact - Core Banking, Payments, Loans, Wealth, Corporate, Trade Finance, Treasury, Financial Crime Mitigation, Cash Management packages.

## Key Sub-Processes (by Package)

| Package | Coverage |
|---|---|
| Core Banking | User journeys |
| Payments | User journeys |
| Loans | User journeys |
| Wealth | User journeys |
| Corporate | User journeys |
| Trade Finance | User journeys |
| Treasury | User journeys |
| Financial Crime Mitigation | User journeys |
| Cash Management | User journeys |

## Fit-Gap Status

| Package | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: which platform packages are relevant -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Integration Framework | IF | 4 | 4 | 16 | system |
| System Core | EB | 321 | 191 | 582 | system |
| Origination Architecture | OA | 5 | 5 | 20 | reference |
| **Total** | | **330** | **200** | **618** | |

### Key API Patterns

- Platform integration framework via IF module
- Origination architecture via OA module (reference domain)
- Core platform services via EB module

### Integration Implications

- Expected adapter: System Adapter + Reference Adapter (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
