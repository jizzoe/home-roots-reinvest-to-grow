# Systems architecture gap analysis

Prepared: 2026-09-18
Purpose: identify gaps separately for (1) technology/tool selection and (2) functional service decomposition. This document does not select a gap closure.

## Status legend

- **Decided direction:** supported by an accepted specification or explicit current, scoped decision.
- **Planned direction:** present in the roadmap but requires a later approved slice.
- **Researched direction:** technically investigated; not a selection.
- **Gap:** no decision sufficient to draw the element as committed.

## Technology and tools gaps

### Full-vision topology

| Technology/tool concern | Current status | What can appear in the diagram now | Gap before a detailed system design |
| --- | --- | --- | --- |
| Entrepreneur mobile | Decided direction: React Native, Expo, TypeScript | Mobile client with those technologies | OS/device support, release/distribution, offline encryption policy |
| Staff web | Researched direction: React, Vite, TypeScript, Material UI | Planned staff portal, visually marked researched/planned | Exact UI architecture, authorization model, hosting, component repository |
| Core API | Decided direction: Java/Spring Boot modular monolith | One Platform API | Module-to-service split triggers, API gateway/edge needs, multi-tenant model |
| Operational data | Decided direction: PostgreSQL | PostgreSQL system-of-record direction | Full entity ownership, data partitioning, backup/recovery objectives, migration policy |
| Document storage | Directional: S3/object storage | Object/document-store boundary | Receipt upload path, lifecycle, malware scanning, retention/deletion, access control |
| Cloud and infrastructure | AWS and Terraform direction; M1.2 proof selected | AWS/Terraform, plus clearly labeled M1.2 ECS/EC2 proof | Account/environment topology, full V1 runtime, network/security architecture, cost and recovery targets |
| Container runtime | M1.2: ECS on EC2 selected; M2/M3: EKS target planned | Both only with proof/target labels | Migration decision and trigger; no current authority for EKS as the deployed V1 runtime |
| Managed database | M1.2 uses colocated PostgreSQL; RDS is planned direction | Current container database and future managed-database placeholder | V1 timing, availability, restore, networking, encryption, and cost decision |
| Identity | Gap | “Identity provider — TBD” boundary only | Provider, entrepreneur/staff identity lifecycle, recovery, MFA, federation, consent, role model |
| Queues/event bus | Gap | No committed SQS/EventBridge box | Whether asynchronous work exists, delivery semantics, retry/DLQ, ownership, event contracts |
| Worker runtime | Gap | “Worker service/runtime — TBD” only | Need for separate deployment, language/runtime, job orchestration, scaling, observability |
| Speech/OCR/translation/AI | Provider-boundary direction only | Generic provider-adapter boundary | On-device versus cloud choices, supported languages, evaluation thresholds, consent/data policy, provider selection |
| Reporting/analytics | Gap | Reporting/analytics boundary only | Operational versus analytical store, BI tool, metric governance, research export controls |
| Notifications | Gap | External notification-provider boundary only | SMS/email/push channels, opt-in/consent, provider, delivery/audit behavior |
| Payment, banking, mobile money, accounting | Future integration candidates | Generic integration boundary only | Actual partner/system, data authority, reconciliation, regulatory/security constraints |
| Security/operations tooling | Directional controls in M1.2 and principles | M1.2 Secrets Manager/CloudWatch/TLS components only | Full V1 observability, audit-log, key management, incident, data-classification, and retention design |

### V1 topology

| Technology/tool concern | Current status | Gap requiring a V1 decision |
| --- | --- | --- |
| Local-first Android client and SQLite outbox | Decided direction | Encryption-at-rest, device loss/recovery, schema migration, sync telemetry |
| Spring Boot sync API and idempotent HTTPS writes | Decided for M1.2/M6 direction | Auth mechanism, transaction/version contract, conflict protocol, rate/abuse controls |
| ECS-on-EC2, container PostgreSQL, ECR, S3 dumps | M1.2 proof selected | Whether this proof runtime serves any V1 pilot; operational hardening and migration evidence |
| EKS/RDS, Helm, CI/promotion | Planned M2/M3 direction | Approval, timing, environment/account layout, production/pilot entry criteria |
| Receipts and object storage | Planned M8 | Capture/upload/storage architecture, offline behavior, scanning/evaluation and retention |
| Staff portal technology | Researched/planned M10 | The portal’s first delivery target, access control, data/export governance, hosting |
| Identity provider | Planned M4, vendor gap | Identity/account-recovery decision before pilot accounts or staff roles |
| Speech, OCR, AI | Future bounded slices | Provider and data-handling decisions after corpus/evaluation evidence |

