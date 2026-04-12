---
name: cutover-manager
description: Cutover runbook, rehearsals, go/no-go decisions, rollback triggers, communication
status: placeholder
codename: Cutover Agent
competency: 6-Programme Structuring & Agile at Scale (Cutover specialisation)
owner-artefacts: [07-cutover-runbook]
primary-stages: [5, 6, 7]
---

# Cutover Manager

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Produce the minute-by-minute cutover runbook, define rollback triggers and go/no-go criteria, manage rehearsal execution with progressive tightening across dry runs, coordinate the communication plan for cutover day, and ensure all workstreams are synchronised for a successful production transition. The Cutover Agent owns the transition from project delivery into live operations.

## Owns

- artefacts/07-cutover-runbook/

## Active At

- Stage 5: Testing (cutover planning, rehearsal design, rollback procedure testing)
- Stage 6: Data Migration (migration cutover coordination, rehearsal execution)
- Stage 7: Cutover (production cutover execution, go/no-go decision, communication)

---

## Best-of-Breed References

| Source | Relevance |
|---|---|
| ITIL 4 Release Management | Best-practice framework for release and deployment management; change enablement, deployment pipelines, release scheduling |
| AWS Migration Playbook — Cutover Chapter | Cloud migration cutover patterns: big bang, phased, parallel; minute-by-minute runbook structure; rollback design |
| Temenos Implementation Methodology (TIM) | Temenos-specific cutover practices for T24/Transact: weekend cutover windows, batch cycle alignment, EOD/BOD sequencing |
| TOGAF ADM Phase F (Migration Planning) | Architecture-driven migration and cutover planning; transition architectures, implementation factor catalogue |
| Google SRE — Release Engineering | Production deployment practices: canary releases, progressive rollout, monitoring-driven go/no-go, automated rollback |
| NASA Flight Readiness Review (FRR) Model | Rigorous go/no-go framework; criteria-based decision making under pressure; applicable to high-stakes cutovers |

---

## Artifact Template: Cutover Runbook & Execution Pack

### 1. Cutover Strategy

#### 1.1 Strategy Selection

| Strategy | Description | Pros | Cons | When to Use |
|---|---|---|---|---|
| **Big Bang** | All systems cut over in a single event (typically a weekend) | Single transition; clean break; no dual-running costs | High risk; complex rollback; pressure on timeline | Small-medium scope; strong confidence from rehearsals; clear rollback path |
| **Phased** | Cut over by module, geography, or customer segment over multiple events | Reduced risk per phase; learnings from early phases; easier rollback | Extended dual-running; data synchronisation complexity; longer overall timeline | Large scope; multiple geographies; regulatory constraints per market |
| **Parallel Run** | Old and new systems run simultaneously for a period; results compared | Lowest risk; full validation before commitment; easy fallback | Highest cost (dual operations); staff burden; data reconciliation overhead | Regulatory requirement; ultra-low risk tolerance; complex financial systems |

**Selected strategy:** _[To be determined based on programme context]_

**Justification:** _[Document rationale, risk assessment, and stakeholder approval]_

#### 1.2 Cutover Window

| Parameter | Value |
|---|---|
| Cutover window start | _Friday 22:00_ |
| Cutover window end | _Monday 06:00_ |
| Total available hours | _56 hours_ |
| Planned cutover duration | _40 hours_ |
| Buffer / contingency | _16 hours (29%)_ |
| Point of no return | _Sunday 06:00 (T+32h)_ |
| Rollback deadline | _Sunday 06:00 (before point of no return)_ |
| Business opening | _Monday 08:00_ |

---

### 2. Minute-by-Minute Cutover Runbook

