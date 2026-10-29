# Release Notes

## v1.1.30
GH#1100 retrospective repair — two bindings that resolved, validated and served while feeding the wrong artefact.

`analyse-data`'s slot is labelled **"Data"** and was bound to Strategic Recommendation, so the data-analysis stage received the *recommendations* that are supposed to follow from it. Re-bound to Feature Comparison Matrix, which is the structured comparison data the stage exists to analyse.

`check-input-gaps`'s slot is labelled **"Inputs Provided"** and its prompt body heads that section `### Inputs Provided` — it reviews what the USER supplied in order to report gaps. It was bound to Data Analysis, so it was auditing the pipeline's own output for completeness instead of the brief. This is `from_step` where `from_input` was needed: a new required `competitor_brief` workflow input now carries it.

**This flow now requires an input it did not require before.** That is the fix, not a regression: previously the user supplied nothing for this slot and the gap-check silently received the pipeline's own analysis output instead of their brief. A required input that is explained is the correct trade against a wrong value that was never visible. No step in this flow produces a brief, so no binding to any step could have been right.

## v1.1.29
GH#1100 consumer wave (batch 4) — declare the data flow this workflow was resolving positionally.

Each stage below now receives its input through a declared `bindings:` entry instead of `default_from_previous`, which K-073 revoked. **The value is unchanged**: each binding names the step that actually produces what the stage consumes. What changes is that the dependency is stated rather than inferred from position, so a reorder can no longer silently feed a stage the wrong artefact.

Bindings added:
  `analyse-data` ← `source: from_step "Strategic Recommendation"` (step 6)
  `check-input-gaps` ← `source: from_step "Data Analysis"` (step 7)

Dependency pins moved to the published versions that declare these slots:
  `analyse-data` 1.0.3 → 1.0.4
  `check-input-gaps` 1.0.4 → 1.0.5
  `polish-language` 1.0.6 → 1.0.7
  `strategic-recommendation` 1.0.1 → 1.0.2

## v1.1.28
GH#858 (A1) — fix the broken analysis handoff that hard-failed the run (*"Strategic Recommendation halted: SWOT analysis and positioning map narrative inputs are empty"*). The bundle shipped `feature-comparison-matrix` and `swot-generator` prompts and the docs said to run them, but the `execution:` block never did — so the brief-writer's SWOT/feature/positioning inputs resolved empty. Restored the intended bound graph: added a **Feature Comparison Matrix** step and a **SWOT Analysis Generator** step (each with a backing skill so they are `from_step`-addressable), ordered `competitor-profiling → feature-comparison → swot-analysis → market-positioning-analysis → strategic-recommendation`, and rewired every cross-step input to an **explicit `from_step` binding** (`{{step.context.*}}`) instead of positional/mis-pointed `{{steps.<Title>.output}}` refs. Each downstream step now receives the real upstream artifact (K-045). No new required inputs beyond the feature matrix's product name/capabilities. Also completed the tail: repinned `polish-language` 1.0.1→1.0.6 (the version that exposes the bindable `source` slot) and bound `language-polish`'s `source` ← the Strategic Recommendation brief, so the `output_step` polishes the actual competitive brief rather than its positional previous (the input-gap-check decision) — correct end-to-end, not just non-failing.

## v1.1.27
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.26
GH#745 — declare per-step `output: {name, type}` on every execution step (competitors/list, positioning_map/text, recommendations/text, analysis/text, input_gaps/decision, polished_analysis/text). Lights up the #744 rich flow-map. Content-only; no bindings or logic changes.

## v1.1.25
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 9 inline shared-content files and declare 9 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.24
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.23
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.22
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.21
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.20
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
