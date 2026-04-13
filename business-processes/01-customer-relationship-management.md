---
process-area: Customer Relationship Management
process-count: 59
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Customer Relationship Management Processes

**Process Count:** 59

## Summary

CRM processes consist of customer on-boarding and associated processes such as KYC, AML and Campaign & Contact Management. It also includes Call Centre processes.

## Key Sub-Processes

- Customer on-boarding
- KYC (Know Your Customer)
- AML (Anti-Money Laundering)
- Campaign & Contact Management
- Call Centre processes

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles CRM today -->

## Target State (Transact)
<!-- Map to Transact packaged business capabilities -->

## Gap Notes
<!-- Identified gaps and customisation requirements -->


## Transact Module & API Coverage

> Source: Temenos R25AMR API Catalog | See also: [Module Cross-Reference](module-api-cross-reference.md)

### Mapped Modules

| Module | Code | IRF APIs | Publisher APIs | PSD2 APIs | Primary Domain |
|---|---|---|---|---|---|
| Customer Relationship Management | CR | 23 | 0 | 23 | party |
| Customer Data Protection | CZ | 10 | 0 | 10 | party |
| Party | PY | 176 | 0 | 176 | party |
| Consent Management | CK | 25 | 0 | 25 | party |
| **Total** | | **234** | **0** | **234** | |

### Key API Patterns

- Customer onboarding and maintenance via CR module (party domain)
- KYC/AML compliance checks via CZ module
- Consent management for data sharing via CK module

### Integration Implications

- Expected adapter: Party Adapter (IRF + PSD2) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
