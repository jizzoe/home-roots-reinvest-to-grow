# Architecture diagram source inventory

Prepared: 2026-09-17
Status terms: **accepted** = living OpenSpec requirement; **active/draft** = current planning record, not implementation authorization; **historical** = useful context but superseded or non-controlling; **vision** = JLP source material, not an approved technical design.

## Authority ladder for this work

1. Accepted OpenSpec specifications set current cross-repository, domain, API, and V1 guardrails.
2. Explicit, dated owner decisions in current control briefs refine the next slice, within accepted specs.
3. The V1 Scope Map controls product scope and sequencing until a later accepted change supersedes it.
4. JLP documents establish intent and the end-state conceptual platform; they do not select implementation technologies.
5. Research, analyses, decks, and older briefs inform options but do not settle conflicts.

## JLP document set — 36 physical files, 32 distinct documents

Four files are exact duplicate exports and should be cited once in future research: Software Engineer Brief, Final Deck 2027 Part 8, Master Architecture 3.1 Final, and Jizzoe Feedback. The `Enterprise Growth Platform 3.0` file is effectively empty; the Technical Implementation Brief is effectively empty/not usable. Neither should be represented as a technical decision source.

| Canonical JLP source | Role for diagrams | Maturity |
| --- | --- | --- |
| `.../PRD v1.0/Building the Enterprise Growth Platform...Software Engineer Brief v1.0.md` | Primary full-vision capability map, conceptual six-layer architecture, data/learning intent | Vision |
| `.../PRD v1.0/Enterprise Growth Platform, Enterprise Growth App, Entrepreneur Application.md` | Primary Business Journal V1 source; extensive future data, AI, reporting, and technical aspirations | Vision / mixed V1 detail |
| `.../Supporting Documents/Reinvest to Grow Master Architecture Version 3.1 Final.md` | Methodology logic, growth, measurement, and proposed EGS context | Vision |
| `.../Supporting Documents/Enterprise Growth Platform 2.0.md` | Standardization, automation, coordination, intelligence framing | Vision |
| `.../Pitch Deck/Final Deck 2027 Version 9.md` | Enterprise-architecture and dashboard summary for external audience | Vision |
| `.../Pitch Deck/Final Deck 2027 Part 8.md` | Operating economics/revenue presentation; duplicate root export exists | Supporting vision |
| `.../PRD v1.0/Executive Product Brief.md` | Concise V1 product framing | Vision / mixed V1 detail |
| `.../PRD v1.0/Features Reference Sheet, Appendix D.md` | Engineer quick-reference feature list | Vision / mixed V1 detail |
| `.../PRD v1.0/Enterprise Growth App 2, UXUI Product Guidelines v1.0.md` | Plain-language, voice/camera/manual-input, confirmation, accessibility, and trust intent | Vision |
| `.../PRD v1.0/Enterprise Growth App 3, Version 1 Pilot Operations Plan.md` | Pilot operations context | Supporting |
| `.../PRD v1.0/Credit Scoring Dialogue.md` | Credit-intelligence discussion; cannot authorize scoring | Supporting / exploratory |
| `.../PRD v1.0/Jizzoe App Suggestions.md` | Informal suggestions | Historical / advisory |
| `.../PRD v1.0/Jizzoe Feedback.md` | Informal architecture feedback; duplicate root export exists | Historical / advisory |
| `.../PRD v1.0/Enterprise Growth App 1, Technical Implementation Brief v1.0.md` | Empty/unusable file | Exclude |
| `.../Supporting Documents/HRF Investment Thesis.md` | Strategic outcome and investment context | Vision |
| `.../Supporting Documents/HRF Strategy Stack.md` | Strategy layers and operating context | Vision |
| `.../Supporting Documents/HRF's Three Competitive Moats.md` | Strategic differentiation context | Vision |
| `.../Supporting Documents/Organizational Capabilities.md` | Minimal organizational-capability note | Supporting |
| `.../Supporting Documents/Reinvest-to-Grow™ Methodology Summary.md` | Concise methodology overview | Vision |
| `.../Supporting Documents/Reinvest-to-Grow™ Methodology Revenue Layers v3.0.md` | Revenue model context | Supporting |
| `.../Supporting Documents/Lexicon.md` | Terminology aid; current repository terminology governs when different | Supporting |
| `.../Supporting Documents/What to Submit.md` | Submission/process context | Exclude from diagram design |
| `.../Supporting Documents/Enterprise Growth Platform 3.0.md` | One-line/empty export | Exclude |
| `.../Methodology Book/Reinvest to Grow Book Chapters, An Evidence Based Theory...md` | Broad methodology and evidence rationale | Vision |
| `.../Methodology Book/The Reinvest to Grow Theory.md` | Concise theory statement | Vision |
| `.../Methodology Book/Reinvest to Grow Book Chapters Preface.md` | Book framing | Supporting |
| `.../Methodology Book/Reinvest To Grow Investor Deck 3.1 Draft 1.md` | Earlier investor-deck draft | Historical vision |
| `.../Methodology Book/Reinvest To Grow Investor Deck 3.1 Draft 2.md` | Later investor-deck draft | Historical vision |
| `.../Methodology Book/A simple revenue architecture for HRF...md` | Revenue-model idea | Supporting |
| `.../Methodology Book/Clarifying chapters.md` | Editorial notes | Exclude |
| `.../Methodology Book/Research stuff in wrong place.md` | Mixed research notes | Historical / exploratory |
| root copies of Engineer Brief, Part 8, Master Architecture, and Jizzoe Feedback | Exact duplicates of the canonical entries above | Do not cite separately |
| root `Enterprise Growth Platform.md` | Short earlier platform framing | Historical vision |

