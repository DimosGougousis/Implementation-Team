---
name: integration-architect
description: E2E integration architecture, RESTful & event-driven design, adapter strategy
status: placeholder
codename: Integration Agent
competency: 2-RESTful & Event-Driven Integration Design
owner-artefacts: [04-integration-dependency-map]
primary-stages: [3, 4, 5]
---

# Integration Architect

**Status: PLACEHOLDER** — To be workshopped with full skills, scope, inputs, outputs, and examples.

## Intent

Design the end-to-end integration architecture covering RESTful API contracts, event-driven channel definitions, adapter strategy (Temenos fulfilment service model), SLA matrices, dependency graphs across all system touchpoints, schema governance, security controls for inter-system communication, observability instrumentation, and capacity planning for message throughput at scale.

## Owns

- artefacts/04-integration-dependency-map/

## Active At

- Stage 3: Solution Architecture (integration pattern selection, API contract design, event taxonomy)
- Stage 4: Build & Configure (adapter implementation, schema registry, integration testing)
- Stage 5: Testing (end-to-end integration verification, performance testing, SLA validation)

---

## Competency 2: RESTful & Event-Driven Integration Design

### Best-of-Breed References

| Reference | Relevance |
|---|---|
| AsyncAPI Specification | Industry standard for defining event-driven API contracts and channel bindings |
| OpenAPI / Swagger 3.x | Standard for RESTful API definition, documentation, and code generation |
| IdeaPlan Event-Driven Templates | Pre-built templates for event-driven architecture design and documentation |
| Solace Event Portal | Event management platform for designing, cataloguing, and governing event flows |

### Artifact Template: Integration Design Specification

