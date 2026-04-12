# Component Model

Logical component diagram for the target-state architecture.

## Diagram

```mermaid
graph TB
    subgraph "Presentation"
        UI[Digital Channels]
    end
    
    subgraph "Integration"
        APIGW[API Gateway]
        ESB[ESB / Middleware]
    end
    
    subgraph "Core Banking"
        T[Temenos Transact]
    end
    
    subgraph "Data"
        DB[(Transact DB)]
    end
    
    UI --> APIGW
    APIGW --> T
    T --> DB
    ESB --> T
```

## Component Descriptions

| Component | Responsibility | Technology | Owner |
|---|---|---|---|
| | | | |
