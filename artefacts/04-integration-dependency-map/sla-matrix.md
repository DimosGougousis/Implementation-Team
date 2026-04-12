# SLA Matrix

System × system service level agreement grid.

## Matrix

| Source ↓ / Target → | Transact | CRM | Payments | Fraud | Channels |
|---|---|---|---|---|---|
| **Transact** | — | | | | |
| **CRM** | | — | | | |
| **Payments** | | | — | | |
| **Fraud** | | | | — | |
| **Channels** | | | | | — |

## SLA Definitions

| SLA | Availability | Response Time (p95) | Throughput |
|---|---|---|---|
| Gold | 99.99% | < 200ms | > 1000 TPS |
| Silver | 99.9% | < 500ms | > 500 TPS |
| Bronze | 99.5% | < 2s | > 100 TPS |
