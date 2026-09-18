# Reinvest-to-Grow™ model naming audit

Research date: 2026-09-17
Status: research and change inventory only; no product, GitHub, mobile, or archive content was changed.

## Scope and conclusion

This audit covers the central planning repository, its live public GitHub metadata, the linked mobile repository at `/Users/joerice/git/joericearchitect/hrf-reinvest-in-growth/hrf-reinvest-to-grow-mobile-app`, and all 36 Markdown documents in `ai-planning/jpaul-documents/markdown/`.

The screenshot visibly contains the old `-reinvest-in-growth` identifier. The public central GitHub repository currently has the matching name `jizzoe/home-roots-reinvest-in-growth` and the description `This is the parent repo for the "reinvest in growth" program and platform - built for the home roots non-profit`. This is a strong, but not conclusive, match for the cropped screenshot source.

The requested public display name is **Reinvest-to-Grow™ model**. The Unicode `™` character is the small raised trademark glyph requested in the comment; it should be used in human-facing Markdown, HTML, native-app strings, GitHub descriptions, and presentation copy. It must not be forced into machine identifiers that do not support it.

The name correction is larger than a text replacement. JLP's Lexicon explicitly differentiates the **Reinvest-to-Grow™ Theory** from the **Reinvest-to-Grow™ Methodology**. A global replacement of either with `model` would erase that distinction. The safe editorial rule is therefore:

| Concept | Recommended display name | Notes |
| --- | --- | --- |
| Public umbrella / project identity | **Home Roots Foundation's Reinvest-to-Grow™ model** | Use this in headlines, GitHub metadata, and general external descriptions. |
| Theory | **Reinvest-to-Grow™ Theory** | Keep when the text means the evidence-informed explanatory theory. |
| Operating practice | **Reinvest-to-Grow™ Methodology** | Keep when the text means the implementation of the theory. |
| Integrated operating whole | **Enterprise Growth System** | Treat as a system-level concept, not as a synonym for the app or platform. Add a Lexicon definition before it becomes a controlled name. |
| Operational infrastructure | **Enterprise Growth Platform** | The integrated infrastructure for the methodology. |
| Entrepreneur-facing product | **Enterprise Growth App** | The app is a component of the Platform. Do not alternate this with `Recipient App` or `Entrepreneur Application` as a product name. |
| Version 1 module | **Business Journal** (or **Business Journal module** when its component role matters) | Not the entire app or platform. |
| Physical operating business | **Enterprise Supply Hub** | `Supply Hub` is an acceptable short form after first formal use. |
| Staff product | **HRF Administrative Portal** | Replace `Nonprofit Back Office`, `Staff Web`, and similar names when they refer to the same product. |
| Organization | **Home Roots Foundation (HRF)** | Use the full name on first formal mention, then `HRF`. |

This is a working editorial map, not a legal trademark opinion or a decision to redefine JLP's theory. An owner should confirm whether `model` is the public umbrella descriptor as assumed here. Once confirmed, it can become a short naming policy in the Lexicon and repository documentation.

## Changes needed for public docs

### 1. Public GitHub identity — highest priority

| Surface | Current state | Needed change | Constraint |
| --- | --- | --- | --- |
| `https://github.com/jizzoe/home-roots-reinvest-in-growth` | Public name displays `home-roots-reinvest-in-growth`; its description says `reinvest in growth` program and platform. | Rename the repository to a technical slug such as `home-roots-reinvest-to-grow`; set a human-readable description such as `Planning, architecture, and specifications for Home Roots Foundation's Reinvest-to-Grow™ model.` | This is an external GitHub write and needs just-in-time approval. GitHub redirects old URLs, but every current remote reference should still be updated after the rename. |
| Central GitHub Open Graph / search display | No custom Open Graph image; GitHub derives public identity from the repository metadata. | Verify the displayed name, description, social preview, and redirected old URL after the rename. | Preview caches may take time to refresh. |
| `https://github.com/jizzoe/hrf-reinvest-to-grow-mobile-app` | Public mobile description ends with bare `Reinvest-to-Grow.` | Change only the description to use `Reinvest-to-Grow™ model` or a precisely scoped `Enterprise Growth App` description. | The existing mobile repository slug is a technically valid and semantically aligned identifier; it does not need a trademark glyph. This is also an external GitHub write. |

### 2. Central README and its linked public asset