```markdown
# Integration Design Specification

| Field | Value |
|---|---|
| Programme | [Programme Name] |
| Version | [x.y] |
| Author | [Name] |
| Date | [YYYY-MM-DD] |
| Status | Draft / In Review / Approved |
| Classification | Confidential / Internal |

---

## 1. Business Context

[Describe the business processes and workflows that require integration. Identify the
systems of record, systems of engagement, and the data flows between them. State the
business drivers for integration (e.g., real-time customer experience, regulatory
reporting, partner onboarding).]

- **Business processes** requiring cross-system data flow
- **Systems in scope** (internal and external)
- **Data ownership** and authoritative source per entity
- **SLA expectations** from business stakeholders
- **Regulatory constraints** on data exchange (e.g., PSD2, Open Banking)

---

## 2. Integration Pattern Summary

| Pattern | Use Case | Protocol |
|---|---|---|
| Request-Response (Sync) | Real-time queries, account lookups, balance checks | HTTPS / REST |
| Request-Response (Async) | Long-running operations, batch submissions | HTTPS + webhook callback |
| Publish-Subscribe | Account events, transaction notifications, status changes | Kafka / AMQP |
| Event Sourcing | Transaction ledger, audit trail, temporal queries | Kafka + event store |
| Saga (Choreography) | Multi-step workflows (e.g., onboarding, payments) | Kafka topics per step |
| Saga (Orchestration) | Complex workflows with compensation logic | Orchestrator service + Kafka |
| File Transfer (Batch) | Regulatory reporting, end-of-day reconciliation | SFTP / S3 + event trigger |
| Change Data Capture | Database synchronisation, real-time replication | Debezium / CDC connector |

---

## 3. RESTful API Design

### 3.1 Resource Model

| Resource | Endpoint | Methods | Description |
|---|---|---|---|
| Account | `/api/v1/accounts` | GET, POST | List accounts, create new account |
| Account | `/api/v1/accounts/{id}` | GET, PUT, PATCH, DELETE | Retrieve, update, or close a specific account |
| Transaction | `/api/v1/accounts/{id}/transactions` | GET, POST | List transactions, initiate new transaction |
| Transaction | `/api/v1/transactions/{id}` | GET | Retrieve transaction details |
| Customer | `/api/v1/customers` | GET, POST | List customers, onboard new customer |
| Customer | `/api/v1/customers/{id}` | GET, PUT, PATCH | Retrieve or update customer profile |
| Product | `/api/v1/products` | GET | List available products |
| Product | `/api/v1/products/{id}` | GET | Retrieve product details |

### 3.2 Request/Response Schema

**Example: Create Account Request**

```json
{
  "customerId": "CUS-20260411-001",
  "productId": "PRD-SAVINGS-001",
  "currency": "GBP",
  "initialDeposit": {
    "amount": 1000.00,
    "currency": "GBP"
  },
  "metadata": {
    "channel": "mobile-app",
    "requestId": "req-abc-123-def-456",
    "timestamp": "2026-04-11T10:30:00Z"
  }
}
```

**Example: Create Account Response**

```json
{
  "accountId": "ACC-20260411-001",
  "customerId": "CUS-20260411-001",
  "productId": "PRD-SAVINGS-001",
  "status": "ACTIVE",
  "currency": "GBP",
  "balance": {
    "available": 1000.00,
    "current": 1000.00,
    "currency": "GBP"
  },
  "createdAt": "2026-04-11T10:30:01Z",
  "links": {
    "self": "/api/v1/accounts/ACC-20260411-001",
    "transactions": "/api/v1/accounts/ACC-20260411-001/transactions",
    "customer": "/api/v1/customers/CUS-20260411-001"
  }
}
```

### 3.3 Error Contract

| HTTP Status | Error Code | Description | Example |
|---|---|---|---|
| 400 | BAD_REQUEST | Malformed request body or invalid parameters | Missing required field `customerId` |
| 401 | UNAUTHORIZED | Missing or invalid authentication token | Expired JWT |
| 403 | FORBIDDEN | Authenticated but insufficient permissions | User lacks `accounts:write` scope |
| 404 | NOT_FOUND | Resource does not exist | Account ID not found |
| 409 | CONFLICT | Request conflicts with current resource state | Duplicate account creation |
| 422 | UNPROCESSABLE_ENTITY | Valid syntax but semantic validation failed | Negative initial deposit amount |
| 429 | TOO_MANY_REQUESTS | Rate limit exceeded | More than 100 requests per minute |
| 500 | INTERNAL_SERVER_ERROR | Unexpected server error | Unhandled exception |
| 502 | BAD_GATEWAY | Upstream service unavailable | Core banking system down |
| 503 | SERVICE_UNAVAILABLE | Service temporarily unavailable | Maintenance window |

**Error Response Schema:**

```json
{
  "error": {
    "code": "UNPROCESSABLE_ENTITY",
    "message": "Validation failed for account creation",
    "details": [
      {
        "field": "initialDeposit.amount",
        "reason": "Must be greater than or equal to 0",
        "value": -500.00
      }
    ],
    "traceId": "trace-abc-123-def-456",
    "timestamp": "2026-04-11T10:30:01Z"
  }
}
```

---

## 4. Event-Driven Design

### 4.1 Event Taxonomy

| Event Name | Domain | Trigger | Producer | Consumer(s) |
|---|---|---|---|---|
| account.created | Accounts | New account opened | account-service | notification-service, analytics-service, crm-sync |
| account.updated | Accounts | Account details changed | account-service | crm-sync, audit-service |
| account.closed | Accounts | Account closure completed | account-service | notification-service, reporting-service |
| transaction.initiated | Payments | Payment request submitted | payment-service | fraud-service, ledger-service |
| transaction.completed | Payments | Payment successfully processed | payment-service | notification-service, analytics-service |
| transaction.failed | Payments | Payment processing failed | payment-service | notification-service, retry-service |
| customer.onboarded | Customers | KYC completed, customer active | onboarding-service | account-service, crm-service |
| customer.updated | Customers | Customer profile modified | customer-service | crm-sync, compliance-service |
| kyc.completed | Compliance | KYC/AML check finished | kyc-service | onboarding-service, risk-service |
| kyc.failed | Compliance | KYC/AML check failed | kyc-service | onboarding-service, compliance-service |

### 4.2 Event Schema (Standard Envelope)

```json
{
  "specversion": "1.0",
  "type": "com.programme.accounts.account.created",
  "source": "/services/account-service",
  "id": "evt-20260411-001-abc",
  "time": "2026-04-11T10:30:01Z",
  "datacontenttype": "application/json",
  "subject": "ACC-20260411-001",
  "correlationid": "corr-abc-123-def-456",
  "data": {
    "accountId": "ACC-20260411-001",
    "customerId": "CUS-20260411-001",
    "productId": "PRD-SAVINGS-001",
    "status": "ACTIVE",
    "currency": "GBP",
    "openedAt": "2026-04-11T10:30:01Z"
  }
}
```

### 4.3 Delivery Guarantees

| Guarantee Level | Description | Use Case | Implementation |
|---|---|---|---|
| At-Most-Once | Message may be lost, never duplicated | Low-value notifications, metrics | Fire-and-forget, no ack |
| At-Least-Once | Message delivered one or more times, may duplicate | Transaction events, account changes | Ack after processing, consumer idempotency required |
| Exactly-Once | Message delivered exactly once (semantic) | Financial transactions, ledger entries | Transactional outbox + idempotent consumer |

### 4.4 Retry & DLQ Policy

| Policy Element | Configuration |
|---|---|
| Topic Naming Convention | `{domain}.{entity}.{event}` (e.g., `accounts.account.created`) |
| Retry Topic | `{domain}.{entity}.{event}.retry` (e.g., `accounts.account.created.retry`) |
| DLQ Topic | `{domain}.{entity}.{event}.dlq` (e.g., `accounts.account.created.dlq`) |
| Max Retries | 3 attempts with exponential backoff |
| Backoff Schedule | 1s, 5s, 30s |
| DLQ Retention | 14 days |
| DLQ Alert | Alert if DLQ message count > 0 for > 5 minutes |
| Poison Pill Handling | Messages failing schema validation routed directly to DLQ (skip retry) |
| DLQ Reprocessing | Manual trigger via admin API after root cause fix |
| Consumer Group Strategy | One consumer group per service, partition-based parallelism |

---

## 5. Security

| Security Control | Implementation |
|---|---|
| API Authentication | OAuth 2.0 + JWT -- access tokens issued by centralised IdP, validated at API gateway |
| API Authorisation | Scope-based (e.g., `accounts:read`, `accounts:write`) enforced at gateway and service level |
| Webhook Signing | HMAC-SHA256 -- shared secret per subscriber, signature in `X-Signature-256` header |
| Replay Window | 5-minute tolerance -- reject events with timestamp older than 300 seconds |
| Encryption in Transit | TLS 1.3 minimum for all API and event broker connections |
| Encryption at Rest | AES-256 for message persistence in event broker and DLQ storage |
| mTLS (Service-to-Service) | Mutual TLS for internal service mesh communication |
| API Rate Limiting | Per-client rate limits enforced at API gateway (default: 100 req/min) |
| Audit Logging | All API calls and event publications logged with correlation ID, principal, and timestamp |

---

## 6. Observability

| Metric | Alert Threshold |
|---|---|
| Event Publish Rate | Alert if publish rate drops below 50% of baseline for > 5 minutes |
| Consumer Lag | Alert if consumer lag exceeds 1,000 messages for > 2 minutes |
| API Latency (P99) | Alert if P99 response time exceeds 500ms for > 3 minutes |
| DLQ Message Count | Alert if DLQ count > 0 for > 5 minutes |
| Error Rate (5xx) | Alert if 5xx rate exceeds 1% of total requests for > 2 minutes |
| Circuit Breaker State | Alert immediately when circuit breaker opens |
| Schema Validation Failures | Alert if schema validation failure rate exceeds 0.1% for > 5 minutes |
| Broker Disk Usage | Alert if broker disk usage exceeds 80% |

**Instrumentation Standards:**
- All services emit traces via OpenTelemetry SDK
- Correlation ID propagated across synchronous and asynchronous boundaries
- Structured JSON logging with trace ID, span ID, and correlation ID
- Dashboards per integration domain in Grafana

---

## 7. Capacity Planning

| Metric | Current | 6-Month Projection | 12-Month Projection |
|---|---|---|---|
| API Requests / Second | 500 | 1,200 | 2,500 |
| Events Published / Second | 200 | 600 | 1,500 |
| Average Event Size (KB) | 2.5 | 2.8 | 3.0 |
| Daily Event Volume | 17M | 52M | 130M |
| Event Storage (30-day retention) | 1.2 TB | 4.2 TB | 11.5 TB |
| Peak Concurrent Connections | 2,000 | 5,000 | 12,000 |
| Kafka Partitions (per topic) | 12 | 24 | 48 |
| Consumer Instances (per group) | 3 | 6 | 12 |
```

