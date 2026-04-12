# Dependency Graph

Directed graph of system dependencies with protocol, SLA, and owner annotations.

## Diagram

```mermaid
graph LR
    DC[Digital Channels] -->|REST| AGW[API Gateway]
    AGW -->|REST| T[Temenos Transact]
    T -->|Event| MQ[Message Broker]
    MQ -->|Event| PAY[Payment Hub]
    MQ -->|Event| CRM[CRM]
    T -->|REST| FDS[Fraud Detection]
    BATCH[Batch Scheduler] -->|SFTP| T
```

## Edge Details

| From | To | Protocol | SLA | Owner |
|---|---|---|---|---|
| | | | | |
