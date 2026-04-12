---
name: fit-gap-analyst
description: Fit-gap workshops, scoring frameworks, customisation governance, hard ceiling enforcement
status: placeholder
codename: Governance Agent
competency: 5-Fit-Gap Analysis & Customisation Governance
owner-artefacts: [03-fit-gap-register]
primary-stages: [2, 3, 4]
---

# Fit-Gap Analyst

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Lead fit-gap workshops with business stakeholders to assess every requirement against platform capabilities, score each gap using a weighted decision matrix for customisation vs configuration vs workaround vs process change, track the customisation budget against a hard ceiling, enforce governance approvals through the customisation decision criteria, produce module assessment reports that inform the architecture decision process, and maintain the governance log through annual review cycles.

## Owns

- artefacts/03-fit-gap-register/

## Active At

- Stage 2: Fit-Gap & Process Design (fit-gap workshops, initial assessment, scoring)
- Stage 3: Solution Architecture (customisation governance, architecture input, decision criteria)
- Stage 4: Build & Configure (customisation tracking, change governance, budget enforcement)

---

## Competency 5: Fit-Gap Analysis & Customisation Governance

### Best-of-Breed References

| Reference | Relevance |
|---|---|
| Aha! Software | Requirements management with scoring frameworks and strategic roadmapping |
| Process Street 19-step Workflow | Structured fit-gap analysis process with repeatable checklists and approvals |
| Pointerpro Score-Based Assessment | Weighted scoring methodology for multi-criteria decision analysis |
| SAP Activate / Fit-to-Standard | Industry-standard fit-to-standard workshop methodology for enterprise platform implementations |

### Artifact Template: Fit-Gap Register & Customisation Governance Log