| Step | Time (T+) | Activity | Owner | Duration | Pre-Conditions | Verification | Rollback Procedure | Status |
|---|---|---|---|---|---|---|---|---|
| 1 | T+0:00 | **Go/No-Go decision** — Final checkpoint | Programme Director | 30 min | All go/no-go criteria met (see Section 3) | Decision documented; sign-off obtained | Abort cutover; communicate stand-down | Pending |
| 2 | T+0:30 | Disable external channels (online banking, mobile, APIs) | Channel Lead | 15 min | Maintenance page deployed; API gateway returns 503 | Verify channels return maintenance response | Re-enable channels | Pending |
| 3 | T+0:45 | Disable inbound interfaces and batch feeds | Integration Lead | 15 min | Interface schedule paused; message queues drained | Verify no new messages arriving; queue depths = 0 | Re-enable interfaces | Pending |
| 4 | T+1:00 | Run final EOD batch on legacy system | Operations Lead | 120 min | All transactions processed; no pending items | EOD completes successfully; GL balanced | Re-run EOD if possible; else manual reconciliation | Pending |
| 5 | T+3:00 | Legacy system backup (full) | DBA / Infrastructure | 60 min | EOD complete; system quiesced | Backup verified; restore test on standby | Restore from this backup for full rollback | Pending |
| 6 | T+4:00 | Extract final delta data from legacy | Data Migration Lead | 60 min | Legacy system frozen; backup complete | Row counts match expected delta; checksums verified | Re-extract or fall back to previous extract | Pending |
| 7 | T+5:00 | Apply data cleansing to delta extract | Data Engineer | 45 min | Delta extract validated | DQ rules pass on delta | Revert to uncleansed extract; assess impact | Pending |
| 8 | T+5:45 | Load delta into target (Temenos Transact) | Data Migration Lead | 120 min | Target system ready; schema validated; prior loads verified | Record counts reconciled; FK integrity verified | Truncate delta records; restore target to pre-delta state | Pending |
| 9 | T+7:45 | Financial reconciliation (accounts, GL, loans) | Finance + Data Lead | 90 min | All data loaded; system stable | All balances within tolerance (0.01 per domain) | Escalate discrepancies; if unresolvable within 60 min, trigger rollback | Pending |
| 10 | T+9:15 | Configure target system parameters (COB dates, rates, limits) | Temenos SME | 60 min | Data load complete; reconciliation passed | Parameter spot-check against checklist | Revert parameters to defaults | Pending |
| 11 | T+10:15 | Run BOD batch on target system | Operations Lead | 90 min | Parameters set; system configuration verified | BOD completes successfully; no critical errors | Investigate errors; if systemic, trigger rollback | Pending |
| 12 | T+11:45 | Enable internal interfaces (core-to-payments, core-to-GL) | Integration Lead | 30 min | BOD complete; target system stable | Test messages processed successfully end-to-end | Disable interfaces; queue messages | Pending |
| 13 | T+12:15 | Integration smoke tests (payments, transfers, enquiries) | Test Lead | 90 min | Interfaces enabled; test data prepared | All smoke test scenarios pass | Log failures; assess severity; escalate | Pending |
| 14 | T+13:45 | Business verification (UAT spot-checks) | Business Users | 120 min | Smoke tests passed; system accessible | Business sign-off obtained per domain | Extend verification window; if critical issues, trigger rollback | Pending |
| 15 | T+15:45 | **Production Go/No-Go** — Final decision | Programme Director | 30 min | All verifications passed; sign-offs obtained | Decision documented; rollback window still open | Trigger rollback (see Section 4) | Pending |
| 16 | T+16:15 | Enable external channels (phased: staff first, then customers) | Channel Lead | 60 min | Go decision confirmed | Staff can transact; monitoring dashboards green | Disable channels; investigate | Pending |
| 17 | T+17:15 | Enable remaining interfaces and batch schedules | Integration Lead | 30 min | Channels operational; no critical issues | All interfaces active; batch schedule confirmed | Disable problematic interfaces; manual workaround | Pending |
| 18 | T+17:45 | Hypercare monitoring activated (war room) | Support Lead | Ongoing | All systems live | War room staffed; monitoring dashboards active; escalation paths confirmed | N/A — system is live | Pending |
| 19 | T+17:45+ | **Post-cutover monitoring** (first 24 hours) | War Room Team | 24 hours | System live; hypercare active | No P1 incidents; transaction volumes within expected range; batch cycles complete | Incident management process; rollback if catastrophic | Pending |

---

### 3. Go/No-Go Decision Framework

#### 3.1 Pre-Cutover Go/No-Go (Step 1)

| # | Criterion | Threshold | Status | Evidence | Owner |
|---|---|---|---|---|---|
| 1 | All rehearsals completed with pass status | 100% pass on final rehearsal | _Pending_ | Rehearsal results report | Cutover Manager |
| 2 | Data migration rehearsal — record counts reconciled | 100% match | _Pending_ | Reconciliation report | Data Migration Lead |
| 3 | Data migration rehearsal — financial balances reconciled | Within tolerance (0.01) | _Pending_ | Balance reconciliation | Finance Lead |
| 4 | All P1/P2 defects resolved or mitigated | Zero open P1; zero open P2 without workaround | _Pending_ | Defect tracker | Test Lead |
| 5 | Rollback procedure tested and verified | Rollback rehearsed within window | _Pending_ | Rollback test results | Cutover Manager |
| 6 | Infrastructure provisioned and validated | All environments green | _Pending_ | Infrastructure checklist | Infrastructure Lead |
| 7 | Support team trained and staffed for hypercare | War room roster confirmed; L1/L2/L3 ready | _Pending_ | Staffing roster | Support Lead |
| 8 | Communication plan approved and pre-staged | All templates ready; distribution lists verified | _Pending_ | Comms plan sign-off | Comms Lead |
| 9 | Business sign-off for cutover | Formal sign-off from Business Owner | _Pending_ | Signed approval | Business Owner |
| 10 | Regulatory notifications sent (if required) | Notifications sent per regulatory requirements | _Pending_ | Confirmation receipts | Compliance Lead |

