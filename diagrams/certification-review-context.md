# Certification review context

I made this diagram to show the context a reviewer may need before approving, revoking, or investigating access.

The scenario uses fictional examples only.

```mermaid
flowchart TD
    ID[Identity]:::identity --> LCS[Lifecycle state]:::lifecycle
    ID --> MGR[Manager]:::context
    ID --> DEPT[Department]:::context
    ID --> TITLE[Job title]:::context

    ID --> ACCESS[Assigned access]:::access
    ACCESS --> AP[Access profile]:::profile
    ACCESS --> ROLE[Role]:::role
    ACCESS --> ENT[Entitlement]:::entitlement

    LCS --> DECISION{Certification decision}:::decision
    MGR --> DECISION
    DEPT --> DECISION
    TITLE --> DECISION
    AP --> DECISION
    ROLE --> DECISION
    ENT --> DECISION

    DECISION --> APPROVE[Approve]:::approve
    DECISION --> REVOKE[Revoke]:::revoke
    DECISION --> INVESTIGATE[Investigate]:::investigate

    classDef identity fill:#EEF8EF,stroke:#7ABF8A,color:#1F2937;
    classDef lifecycle fill:#FFF6E5,stroke:#D6A84F,color:#1F2937;
    classDef context fill:#F2F4F7,stroke:#98A2B3,color:#1F2937;
    classDef access fill:#F1ECFF,stroke:#9B7EDC,color:#1F2937;
    classDef profile fill:#EAF4FF,stroke:#6BA6D8,color:#1F2937;
    classDef role fill:#EEF2FF,stroke:#818CF8,color:#1F2937;
    classDef entitlement fill:#FDEEF4,stroke:#D77FA1,color:#1F2937;
    classDef decision fill:#FFF0E8,stroke:#D9905F,color:#1F2937;
    classDef approve fill:#ECFDF3,stroke:#12B76A,color:#1F2937;
    classDef revoke fill:#FEF3F2,stroke:#F04438,color:#1F2937;
    classDef investigate fill:#FFFAEB,stroke:#F79009,color:#1F2937;
```

## Analyst takeaway

Certification review should not be a blind approval exercise.

Reviewers need identity context, lifecycle state, business context, and access details before deciding whether to approve, revoke, or investigate access.