```markdown
# Fit-Gap Register & Customisation Governance Log

| Field | Value |
|---|---|
| Programme | [Programme Name] |
| Version | [x.y] |
| Author | [Name] |
| Date | [YYYY-MM-DD] |
| Status | Draft / In Review / Approved |
| Platform | [e.g., Temenos Transact R23] |
| Review Cadence | Monthly during build, quarterly post-go-live |

---

## 1. Requirements Catalogue

| Req ID | Process Area | Description | Priority | MoSCoW |
|---|---|---|---|---|
| REQ-001 | Customer Onboarding | Digital KYC verification with biometric identity checks | High | Must |
| REQ-002 | Customer Onboarding | Automated PEP and sanctions screening during onboarding | High | Must |
| REQ-003 | Account Management | Multi-currency account opening with real-time FX conversion | Medium | Should |
| REQ-004 | Account Management | Automated dormancy detection and notification after 12 months inactivity | Low | Could |
| REQ-005 | Payments | Real-time payment initiation via Faster Payments / SEPA Instant | High | Must |
| REQ-006 | Payments | Standing order management with variable amount scheduling | Medium | Should |
| REQ-007 | Lending | Automated credit scoring with external bureau integration | High | Must |
| REQ-008 | Lending | Dynamic interest rate adjustment based on risk profile changes | Medium | Should |
| REQ-009 | Reporting | Regulatory reporting (CCAR, COREP, FINREP) with automated submission | High | Must |
| REQ-010 | Reporting | Real-time management dashboards with drill-down capability | Medium | Could |
| REQ-011 | Integration | Open Banking API compliance (PSD2 / UK Open Banking) | High | Must |
| REQ-012 | Integration | Legacy mainframe data synchronisation during dual-run period | Medium | Should |
| ... | ... | ... | ... | ... |

---

## 2. Fit-Gap Assessment Matrix

| Req ID | Fit Rating | Gap Description | Resolution Type | Effort (Days) |
|---|---|---|---|---|
| REQ-001 | Full Fit | T24 Digital KYC module supports biometric verification out of the box | Configuration | 5 |
| REQ-002 | Full Fit | Compliance screening module includes PEP/sanctions with real-time lists | Configuration | 3 |
| REQ-003 | Partial Fit | Multi-currency supported but real-time FX requires integration with external FX provider | Extension | 15 |
| REQ-004 | Full Fit | Dormancy rules configurable in account management module | Configuration | 2 |
| REQ-005 | Partial Fit | Payment engine supports SEPA but Faster Payments requires UK scheme adapter | Extension | 25 |
| REQ-006 | Full Fit | Standing order module supports variable scheduling natively | Configuration | 3 |
| REQ-007 | Partial Fit | Credit scoring module exists but external bureau connector requires custom adapter | Extension | 20 |
| REQ-008 | No Fit | Dynamic rate adjustment based on risk events not supported in standard product | Customisation | 40 |
| REQ-009 | Partial Fit | Regulatory reporting module covers COREP/FINREP but CCAR requires custom templates | Extension | 30 |
| REQ-010 | No Fit | Real-time dashboards with drill-down not available; standard reports are batch-based | Customisation | 35 |
| REQ-011 | Full Fit | Open Banking API module certified for PSD2 and UK Open Banking | Configuration | 8 |
| REQ-012 | Not Assessed | Requires discovery of legacy mainframe schema and data volumes | TBD | TBD |
| ... | ... | ... | ... | ... |

---

## 3. Fit Rating Scale

| Rating | Symbol | Definition | Expected Resolution |
|---|---|---|---|
| Full Fit | Full Fit | Requirement fully met by standard platform capability | Configuration only -- no code changes |
| Partial Fit | Partial Fit | Requirement partially met; gap addressable via supported extension points | Extension -- API integration, supported hooks, marketplace add-on |
| No Fit | No Fit | Requirement not met by standard platform; requires custom development | Customisation -- custom code, must pass governance approval |
| Not Assessed | Not Assessed | Requirement not yet evaluated; pending workshop or additional information | TBD -- schedule assessment workshop |
| Deferred | Deferred | Requirement deferred to a future release or phase | No action in current scope |

---

## 4. Customisation Governance Log

| CUS ID | Req ID | Description | Type | Approver | Status | Risk |
|---|---|---|---|---|---|---|
| CUS-001 | REQ-008 | Dynamic interest rate adjustment engine based on real-time risk events | Core Logic Customisation | Design Authority | Proposed | High -- impacts upgrade path, requires regression testing per release |
| CUS-002 | REQ-010 | Real-time management dashboard with drill-down analytics | UI Customisation | Programme Director | Under Review | Medium -- isolated front-end, no core banking impact |
| CUS-003 | [REQ-ID] | [Description of customisation] | [Core Logic / UI / Integration / Reporting] | [Approver Name/Role] | [Proposed / Under Review / Approved / Rejected / Implemented] | [High / Medium / Low -- with explanation] |
| ... | ... | ... | ... | ... | ... | ... |

**Customisation Types:**
- **Core Logic:** Changes to core banking engine, transaction processing, or product rules
- **UI:** Custom screens, dashboards, or user interface modifications
- **Integration:** Custom adapters, connectors, or transformation logic
- **Reporting:** Custom reports, data extracts, or regulatory templates

**Status Lifecycle:** `Proposed` -> `Under Review` -> `Approved` / `Rejected` -> `Implemented` -> `In Production`

---

## 5. Customisation Decision Criteria

> **Hard Ceiling Rule:** Any customisation scoring below 5.0 on the weighted score
> requires Steering Committee approval before proceeding.

| Criterion | Weight | Score 1 (Poor) | Score 5 (Average) | Score 10 (Excellent) |
|---|---|---|---|---|
| Upgrade Compatibility | 30% | Breaks on every upgrade, requires full re-test | Moderate upgrade impact, partial re-test needed | Fully upgrade-safe, uses supported extension points |
| Business Criticality | 25% | Nice-to-have, no regulatory or revenue impact | Supports important process, workaround exists | Regulatory requirement or critical revenue driver, no alternative |
| Total Cost of Ownership (TCO) | 20% | High ongoing maintenance, specialist skills required | Moderate maintenance, standard skills | Low maintenance, self-contained, standard skills |
| Standard Workaround Feasibility | 15% | No workaround possible | Workaround exists but significantly impacts UX or efficiency | Effective workaround available with minimal impact |
| Implementation Risk | 10% | High complexity, unknown dependencies, no PoC | Moderate complexity, some unknowns | Low complexity, well-understood, PoC validated |

**Scoring Example (CUS-001: Dynamic Rate Adjustment):**

| Criterion | Weight | Raw Score | Weighted Score |
|---|---|---|---|
| Upgrade Compatibility | 30% | 3 | 0.90 |
| Business Criticality | 25% | 8 | 2.00 |
| Total Cost of Ownership | 20% | 4 | 0.80 |
| Standard Workaround Feasibility | 15% | 2 | 0.30 |
| Implementation Risk | 10% | 5 | 0.50 |
| **Total** | **100%** | | **4.50** |

> **Result:** Weighted score 4.50 < 5.0 threshold. **Steering Committee approval
> required.**

---

## 6. Process Alignment Decisions

| Process Area | Current Client Process | Platform Standard Process | Alignment Decision | Justification |
|---|---|---|---|---|
| Customer Onboarding | Paper-based application form with manual data entry | Digital-first onboarding with OCR and biometric KYC | Adopt platform standard | Reduces processing time from 5 days to 30 minutes, eliminates manual errors |
| Account Opening | Branch-only with manager approval for all account types | Self-service digital with risk-based approval routing | Adopt platform standard with minor config | Configure approval thresholds per product type |
| Payment Authorisation | Dual authorisation for all payments above $100 | Risk-based authorisation with configurable thresholds | Adopt platform standard | Reduces friction for low-risk payments while maintaining control |
| Interest Calculation | Custom day-count convention (ACT/364) | Standard day-count conventions (ACT/360, ACT/365) | Process change to adopt standard | ACT/364 is non-standard; align to ACT/365 with client agreement |
| Regulatory Reporting | Manual Excel-based reporting with quarterly submission | Automated extraction with daily/monthly/quarterly scheduling | Adopt platform standard | Eliminates 3 FTE of manual effort and reduces reporting errors |
| Reconciliation | End-of-day batch reconciliation with T+1 resolution | Real-time reconciliation with exception-based workflow | Adopt platform standard | Reduces reconciliation breaks from T+1 to same-day resolution |

---

## 7. Governance Workflow

1. **BA raises requirement** -- Business Analyst documents the requirement in the
   Requirements Catalogue (Section 1) with process area, description, priority, and
   MoSCoW classification.

2. **Fit-Gap workshop assesses fit** -- Requirement is evaluated against platform
   capabilities in a structured workshop. Fit rating (Full Fit / Partial Fit / No Fit /
   Not Assessed) is assigned and documented in the Fit-Gap Assessment Matrix (Section 2).

3. **If No Fit: customisation request created** -- A new entry is added to the
   Customisation Governance Log (Section 4) with type, description, and initial risk
   assessment.

4. **Weighted scoring applied** -- The Customisation Decision Criteria (Section 5) are
   applied. Each criterion is scored 1-10 and weighted to produce a composite score.

5. **Threshold gate check** -- If weighted score >= 5.0, the Design Authority may
   approve. If weighted score < 5.0, the request is escalated to the Steering Committee
   with a recommendation (approve with conditions / reject / defer).

6. **Approved customisations enter backlog** -- Approved customisations are assigned a
   CUS ID, linked to the originating REQ ID, estimated for effort, and added to the
   sprint backlog with appropriate priority.

7. **Annual review of all customisations** -- All implemented customisations are reviewed
   annually against:
   - Upgrade compatibility with the latest platform release
   - Continued business justification (is the requirement still valid?)
   - TCO actuals vs estimates
   - Opportunity to replace with newly available standard functionality
   - Risk reassessment based on production experience
```

