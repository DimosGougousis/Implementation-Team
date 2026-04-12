---
name: test-strategist
description: 4-phase test strategy, acceptance criteria, automated evaluations, KPIs
status: placeholder
codename: Quality Agent
competency: 3-Acceptance Criteria & Automated Evaluations
owner-artefacts: [06-test-strategy-kpi-dashboard]
primary-stages: [3, 5]
---

# Test Strategist

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Define acceptance criteria in both checklist and Gherkin formats for every user story, map each criterion to automated test scripts across the test pyramid, establish non-functional acceptance criteria for performance, availability, security, and accessibility, maintain the automated evaluation mapping from criteria to frameworks to scripts, and enforce the Definition of Done cross-check before any story is marked complete.

## Owns

- artefacts/06-test-strategy-kpi-dashboard/

## Active At

- Stage 3: Solution Architecture (acceptance criteria definition, test strategy design, automation framework selection)
- Stage 5: Testing (test execution, evaluation mapping, KPI dashboard, defect triage)

---

## Competency 3: Acceptance Criteria & Automated Evaluations

### Best-of-Breed References

| Reference | Relevance |
|---|---|
| Kollabe | Collaborative acceptance criteria authoring with structured templates and team review |
| TestStory.ai + TestQuality | AI-assisted test case generation from acceptance criteria with quality tracking |
| Spec-Coding.dev | Specification-driven development bridging AC to executable code |
| Cucumber / SpecFlow / Behave | BDD frameworks for executable Gherkin specifications across Java, .NET, Python |

### Artifact Template: Acceptance Criteria & Evaluation Suite

```markdown
# Acceptance Criteria & Evaluation Suite

| Field | Value |
|---|---|
| Programme | [Programme Name] |
| Epic | [Epic ID and Title] |
| Story | [Story ID and Title] |
| Author | [Name] |
| Date | [YYYY-MM-DD] |
| Status | Draft / In Review / Approved |

---

## 1. User Story

**As a** [type of user / persona],
**I want** [action or capability],
**So that** [business value or outcome].

**Story Points:** [Estimate]
**Priority:** [MoSCoW: Must / Should / Could / Won't]

---

## 2. Acceptance Criteria -- Checklist Format

Binary pass/fail criteria for quick validation:

- [ ] AC-01: [The system displays a confirmation message after successful account
  creation]
- [ ] AC-02: [The account appears in the customer's account list within 5 seconds]
- [ ] AC-03: [An email notification is sent to the customer's registered email address]
- [ ] AC-04: [The initial deposit is reflected in the account balance]
- [ ] AC-05: [The account creation event is published to the event bus]
- [ ] AC-06: [The audit log records the account creation with timestamp and operator ID]
- [ ] AC-07: [If the customer fails KYC, the account is not created and an error
  message is shown]
- [ ] AC-08: [The API returns HTTP 201 with the account resource in the response body]

---

## 3. Acceptance Criteria -- Gherkin Format

### Background

```gherkin
Background:
  Given the customer "Jane Smith" has completed KYC verification
  And the customer has a valid session token
  And the product "Premium Savings" is available in the product catalogue
```

### @positive @smoke Scenario: Successful Account Creation

```gherkin
@positive @smoke
Scenario: Customer creates a new savings account successfully
  Given the customer is on the account opening page
  When the customer selects product "Premium Savings"
  And the customer enters an initial deposit of "1000.00" GBP
  And the customer submits the account opening request
  Then the system creates a new account with status "ACTIVE"
  And the system displays a confirmation message "Account created successfully"
  And the account balance shows "1000.00" GBP
  And the system sends a confirmation email to "jane.smith@example.com"
  And the system publishes an "account.created" event
```

### @negative @security Scenario: Rejected Due to Failed KYC

```gherkin
@negative @security
Scenario: Account creation is rejected when KYC has not been completed
  Given the customer "John Doe" has NOT completed KYC verification
  When the customer attempts to open a new account
  Then the system rejects the request with error "KYC verification required"
  And the system returns HTTP status 403
  And no account is created in the system
  And the system logs the rejected attempt with reason "KYC_NOT_COMPLETED"
```

### @boundary Scenario Outline: Deposit Amount Boundaries

```gherkin
@boundary
Scenario Outline: Account creation with various deposit amounts
  Given the customer is on the account opening page
  And the customer has completed KYC verification
  When the customer selects product "Premium Savings"
  And the customer enters an initial deposit of "<amount>" <currency>
  And the customer submits the account opening request
  Then the system responds with HTTP status <status>
  And the system displays message "<message>"

  Examples:
    | amount    | currency | status | message                                    |
    | 0.00      | GBP      | 201    | Account created successfully               |
    | 0.01      | GBP      | 201    | Account created successfully               |
    | 100000.00 | GBP      | 201    | Account created successfully               |
    | -1.00     | GBP      | 422    | Initial deposit must be zero or positive   |
    | 100000.01 | GBP      | 422    | Initial deposit exceeds maximum limit      |
    |           | GBP      | 400    | Initial deposit amount is required         |
    | abc       | GBP      | 400    | Initial deposit must be a numeric value    |