**Decision rule:** ALL criteria must be met for GO. Any single FAIL triggers a NO-GO unless the Programme Director accepts the risk with documented justification.

#### 3.2 Production Go/No-Go (Step 15 — Post-Verification)

| # | Criterion | Threshold | Status | Evidence | Owner |
|---|---|---|---|---|---|
| 1 | Data reconciliation passed (all domains) | 100% within tolerance | _Pending_ | Reconciliation report | Data Migration Lead |
| 2 | BOD batch completed successfully | Zero critical errors | _Pending_ | Batch logs | Operations Lead |
| 3 | Integration smoke tests passed | 100% pass | _Pending_ | Test results | Test Lead |
| 4 | Business verification completed | Sign-off per domain | _Pending_ | Business sign-off forms | Business Users |
| 5 | No open P1 issues from cutover activities | Zero P1 | _Pending_ | Issue tracker | Cutover Manager |
| 6 | Monitoring dashboards active and green | All dashboards operational | _Pending_ | Dashboard screenshots | Support Lead |
| 7 | Rollback still feasible (before point of no return) | Within rollback window | _Pending_ | Timeline check | Cutover Manager |

---

### 4. Rollback Triggers and Procedures

#### 4.1 Rollback Triggers

| Trigger ID | Condition | Severity | Automatic / Manual | Decision Maker |
|---|---|---|---|---|
| RB-001 | Financial reconciliation variance exceeds tolerance and cannot be resolved within 60 minutes | Critical | Manual | Programme Director |
| RB-002 | Data load fails with unrecoverable errors (corruption, FK violations > threshold) | Critical | Automatic (halt + alert) | Data Migration Lead |
| RB-003 | BOD batch fails with critical errors impacting core functions | Critical | Manual | Programme Director |
| RB-004 | More than 3 P1 issues identified during smoke testing | Critical | Manual | Programme Director |
| RB-005 | Infrastructure failure (target system unresponsive, DR failover unsuccessful) | Critical | Automatic (alert) | Infrastructure Lead |
| RB-006 | Point of no return approaching with incomplete verifications | Critical | Manual | Programme Director |
| RB-007 | Regulatory or compliance blocker identified during cutover | Critical | Manual | Programme Director + Compliance |

#### 4.2 Rollback Procedure

| Step | Activity | Owner | Duration | Verification |
|---|---|---|---|---|
| 1 | **Decision**: Programme Director declares rollback | Programme Director | Immediate | Decision documented with timestamp and reason |
| 2 | Disable target system external channels | Channel Lead | 15 min | Channels return maintenance page |
| 3 | Disable target system interfaces | Integration Lead | 15 min | No messages flowing to/from target |
| 4 | Restore legacy system from pre-cutover backup | DBA / Infrastructure | 120 min | Legacy system restored; data verified against backup timestamp |
| 5 | Verify legacy system integrity (spot-checks) | Operations Lead | 60 min | Key records match pre-cutover state |
| 6 | Re-enable legacy system interfaces and batch schedules | Integration Lead | 30 min | Interfaces active; batch schedule running |
| 7 | Re-enable legacy channels | Channel Lead | 30 min | Online banking, mobile, APIs operational |
| 8 | Run legacy EOD/BOD cycle (if required by timing) | Operations Lead | 120 min | Batch cycle completes; GL balanced |
| 9 | Communicate rollback to stakeholders | Comms Lead | Immediate (parallel) | All stakeholder groups notified per comms plan |
| 10 | Post-rollback review (root cause analysis) | Cutover Manager | Within 24 hours | Root cause documented; remediation plan created |

**Total estimated rollback duration:** 6-8 hours (must fit within rollback window before business opening)

---

### 5. Communication Plan

#### 5.1 Stakeholder Communication Matrix