## Functional service-boundary gaps

### Full vision

| Logical service | Current status | Boundary gap |
| --- | --- | --- |
| Identity & access | Needed across the platform; no service decision | Ownership of users, roles, consent, organization/tenant boundary, authorization policy |
| Entrepreneur & enterprise | Core conceptual context; accepted domain direction is partial | Lifecycle, business relationship cardinality, enrollment ownership, cross-service identifiers |
| Business Journal & documents | V1 foundation with partial accepted/prototype behavior | Journal/document relationship, correction/audit ownership, document lifecycle |
| Supply Hub & purchasing | Central JLP vision; no design | Catalog/inventory/order/fulfillment scope, pricing authority, supplier interface, offline responsibilities |
| Financing & repayment | JLP vision; conditional V1 visibility only | System of record, servicing integration, staff approval, reconciliation, regulatory boundary |
| Coaching & training | JLP vision; no design | Confidentiality, action-plan ownership, staff roles, scheduling/notification integration |
| Assessment & measurement | JLP vision and traceability intent; no design | Instrument versioning, observation source/provenance, EGS governance, evaluation access |
| Reporting & learning | Broad vision; V1 reports planned | Metric definitions, calculation ownership, operational/analytics separation, research exports |
| Integration & notification | Future integration direction | API/event contracts, provider adapters, consent, failure/retry/audit behavior |
| Document & intelligence worker | Possible cross-cutting service | Whether it is a module or separate microservice; queue/event and data-access contracts |

### V1

| Logical service | Current status | Boundary gap |
| --- | --- | --- |
| Identity & profile | Planned M4 | Account lifecycle and role policy; exact ownership of entrepreneur/business profile |
| Business Journal & audit | M5 scope; prototype precedent | Required records, correction/void policy, audit event model, duplicate handling |
| Synchronization | M1.2 active proof and M6 direction | Outbox/API contract, server-side idempotency identity, retry and conflict resolution policy |
| Reporting | Planned M7 | Local versus server calculation, consistency point, report definition/version ownership |
| Receipt & document | Planned M8 | Storage/metadata boundary, offline upload, security scanning, link to financial record |
| Bounded assistance | Planned M9 | Scope of the service, data minimization, consent, fallback, model-evaluation ownership |
| Staff portal access | Planned M10 | Whether it is only a channel or requires staff-specific BFF/service; authorization and export boundaries |
| Loan visibility | Conditional M11 | Existence of a loan source, integration versus owned service, staff/entrepreneur visibility rules |

## Decomposition rules before any microservice split

The current selected backend shape is one Spring Boot modular monolith. A logical service should remain a module until an approved design shows a reason to deploy it independently, such as materially different scaling, isolation/security, ownership, release cadence, resilience, or integration needs.

Before extracting any microservice, define:

1. Its business ownership and authoritative data.
2. Its API/event contract and compatibility policy.
3. Consistency, idempotency, retry, and failure behavior across the boundary.
4. Authentication/authorization and audit responsibilities.
5. Deployment, observability, recovery, and cost model.
6. A migration plan from the modular-monolith module without copying or splitting authority ambiguously.

## Recommended next design decisions

For the diagrams, leave gaps visibly undecided. For the later V1 detailed design, resolve in this order:

1. Identity and role lifecycle.
2. Business Journal, sync, and report-authority model.
3. V1 runtime target and the M1.2-to-target migration decision.
4. Receipt/document storage and processing boundary.
5. Staff portal and export authorization boundary.
6. AI/provider data policy and only then the bounded-assistance service shape.

Full-vision services beyond V1—Supply Hub, financing, coaching, assessments, measurement, and organizational learning—should be designed from validated operating workflows, not inferred solely from conceptual vision documents.
