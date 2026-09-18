# Architecture description and ASCII reference

This is a diagram drafting aid. It deliberately includes only decisions supported by accepted specifications or current scoped planning records. Square brackets are components; parentheses are replaceable/external boundaries; dotted text is planned or conceptual, not currently delivered.

## Full vision — conceptual architecture

```text
 Entrepreneurs       Coaches / Hub / Finance / HRF staff       Leadership / Researchers
      |                           |                                      |
      +---- mobile experience ----+---- staff web / field tools ----------+
                                      |
                                      v
                 +------------------------------------------------+
                 |       Enterprise Growth Platform               |
                 |  shared entrepreneur + enterprise context      |
                 +------------------------------------------------+
                  |         |          |          |         |
                  v         v          v          v         v
           [Enrollment] [Business] [Supply Hub] [Coaching] [Financing]
           [Consent]    [Journal]  [Catalog /    [Training] [Repayment]
                                    inventory /  [Actions]
                                    purchasing]
                  \         |          |          |         /
                   \        +----------+----------+--------/
                    v                  v
          [Assessments / outcome observations / reinvestment / milestones]
                    |                  |
                    v                  v
        [Dashboards / reporting]   [Learning / evaluation / research export]
                    ^                  |
                    +---- governed, traceable confirmed records --+

  (identity) (SMS/email) (payments/mobile money/banking) (accounting)
  (speech/OCR/translation/AI) (supplier/partner systems) (analytics/mapping)
                  \_______________________________________________/
                         versioned, replaceable integration boundaries
```

The diagram should make the methodology loop visible: operational activity yields traceable information, information supports human decisions and coaching, and the resulting learning improves operations. It must label the Enterprise Growth Score and outcome inference as proposed/evidence-seeking, not automated truth.

## V1 — product architecture and proof/target distinction

```text
 Entrepreneur Android app                         HRF staff web (M10)
 [business-language UI]                            [role-limited views / exports]
 [profile + Business Journal]                                  |
 [SQLite local projection]                                     |
 [sync outbox; local/syncing/synced/failed/needs-review]       |
              |                                                |
              +--------------- HTTPS / versioned API ----------+
                                      |
                                      v
              [Spring Boot modular monolith: V1 API boundary]
              [profile | journal | sync | reporting | audit]
              [receipt metadata | conditional loan visibility]
                      |                    |                 |
                      v                    v                 v
              [PostgreSQL records]  [object/document]  (identity provider)
                                      storage
                                      |
                         (speech / OCR / AI provider boundary)
                                      |
                    proposal -> validation -> human confirmation -> record

 M1.2 selected proof (solid, temporary):
 Android -> SQLite/outbox -> HTTPS -> ECS singleton on EC2:
 Spring Boot container + colocated PostgreSQL container -> encrypted S3 dumps
 cold-off lifecycle; no EKS, RDS, staff portal, or full identity in this proof.

 Planned V1 platform direction (dashed; requires future approval):
 portable container -> EKS runtime; PostgreSQL -> RDS; object storage, OIDC,
 CI/promotion, and worker/provider boundaries as later M2/M3+ work establishes them.
```

## Current component ownership

```text
 Planning repository: product scope, architecture, accepted cross-component specs,
                      central coordination and system-acceptance evidence

 Mobile repository: Expo/React Native UI, SQLite, device behavior, mobile tests
 Backend repository: Spring Boot API, contracts, migrations, service tests, container
 Infrastructure repo: Terraform, environments, deployment permissions, recovery evidence
 Staff-web repository: HRF portal implementation and validation when M10 is approved
 Worker repository: only if a separately deployed worker is justified and approved
```

## Detail-level rule

The full-vision diagram stops at capabilities and integration boundaries. The V1 diagram stops at components and durable stores. The later V1 detailed design may add module interfaces, entity ownership, state machines, API messages, trust boundaries, and operational controls—after the open decisions are resolved.