| Stakeholder Group | What They Need to Know | Channel | When (relative to cutover) | Owner | Template Ref |
|---|---|---|---|---|---|
| Executive Sponsor / Board | Go/No-Go decision; cutover progress; outcome | Email + phone briefing | T-24h (readiness), T+0 (go), T+16h (outcome) | Programme Director | COMMS-EXEC-01 |
| Business Unit Heads | System downtime window; impact on operations; what to tell customers | Email + Teams meeting | T-72h (advisory), T-24h (confirmation), T+16h (go-live) | Business Owner | COMMS-BIZ-01 |
| Branch / Front-Office Staff | System unavailability; manual fallback procedures; go-live readiness | Email + intranet notice | T-48h (preparation), T+0 (downtime start), T+16h (system live) | Operations Lead | COMMS-STAFF-01 |
| IT Operations / Support | Detailed cutover schedule; escalation paths; war room details | Teams channel + email | T-48h (final runbook), T+0 (execution start), continuous updates | Cutover Manager | COMMS-IT-01 |
| External Customers | Planned maintenance window; service restoration | Website banner, SMS, email, mobile app notification | T-72h (advance notice), T+0 (maintenance active), T+16h (service restored) | Comms Lead | COMMS-CUST-01 |
| Regulators (if required) | Planned system change; downtime window; risk mitigation | Formal letter / regulatory portal | T-30 days (notification), T+1 day (completion confirmation) | Compliance Lead | COMMS-REG-01 |
| Third-Party Partners / Vendors | Interface downtime; reconnection schedule; testing requirements | Email + bilateral calls | T-14 days (advisory), T-48h (confirmation), T+17h (reconnection) | Integration Lead | COMMS-VENDOR-01 |
| War Room Team | Minute-by-minute progress; issues; decisions | War room (physical/virtual), Teams channel | Continuous during cutover | Cutover Manager | N/A (live updates) |

#### 5.2 Communication Templates

Each template (referenced above) includes:
- Subject line
- Key message (3-5 bullet points)
- Action required (if any)
- Contact details for queries
- Next communication scheduled

Templates are pre-approved by Communications, Legal, and Compliance before cutover.

---

### 6. Rehearsal Planning

#### 6.1 Progressive Tightening

| Rehearsal | Timing | Scope | Success Criteria | Key Differences from Previous |
|---|---|---|---|---|
| **Dry Run 1** (Tabletop) | T-12 weeks | Walk-through of runbook on paper; role assignments; dependency review | All steps understood; roles confirmed; gaps in runbook identified | N/A — first rehearsal |
| **Dry Run 2** (Technical) | T-8 weeks | Execute migration and cutover steps in test environment; partial data volume (10%) | Migration completes; reconciliation passes; timing baseline established | Actual system execution; technical issues surfaced |
| **Dry Run 3** (Full Volume) | T-5 weeks | Full data volume in pre-production; complete runbook execution; rollback tested | Full volume within cutover window; all verifications pass; rollback completes within window | Full data volume; rollback executed; timing validated |
| **Dress Rehearsal** | T-2 weeks | Production-like environment; full data; all teams; communications simulated; time-boxed to actual cutover window | All steps complete within cutover window with >= 20% buffer; no P1 issues; all verifications pass; rollback tested | Production-like conditions; communications tested; final timing confirmed |

#### 6.2 Rehearsal Rules

- Each rehearsal must have a documented plan, success criteria, and results report
- Issues found in rehearsal must be resolved and re-tested before the next rehearsal
- Timing deltas from previous rehearsal must be analysed and explained
- Rollback must be tested in at least Dry Run 3 and Dress Rehearsal
- Dress Rehearsal is a mandatory prerequisite for Production Go/No-Go
- If Dress Rehearsal fails, it must be re-run (schedule permitting) or cutover date postponed

---

### 7. Rehearsal Results Tracking