## Complete internal technical-design discovery register

These are the non-JLP documents discovered as potential sources. Entries are grouped only for readability; no group implies equal authority. “Inspect if needed” means it is not a primary source for the first two diagrams, but may matter for the detailed V1 design.

| Location | Documents | Use |
| --- | --- | --- |
| Repository framing | `../../../../README.md`; `../../../../AGENTS.md`; `../../../../docs/product-terminology.md`; `../../../../docs/sdd-workflow.md`; `../../../../docs/cross-repository-sdd-flow.md`; `../../../../docs/sdd-bootstrap-evidence.md` | README has public architecture context; terminology and workflow constrain language/authority; the rest are governance, not diagram content |
| Accepted living specs | `core-domain-model`; `cross-repository-architecture`; `api-contract-conventions`; `v1-product-guardrails`; `prototype-manual-offline-transaction`; `prototype-speech-proposal-confirmation` under `../../../../openspec/specs` | Primary current technical authority |
| Active OpenSpec change | `openspec/changes/m1-2-phase-a-delivery/{proposal,design,tasks}.md` and `specs/prototype-development-environment/spec.md` | Primary only for the active M1.2 proof; do not generalize to V1 |
| Archived decision history | `define-cross-repository-architecture`; `define-api-contract-conventions`; `define-core-domain-model`; `define-v1-product-guardrails`; `m1-manual-offline-delivery`; `prototype-manual-offline-transaction`; `prototype-speech-proposal-confirmation`; `prototype-receipt-capture-ocr-review`; `close-m0-foundation`; `close-m1-prototype` under `../../../../openspec/changes/archive` | Rationale/evidence when living specs are insufficient; superseded by accepted living specs or explicit supersession notes |
| Product/control briefs | `V1 Scope Map and Milestone Plan`; `JLP UX Synthesis and V1 Design Decisions`; `Reinvest-to-Grow Methodology Synthesis and V1 Design Brief`; `m0-sdd-and-product-foundation`; `m1-rapid-thin-slice-prototype`; `m1-later-phase-deferred-work` | Primary scope, sequencing, and prototype-boundary context |
| Slice design briefs | `m1-mobile-prototype-workflows`; `m1-mobile-ui-design-brief-and-screen-inventory`; `m1.1-offline-multilingual-speech`; `m1.2-live-sync-rest-api-proof`; `m1-receipt-extraction-acceptance-and-eval-rules` | Use by relevant V1 component; M1.2 is current technical detail |
| Planning/handoff material | `m1.2-live-sync-session-handoff`; `m1.2-phase-a-propose-handoff`; receipt-slice handoffs/reset; `mobile-bookkeeping-new-repository-handoff`; two implementation plans under `../../../ai-planning/implementation-plans`; M1 Terraform and speech-corpus plans | Execution context only; not diagram authority |
| Earlier analysis/options | `PROJECT_SUMMARY.md`; `INTERNAL_ARCHITECTURE_ANALYSIS_v0.1.md`; `ALIGNMENT_BRIEF_v0.1.md`; `BUILD_VS_BUY_ANALYSIS.md`; `ARCHITECTURE_RESEARCH_NEEDS.md`; `FOCUSED_ARCHITECTURE_RESEARCH.md` | Historical rationale, option discovery, and gap context |
| Core technical research | `phase-01-mobile-foundation-react-native-expo-typescript`; `phase-02-offline-first-sqlite-sync-architecture`; `phase-03-thin-backend-sync-slice-spring-boot-modular-monolith`; `phase-04-touch-first-bookkeeping-mobile-ux`; `phase-05-receipt-capture-mobile-document-scanning`; `phase-06-speech-multilingual-ai-proposal-workflow`; `phase-07-staff-back-office-react-vite-material-ui` | Research evidence for named stack/delivery choices, never higher authority than accepted specs |
| Supporting technical research | `eks-cicd-and-environment-strategy`; `react-native-ui-design-system-options`; on-device OCR findings/comparison; speech/TTS findings and sources; mobile text-to-speech findings; mobile prototype testing suite; React Native Expo platform/testing guides; UX/Figma research; AI coding-evaluation research | Inspect if the detailed design addresses that concern; no direct effect on the high-level full-vision map unless explicitly decided |
| Evidence and operational verification | M0/M1 closure audits, M1 manual/speech verification evidence, M1.2 Terraform verification, prototype testing records | Evidence of prototype work; not architecture selection sources |

