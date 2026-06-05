# Skill Playbook System — Design Specification

**Date:** 2026-04-13
**Status:** Draft
**Author:** Design session with Dimos
**Scope:** Defines the structure, quality bar, and reusable template for building 72+ consultant skill playbooks for the Implementation Team OS.

---

## Context

The Implementation Team OS has 11 AI agents with 72 planned skills (potentially 83 with gap additions). Today, all skills exist only as descriptions embedded in `.agent.md` files. The `.claude/skills/` directory is empty.

**Problem:** Without standalone, structured skill playbooks, consultants have no repeatable process to follow when executing agent competencies. A junior consultant cannot independently run a fit-gap workshop, write an ADR, or design an API contract without extensive mentoring.

**Goal:** Create a standardised skill playbook format that:
1. Gives consultants **clarity on what is required** (inputs, prerequisites, process)
2. Defines **clear outcomes** (named deliverables + pass/fail quality checklist)
3. Is detailed enough for a **junior consultant to execute independently**
4. Works across all skill types (facilitation, analysis, documentation, technical design)

---

## Design Decisions

| Decision | Choice | Rationale |
|---|---|---|
| Primary consumer | Human consultants | Skills are practitioner playbooks, not AI prompts |
| Detail level | Full playbook | Junior consultant can execute independently |
| Outcomes format | Deliverable + Quality Checklist | Pass/fail per item, auditable |
| Structure | Process-Centric (Approach A) | Preparation -> Execution -> Follow-Up mirrors how consultants work |
| Build strategy | One prototype first, then scale | Validate the template with `run-fit-gap-workshop` before building all 72 |

---

## Deliverables

| # | Deliverable | File Path | Description |
|---|---|---|---|
| 1 | **Skill Playbook Template** | `.claude/skills/_skill-playbook-template.md` | Reusable 10-section template for all 72 skills |
| 2 | **Prototype Skill: run-fit-gap-workshop** | `.claude/skills/run-fit-gap-workshop.md` | Complete playbook for fit-gap workshop facilitation |
| 3 | **Fit-Gap Workshop Excel Template** | `artefacts/03-fit-gap-register/fit-gap-workshop-tracker.xlsx` | Excel spreadsheet for capturing workshop discussions, scores, and decisions |

---

## 1. Skill Playbook Template (10 Sections)

Every skill file follows this structure. Sections scale in length based on skill complexity — a simple documentation skill may have a 3-line Preparation section, while a facilitation skill like `run-fit-gap-workshop` has a full agenda.

```markdown
# [Skill Name]

**Agent:** [agent-name]
**Competency:** [N]-[Competency Name]
**Stage(s):** [primary stages]
**Difficulty:** [Junior can execute independently / Requires senior oversight / Senior only]

---

## 1. Purpose & Context

[Why this skill matters. Where it sits in the lifecycle. What downstream agents depend on its outputs. What happens if this skill is done poorly.]

## 2. Prerequisites

[What must be true before starting — stage gate requirements, prior artefacts that must exist, people/roles confirmed, tools available]

## 3. Inputs

| Input | Source | File Path / Format |
|---|---|---|
| [Input name] | [Source agent or role] | [Exact path or format description] |

## 4. Process

### 4A. Preparation
[Steps to take before the main activity — research, materials, scheduling]

### 4B. Execution
[Step-by-step process for the core activity — the main work]

### 4C. Follow-Up
[Steps after completion — documentation, handoffs, review cycles]

## 5. Deliverables

| # | Deliverable | File Path | Format |
|---|---|---|---|
| D1 | [Name] | [Exact path with placeholders] | [Markdown / Excel / etc.] |

## 6. Quality Checklist

| # | Check | Pass Criteria |
|---|---|---|
| Q1 | [Check name] | [Measurable, pass/fail criterion] |

## 7. Downstream Handoffs

| To Agent | When | What to Create | File Path |
|---|---|---|---|
| [agent-name] | [Trigger condition] | [Artefact to create/update] | [Exact path] |

## 8. Common Pitfalls

| Pitfall | How to Avoid |
|---|---|
| [Name] | [Prevention strategy] |

## 9. Worked Example

[Realistic scenario with actual data showing: inputs used, process followed, outputs produced, quality checklist applied]

## 10. Related Skills

| Skill | Agent | Relationship |
|---|---|---|
| [skill-name] | [agent-name] | [Feeds into / Depends on / Overlaps with] |
```

