# Prompt-calibration lineage and frozen selection

This document supplements the concise calibration descriptions in Chapter 6
and the development results in Chapter 7. It records why each prompt changed
without reproducing every complete intermediate prompt. Only the final Stage 1
V6 and Stage 2 P5 prompts were used in the frozen workflow evaluated in the
report.

## Stage 1: evidence extraction, V1–V6

The archived mutation log shows five sequential instruction additions. Each
revision responded to failures in the immediately preceding development run.
The complete exact added text and recorded rationale are preserved in
`stage1_mutation_log.original.json`.

| Transition | Observed problem | Targeted change |
|---|---|---|
| V1 → V2 | Webpage page-field violations and non-contiguous or reconstructed quotations, particularly in tables, lists and page boundaries | Added a final item-level self-check for empty webpage page fields, literal quotation matching and shorter uninterrupted spans. |
| V2 → V3 | Omissions, stitched passages and reconstructed passages remained despite schema compliance | Required copying an atomic quotation unit first and verifying it as one literal span. |
| V3 → V4 | Source text was omitted and form/table text was reconstructed around page and layout boundaries | Treated page markers, metadata comments and table boundaries as absolute quotation boundaries. |
| V4 → V5 | Substantial and webpage reconstructions and inserted omission symbols persisted | Made quotation atomicity mandatory and required preservation of visible Markdown markers. |
| V5 → V6 | Some records still removed intervening material, inserted an omission or altered an OCR token | Added a literal-span rejection test immediately before JSON serialization. |

V6 was frozen as `dema-lenient-calibration/evidence-extraction`, Langfuse
prompt version 6. Its checksum is the checksum recorded in the canonical run.
The report's qualitative discussion of researcher inspection also describes
substantive concerns such as eligibility, classification and interpretation
scope. The machine-readable mutation log, however, records the exact V1–V6
instruction additions above, which primarily tightened quotation fidelity and
technical traceability. These two levels should not be conflated.

## Stage 2: maturity scoring

Stage 2 contains two related pieces of calibration provenance.

### Behavioural calibration underlying the scoring baseline

The behavioural study evaluated a documentary-gap-aware baseline and targeted
criterion-application failures. Narrative rules alone did not resolve all
failures. Later versions introduced an assigned-phase requirement matrix,
explicit framework-ambiguity handling and a distinction between mandatory and
conditional wording. The selected behavioural prompt passed 45/45
prespecified calibration checks across 12/12 cases and 23/23 checks across six
temporally separated test cases. The test cases were assistant-authored in the
same session and were not independently blinded. The original compact record is
preserved as `stage2_behavioural_refinement_log.original.md`.

### Final-strategy refinements, P1–P5

The final-strategy sequence then refined the usefulness and internal
consistency of the scoring output. The complete final P5 prompt itself retains
these five refinements verbatim.

| Version | Refinement introduced |
|---|---|
| P1 | Restrict `evidence_supporting_score` to evidence IDs that directly support the assigned phase rather than all broadly relevant evidence. |
| P2 | Include scope-limiting, implementation-limiting, planned-not-operational and partial-attribution records in `contrary_or_limiting_evidence`. |
| P3 | Require `next_phase_gap` to identify the exact missing next-phase requirement and concrete proof needed. |
| P4 | Require concrete organisations, instruments, datasets, platforms, practices or government levels to be named in central claims. |
| P5 | Require a final consistency audit across the phase score, matched criterion, assigned-phase checks, limiting reasoning and next-phase gap. |

P5 was selected for the final workflow. The preserved selection manifest
records 212/217 checks, with no parse, indicator-coverage, citation or phase-gate
failures; five justifications remained below the specified reasoning-depth
threshold. These calibration results concern adherence to the designed scoring
behaviour and do not establish the validity of the empirical Togo maturity
scores.

## Reproducibility boundary

The final prompt files in `../prompts/` are sufficient to inspect the frozen
workflow. The files in this directory document how those prompts were selected
and refined. Intermediate prompt bodies remain in the main research repository
under `prompts/stage1/development/` and `prompts/stage2/development/`; they are
not duplicated here because they were not used in the final evaluated run.

