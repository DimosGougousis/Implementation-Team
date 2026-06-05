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
- Send pre-read to attendees **48 hours** before the workshop
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
| **Read** | Facilitator | 1 min | Read the requirement aloud. Confirm with Business SME: "Is this still accurate and in scope?" |
| **Demonstrate** | Platform SME | 3-4 min | Show how the platform handles this. Live demo preferred. If no demo, walk through module documentation. State clearly: "The platform does X. It does NOT do Y." |
| **Score** | Facilitator | 2-3 min | Propose pre-scored rating. Ask: "Platform SME, do you agree?" Then: "Business SME, does this meet your requirement?" |
| **Resolve** | All | 2-4 min | If Full Fit: confirm Configuration, estimate effort, record, move on. If gap: use the resolution decision tree below. |

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
- **Business vs Platform SME disagree on Fit Rating:** Ask the Platform SME to demonstrate the specific capability. If they cannot demonstrate it, it is a gap. Evidence over opinion.
- **Business insists on unsupported feature:** Document as No Fit. The governance scoring (Step 9) is where the trade-off decision happens, not the workshop floor.
- **Dominant voice problem:** Pause and directly ask quiet attendees: "[Name], does this match how your team operates today?"
- **Scope creep:** New requirements go into the Catalogue for the next workshop, not this session.

**Real-time recording:**
- Record every decision in the Fit-Gap Workshop Tracker Excel immediately — not "we'll clean up later"
- For every No Fit: capture the **exact gap** (not vague: "doesn't meet requirement" — specific: "platform supports fixed-rate standing orders but not variable-amount scheduling")
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
- Populate all sections: Requirements Catalogue, Fit-Gap Assessment Matrix, Process Alignment Decisions

**Step 9: Create Customisation Requests**

For every "No Fit" scored as Customisation, create a Governance Log entry:

| Field | How to fill it |
|---|---|
| CUS ID | Sequential: CUS-001, CUS-002, etc. (per programme) |
| Req ID | Link to the originating requirement (e.g., REQ-008) |
| Description | Copy the exact gap description from the workshop — be specific |
| Type | Core Logic / UI / Integration / Reporting |
| Approver | Design Authority for scores >= 5.0; Steering Committee for scores < 5.0 |
| Status | "Proposed" |
| Risk | High / Medium / Low with explanation |

Apply the Weighted Scoring for each customisation:

| # | Criterion | Weight | Question to Ask | 1 = Poor | 10 = Excellent |
|---|---|---|---|---|---|
| 1 | Upgrade Compatibility | 30% | "Will this break on every Temenos upgrade?" | Breaks every time | Uses supported extension points |
| 2 | Business Criticality | 25% | "What happens if we don't do this?" | Nice-to-have | Regulatory, no alternative |
| 3 | TCO | 20% | "What will it cost to maintain per year?" | Specialist skills, constant fixes | Self-contained, standard skills |
| 4 | Workaround Feasibility | 15% | "Is there any other way to achieve this?" | No workaround exists | Good workaround, minimal impact |
| 5 | Implementation Risk | 10% | "How confident are we in the estimate?" | Unknown dependencies, no PoC | Well-understood, PoC validated |

**Calculation:** `Weighted Score = (Score1 x 0.30) + (Score2 x 0.25) + (Score3 x 0.20) + (Score4 x 0.15) + (Score5 x 0.10)`

**Threshold decision:**
- Score >= 5.0: **Design Authority may approve.** Set Approver = Design Authority.
- Score < 5.0: **Steering Committee required.** Prepare 1-page escalation brief:
  - **What:** the requirement and the gap
  - **Why it scored below threshold:** which criteria pulled it down
  - **Options:** (a) approve with conditions, (b) accept the gap, (c) defer to future release
  - **Recommendation:** your recommended option with rationale

**Update the customisation budget:**
- Add effort estimate (days) for each approved customisation to the running total
- 50% of ceiling consumed: flag to programme-governance as "caution"
- 75% of ceiling consumed: escalate to Steering Committee immediately

**Step 10: Trigger downstream handoffs**

| To Agent | When | What to Create | Where |
|---|---|---|---|
| **design-authority** | Gap requires architecture decision (build custom vs integrate third-party vs accept gap) | Draft ADR: Title = "ADR-NNN: [Decision needed for REQ-XXX]", Status = Proposed, Context = gap description + workshop notes, Links = REQ-ID + CUS-ID | `artefacts/01-architecture-decision-records/` |
| **integration-architect** | Partial Fit or Extension requiring system-to-system integration | Integration register entry: Source system, Target system, Integration type (API/Event/File), Priority, linked REQ-ID | `artefacts/04-integration-dependency-map/integration-register.md` |
| **process-analyst** | "Adopt platform standard" or "Process Change" resolution | Note under Gap Notes: REQ-ID, current process, target process, impact (training/operations change needed) | `business-processes/NN-*.md` |
| **programme-governance** | Always (after every workshop) | Update: budget consumed vs ceiling, new CUS-IDs raised, escalations pending | `pipeline/active/[programme]/STAGE-STATUS.md` |