### Template Design Rationale

| Section | Why it exists |
|---|---|
| Purpose & Context | Connects the skill to the bigger picture — consultants need to understand WHY |
| Prerequisites | Prevents starting work without required inputs (common failure mode) |
| Inputs | Named files and sources — no ambiguity about what data is needed |
| Process (Prep/Execute/Follow-Up) | Mirrors how consultants actually work; natural sequencing |
| Deliverables | Named files with exact paths — consultant knows exactly what to produce |
| Quality Checklist | Pass/fail items — auditable, objective, no subjective judgment |
| Downstream Handoffs | Explicit artefact creation for receiving agents — prevents "forgotten handoffs" |
| Common Pitfalls | Learning from experience — saves junior consultants from known failure modes |
| Worked Example | Shows what "good" looks like with real data |
| Related Skills | Maps the skill into the ecosystem — consultants see the network |

---

## 2. Prototype Skill: run-fit-gap-workshop

### Full Content

```markdown
# Run Fit-Gap Workshop

**Agent:** fit-gap-analyst
**Competency:** 5-Fit-Gap Analysis & Customisation Governance
**Stage(s):** 2 (primary), 3-4 (refresh workshops)
**Difficulty:** Requires senior oversight (first 2 workshops — senior sits in as observer and reviews deliverables before circulation), then junior can execute independently

---

## 1. Purpose & Context

Enable a consultant to plan, facilitate, and close a structured Fit-Gap workshop that assesses business requirements against Temenos Transact platform capabilities, producing a scored Fit-Gap Register ready for architecture and governance review.

This is the foundational skill of the Fit-Gap Analyst (Competency 5). It runs during Stage 2: Fit-Gap & Process Design and feeds into:
- **design-authority** — gaps requiring architecture decisions become ADRs
- **process-analyst** — "adopt platform standard" decisions trigger process redesign
- **integration-architect** — integration gaps feed the integration register
- **programme-governance** — customisation budget tracking

A poorly-run workshop produces ambiguous scores that cascade into bad architecture decisions, budget overruns, and scope disputes in Stage 4.

## 2. Prerequisites

1. Programme has passed Stage 1 (Discovery) gate
2. Requirements Catalogue exists (even if draft) — at minimum: Req ID, Process Area, Description, Priority, MoSCoW
3. process-analyst has documented as-is processes for the module being assessed
4. Platform capability documentation is available (Temenos module guides, R25AMR API catalog)
5. Business SMEs identified and confirmed for the module scope (minimum: 1 process owner + 1 operations representative)
6. Workshop logistics booked (room/virtual, 3-4 hours per module, scoring tools ready)

## 3. Inputs

| Input | Source | File Path / Format |
|---|---|---|
| Requirements Catalogue | Business Analysts | `artefacts/03-fit-gap-register/requirements-catalogue.md` |
| As-Is Process Maps | process-analyst | `business-processes/NN-*.md` |
| Temenos Module Guide | Vendor documentation | PDF / online reference |
| R25AMR API Catalog | Reference data | `docs/reference-data/temenos-r25amr-api-catalog.xlsx` |
| Module-API Cross-Reference | Reference data | `business-processes/module-api-cross-reference.md` |
| Customisation Budget Status | programme-governance | Current ceiling vs consumed (from STAGE-STATUS.md) |
| Fit-Gap Workshop Tracker | Template | `artefacts/03-fit-gap-register/fit-gap-workshop-tracker.xlsx` |

## 4. Process

### 4A. Preparation (1-2 days before workshop)

**Step 1: Scope the module**
- Identify which Transact module(s) the workshop covers (e.g., AA for Retail Lending, FT for Payments)
- Pull the relevant requirements from the Requirements Catalogue (filter by Process Area)
- Count: target 15-25 requirements per 3-hour session. If more, split into multiple sessions.

**Step 2: Pre-score requirements**
- Review each requirement against Temenos documentation and the API catalog
- Mark your preliminary Fit Rating (Full Fit / Partial Fit / No Fit / Not Assessed) with notes
- Flag requirements where you are uncertain — these need the most workshop time
- Purpose: this is NOT the final score. It is preparation so you can guide the conversation, not discover capabilities live.

**Step 3: Prepare workshop materials**
- Print/share the Fit Rating Scale — every attendee needs this:

| Rating | Definition | Expected Resolution |
|---|---|---|
| Full Fit | Requirement fully met by standard platform capability | Configuration only — no code changes |
| Partial Fit | Requirement partially met; gap addressable via supported extension points | Extension — API, supported hooks, marketplace add-on |
| No Fit | Requirement not met by standard platform; requires custom development | Customisation — must pass governance approval |
| Not Assessed | Not yet evaluated; pending workshop or additional information | Schedule assessment |
| Deferred | Deferred to a future release or phase | No action in current scope |

- Prepare a pre-read pack: module scope, requirement list, preliminary scores, known capabilities
- Send pre-read to attendees 48 hours before the workshop
- Open the Fit-Gap Workshop Tracker Excel and pre-populate the Requirements tab with the in-scope requirements

**Step 4: Confirm attendees and roles**
- **Facilitator** (you): runs the session, captures scores, manages time
- **Platform SME**: confirms what the platform can/cannot do (Temenos consultant or solution architect)
- **Business SME(s)**: confirm business requirements and accept/reject proposed resolutions
- **Scribe**: captures detailed notes, action items, decisions (can be the facilitator if team is small)
- Send calendar invite with agenda, pre-read link, and roles

### 4B. Execution (During the workshop — 3-4 hours per module)

**Step 5: Open the workshop (15 min)**
- State the objective: "By end of session, every requirement for [Module] has a Fit Rating and, if a gap, a proposed resolution type"
- Walk through the Fit Rating Scale — ensure everyone understands definitions
- Set ground rules: one requirement at a time, decisions recorded not debated endlessly, "parking lot" for out-of-scope topics
- Confirm the customisation budget status: "We have X days remaining of the Y-day ceiling"

**Step 6: Walk through each requirement (2.5-3 hours)**

Work through requirements in process-area order. Allocate 8-12 minutes per requirement. Set a visible timer. If a requirement hits 12 minutes without resolution, move it to the parking lot.

For each requirement, follow this assessment loop:

| Phase | Who Leads | Duration | Action |
|---|---|---|---|
| Read | Facilitator | 1 min | Read the requirement aloud. Confirm with Business SME: "Is this still accurate and in scope?" |
| Demonstrate | Platform SME | 3-4 min | Show how the platform handles this. Live demo preferred. If no demo, walk through module documentation. State clearly: "The platform does X. It does NOT do Y." |
| Score | Facilitator | 2-3 min | Propose pre-scored rating. Ask: "Platform SME, do you agree?" Then: "Business SME, does this meet your requirement?" |
| Resolve | All | 2-4 min | If Full Fit: confirm Configuration, estimate effort, record, move on. If gap: use the resolution decision tree below. |

**Resolution Decision Tree (for Partial Fit and No Fit):**

```
Partial Fit or No Fit?
|-- Can the business process change to match the platform?
|   |-- YES --> Resolution = "Process Change" --> Flag to process-analyst
|   |-- NO
|       |-- Is there a supported extension point (API, hook, marketplace)?
|       |   |-- YES --> Resolution = "Extension" --> Estimate effort
|       |   |-- NO
|       |       |-- Is there a workaround (manual step, different workflow)?
|       |       |   |-- YES and acceptable --> Resolution = "Workaround" --> Document limitations
|       |       |   |-- NO or unacceptable
|       |       |       --> Resolution = "Customisation" --> Flag for governance scoring (Step 9)
```

**Handling disagreements:**
- Business vs Platform SME disagree on Fit Rating: Ask the Platform SME to demonstrate. If they cannot, it is a gap. Evidence over opinion.
- Business insists on an unsupported feature: Document as No Fit. The governance scoring is where the trade-off happens, not the workshop floor.
- Dominant voice: Pause and directly ask quiet attendees: "[Name], does this match how your team operates today?"
- Scope creep: New requirements go into the Catalogue, not this session.

**Real-time recording:**
- Record every decision in the Fit-Gap Workshop Tracker Excel immediately
- For every No Fit: capture the exact gap (not vague: specific)
- For every effort estimate: ask for optimistic/pessimistic range, record the pessimistic number

**Step 7: Close the workshop (15 min)**
- Review the parking lot — assign owners and deadlines
- Summarise: X requirements scored, Y Full Fit, Z Partial Fit, W No Fit, V Not Assessed
- Flag customisation requests needing Steering Committee escalation
- Confirm next steps: register circulation timeline, comment deadline

### 4C. Follow-Up (1-3 days after workshop)

**Step 8: Produce the Fit-Gap Register**
- Transfer all scores from the Workshop Tracker Excel into the formal register
- File path: `artefacts/03-fit-gap-register/module-assessments/[module-name].md`
- Use the template: `artefacts/03-fit-gap-register/module-assessments/_template.md`
- Populate: Requirements Catalogue, Fit-Gap Assessment Matrix, Process Alignment Decisions

**Step 9: Create Customisation Requests**
For every "No Fit" scored as Customisation:
- Create an entry in the Customisation Governance Log
- Fill in: CUS ID (sequential), Req ID (link), Description (exact gap), Type (Core Logic / UI / Integration / Reporting), Risk level

Apply the Weighted Scoring for each customisation:

| # | Criterion | Weight | Question to Ask | 1 = Poor | 10 = Excellent |
|---|---|---|---|---|---|
| 1 | Upgrade Compatibility | 30% | "Will this break on every Temenos upgrade?" | Breaks every time | Uses supported extension points |
| 2 | Business Criticality | 25% | "What happens if we don't do this?" | Nice-to-have | Regulatory, no alternative |
| 3 | TCO | 20% | "What will it cost to maintain per year?" | Specialist skills, constant fixes | Self-contained, standard skills |
| 4 | Workaround Feasibility | 15% | "Is there any other way to achieve this?" | No workaround exists | Good workaround, minimal impact |
| 5 | Implementation Risk | 10% | "How confident are we in the estimate?" | Unknown dependencies, no PoC | Well-understood, PoC validated |

Calculation: `Weighted Score = Sum(Raw Score x Weight)`

Threshold decision:
- Score >= 5.0: Design Authority may approve. Set Approver = Design Authority.
- Score < 5.0: Steering Committee required. Prepare 1-page escalation brief: What (requirement + gap), Why it scored below threshold (which criteria pulled it down), Options (approve with conditions / accept gap / defer), Recommendation.

Update the customisation budget:
- Add effort estimate (days) for each approved customisation to running total
- 50% of ceiling consumed: flag to programme-governance as "caution"
- 75% of ceiling consumed: escalate to Steering Committee immediately

**Step 10: Trigger downstream handoffs**

| To Agent | When | What to Create | Where |
|---|---|---|---|
| design-authority | Gap requires architecture decision | Draft ADR: Title, Status=Proposed, Context=gap description, linked REQ-ID and CUS-ID | `artefacts/01-architecture-decision-records/` |
| integration-architect | Partial Fit or Extension requiring system integration | Integration register entry: Source, Target, Type (API/Event/File), Priority, linked REQ-ID | `artefacts/04-integration-dependency-map/integration-register.md` |
| process-analyst | "Adopt platform standard" or "Process Change" resolution | Note under Gap Notes: REQ-ID, current process, target process, impact | `business-processes/NN-*.md` |
| programme-governance | Always (after every workshop) | Update: budget consumed vs ceiling, new CUS-IDs raised, escalations pending | `pipeline/active/[programme]/STAGE-STATUS.md` |

**Step 11: Circulate for review**
- Send completed module assessment to all workshop attendees
- Set 5-working-day review window
- Track comments, resolve, update register
- Change status: Draft -> In Review -> Approved

## 5. Deliverables

| # | Deliverable | File Path | Format |
|---|---|---|---|
| D1 | Module Assessment | `artefacts/03-fit-gap-register/module-assessments/[module-name].md` | Markdown |
| D2 | Customisation Governance Log entries | `artefacts/03-fit-gap-register/customisation-governance-log.md` | Append |
| D3 | Workshop Notes | `artefacts/03-fit-gap-register/workshop-notes/[YYYY-MM-DD]-[module]-workshop.md` | Markdown |
| D4 | Downstream handoff notes | Various (ADRs, integration register, business processes, STAGE-STATUS) | Updates |
| D5 | Parking lot items | `artefacts/03-fit-gap-register/workshop-notes/[date]-parking-lot.md` | Action items |
| D6 | Completed Workshop Tracker | `artefacts/03-fit-gap-register/fit-gap-workshop-tracker.xlsx` (per workshop copy) | Excel |

## 6. Quality Checklist

| # | Check | Pass Criteria |
|---|---|---|
| Q1 | All in-scope requirements scored | Zero "Not Assessed" remaining (except formally deferred) |
| Q2 | Every gap has a specific description | No vague gaps — each describes exactly what is missing |
| Q3 | Every gap has a resolution type | Configuration / Extension / Customisation / Process Change / Workaround / Deferred |
| Q4 | Every customisation has weighted scoring | All 5 criteria scored, weighted total calculated, threshold check done |
| Q5 | Effort estimates are pessimistic | Every Extension and Customisation has an effort estimate in days |
| Q6 | Customisation budget updated | STAGE-STATUS.md reflects new consumed total vs ceiling |
| Q7 | Downstream handoffs created | ADR drafts, integration entries, process notes — all created for relevant gaps |
| Q8 | Workshop notes circulated | Attendees have the register within 3 working days |
| Q9 | Review window set | 5-working-day deadline communicated with escalation path |
| Q10 | Parking lot resolved or assigned | Every item has an owner and a deadline |

## 7. Downstream Handoffs

(Detailed in Step 10 above — this section provides a summary view)

| To Agent | Trigger | Artefact Created |
|---|---|---|
| design-authority | Gap requiring architecture decision | Draft ADR (Proposed) |
| integration-architect | Gap requiring system integration | Integration register entry |
| process-analyst | "Adopt platform standard" resolution | Process redesign note |
| programme-governance | Every workshop (always) | Budget and escalation update |

## 8. Common Pitfalls

| Pitfall | Why It Happens | How to Avoid |
|---|---|---|
| Scoring without demonstration | Platform SME says "yes" without showing it | Require live demo or documented proof for every Full Fit |
| Vague gap descriptions | Time pressure | Enforce: if you cannot describe the gap in one sentence, you have not understood it |
| Customisation bias | Business defaults to "build it custom" | Always walk the decision tree: process change -> extension -> workaround -> customisation (last resort) |
| Missing effort estimates | "We'll estimate later" | Capture a range in the workshop. Pessimistic number goes in the register |
| Forgotten handoffs | Workshop finishes without notifying downstream agents | Use handoff checklist (Step 10) as a closing activity |
| Scope creep | New requirements surface and get scored immediately | New requirements go into the Catalogue, not the current session |

## 9. Worked Example

**Module: AA (Retail Lending)**

Workshop details:
- Date: 2026-03-15, Duration: 3.5 hours
- Attendees: Fit-Gap Analyst (facilitator), Temenos AA Consultant (Platform SME), Head of Retail Lending (Business SME), Lending Operations Manager (Business SME), BA (scribe)
- Requirements in scope: 18

Results:
- 10 Full Fit (Configuration, 45 days total effort)
- 5 Partial Fit (3 Extensions at 60 days, 2 Process Changes)
- 2 No Fit (Customisation candidates)
- 1 Deferred (pending regulatory clarity)

Customisation Requests:
- CUS-001: Dynamic rate adjustment based on real-time risk events
  - Scoring: Upgrade Compat (3), Business Crit (8), TCO (4), Workaround (2), Risk (5)
  - Weighted Score: 4.50 — Below 5.0 threshold — Steering Committee escalation
- CUS-002: Custom credit decisioning dashboard
  - Scoring: Upgrade Compat (7), Business Crit (6), TCO (7), Workaround (3), Risk (6)
  - Weighted Score: 6.20 — Above threshold — Design Authority approved

Handoffs triggered:
- 1 ADR draft: "ADR-003: Build vs Buy for real-time risk-based rate adjustment"
- 1 Integration entry: "External credit bureau API integration for lending decisioning"
- 2 Process redesign notes: "Adopt standard payment authorisation thresholds", "Adopt standard account dormancy rules"

Budget impact:
- 75 days added (40 + 35 from customisations)
- Running total: 135 of 300-day ceiling (45%)

## 10. Related Skills

| Skill | Agent | Relationship |
|---|---|---|
| score-requirements | fit-gap-analyst | Depends on — scoring methodology used during workshops |
| evaluate-customisation-trade-off | fit-gap-analyst | Feeds into — customisation requests from workshops enter trade-off analysis |
| track-customisation-budget | fit-gap-analyst | Feeds into — budget updates after every workshop |
| map-current-state-process | process-analyst | Depends on — as-is processes are a prerequisite input |
| write-adr | design-authority | Feeds into — gaps trigger draft ADRs |
| build-integration-register | integration-architect | Feeds into — integration gaps feed the register |
```