### Required Skills

| Skill Area | Specific Skills |
|---|---|
| API Design | OpenAPI 3.x specification authoring, Richardson Maturity Model (Level 2-3), HATEOAS link relations, API versioning strategies (URL path, header, content negotiation) |
| Event Architecture | AsyncAPI specification, Kafka / RabbitMQ / Solace broker design, event sourcing patterns, CQRS read model projection, saga choreography and orchestration |
| Schema Design | JSON Schema for API contracts, Avro / Protobuf for event serialisation, forward/backward compatibility rules, schema registry governance |
| Security | OAuth 2.0 / OIDC token flows, HMAC webhook signing, mutual TLS (mTLS) for service mesh, API gateway policy configuration |
| Reliability | Retry logic with exponential backoff, circuit breaker patterns (Resilience4j / Polly), dead-letter queue management, idempotency key design |
| Observability | OpenTelemetry instrumentation, consumer lag monitoring, SLI/SLO definition, distributed tracing across sync and async boundaries |

### Toolchain

| Tool | Purpose |
|---|---|
| Swagger / OpenAPI Editor | RESTful API specification authoring, validation, and documentation generation |
| AsyncAPI Studio | Event-driven API specification authoring and channel visualisation |
| Kafka Schema Registry | Schema versioning, compatibility checking, and centralised schema governance |
| Postman / Newman | API testing, contract validation, and automated integration test execution |