| Location | Current wording or asset | Needed change |
| --- | --- | --- |
| `README.md:1` | `Invest in Growth Technology Planning` | Retitle around the public umbrella, for example `Reinvest-to-Grow™ Model Technology Planning`; confirm whether `Home Roots Foundation` belongs in the H1. |
| `README.md:3` | Describes `Invest in Growth` as the program and uses bare `Reinvest-to-Grow methodology`. | Replace the generic program name with the approved umbrella name; retain `Methodology` only where the sentence means the operating practice. |
| `README.md:11` | `Invest in Growth will support women entrepreneurs...` | Use `The Reinvest-to-Grow™ model...` or `Home Roots Foundation's Reinvest-to-Grow™ model...`. |
| `README.md:25` | `Reinvest-to-Grow is based on...` | Apply the trademarked display form and a semantically accurate descriptor, for example `The Reinvest-to-Grow™ model is based on...`. |
| `README.md:68` | Uses the role label `Staff web`. | Use `HRF Administrative Portal` if it means the staff product described in the JLP PRD. |
| `ai-planning/architecture/microlending-ngapp-architecture.png` | README-linked visual asset; filename is legacy `microlending-ngapp`; visible boxes say `Recipient Mobile App` and `Nonprofit Back Office`. | Replace or regenerate the diagram. Use `Enterprise Growth App` and `HRF Administrative Portal`; rename the asset to a neutral current name such as `enterprise-growth-platform-architecture.png`, then update the README link and alt text. |
| `ai-planning/PROJECT_SUMMARY.md` | General-audience project summary with `Mobile Bookkeeping Project Summary`, `Recipient Business App`, `Nonprofit Back-Office App`, microloan-first positioning, and the same legacy architecture image. | Treat it as public-risk content because it reads like a shareable project overview in a public repository. Rewrite it around the Reinvest-to-Grow™ model and current product hierarchy, or explicitly retire/move it before sharing the repository with funders. Do not apply a word-only replacement: its scope narrative is old. |

### 3. JLP material that is investor-, partner-, or reader-facing

The complete JLP corpus contains 36 Markdown files. Twenty-nine contain a Reinvest naming form. The seven files below expose `Reinvest to Grow` in a filename and H1; two additional duplicate deck copies contain bare `Reinvest-to-Grow` in body copy. Rename the file and its H1 together, then repair inbound Markdown links.

| Current path / visible H1 | Required branded-form correction | Publication note |
| --- | --- | --- |
| `ai-planning/jpaul-documents/markdown/Reinvest to Grow Master Architecture Version 3.1 Final.md` | Change the visible brand to `Reinvest-to-Grow™`; select a semantic title such as `Reinvest-to-Grow™ Master Architecture v3.1`. | Exact duplicate of the nested Supporting Documents copy. Select one canonical source before editing or publishing. |
| `.../Supporting Documents/Reinvest to Grow Master Architecture Version 3.1 Final.md` | Same correction. | Same content as the root-level duplicate. |
| `.../Reinvest-to-Grow™ Methodology Book/Reinvest To Grow Investor Deck 3.1 Draft 1.md` | `Reinvest-to-Grow™ Investor Deck 3.1 Draft 1`. | Investor-facing draft; correct before sending externally. |
| `.../Reinvest-to-Grow™ Methodology Book/Reinvest To Grow Investor Deck 3.1 Draft 2.md` | `Reinvest-to-Grow™ Investor Deck 3.1 Draft 2`. | Investor-facing draft; correct before sending externally. |
| `.../Reinvest-to-Grow™ Methodology Book/Reinvest to Grow Book Chapters Preface.md` | Use `Reinvest-to-Grow™` in the file and H1. | Reader-facing manuscript material. |
| `.../Reinvest-to-Grow™ Methodology Book/Reinvest to Grow Book Chapters, An Evidence Based Theory of Enterprise Transformation.md` | Use `Reinvest-to-Grow™` in the file and H1; retain `Theory` where semantically intended. | This document also uses Theory, Methodology, Framework, and System; use the editorial map above rather than normalizing all of them to `model`. |
| `.../Reinvest-to-Grow™ Methodology Book/The Reinvest to Grow Theory.md` | `The Reinvest-to-Grow™ Theory`. | The title can be corrected exactly without changing its theory/methodology distinction. |
| `ai-planning/jpaul-documents/markdown/Final Deck 2027 Part 8.md:219` and the duplicate `.../Pitch Deck/Final Deck 2027 Part 8.md:219` | `That aligns with Reinvest-to-Grow™.` | The two files are byte-for-byte duplicates; edit one canonical source or keep both deliberately synchronized. |