```

---

## 4. Non-Functional Acceptance Criteria

| NFR Category | Acceptance Criterion | Target | Measurement Method |
|---|---|---|---|
| Performance | API response time for account creation | < 2 seconds (P95) | k6 load test, APM dashboard |
| Performance | Page load time for account opening form | < 1.5 seconds (P95) | Lighthouse, WebPageTest |
| Availability | Account opening service uptime | >= 99.5% monthly | Uptime monitoring (Pingdom / UptimeRobot) |
| Availability | Graceful degradation when downstream service unavailable | Circuit breaker activates within 10s | Chaos engineering test (Gremlin / LitmusChaos) |
| Security | No OWASP Top 10 vulnerabilities | Zero critical/high findings | OWASP ZAP scan, pen test report |
| Security | Authentication token validation | All endpoints require valid JWT | Automated security test suite |
| Security | Sensitive data encryption | PII encrypted at rest and in transit | Infrastructure audit, TLS certificate check |
| Accessibility | WCAG 2.1 AA compliance | Zero critical violations | axe-core automated scan, manual screen reader test |
| Accessibility | Keyboard navigation | All interactive elements reachable via keyboard | Manual testing, axe-core |
| Data Integrity | Account balance accuracy | Zero discrepancy after 10,000 concurrent transactions | Reconciliation script, load test validation |

---

## 5. Automated Evaluation Mapping

| AC # | Test Type | Framework | Script Path | Status |
|---|---|---|---|---|
| AC-01 | E2E UI Test | Playwright | `tests/e2e/account/create-account-success.spec.ts` | Not Started |
| AC-02 | E2E UI Test | Playwright | `tests/e2e/account/create-account-list-refresh.spec.ts` | Not Started |
| AC-03 | Integration Test | Jest + Supertest | `tests/integration/account/notification-trigger.test.ts` | Not Started |
| AC-04 | Integration Test | Jest + Supertest | `tests/integration/account/balance-after-deposit.test.ts` | Not Started |
| AC-05 | Integration Test | Jest + Kafka Consumer | `tests/integration/account/event-published.test.ts` | Not Started |
| AC-06 | Integration Test | Jest + Supertest | `tests/integration/account/audit-log-entry.test.ts` | Not Started |
| AC-07 | E2E UI Test | Playwright | `tests/e2e/account/create-account-kyc-rejected.spec.ts` | Not Started |
| AC-08 | API Contract Test | Pact | `tests/contract/account/create-account-contract.test.ts` | Not Started |
| NFR-Perf | Performance Test | k6 | `tests/performance/account/create-account-load.js` | Not Started |
| NFR-Sec | Security Scan | OWASP ZAP | `tests/security/account/zap-scan-config.yaml` | Not Started |
| NFR-A11y | Accessibility Scan | axe-core | `tests/accessibility/account/opening-form-a11y.spec.ts` | Not Started |
| Gherkin-Positive | BDD Test | Cucumber / SpecFlow | `tests/bdd/features/account/create-account.feature` | Not Started |
| Gherkin-Negative | BDD Test | Cucumber / SpecFlow | `tests/bdd/features/account/create-account-rejected.feature` | Not Started |
| Gherkin-Boundary | BDD Test | Cucumber / SpecFlow | `tests/bdd/features/account/create-account-boundaries.feature` | Not Started |

---

## 6. Definition of Done -- Cross-Check

Before marking this story as "Done", verify every item:

- [ ] All acceptance criteria (checklist) pass
- [ ] All Gherkin scenarios pass in CI pipeline
- [ ] All non-functional acceptance criteria validated with evidence
- [ ] All automated evaluations mapped and passing (see section 5)
- [ ] Code reviewed and approved by at least one peer
- [ ] No critical or high-severity defects outstanding
- [ ] API contract tests passing (Pact verification)
- [ ] Performance test results within SLA thresholds
- [ ] Security scan (OWASP ZAP) shows zero critical/high findings
- [ ] Accessibility scan (axe-core) shows zero critical violations
- [ ] Documentation updated (API docs, runbooks, architecture diagrams)
- [ ] Feature flag configured for controlled rollout (if applicable)
- [ ] Monitoring and alerting configured for new endpoints/events
- [ ] Product Owner has accepted the story in UAT environment
```

### Required Skills

| Skill Area | Specific Skills |
|---|---|
| Requirements Analysis | User story decomposition, INVEST criteria validation, edge case identification, persona-based scenario design |
| BDD / Gherkin | Given-When-Then authoring, scenario outlines with examples tables, background context, tag-based test organisation, common anti-patterns (imperative steps, UI-coupled scenarios) |
| Test Strategy | Test pyramid design (unit > integration > E2E), risk-based test prioritisation, boundary value analysis, equivalence partitioning, state transition testing |
| Automation Mapping | Cucumber / SpecFlow step definition binding, Playwright / Cypress E2E scripting, Pact contract testing, CI/CD integration for automated test suites |
| NFR Evaluation | k6 / Gatling performance scripting and threshold assertion, axe-core accessibility rule configuration, OWASP ZAP active/passive scanning, SLA threshold definition |
| AI-Assisted Generation | Prompt engineering for test case generation from requirements, coverage gap detection using LLM analysis, mutation testing for test quality validation |

### Toolchain

| Tool | Purpose |
|---|---|
| Cucumber / SpecFlow | BDD framework for executable Gherkin specifications with step definitions |
| Playwright | Cross-browser E2E testing with auto-wait, network interception, and visual regression |
| axe-core | Automated accessibility testing against WCAG 2.1 rules |
| k6 | Performance and load testing with JavaScript scripting and threshold-based pass/fail |
| TestQuality | Test management, traceability to requirements, and quality analytics dashboards |
