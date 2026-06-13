# Identity governance map

I made this diagram to show how I understood the relationship between identity data, lifecycle state, access review, and investigation context.

The scenario uses the fictional **Northstar Identity Lab** organization.

```mermaid
flowchart LR
    SRC[Source attributes]:::source --> MAP[Attribute mappings]:::mapping
    MAP --> PROF[Identity profile]:::identity
    PROF --> ID[Governed identity]:::identity
    PROF --> LCS[Lifecycle state]:::lifecycle

    ID --> REQ[Access requests]:::request
    ID --> ROLE[Role evaluation]:::access
    ID --> CERT[Certifications]:::review
    ID --> SEARCH[Search]:::context
    ID --> GRAPH[Identity Graph]:::context

    LCS --> REQ
    LCS --> CERT
    ROLE --> CERT

    classDef source fill:#EAF4FF,stroke:#6BA6D8,color:#1F2937;
    classDef mapping fill:#EEF2FF,stroke:#818CF8,color:#1F2937;
    classDef identity fill:#EEF8EF,stroke:#7ABF8A,color:#1F2937;
    classDef lifecycle fill:#FFF6E5,stroke:#D6A84F,color:#1F2937;
    classDef access fill:#F1ECFF,stroke:#9B7EDC,color:#1F2937;
    classDef request fill:#FDEEF4,stroke:#D77FA1,color:#1F2937;
    classDef review fill:#FFF0E8,stroke:#D9905F,color:#1F2937;
    classDef context fill:#F2F4F7,stroke:#98A2B3,color:#1F2937;
```

## Analyst takeaway

Identity governance starts with usable identity data.

If source attributes and mappings are unclear, it becomes harder to trust lifecycle decisions, access requests, role evaluation, and certification reviews.
