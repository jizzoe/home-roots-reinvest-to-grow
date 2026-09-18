# High-level systems architecture

Prepared: 2026-09-18
Purpose: source material for two system-architecture diagram types:

1. **Technology and tools view** — the runtime topology: clients, frameworks, major cloud/data services, workers, and external-provider boundaries.
2. **Service-boundary view** — the functional decomposition into logical services. A service is the smallest element shown; individual features, endpoints, tables, and jobs do not appear.

## Diagram conventions

- **Selected / accepted direction** means the technology or boundary has a current supporting decision.
- **Planned** means the roadmap has a direction but a future slice must still approve and implement it.
- **TBD** means the diagram deliberately identifies a gap; it is not a placeholder decision.
- A box inside **“modular monolith, initially”** is a logical service boundary, not a separately deployed microservice. It becomes a microservice only after an explicit reason and approved change justify independent deployment.
- AI, OCR, speech, translation, and external finance/notification systems stay behind provider/integration boundaries. Their output cannot bypass proposal, validation, and human confirmation for consequential records.

---

## Full vision — technology and tools view

This is the long-term directional topology. It communicates the technology families already selected or researched and exposes undecided technology slots. It does not imply that every planned tool exists today.

```mermaid
flowchart TB
  entrepreneur["Entrepreneur mobile app\nReact Native + Expo + TypeScript\nselected direction"]
  staff["HRF staff portal\nReact + Vite + TypeScript + Material UI\nresearched direction"]
  partner["Partner / external systems\nversioned integration APIs"]

  entrepreneur --> api
  staff --> api
  partner <--> api

  subgraph platform["Enterprise Growth Platform"]
    api["Platform API\nJava + Spring Boot\nmodular monolith initially"]
    postgres[("PostgreSQL\noperational system of record")]
    objects["Object/document storage\nS3 direction"]
    workers["Asynchronous worker runtime\nTBD service/compute choice"]
    analytics["Reporting / analytics platform\nTBD"]
    identity["Identity provider\nTBD"]
    api <--> postgres
    api <--> objects
    api --> workers
    api --> analytics
    api <--> identity
  end

  workers <--> ai["Speech / OCR / translation / AI\nprovider adapters; vendor TBD"]
  api <--> integrations["Payments, mobile money, banking, accounting,\nSMS/email, supplier, mapping, learning systems\nreplaceable provider boundaries"]

  terraform["Terraform\ninfrastructure-as-code direction"] -. provisions .-> aws["AWS platform direction\ncontainer runtime and environment topology TBD"]
  aws -. hosts .-> platform
```

**Rendering note:** arrange clients across the top, the Platform API at the visual center, primary stores beneath it, worker/provider services to one side, and reporting/analytics below. Use a distinct dashed or muted treatment for every `TBD` and planned box.

## Full vision — service-boundary view

The JLP vision calls for these service-sized domains. The source material does **not** authorize deployment as microservices; the default is modules in the Platform API until a service has a strong independent-scale, security, ownership, or release need.

```mermaid
flowchart LR
  mobile["Entrepreneur mobile"] --> edge
  portal["Staff portal"] --> edge
  partners["External partners"] <--> edge
  edge["API / integration edge"] --> platform

  subgraph platform["Enterprise Growth Platform — modular monolith initially"]
    identity["Identity & access service"]
    enterprise["Entrepreneur & enterprise service"]
    hub["Supply Hub & purchasing service"]
    journal["Business Journal & document service"]
    finance["Financing & repayment service"]
    coaching["Coaching & training service"]
    assessment["Assessment & measurement service"]
    reporting["Reporting & learning service"]
    notify["Integration & notification service"]
  end

  edge --> identity
  edge --> enterprise
  edge --> hub
  edge --> journal
  edge --> finance
  edge --> coaching
  edge --> assessment
  edge --> reporting
  edge --> notify

  docs["Document & intelligence worker service\nfuture microservice candidate"] <--> journal
  docs <--> notify
  reporting --> research["Governed analytics / research export boundary"]
```