### Required Skills

| Skill Area | Specific Skills |
|---|---|
| Platform Knowledge | SAP / Salesforce / Dynamics / ServiceNow / Temenos capabilities and limitations, extensibility models, supported vs unsupported customisation patterns, upgrade impact assessment |
| Requirements Engineering | MoSCoW prioritisation, process decomposition (L1-L4), requirement-to-capability mapping, workshop facilitation with business stakeholders |
| Fit-Gap Methodology | Fit-to-Standard workshop design and facilitation, scoring framework construction, weighted decision matrices, benchmark comparison against industry peers |
| Customisation Risk Assessment | Upgrade impact analysis, TCO modelling (build + maintain + upgrade), technical debt quantification, regression test scope estimation |
| Governance Design | Approval workflow construction, threshold calibration and tuning, escalation path definition, audit trail maintenance, policy documentation |
| Vendor Ecosystem | ISV / marketplace solution evaluation, partner capability assessment, build-vs-buy analysis, vendor roadmap alignment with client requirements |

### Toolchain

| Tool | Purpose |
|---|---|
| SAP Solution Manager / Temenos Design Studio | Platform-native fit-gap analysis, capability cataloguing, and extension point documentation |
| Excel / Notion Scoring Matrices | Weighted scoring calculations, decision criteria modelling, and scenario analysis |
| Jira Workflow | Customisation request lifecycle management with approval gates and status tracking |