## Current internal decision sources

| Source(s) | What it contributes | Diagram eligibility |
| --- | --- | --- |
| `../../../../openspec/specs/cross-repository-architecture/spec.md` | Planning/component repository boundaries and ownership | Solid: accepted |
| `../../../../openspec/specs/core-domain-model/spec.md` | Business-centered entities, traceability, record states | Solid: accepted |
| `../../../../openspec/specs/api-contract-conventions/spec.md` | Versioned APIs, idempotency, executable contract publication | Solid: accepted |
| `../../../../openspec/specs/v1-product-guardrails/spec.md` | Offline, confirmation, auditability, safety boundaries | Solid: accepted |
| `../../../../openspec/specs/prototype-manual-offline-transaction/spec.md`, `prototype-speech-proposal-confirmation/spec.md` | Narrow M1 proof behavior | Solid only in the M1 proof view; not V1 scope |
| `ai-planning/design-briefs/V1 Scope Map and Milestone Plan.md` | V1 scope, M0–M12 path, known tensions | Solid for scope; dates/status must be rechecked before publishing |
| `ai-planning/design-briefs/JLP UX Synthesis and V1 Design Decisions.md` | User-experience/data/API constraints | Solid where not contradicted by accepted specs |
| `../../../design-briefs/m1.2-live-sync-rest-api-proof.md` and active `../../../../openspec/changes/m1-2-phase-a-delivery` | Selected M1.2 proof architecture and active work | Solid only when labeled “M1.2 prototype proof” |
| `../../../design-briefs/m1.1-offline-multilingual-speech.md`, `m1-receipt-extraction-acceptance-and-eval-rules.md`, `m1-later-phase-deferred-work.md` | Later-slice constraints and deferrals | Dashed/future capability only |
| `ai-planning/research/tech-research/phase-01` through `phase-07` | Stack options/research for mobile, sync, backend, UX, receipt, speech, staff portal | Annotate as researched direction, not a final selection |
| `../../eks-cicd-and-environment-strategy.md` | M2/M3 target delivery direction | Dashed planned target |
| `../../../../README.md` | Current public explanation and existing diagram location | Context only; working-tree changes are not authority |
| `../../../PROJECT_SUMMARY.md`, `INTERNAL_ARCHITECTURE_ANALYSIS_v0.1.md`, `ALIGNMENT_BRIEF_v0.1.md`, `BUILD_VS_BUY_ANALYSIS.md` | Earlier backbone/options/gap analysis | Historical/advisory; do not override current records |
| Archived OpenSpec proposals/designs under `openspec/changes/archive/2026-08-*` and `2026-09-*` | Decision history and evidence trail | Use only when their accepted living spec lacks needed rationale |

## Source set by planned artifact

| Artifact | Primary sources | Secondary sources |
| --- | --- | --- |
| Full-vision diagram | JLP Software Engineer Brief; JLP PRD; Master Architecture 3.1; repository product direction | Platform 2.0, Version 9 deck, alignment/internal analyses |
| V1 diagram | V1 Scope Map; accepted V1/domain/API/cross-repository specs; M1.2 brief | UX synthesis, M1/M1.1/M1.3 briefs, phase research |
| V1 detailed design | Accepted specs plus approved slice design(s) and component-repository contracts | Research only for options; JLP PRD for product intent |