---

## 3. Fit-Gap Workshop Tracker Excel

An Excel workbook with 4 sheets for real-time workshop capture:

### Sheet 1: Requirements (pre-populated before workshop)

| Column | Content |
|---|---|
| A: Req ID | e.g., REQ-001 |
| B: Process Area | e.g., Customer Onboarding |
| C: Description | Requirement text |
| D: Priority | High / Medium / Low |
| E: MoSCoW | Must / Should / Could / Won't |
| F: Pre-Score | Facilitator's preliminary rating |
| G: Pre-Score Notes | Why the facilitator thinks this rating |

### Sheet 2: Workshop Scoring (completed during workshop)

| Column | Content |
|---|---|
| A: Req ID | Linked from Sheet 1 |
| B: Description | Linked from Sheet 1 |
| C: Fit Rating | Full Fit / Partial Fit / No Fit / Not Assessed / Deferred |
| D: Gap Description | Specific description of what is missing (required for Partial/No Fit) |
| E: Resolution Type | Configuration / Extension / Customisation / Process Change / Workaround / Deferred |
| F: Effort (Days) | Pessimistic estimate |
| G: Risk | High / Medium / Low |
| H: Notes | Discussion notes, SME quotes, evidence |
| I: Parking Lot? | Yes/No — if Yes, moved to Sheet 4 |