The following JLP documents already use the trademarked form prominently and should be retained as references for public copy: `Reinvest-to-Grow™ Methodology Summary.md`, `HRF Strategy Stack.md`, `HRF Investment Thesis.md`, `Final Deck 2027 Version 9.md`, the Software Engineer Brief, and the Executive Product Brief.

### 4. User-facing mobile application copy

The mobile app contains five live human-facing name sources. All should display the exact same Unicode string: **`Reinvest-to-Grow™ model`**, subject to the owner confirming that `model` belongs in the app's display name rather than only its description.

| Mobile path | Current value | Needed change | Notes |
| --- | --- | --- | --- |
| `app.json:3` | `expo.name: "Reinvest to Grow"` | Set the approved display name. | This feeds Expo configuration and generated native labels. |
| `android/app/src/main/res/values/strings.xml:2` | `<string name="app_name">Reinvest to Grow</string>` | Set the same approved display name. | This is the Android launcher/application label. |
| `src/i18n/en.json:59` | `"title": "Reinvest to Grow"` | Set the approved display name. | The current app does not appear to render this key, but it is a future UI/localization source and must not drift. |
| `src/i18n/fr.json:59` | `"title": "Reinvest to Grow"` | Set the identical proper name, not a translated or re-spaced brand. | Proper-name capitalization and trademark glyph should remain stable across locales. |
| `src/i18n/ht.json:66` | `"title": "Reinvest to Grow"` | Set the identical proper name. | Same rule as English and French. |
| `android/settings.gradle:34` | `rootProject.name = 'Reinvest to Grow'` | Update as part of the native configuration refresh if it is retained as a human-readable build label. | Primarily an internal build label, but it should not preserve the old display name. |
| `README.md:1-2` in the mobile repository | Technical H1 and a bare `Reinvest-to-Grow.` description. | Keep a technical repository H1 if desired, but update the descriptive sentence to use the approved display form. | Public repository copy. |

After the source change, build a new Android artifact and confirm the launcher label on a device. The currently published APK will continue to show the old label until rebuilt; building or publishing is a separate authorized action.

## Changes needed for internal docs

### 1. Core central-repository identity and governance

These are live internal control documents. They should use the new umbrella name in prose, while keeping theory and methodology terms where their specific definitions matter.

| Location | Current issue | Needed change |
| --- | --- | --- |
| `AGENTS.md:16` | Calls the initiative `Invest in Growth` and uses bare `Reinvest-to-Grow methodology`. | State the current public identity as `Home Roots Foundation's Reinvest-to-Grow™ model`; retain `Methodology` only as the named operating practice. |
| `docs/sdd-workflow.md:5,11` | Calls this the `Invest in Growth planning repository`. | Update the repository/product identity clause and add the approved short-name rule. |
| `openspec/config.yaml:4-5` | Product context says `Invest in Growth technology planning` and bare `Reinvest-to-Grow`. | Update the living OpenSpec context. |
| `openspec/specs/cross-repository-architecture/spec.md:5,13` | Living specification says `Invest in Growth`. | Update the accepted current specification; do not alter the archived copy merely to revise its history. |
| `ai-planning/design-briefs/m0-sdd-and-product-foundation.md:10` | Prose says `Invest in Growth needs...`. | Update the human-readable product name; keep literal repository names as technical identifiers until an actual rename occurs. |
| `ai-planning/ALIGNMENT_BRIEF_v0.1.md:5,20,36,264` | Bare `Reinvest-to-Grow` and ambiguous `current model` wording. | Apply the umbrella name and add the Theory/Methodology distinction to the brief's terminology section. |
| `ai-planning/design-briefs/Reinvest-to-Grow Methodology Synthesis and V1 Design Brief.md` | The rendered H1 already has `™`, but the filename omits it. | Decide whether filenames use the trademark glyph. If yes, rename the file and repair links; if no, record a machine-safe filename policy and keep rendered headings trademarked. |
| `ai-planning/research/mobile-text-to-speech/whisper-vosk-local-stt/sources.md:9,16` | Publisher says `Home Roots / Invest in Growth planning repository`. | Update source-record publisher metadata without changing third-party source claims. |
| `ai-planning/research/tech-research/speech-to-text-and-text-to-speech/sources.md:4,13,22,31,40,49` | Publisher says `Invest in Growth planning repository`. | Update current repository publisher metadata. |