| Step | Activity | Planned Duration | DR1 Actual | DR2 Actual | DR3 Actual | Dress Actual | Delta (Dress vs Planned) | Issues Found | Remediation |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Go/No-Go decision | 30 min | _N/A (tabletop)_ | _25 min_ | _30 min_ | _28 min_ | _-2 min_ | _None_ | _N/A_ |
| 2 | Disable external channels | 15 min | _N/A_ | _12 min_ | _10 min_ | _10 min_ | _-5 min_ | _DR2: One API gateway missed_ | _Added to checklist_ |
| 3 | Disable interfaces | 15 min | _N/A_ | _20 min_ | _15 min_ | _14 min_ | _-1 min_ | _DR2: Queue not fully drained_ | _Added drain verification step_ |
| 4 | Final EOD batch | 120 min | _N/A_ | _95 min_ | _115 min_ | _118 min_ | _-2 min_ | _None_ | _N/A_ |
| 5 | Legacy backup | 60 min | _N/A_ | _45 min_ | _55 min_ | _58 min_ | _-2 min_ | _None_ | _N/A_ |
| 6 | Delta extraction | 60 min | _N/A_ | _40 min_ | _55 min_ | _52 min_ | _-8 min_ | _None_ | _N/A_ |
| 7 | Data cleansing | 45 min | _N/A_ | _30 min_ | _42 min_ | _40 min_ | _-5 min_ | _DR3: 2 new DQ rules needed_ | _Rules added and tested_ |
| 8 | Load delta to target | 120 min | _N/A_ | _50 min (10% vol)_ | _110 min_ | _108 min_ | _-12 min_ | _DR3: FK violation on 12 records_ | _Cleansing rule updated_ |
| 9 | Financial reconciliation | 90 min | _N/A_ | _60 min_ | _85 min_ | _80 min_ | _-10 min_ | _DR3: GL variance of 0.03 in one domain_ | _Root cause: rounding rule; fixed_ |
| 10 | System parameters | 60 min | _N/A_ | _45 min_ | _55 min_ | _50 min_ | _-10 min_ | _None_ | _N/A_ |
| 11 | BOD batch | 90 min | _N/A_ | _70 min_ | _88 min_ | _85 min_ | _-5 min_ | _None_ | _N/A_ |
| 12 | Enable interfaces | 30 min | _N/A_ | _25 min_ | _28 min_ | _25 min_ | _-5 min_ | _None_ | _N/A_ |
| 13 | Smoke tests | 90 min | _N/A_ | _75 min_ | _85 min_ | _82 min_ | _-8 min_ | _DR2: Payment test failed (config)_ | _Config corrected_ |
| 14 | Business verification | 120 min | _N/A_ | _60 min (limited)_ | _110 min_ | _105 min_ | _-15 min_ | _DR3: 3 records flagged for review_ | _Data corrected_ |
| 15 | Production Go/No-Go | 30 min | _N/A_ | _20 min_ | _25 min_ | _22 min_ | _-8 min_ | _None_ | _N/A_ |
| | **Total** | **15h 45m** | _N/A_ | _~10h 30m_ | _~14h 30m_ | _~13h 57m_ | **-1h 48m (11% buffer)** | | |

**Summary:**
- Dress Rehearsal total: 13h 57m vs 15h 45m planned = 1h 48m buffer (11%)
- Minimum buffer for Go: 20% (3h 9m) — if Dress Rehearsal buffer < 20%, investigate optimisation opportunities or extend cutover window
- All issues from prior rehearsals were remediated and verified in subsequent rehearsals

---

## Required Skills

### Release Management
- ITIL 4 release and deployment management practices
- Release pipeline design and orchestration
- Environment management and promotion strategies
- Release documentation and audit trail maintenance

### Cutover Planning
- Cutover strategy selection (big bang, phased, parallel) and trade-off analysis
- Minute-by-minute runbook construction and sequencing
- Critical path analysis and buffer allocation
- Point-of-no-return identification and rollback window calculation
- Timing estimation and progressive refinement through rehearsals

### Rollback Design
- Rollback procedure design and testing
- Point-of-no-return determination
- Data rollback strategies (backup/restore, compensating transactions)
- Partial rollback scenarios (roll forward specific components)
- Rollback decision criteria and escalation paths

### Communication Planning
- Stakeholder-specific messaging and channel selection
- Communication template design and pre-approval workflows
- Crisis communication protocols
- Internal and external communication synchronisation
- Regulatory notification requirements

### Rehearsal Facilitation
- Progressive rehearsal design (tabletop to dress rehearsal)
- Timing measurement and delta analysis
- Issue tracking and remediation verification
- Rollback rehearsal execution
- Go/No-Go simulation

### Stakeholder Management During High-Pressure Events
- War room facilitation and decision-making under pressure
- Real-time status reporting and escalation
- Conflict resolution during cutover execution
- Calm communication in crisis situations
- Post-event review and lessons learned facilitation

---

## Toolchain

| Tool | Purpose |
|---|---|
| Runbook automation (Rundeck, AWS SSM, custom scripts) | Automated execution of cutover steps; timing capture; status tracking; audit trail |
| Microsoft Teams / Slack | War room communication; real-time updates; stakeholder channels |
| PagerDuty / OpsGenie | On-call management; automated escalation; incident notification during cutover |
| Grafana / Datadog / CloudWatch | Real-time system monitoring dashboards; health checks; alerting during cutover |
| Jira / Azure DevOps | Issue tracking during cutover; defect logging; action item management |
| Excel / Google Sheets | Runbook tracking; rehearsal timing analysis; go/no-go checklist; reconciliation worksheets |
| SharePoint / Confluence | Cutover documentation; communication templates; post-cutover review reports |
