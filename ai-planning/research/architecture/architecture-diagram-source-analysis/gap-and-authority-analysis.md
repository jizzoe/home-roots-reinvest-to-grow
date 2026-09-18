# Gap, contradiction, and authority analysis

## Full-vision gaps

| JLP capability | Current architecture decision coverage | Gap to resolve before a detailed end-state design |
| --- | --- | --- |
| Enrollment, consent, entrepreneur/business lifecycle | Profiles are in V1 roadmap; consent/lifecycle governance is not designed | Consent basis, retention/deletion, multiple-business relationship, staff workflows |
| Supply Hub, catalog, inventory, suppliers, collective purchasing | Strong JLP vision; no current domain/module/API architecture | Operating model, inventory authority, ordering, fulfillment, pricing, and offline needs |
| Coaching, training, actions | JLP vision and future admin context; no architecture decision | Actor permissions, notes/privacy, action model, calendar/notification integration |
| Financing/repayment | Conditional V1 visibility and broad JLP aspiration | Source of truth, servicing vs display, human approvals, reconciliation, regulatory/privacy controls |
| Assessments, outcomes, EGS, research | JLP and accepted traceability guardrails point toward it; no instrument/version architecture | Instrument versioning, observation provenance, measurement governance, EGS formula ownership, research-access controls |
| Notifications and partner integrations | Mentioned as future interfaces only | Integration catalog, event ownership, consent, delivery failure behavior, vendor selection |
| Full analytics/learning architecture | JLP vision only | Operational store versus analytics store, export/research boundary, metric definitions, data quality governance |
| End-state nonfunctional model | Directional security principles exist | Tenant model, data classification, regional/data-residency needs, recovery objectives, scale/availability targets |

## V1 gaps

| V1 capability | What is decided | What remains open |
| --- | --- | --- |
| Identity and roles | V1 requires authentication and role separation; M1.2 excludes full identity/profile | Provider, provisioned accounts vs self-service, recovery, role model, staff visibility, consent |
| Business Journal semantics | Accepted business-centered/audit/confirmation direction | Mandatory transaction types/fields, corrections versus delete/void, cash-position definition, duplicate policy |
| Offline sync | Local-first, durable queue, idempotency, status, preserve-on-conflict are decided | Sync protocol, server versioning, conflict matrix, local/server report authority, retry/backoff, device recovery |
| Receipts | Capture/review/manual fallback and evaluation gate are decided | Local/cloud retention, upload timing, metadata, malware scanning, extraction engine, accuracy thresholds before pilot |
| AI | Proposal/confirmation boundary and failure tolerance are decided | Allowed provider/data use, consent, prompt/data minimization, model evaluation, explanation/source labeling, exact V1 features |
| Dashboard/reporting | Basic reports are V1 scope and calculations must be deterministic | Calculation definitions, handling incomplete/unsynced data, local vs server calculation, label language |
| Staff portal/export | V1 target scope is clear | First pilot need, data-access matrix, export format/governance, coach notes/read-write behavior |
| Loan visibility | Conditional/read-only concept | Whether loan data exists, source system, audience, data update/reconciliation, approval boundary |
| V1 runtime | M1.2 proof is ECS/EC2/cold-off; later target direction is EKS/RDS | Exact V1 deployment target, migration trigger/evidence, environment/account layout, recovery requirements |

## Recorded contradictions and their handling

| Tension | Sources | Current defensible interpretation |
| --- | --- | --- |
| Voice is immediate V1 versus V1.1 | JLP PRD/UX versus V1 roadmap | Treat real offline multilingual voice as M1.1; maintain a replaceable boundary, not a V1 diagram dependency |
| OCR/extraction is required versus progressive assistance | JLP PRD/Appendix versus receipt rules/roadmap | Capture/review/fallback are required; automation cannot be a single point of failure and awaits evaluation evidence |
| AI Growth Coach versus bounded assistance | JLP PRD versus V1 guardrails/roadmap | V1 only has bounded assistance; no autonomous financial write, loan decision, or ungrounded impact claim |
| Full platform versus Business Journal V1 | JLP Engineer Brief/PRD versus V1 roadmap | Use a full-vision diagram and a separate V1 diagram; never imply V1 builds the full platform |
| EKS/RDS public direction versus ECS/EC2 M1.2 proof | README/older architecture direction versus M1.2 brief | ECS/EC2 plus colocated PostgreSQL is the selected proof; EKS/RDS is a later, planned target only |
| Loan capability is broad versus “if applicable” | JLP PRD/Appendix versus roadmap | Draw conditional read-only loan visibility only in V1; do not draw loan origination/scoring automation |
| Haitian Creole and language scope | JLP sources versus roadmap and corpus dependency | Language preference is V1; actual speech/language coverage remains an evidence and corpus decision |

## Diagram-safe decisions already made

- Mobile-first, Android-priority, low-connectivity operation and manual fallback.
- React Native/Expo/TypeScript direction for mobile; React/Vite/Material UI direction for future staff web.
- Local SQLite projection plus durable sync outbox; idempotent API writes and explicit sync state.
- Spring Boot modular monolith as the early backend shape; no premature microservice decomposition.
- PostgreSQL as the primary relational system-of-record direction and S3/object storage for documents.
- Versioned APIs and replaceable external-provider boundaries.
- Records from speech/OCR/AI are proposals until a person confirms them; auditability and source traceability are cross-cutting.
- Central planning is distinct from component repositories; mobile, backend, infrastructure, staff-web, and independently deployed workers own their implementation.

## Authority note

None of the listed gaps should be silently resolved by the diagram. The next detailed V1 design must either cite an accepted/owner decision or mark the item open. The full-vision diagram may show unresolved domains as conceptual capabilities, but should not imply their implementation topology, provider, or operational policy.