### 2. JLP source-corpus consistency and controlled vocabulary

The JLP Lexicon is the strongest internal naming authority found. It already defines the Theory, Methodology, Enterprise Supply Hub, and Enterprise Growth Platform. The controlled vocabulary needs three extensions before broad cleanup:

1. Record **Reinvest-to-Grow™ model** as the general public umbrella descriptor, if the owner confirms this interpretation of the comment.
2. Define **Enterprise Growth System** and specify how it differs from the Platform. JLP uses the term 41 times, but the Lexicon does not currently define it.
3. Define product aliases and forbid unintended replacements: `Enterprise Growth App` is the product name; `Business Journal` is its V1 module; `Entrepreneur Application` and `Entrepreneur Mobile Application` are descriptive phrases, not peer product names.

The following internal source cleanups are needed after that policy exists:

| Source / group | Inconsistency | Needed action |
| --- | --- | --- |
| `Jizzoe App Suggestions.md` | Preserves an older `Mobile Bookkeeping Project Summary` with `Recipient Business App`, `Nonprofit Back-Office App`, microloan-first framing, and `mobile recipient app`. | Treat it as historical/advisory input, not a current naming authority. Add a clear historic/source label or rewrite its framing when it is intentionally retained. |
| `ai-planning/PROJECT_SUMMARY.md` | Mirrors that older naming model and is likely to drift from current product truth. | Rewrite or archive as superseded; do not leave it as an apparently current project summary. |
| `ai-planning/BUILD_VS_BUY_ANALYSIS.md` | Uses `recipient`, `nonprofit back office`, and microloan-first category labels. | Preserve terminology when it quotes/evaluates a vendor category, but revise its project framing, diagrams, and recommendations to use `entrepreneur`, `HRF Administrative Portal`, and the broader model. |
| `ai-planning/INTERNAL_ARCHITECTURE_ANALYSIS_v0.1.md`, `ai-planning/ALIGNMENT_BRIEF_v0.1.md`, older handoff/research plans | Mix `recipient`, `back office`, `staff web`, `microloan`, and `microlending` with current names. | Mark historical comparisons clearly; update current recommendations and diagrams. Do not alter transcripts or quoted original requests. |
| `ai-planning/architecture/microlending-ngapp-architecture.png`, `ai-planning/PROJECT_SUMMARY.md`, `ai-planning/BUILD_VS_BUY_ANALYSIS.md` | `Recipient Mobile App` / `Recipient Mobile Experience`, `Nonprofit Back Office`, and microlending image filename contradict the JLP hierarchy. | Use `Enterprise Growth App` and `HRF Administrative Portal`; reserve `growth capital` for the broader financing concept and `microloan` only for a specific loan product or historical source. |

There are four exact duplicate pairs in the JLP source corpus. They create a repeat-drift risk: a correction can be made in one public-looking file but not its twin.

| Duplicate content | Recommended management action |
| --- | --- |
| Root and nested copies of `Building the Enterprise Growth Platform, An Introduction for Software Engineers and Technical Partners, Software Engineer Brief v1.0.md` | Choose the nested PRD copy or another designated canonical path; replace the other with a provenance note or retain it only if synchronization is automated. |
| Root and nested `Final Deck 2027 Part 8.md` | Same canonical-source decision. |
| Root and nested `Jizzoe Feedback.md` | Same canonical-source decision. |
| Root and nested `Reinvest to Grow Master Architecture Version 3.1 Final.md` | Correct the brand title only after selecting a canonical copy; otherwise both must be changed together. |

### 3. Mobile repository internal configuration and evidence

The mobile repository was inspected but not changed. Its internal cleanup should follow the public display update.

| Location | Needed action |
| --- | --- |
| `AGENTS.md:22`, `docs/sdd-workflow.md:5`, `openspec/config.yaml:5`, `docs/brand-assets.md:13` | Update bare human-readable `Reinvest-to-Grow` references to the approved display rule. |
| `docs/translation-review/ht-review-2026-09.md:79` | Update the recorded title values only as part of the approved localization change; preserve the review status and evidence context. |
| Mobile `openspec/config.yaml:11` | Update the central GitHub owner/repository reference only after the central repository is actually renamed. |
| `android/settings.gradle:34` | Keep aligned with the new human display label if native files remain committed. |

