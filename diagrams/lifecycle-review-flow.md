# Lifecycle review flow

I used this flow to think through how joiner, mover, and leaver events can affect access review.

The scenario uses fictional examples only.

```mermaid
flowchart TD
    EVENT[Identity event]:::event --> TYPE{Event type}:::decision

    TYPE --> JOINER[Joiner]:::joiner
    TYPE --> MOVER[Mover]:::mover
    TYPE --> LEAVER[Leaver]:::leaver

    JOINER --> J1[Create or update governed identity]:::process
    J1 --> J2[Check baseline access]:::access
    J2 --> J3[Confirm manager and department]:::review

    MOVER --> M1[Detect job or department change]:::process
    M1 --> M2[Compare old access to new role]:::access
    M2 --> M3[Remove stale access or investigate]:::review

    LEAVER --> L1[Detect inactive or terminated status]:::process
    L1 --> L2[Remove or disable access]:::access
    L2 --> L3[Confirm cleanup]:::review

    J3 --> OUT[Document finding or close review]:::output
    M3 --> OUT
    L3 --> OUT

    classDef event fill:#EAF4FF,stroke:#6BA6D8,color:#1F2937;
    classDef decision fill:#F2F4F7,stroke:#98A2B3,color:#1F2937;
    classDef joiner fill:#EEF8EF,stroke:#7ABF8A,color:#1F2937;
    classDef mover fill:#FFF6E5,stroke:#D6A84F,color:#1F2937;
    classDef leaver fill:#FFF0E8,stroke:#D9905F,color:#1F2937;
    classDef process fill:#EEF2FF,stroke:#818CF8,color:#1F2937;
    classDef access fill:#F1ECFF,stroke:#9B7EDC,color:#1F2937;
    classDef review fill:#FDEEF4,stroke:#D77FA1,color:#1F2937;
    classDef output fill:#F2F4F7,stroke:#98A2B3,color:#1F2937;
```

## Analyst takeaway

Joiner, mover, and leaver review should focus on whether access matches the identity’s current business need.

Mover and leaver scenarios usually need extra attention because stale access can remain after role or employment changes.
