# Business Processes — Core Banking Process Reference Library

Reference library of Temenos Transact core banking processes for implementation programmes.

## Purpose

This folder contains the **gold-standard process catalogue** — 22 process areas covering 2,485+ Temenos Transact processes. Each file describes a process area with its summary, process count, and current/target-state mapping placeholders.

## Integration Rules

- **One-directional flow:** Processes are the INPUT. They feed into:
  - `artefacts/03-fit-gap-register/` — gap analysis per process area
  - `artefacts/02-target-state-reference-architecture/` — capability mapping
- Process files are reference templates. Programme-specific adaptations live in `pipeline/active/<programme>/`.

## Process Area Index

| # | Process Area | Processes | File |
|---|---|---|---|
| 01 | Customer Relationship Management | 59 | `01-customer-relationship-management.md` |
| 02 | Retail Banking | 166 | `02-retail-banking.md` |
| 03 | Corporate Banking | 238 | `03-corporate-banking.md` |
| 04 | Transactional | 496 | `04-transactional.md` |
| 05 | Treasury | 79 | `05-treasury.md` |
| 06 | Private Wealth Management | 319 | `06-private-wealth-management.md` |
| 07 | Online Channels | 116 | `07-online-channels.md` |
| 08 | Security Management (SMS) | 5 | `08-security-management.md` |
| 09 | Financial Accounting Parameters | 34 | `09-financial-accounting-parameters.md` |
| 10 | Core Parameters | 9 | `10-core-parameters.md` |
| 11 | Islamic Banking | 134 | `11-islamic-banking.md` |
| 12 | Regionalized Solutions | 268 | `12-regionalized-solutions.md` |
| 13 | Digital Engagement | 22 | `13-digital-engagement.md` |
| 14 | Regulatory Reporting & Compliance | 66 | `14-regulatory-reporting-compliance.md` |
| 15 | Financial Crime Mitigation | 74 | `15-financial-crime-mitigation.md` |
| 16 | Fund Accounting | 69 | `16-fund-accounting.md` |
| 17 | Temenos Digital | 46 | `17-temenos-digital.md` |
| 18 | Temenos Banking Solution (TBS) | 75 | `18-temenos-banking-solution.md` |
| 19 | Business Banking | 34 | `19-business-banking.md` |
| 20 | Enterprise Services | 157 | `20-enterprise-services.md` |
| 21 | Financial Risk Management | 19 | `21-financial-risk-management.md` |
| 22 | Platform Based Approach | 275 | `22-platform-based-approach.md` |

**Total: 2,485+ processes across 22 areas**

## ALWAYS / NEVER

- ALWAYS reference specific process IDs when linking to fit-gap register entries.
- NEVER modify the reference summaries — programme-specific adaptations go in pipeline/.
