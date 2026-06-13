# Access model map

I made this diagram to map the access model from low-level entitlements to request and certification review context.

The scenario uses fictional access examples only.

```mermaid
flowchart LR
    ENT[Entitlements]:::entitlement --> AP[Access profiles]:::profile
    AP --> ROLE[Roles]:::role
    ROLE --> CERT[Certifications]:::review

    AP --> REQ[Request settings]:::request
    REQ --> APPROVAL[Approval context]:::request

    ENT --> CERT
    AP --> CERT

    OWNER[Access owner]:::owner --> AP
    OWNER --> CERT

    classDef entitlement fill:#EAF4FF,stroke:#6BA6D8,color:#1F2937;
    classDef profile fill:#F1ECFF,stroke:#9B7EDC,color:#1F2937;
    classDef role fill:#EEF8EF,stroke:#7ABF8A,color:#1F2937;
    classDef request fill:#FDEEF4,stroke:#D77FA1,color:#1F2937;
    classDef review fill:#FFF0E8,stroke:#D9905F,color:#1F2937;
    classDef owner fill:#F2F4F7,stroke:#98A2B3,color:#1F2937;
```

## Analyst takeaway

Entitlements are the low-level access.

Access profiles make access easier to understand, request, and review.

Roles help compare assigned access against job or department expectations.

Certifications need enough context to decide whether access should stay assigned.