### Sheet 3: Customisation Scoring (for No Fit items only)

| Column | Content |
|---|---|
| A: CUS ID | Sequential (CUS-001, etc.) |
| B: Req ID | Linked |
| C: Description | Gap description |
| D: Type | Core Logic / UI / Integration / Reporting |
| E: Upgrade Compatibility (30%) | Score 1-10 |
| F: Business Criticality (25%) | Score 1-10 |
| G: TCO (20%) | Score 1-10 |
| H: Workaround Feasibility (15%) | Score 1-10 |
| I: Implementation Risk (10%) | Score 1-10 |
| J: Weighted Score | Formula: =(E*0.3)+(F*0.25)+(G*0.2)+(H*0.15)+(I*0.1) |
| K: Threshold | Formula: =IF(J>=5,"Design Authority","Steering Committee") |
| L: Approver | Name |
| M: Status | Proposed / Under Review / Approved / Rejected |

### Sheet 4: Parking Lot

| Column | Content |
|---|---|
| A: Item # | Sequential |
| B: Req ID | If applicable |
| C: Description | What was parked |
| D: Reason | Why it was parked (time, missing info, out of scope) |
| E: Owner | Who is responsible for resolving |
| F: Deadline | When it must be resolved |
| G: Status | Open / Resolved / Deferred |

---

## 4. File Locations Summary

| File | Path | Purpose |
|---|---|---|
| Skill Playbook Template | `.claude/skills/_skill-playbook-template.md` | Reusable template for all 72 skills |
| Prototype Skill | `.claude/skills/run-fit-gap-workshop.md` | First complete skill playbook |
| Workshop Tracker Excel | `artefacts/03-fit-gap-register/fit-gap-workshop-tracker.xlsx` | Real-time workshop capture tool |
| This Design Spec | `docs/superpowers/specs/2026-04-13-skill-playbook-system-design.md` | Design documentation |

---

## 5. Verification

1. **Template completeness:** All 10 sections present, no placeholders, no TBDs
2. **Prototype skill:** `run-fit-gap-workshop.md` follows the template exactly, all sections populated with real content
3. **Excel template:** 4 sheets with correct columns, formulas in Customisation Scoring sheet work correctly
4. **Cross-references:** All file paths in the skill reference real locations in the repo
5. **Quality checklist:** 10 items, all pass/fail, all measurable
