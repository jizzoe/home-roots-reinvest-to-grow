# Architecture diagram research package

Prepared: 2026-09-17
Purpose: prepare the replacement for the README **Overarching Technical Direction** diagram. No diagram or product decision is approved by this package.

## Intended outputs

1. **Full-vision architecture diagram** — a conceptual platform map for the Enterprise Growth Platform, aligned to the JLP end-state vision.
2. **V1 architecture diagram** — the smaller architecture that can deliver V1 Business Journal scope, explicitly distinguishing the active M1.2 proof from the later V1 target environment.
3. **V1 detailed design document** — one level below the V1 diagram, covering module responsibilities, data ownership, APIs, state transitions, security, and deployment assumptions.

## Reading order

1. `source-inventory.md` — all candidate sources, duplicates, maturity, and diagram eligibility.
2. `jlp-end-state-review.md` — the full platform vision, synthesized from the JLP document set.
3. `v1-roadmap-review.md` — V1 capabilities and current milestone path.
4. `gap-and-authority-analysis.md` — unsupported capabilities, contradictions, and source precedence.
5. `architecture-description-and-ascii.md` — the agreed/current direction that can safely inform a draft diagram.
6. `architecture-diagram-source-analysis-findings.md` and `sources.md` — research-workflow provenance across 30 distinct source documents.

## Diagram discipline

- A full-vision diagram communicates **conceptual capability relationships**, not a commitment to build every module or use a particular cloud product.
- A V1 diagram communicates **planned product scope and technical boundaries**, not the narrower M1 prototype as if it were V1.
- Use solid lines/boxes only for accepted or currently selected direction. Use a clearly labeled dashed treatment for planned-but-unaccepted target state and for replaceable external providers.
- Do not depict AI, OCR, speech, credit scoring, or lending as autonomous writers or decision makers. Suggestions remain distinct from confirmed records and human decisions.

## Scope and provenance caveat

The repository has unrelated uncommitted changes, including the README and current architecture material. They were preserved and inspected only as working context. Source authority in this package is based on accepted specifications and explicit status/date statements, not Git working-tree state.
