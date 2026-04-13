---
process-area: Financial Crime Mitigation
process-count: 74
fit-gap-status: pending
primary-artefacts: [03-fit-gap-register, 02-target-state-reference-architecture]
---

# Financial Crime Mitigation Processes

**Process Count:** 74

## Summary

Financial Crime Mitigation Processes covers the creation of Mandator and User for application and data restrictions. It also caters to creation of Customer on-boarding/Enhanced due diligence form and creation of Risk Matrix for classification of risk. Knowledge Management allows user to create, generate and manage reports, schedule them and represent the generated reports as dashboards.

## Key Sub-Processes

- Mandator and User creation (application/data restrictions)
- Customer on-boarding forms
- Enhanced Due Diligence (EDD) forms
- Risk Matrix creation and risk classification
- Knowledge Management (report creation, generation, management)
- Report scheduling
- Dashboard representation of reports

## Fit-Gap Status

| Sub-Process | Status | Gap Score | Notes |
|---|---|---|---|
| | pending | | |

## Current State
<!-- Bank-specific: how the bank handles financial crime mitigation today -->

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
| **Total** | | **33** | **0** | **33** | |

### Key API Patterns

- AML screening and customer due diligence via CR module
- Customer data protection and GDPR via CZ module

### Integration Implications

- Expected adapter: Party Adapter (IRF + PSD2) (see `artefacts/04-integration-dependency-map/adapter-strategy.md`)