**Step 11: Circulate for review**
- Send completed module assessment to all workshop attendees
- Set **5-working-day** review window
- Track comments, resolve, update register
- Change status: Draft -> In Review -> Approved

## 5. Deliverables

| # | Deliverable | File Path | Format |
|---|---|---|---|
| D1 | Module Assessment | `artefacts/03-fit-gap-register/module-assessments/[module-name].md` | Markdown |
| D2 | Customisation Governance Log entries | `artefacts/03-fit-gap-register/customisation-governance-log.md` | Append new CUS entries |
| D3 | Workshop Notes | `artefacts/03-fit-gap-register/workshop-notes/[YYYY-MM-DD]-[module]-workshop.md` | Markdown |
| D4 | Downstream handoff notes | Various (ADRs, integration register, business processes, STAGE-STATUS) | Updates to existing files |
| D5 | Parking lot items | `artefacts/03-fit-gap-register/workshop-notes/[date]-parking-lot.md` | Action items with owners and deadlines |
| D6 | Completed Workshop Tracker | `artefacts/03-fit-gap-register/fit-gap-workshop-tracker.xlsx` (per-workshop copy) | Excel |

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

| To Agent | Trigger | Artefact Created |
|---|---|---|
| design-authority | Gap requiring architecture decision | Draft ADR (Status: Proposed) |
| integration-architect | Gap requiring system integration | Integration register entry |
| process-analyst | "Adopt platform standard" resolution | Process redesign note in business-processes/ |
| programme-governance | Every workshop (always) | Budget and escalation update in STAGE-STATUS.md |

## 8. Common Pitfalls

| Pitfall | How to Avoid |
|---|---|
| **Scoring without demonstration** | Require live demo or documented proof for every Full Fit. Platform SME saying "yes" is not evidence. |
| **Vague gap descriptions** | Enforce: if you cannot describe the gap in one sentence, you have not understood it. |
| **Customisation bias** | Always walk the decision tree: process change -> extension -> workaround -> customisation (last resort). |
| **Missing effort estimates** | Capture a range in the workshop, even if rough. Pessimistic number goes in the register. |
| **Forgotten handoffs** | Use the handoff checklist (Step 10) as a closing activity — do not leave the room without it. |
| **Scope creep in workshops** | New requirements go into the Catalogue, not the current scoring session. |

## 9. Worked Example

**Module: AA (Retail Lending)**

**Workshop details:**
- Date: 2026-03-15, Duration: 3.5 hours
- Attendees: Fit-Gap Analyst (facilitator), Temenos AA Consultant (Platform SME), Head of Retail Lending (Business SME), Lending Operations Manager (Business SME), BA (scribe)
- Requirements in scope: 18

**Results:**
- 10 Full Fit (Configuration, 45 days total effort)
- 5 Partial Fit (3 Extensions at 60 days, 2 Process Changes)
- 2 No Fit (Customisation candidates)
- 1 Deferred (pending regulatory clarity)

**Customisation Requests:**

| CUS ID | Req ID | Description | Weighted Score | Decision |
|---|---|---|---|---|
| CUS-001 | REQ-008 | Dynamic rate adjustment based on real-time risk events | 4.50 | Below 5.0 — Steering Committee escalation |
| CUS-002 | REQ-010 | Custom credit decisioning dashboard | 6.20 | Above 5.0 — Design Authority approved |

CUS-001 scoring breakdown:
- Upgrade Compatibility (30%): Score 3, Weighted 0.90
- Business Criticality (25%): Score 8, Weighted 2.00
- TCO (20%): Score 4, Weighted 0.80
- Workaround Feasibility (15%): Score 2, Weighted 0.30
- Implementation Risk (10%): Score 5, Weighted 0.50
- **Total: 4.50** — Below threshold, requires Steering Committee

**Handoffs triggered:**
- 1 ADR draft: "ADR-003: Build vs Buy for real-time risk-based rate adjustment"
- 1 Integration entry: "External credit bureau API integration for lending decisioning"
- 2 Process redesign notes: "Adopt standard payment authorisation thresholds", "Adopt standard account dormancy rules"

**Budget impact:**
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
