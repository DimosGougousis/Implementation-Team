# Integration Register

All system-to-system touchpoints in the programme.

## Transact API Integration Baseline

Temenos R25AMR exposes 26,689 active REST APIs across three integration surfaces:

| Surface | Active APIs | Primary Pattern | Typical Consumers |
|---|---|---|---|
| IRF (Internal) | 19,255 | Request-Reply (REST) | Back-office, middleware, batch |
| Publisher | 4,381 | Event/Notification (REST) | Downstream systems, reporting |
| PSD2 | 3,053 | Request-Reply (REST) | Third-party providers, open banking |

### Method Distribution

| Method | IRF | Publisher | PSD2 | Total |
|---|---|---|---|---|
| GET | 8,866 | 2,090 | 1,542 | 12,498 |
| POST | 5,054 | 1,190 | 602 | 6,846 |
| PUT | 4,822 | 988 | 766 | 6,576 |
| DELETE | 511 | 184 | 150 | 845 |

> Full API catalog: `docs/reference-data/temenos-r25amr-api-catalog.xlsx`

## Register

| ID | Source System | Target System | Protocol | Direction | Pattern | Owner | Status |
|---|---|---|---|---|---|---|---|
| INT-001 | | | | Sync/Async | Request-Reply / Event / Batch | | |

## Summary

| Protocol | Count |
|---|---|
| REST (Transact IRF) | 19,255 |
| REST (Transact Publisher) | 4,381 |
| REST (Transact PSD2) | 3,053 |
| SOAP | _(per-programme)_ |
| Event (Kafka/RabbitMQ) | _(per-programme)_ |
| File/SFTP | _(per-programme)_ |
| Database | _(per-programme)_ |
| **Total** | **26,689+** |