Do **not** mechanically rename these technical identifiers simply to add a trademark or spaces:

- the mobile GitHub repository name `hrf-reinvest-to-grow-mobile-app`;
- Expo `slug` `hrf-reinvest-to-grow` and the EAS project identifier;
- Android application ID and Kotlin namespace `org.homerootsfoundation.reinvesttogrow`;
- SQLite database name `reinvest-to-grow-m1.db`;
- npm package name and `package-lock.json` identity; or
- the existing checkout directory names.

Changing those identifiers can break app upgrades, local data continuity, build/OTA association, automation, or historical evidence. Treat each as a separately planned migration with redirects or compatibility checks where applicable.

### 4. Literal `reinvest-in-growth` inventory and archive boundary

The pre-report audit found 37 literal matches for `reinvest-in-growth` outside `.git`. This report and its sources intentionally quote the term seven times as evidence, so a later repository-wide search returns 44 matches. The original 37 locations are not all erroneous public copy:

- The public GitHub repository name and description are the immediate display-name problem and should be changed after approval.
- Current working documents use the old name in URLs, local checkout paths, and repository references. Update those only after the actual GitHub/local-path migration, so they remain true.
- Planning/evidence files record actual historical local paths. Preserve the historical statement or add a dated migration note rather than rewriting the past.
- Archived OpenSpec change packages contain repository URLs, paths, and completed-check evidence. Do not bulk-edit them: their literal paths and URLs are audit evidence of what was approved and verified at the time.

The complete pre-report inventory is below. It is the full list to review when planning an actual repository rename.

**Current or non-archive references — update only when the underlying GitHub/local identifier changes (18 matches):**

- `ai-planning/design-briefs/V1 Scope Map and Milestone Plan.md:305`
- `ai-planning/design-briefs/m0-sdd-and-product-foundation.md:10,62,63`
- `ai-planning/evidence/m0-foundation-closure-audit.md:35,43`
- `ai-planning/handoff-docs/m1-receipt-slice-reset-and-restart-handoff.md:26`
- `ai-planning/handoff-docs/m1-receipt-slice-session-handoff.md:40,42`
- `ai-planning/handoff-docs/m1.2-live-sync-session-handoff.md:44,214`
- `ai-planning/plans/m1-receipt-slice-cleanup-and-restart-plan.md:157,167,177,191,202`
- `ai-planning/research/tech-research/ai-coding-evals-and-invariants/ai-coding-evals-and-invariants-findings.md:127`
- `docs/sdd-bootstrap-evidence.md:5`

**Archived OpenSpec evidence — preserve as historical truth (19 matches):**

- `openspec/changes/archive/2026-08-15-define-api-contract-conventions/tasks.md:3`
- `openspec/changes/archive/2026-08-15-define-core-domain-model/tasks.md:3`
- `openspec/changes/archive/2026-08-15-define-cross-repository-architecture/design.md:36`
- `openspec/changes/archive/2026-08-15-define-cross-repository-architecture/proposal.md:7,36`
- `openspec/changes/archive/2026-08-15-define-cross-repository-architecture/tasks.md:3`
- `openspec/changes/archive/2026-08-15-define-v1-product-guardrails/proposal.md:35`
- `openspec/changes/archive/2026-08-15-define-v1-product-guardrails/tasks.md:3`
- `openspec/changes/archive/2026-08-15-prototype-manual-offline-transaction/verification.md:37`
- `openspec/changes/archive/2026-08-17-m1-manual-offline-delivery/design.md:5`
- `openspec/changes/archive/2026-08-17-m1-manual-offline-delivery/evidence/autonomous-sdd-controller.json:9`
- `openspec/changes/archive/2026-08-17-m1-manual-offline-delivery/handoffs/mobile-dispatch.md:7`
- `openspec/changes/archive/2026-08-17-m1-manual-offline-delivery/linkage.md:5`
- `openspec/changes/archive/2026-08-17-m1-manual-offline-delivery/proposal.md:13`
- `openspec/changes/archive/2026-08-17-m1-manual-offline-delivery/tasks.md:5`
- `openspec/changes/archive/2026-08-18-prototype-speech-proposal-confirmation/handoffs/mobile-dispatch.md:7`
- `openspec/changes/archive/2026-08-18-prototype-speech-proposal-confirmation/linkage.md:17`
- `openspec/changes/archive/2026-09-06-prototype-receipt-capture-ocr-review/handoffs/mobile-dispatch.md:7`
- `openspec/changes/archive/2026-09-06-prototype-receipt-capture-ocr-review/linkage.md:19`

