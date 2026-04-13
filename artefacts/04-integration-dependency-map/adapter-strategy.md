# Adapter Strategy

Temenos fulfilment service model and middleware integration patterns.

## Fulfilment Service Model

| Service | Purpose | Protocol | Notes |
|---|---|---|---|
| Holdings Service | Account/arrangement queries & maintenance | REST (IRF) | 11,899 APIs -- largest surface |
| Order Service | Transaction initiation & lifecycle | REST (IRF/Publisher) | 3,270+ APIs |
| Party Service | Customer data (CRM, KYC, beneficiaries) | REST (IRF/PSD2) | 1,918 IRF + 2,161 PSD2 |
| Product Service | Product catalog & configuration | REST (IRF) | 974 APIs |
| Reference Service | Static/reference data lookups | REST (IRF/Publisher) | 849+ APIs |
| System Service | Platform admin, config, integration framework | REST (Publisher/PSD2) | 174 IRF + 696 PSD2 |

## Middleware Patterns

### Request-Reply
- Use for synchronous operations (balance enquiry, account lookup)
- Timeout: 5s default
- Circuit breaker: 5 failures in 60s

### Event-Driven
- Use for asynchronous notifications (transaction events, account changes)
- At-least-once delivery
- Idempotency required on consumer side

### Batch
- Use for bulk operations (statement generation, end-of-day)
- SFTP or database staging
- Scheduled windows defined in infrastructure-stack.md

## Adapter Inventory

| Adapter | Source | Target | Pattern | Status |
|---|---|---|---|---|
| Holdings Adapter | Transact (IRF) | Middleware / API Gateway | REST Request-Reply | Baseline |
| Order Adapter | Transact (IRF) | Middleware / API Gateway | REST Request-Reply | Baseline |
| Party Adapter | Transact (IRF + PSD2) | Middleware / API Gateway | REST Request-Reply | Baseline |
| Publisher Adapter | Transact (Publisher) | Event Bus / Downstream | REST Notification | Baseline |
| PSD2 Adapter | Transact (PSD2) | TPP Gateway | REST Request-Reply | Baseline |