The enterprise context connects the services conceptually; it does not authorize a shared-database free-for-all. The detailed design must define ownership, interfaces, and consistency rules before any service split.

---

## V1 — technology and tools view

This diagram combines the **selected M1.2 proof** with the **planned V1 direction** without presenting them as the same environment.

```mermaid
flowchart TB
  mobile["Android Enterprise Growth App\nReact Native + Expo + TypeScript\nSQLite local projection + sync outbox"]
  staff["HRF staff portal (M10)\nReact + Vite + Material UI\nplanned"]
  mobile --> api
  staff -. planned HTTPS API .-> api

  subgraph app["V1 Platform API — Spring Boot modular monolith"]
    api["Versioned HTTPS API\nidempotent writes"]
    db[("PostgreSQL\nM1.2: colocated container\nV1 target: managed database TBD")]
    receipts["Receipt/document storage\nplanned M8; object-store design TBD"]
    idp["Identity provider\nplanned M4; vendor TBD"]
    providers["Speech / OCR / AI provider adapters\nplanned M1.1/M1.3/M9; vendor TBD"]
    api <--> db
    api <--> receipts
    api <--> idp
    api <--> providers
  end

  subgraph proof["M1.2 selected live-sync proof — temporary"]
    tf["Terraform"]
    ecs["AWS ECS on EC2\none singleton task"]
    ecr["Amazon ECR\nimmutable image digest"]
    dump["Encrypted S3 dumps\nchecksum + restore metadata"]
    sec["Secrets Manager, CloudWatch,\nRoute 53 + host-local TLS proxy"]
    tf --> ecs
    ecr --> ecs
    ecs --> dump
    sec --> ecs
  end
  ecs -. hosts .-> api

  target["Planned M2/M3+ target\nEKS, managed PostgreSQL, CI/promotion\nnot approved/deployed as V1 runtime"] -. future migration .-> api
```

The V1 diagram should use solid styling for the mobile, SQLite, Spring Boot, versioned/idempotent API, PostgreSQL direction, and M1.2 proof. It should use dashed styling for the staff portal, receipts, identity, AI providers, and M2/M3 target components that remain unimplemented or undecided.

## V1 — service-boundary view

The V1 logical services below are initially modules in one deployable Spring Boot service. The boxes describe the largest acceptable functional boundaries, not individual workflows such as “record sale” or “receipt parse.”

```mermaid
flowchart LR
  mobile["Entrepreneur mobile app\nlocal-first SQLite + outbox"] --> sync
  staff["HRF staff portal\nplanned M10"] -.-> platform

  subgraph platform["V1 Platform API — one modular-monolith deployment initially"]
    access["Identity & profile service\nplanned M4"]
    journal["Business Journal & audit service\nM5"]
    sync["Synchronization service\nM1.2 / M6"]
    reports["Business reporting service\nM7"]
    documents["Receipt & document service\nplanned M8"]
    assistance["Bounded assistance service\nplanned M9"]
    loans["Loan visibility service\nconditional M11"]
  end

  sync --> journal
  access --> journal
  journal --> reports
  journal <--> documents
  journal <--> assistance
  journal <--> loans
  staff -. role-limited API .-> access
  staff -. role-limited API .-> reports
  staff -. role-limited API .-> journal

  docsWorker["Document / intelligence worker service\nonly if independently deployed later"] -. provider-mediated .-> documents
  docsWorker -. provider-mediated .-> assistance
```

The active M1.2 proof contains only the synchronization path and a minimal transaction store. It does not deliver the staff portal, full identity, document storage, receipt processing, AI assistance, reports, or loan visibility.

## Diagram handoff checklist

- Produce four separate panels: full-vision tools, full-vision services, V1 tools, V1 services.
- Put the legend on every exported diagram: selected, planned, and TBD.
- Do not name AWS Transcribe, Polly, Textract, Bedrock, SQS, EventBridge, Cognito, EKS, or RDS as a committed end-state choice unless a new decision approves it. The prior image may be used as a layout reference, not as authority for those selections.
- Do not draw a service box below the microservice/module level. Screens, endpoints, tables, queues, and individual automations belong in the later detailed design.