This distinction matters because changing every literal string before renaming the actual repository would leave documentation pointing to a name that does not yet exist; changing archived evidence afterward would destroy historical accuracy.

## Other naming inconsistencies found

| Inconsistency | Evidence | Recommendation |
| --- | --- | --- |
| `Invest in Growth` vs `Reinvest-to-Grow™ model` | README, AGENTS, SDD workflow, OpenSpec context/living spec, M0 design brief, and research-source publisher metadata retain `Invest in Growth`. | Retire `Invest in Growth` as a current product/program name unless the owner explicitly says it is a separate program brand. The JLP corpus does not use it. |
| `Reinvest to Grow`, bare `Reinvest-to-Grow`, and `Reinvest-to-Grow™` | Seven JLP filenames/H1s use spaced forms; two duplicated deck lines use bare hyphenated form; mobile display strings use the spaced form. | Standardize visible brand text as `Reinvest-to-Grow™`; use the semantic qualifier from the editorial map. |
| Model / Theory / Methodology / Framework / System | JLP uses 214 `Methodology`, 37 `Theory`, 23 `Framework`, and 41 `Enterprise Growth System` mentions. | Do not collapse them. Define their relationship in the Lexicon and apply the user-approved `model` term only as umbrella public language unless a deeper semantic change is approved. |
| Platform / App / Entrepreneur Application / Business Journal | JLP uses 337 `Enterprise Growth Platform`, 71 `Enterprise Growth App`, 4 `Entrepreneur Application`, 5 `Entrepreneur Mobile Application`, and 45+ Business Journal mentions. | Use the Platform → App → Business Journal hierarchy. Retire aliases as stand-alone product names. |
| `Recipient` / `Business owner` / `Entrepreneur` | The legacy Project Summary, Jizzoe App Suggestions, and image use `Recipient`; JLP's current product material centers entrepreneurs. | Use `entrepreneur` for the primary person/role. Reserve `recipient` for a specific program-administration context only if it is intentionally defined. |
| `Nonprofit Back Office`, `Staff Web`, and `HRF Administrative Portal` | README, legacy diagram, Project Summary, research docs, and JLP Appendix D vary. | Standardize on `HRF Administrative Portal`; choose an allowed short form only after it is defined. |
| `microloan` / `microlending` vs `growth capital` | Legacy planning materials are microloan-first; JLP frames financing as one element of the broader methodology. | Use `growth capital` in model/platform framing. Use `microloan` only when describing a particular lending product, historic source, or vendor category. |

## Recommended implementation order

1. Confirm the one public-identity decision: `Reinvest-to-Grow™ model` is the umbrella descriptor, while Theory and Methodology retain their JLP meanings.
2. Approve a short naming policy and add it to the JLP Lexicon plus the central README/SDD context.
3. Make the public GitHub repository rename and description update, then update current remote references and verify redirects.
4. Correct the central README, replace its public architecture visual, and either rewrite or retire the legacy Project Summary.
5. Update the mobile display name, localized title values, Android launcher label, and mobile GitHub description; rebuild and verify the resulting Android app label.
6. Normalize active internal docs and source metadata, select canonical JLP source locations, and repair links after any filename changes.
7. Preserve archived OpenSpec and historical evidence; add migration notes when historical repository names need context.

## Research method and residual decisions

- Read-only scans covered both repositories, current public GitHub metadata, the supplied screenshot, the README-linked architecture image, and all 36 JLP Markdown documents.
- The JLP Lexicon and Methodology Summary were treated as the strongest sources for semantic distinctions. Old architecture summaries, transcript material, prompts, and archived evidence were treated as historical context, not controlling naming authority.
- The research workflow ran at deep depth with 32 distinct sources. Its embedded Codex recommendation was `gpt-5.6-sol` and explicitly marked stale-risk; the current official OpenAI documentation retrieved on 2026-09-17 identifies GPT-6 Astra as the most capable current model. No session model was changed.
- The remaining material decision is whether `model` is an umbrella descriptor only or whether the owner intends to replace other JLP terms. This report assumes umbrella-only because the existing Lexicon gives Theory and Methodology different meanings.

See `sources.md` for the detailed source provenance.
