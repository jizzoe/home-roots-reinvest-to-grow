# V1 roadmap review

## V1 outcome

V1 is the **Business Journal Module** of the entrepreneur-facing Enterprise Growth App. It gives entrepreneurs reliable, understandable business records despite intermittent connectivity, while giving HRF sufficient role-controlled visibility to support pilot operations, coaching, and learning. It preserves a path to future Supply Hub, financing, inventory, AI, and impact capabilities without building them all now.

## In-scope architecture implications

| V1 capability | Architecture implication |
| --- | --- |
| Account, entrepreneur profile, business profile, language | Identity/profile boundary; business is the aggregation context for activity |
| Sale, expense, cash movement, history, correction, duplicate review | Business Journal module; validation; append-only/auditable history and clear state |
| Offline use and sync | Device-local durable projection and outbox, retries, idempotent server writes, human-understandable sync states, data-preserving conflict review |
| Dashboard and reports | Deterministic calculations with plain-language presentation; explicit handling of local/unsynced/estimated state |
| Receipts | Capture/storage/review path; any extraction stays optional assistance and requires confirmation |
| Bounded AI assistance | Provider boundary; proposed/estimated/confirmed distinction; failure cannot block core activity |
| HRF admin portal | Separate staff channel with role-based access to businesses, activity, summaries, engagement, reports, and exports |
| Loan visibility if applicable | Read-only/conditional module, pending source-data and pilot decision |
| Pilot readiness | Observability, security/privacy, offline resilience, support flows, and controlled deployment evidence |

## Delivery path versus V1 target

The roadmap contains two very different technical views that must not be collapsed into one image.

| View | What it is | Current state |
| --- | --- | --- |
| M1 prototype | Local Android manual-entry proof plus mocked speech/TTS | Completed; intentionally narrow |
| M1.2 live-sync proof | One Android local-first client synchronizing to a Spring Boot API in a cold-off ECS-on-EC2 singleton with colocated PostgreSQL and encrypted S3 dumps | Active next milestone; selected proof design, not V1 target runtime |
| M2/M3 foundation | Planned EKS/RDS/S3, Terraform, OIDC, CI/CD, Helm/promotion direction for later shared environments | Planned, contingent on future approved work |
| V1 product | M4–M12: profiles, core journal, sync, reports, receipts, bounded AI, admin, conditional loan visibility, pilot readiness | Roadmap scope; many detailed design decisions remain open |

## V1 diagram recommendation

The V1 architecture diagram should have a solid **product architecture** and two clearly separated deployment annotations:

- **M1.2 proof lane (solid, dated):** Android prototype → SQLite/outbox → HTTPS → single Spring Boot API → colocated PostgreSQL; encrypted dump storage and cold-off controls.
- **Planned V1 platform lane (dashed):** portable containerized API, PostgreSQL, document storage, staff portal, identity/provider boundary, and worker/provider boundary. Only label EKS/RDS/Helm where the image expressly says “planned M2/M3 target — not yet approved/deployed.”

This prevents the README from repeating the older claim that the current prototype “will use EKS” when the current M1.2 decision intentionally uses ECS on EC2 for the proof.

## V1 design document outline

The requested one-level-deeper design should be created after resolving the gaps in the next document. Its minimum sections should be:

1. Scope, non-goals, and authority sources.
2. Context/container view and component ownership.
3. Module boundaries: identity/profile, journal, sync, reporting, receipt metadata, audit, staff access; conditional loan and AI boundaries.
4. Core entities and ownership, including confirmed/proposed/unsynced/needs-review/audit state.
5. Offline state machine, outbox contract, idempotency, retry, and conflict policy.
6. API contracts, versioning, authn/authz, pagination/filtering, and error semantics.
7. Receipt and AI proposal pipeline with manual fallback and consent/privacy boundaries.
8. Reporting calculation ownership and local-versus-server semantics.
9. Security, privacy, observability, backup/recovery, retention, and support operations.
10. Deployment topology stated separately for M1.2 proof and approved V1 target decisions.
11. Acceptance scenarios, component validation, and explicit unresolved decisions.
