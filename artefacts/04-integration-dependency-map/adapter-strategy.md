# Adapter Strategy

Temenos fulfilment service model and middleware integration patterns.

## Fulfilment Service Model

| Service | Purpose | Protocol | Notes |
|---|---|---|---|
| | | | |

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
| | | | | |
