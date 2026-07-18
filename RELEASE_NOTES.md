# Release Notes

## v1.2.0
GH#863 (K-045 intent/output-mismatch) — wire the two previously-uninvoked instrument prompts into the pipeline so it now delivers the interview guide and survey questions it promises. Added execution steps `interview-guide-design` (interview-guide-builder) and `survey-question-design` (survey-question-writer), each derived from the research plan and sequenced after Survey Design, before the insight report. Added two backing skills (Interview Guide Design, Survey Question Design) so the `from_step` bindings resolve. Converted positional/title prompt refs to explicit `context_params` bindings (interview-guide-builder, survey-question-writer, insight-report-prompt). Re-pinned polish-language to 1.0.6 and bound language-polish `source` ← Insight Extraction. Skills 3→5, total 14→16.

## v1.1.29
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.28
GH#745 — declare per-step `output: {name, type}` on every execution step (interview_synthesis/text, research_plan/text, insights/text, analysis/text, masked_data/text, polished_report/text, evidence_report/text, merged_findings/text). Lights up the #744 rich flow-map. Content-only; no bindings or logic changes.

## v1.1.27
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 9 inline shared-content files and declare 9 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.26
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.25
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.24
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.23
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.22
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
