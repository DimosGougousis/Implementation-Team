# Pre-Work Checklist

Activities that must be completed before Stage 1 (Discovery) begins for a re-implementation programme.

**Timing:** 2–4 weeks before Stage 1
**Owner:** Programme Lead
**Gate Input:** Pre-Work Complete → Stage 1 Entry

## Legacy System Inventory

- [ ] Legacy system name, version, vendor documented
- [ ] Legacy system architecture diagram produced
- [ ] Legacy database schema documented (tables, relationships, volumes)
- [ ] Legacy integrations listed (source, target, protocol, frequency)
- [ ] Legacy batch jobs listed (schedule, purpose, dependencies)
- [ ] Legacy customisations listed (modules, complexity, business justification)
- [ ] Legacy licences and contracts documented (cost, expiry, terms)
- [ ] Legacy support arrangements documented (vendor, SLA, contacts)

## Data Estate Assessment

- [ ] Source system inventory completed (tables, records, relationships)
- [ ] Data quality baseline measured (completeness, accuracy, consistency)
- [ ] Data volume estimates per domain produced
- [ ] Regulatory data requirements identified (retention, access, audit trail)
- [ ] Data ownership and stewardship identified
- [ ] Data Estate Report produced (see `artefacts/05-data-quality-scorecard/data-estate-report.md`)

## Integration Landscape Mapping

- [ ] All system-to-system touchpoints identified
- [ ] Integration protocols documented (REST, SOAP, event, file, database)
- [ ] Integration owners identified
- [ ] Integration SLAs documented
- [ ] Integration retire/rebuild decisions flagged (preliminary)
- [ ] Undocumented integrations discovered and logged

## Business Process Documentation (As-Is)

- [ ] Current-state processes documented for all 22 business process areas
- [ ] Process owners identified
- [ ] Pain points and workarounds documented
- [ ] Process-to-system mapping completed
- [ ] Regulatory processes identified and flagged

## Programme Setup

- [ ] Programme charter drafted
- [ ] Stakeholder map produced
- [ ] Budget estimate produced
- [ ] Resource plan drafted
- [ ] Risk register initialised
- [ ] Programme team onboarded

## Deliverables

| Deliverable | Template | Status |
|---|---|---|
| Legacy System Inventory | (custom — no template yet) | |
| Data Estate Report | `artefacts/05-data-quality-scorecard/data-estate-report.md` | |
| Integration Landscape Map | `artefacts/04-integration-dependency-map/integration-register.md` | |
| As-Is Process Documentation | `business-processes/` (22 files) | |
| Programme Charter | (custom — no template yet) | |
| Stakeholder Map | `governance/stakeholder-and-vendor-orchestration.md` | |

## Exit Criteria

All checklist items completed → Programme Lead confirms Pre-Work Complete → Stage 1 begins.
