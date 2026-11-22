# GIMA DEMA reproducibility supplement

This repository accompanies a GIMA MSc internship report on an LLM-assisted documentary pre-assessment of Togo's disaster-related Data Ecosystem Maturity Assessment (DEMA). It publishes the prompt artefacts and output definitions needed to inspect how the two-stage workflow was designed and frozen.

The workflow was intended to prepare structured documentary evidence for expert review. It was not designed to replace stakeholder consultation or produce definitive national maturity scores.

## Workflow

1. **Stage 1 — evidence extraction:** documentary processing units were read, eligible observations were classified at DEMA subdimension level, and exact supporting quotations and interpretation boundaries were returned.
2. **Stage 2 — maturity scoring:** the combined evidence bank was assessed against indicator-specific maturity descriptions to generate provisional phases, evidence-linked reasoning, limitations and next-phase gaps.

## Prompt files

| Stage | Role in calibration | File | SHA-256 |
|---|---|---|---|
| Stage 1 | Calibration baseline (V1) | [`prompts/stage1_baseline_v1.txt`](prompts/stage1_baseline_v1.txt) | `08e557eca5d79ffc677fcf66302f02fb47bf98e2f3d5f127df6bb39e1fb0447b` |
| Stage 1 | Final frozen prompt (V6) | [`prompts/stage1_final_frozen_v6.txt`](prompts/stage1_final_frozen_v6.txt) | `d2436f48ec0c9ff693f2b4f1964adc21e179995ec11905d1bf70902bcd8c355c` |
| Stage 2 | Calibration baseline (P0) | [`prompts/stage2_baseline_p0.txt`](prompts/stage2_baseline_p0.txt) | `883fc330bc82bd2bf5824a80e6f9f518db3fc73e6ac429b505dd7635f1ea619f` |
| Stage 2 | Final frozen prompt (P5) | [`prompts/stage2_final_frozen_p5.txt`](prompts/stage2_final_frozen_p5.txt) | `a3734a364931d5aaa90188c82eee400b0812023a5d4dcb14da70d917067669af` |

The Stage 1 V1 file was the baseline of the recorded V1–V6 calibration series; it was itself derived from an earlier prompt lineage. It should not be interpreted as the first prompt ever written during the research. Likewise, Stage 2 P0 was an already documentary-gap-aware baseline rather than an untouched historical first draft.

The two final prompt checksums correspond with the recorded canonical workflow. The prompt files include the complete instructions, dynamic placeholders, output templates and embedded DEMA framework material supplied to the model.

## Other contents

- [`calibration/`](calibration/) documents the prompt-refinement lineage and preserves the original mutation and selection records.
- [`schemas/`](schemas/) contains the original prompt-level output templates and machine-readable schemas reconstructed from the prompts and runtime checks.
- [`docs/ENVIRONMENT.md`](docs/ENVIRONMENT.md) records the best-supported historical software and model configuration.
- [`docs/REPRODUCIBILITY_LIMITATIONS.md`](docs/REPRODUCIBILITY_LIMITATIONS.md) explains what this archive can and cannot reproduce.
- [`docs/DATA_AVAILABILITY.md`](docs/DATA_AVAILABILITY.md) describes materials intentionally excluded from this public repository.
- [`expert_review/`](expert_review/) records the eight indicator-specific review
  pages and the nine-item expert-review instrument.
- [`data/SOURCE_LIST.csv`](data/SOURCE_LIST.csv) lists all 22 documentary sources,
  their development/held-out assignment, processing-unit counts and source URLs.
- [`data/DEMA_Data_Collection_2026_ENG.xlsx`](data/DEMA_Data_Collection_2026_ENG.xlsx)
  provides the English DEMA assessment workbook used as the framework reference.
- [`outputs/`](outputs/) contains the unchanged complete 622-record evidence
  bank and validated 31-indicator Stage 2 output.

## Recorded configuration

- Model/deployment: `gpt-4.1-students`
- Temperature: `0`
- Docling: `2.94.0` (historical exact pin)
- OpenAI Python SDK: `2.41.0` (historical exact pin; Azure-compatible endpoint)
- Langfuse: local `4.9.0` installation supported by historical metadata; the canonical run manifest did not record the imported package version
- Best-supported Python runtime: Python 3.14; exact patch version was not recorded in the canonical manifest

## Reproducibility boundary

This repository supports inspection of prompt design, prompt evolution, output structure and the recorded final outputs. It does not enable exact end-to-end regeneration by itself: the source-document corpus, credentials and full pipeline implementation are excluded. Hosted model behaviour can also change, so a later execution would be a new run rather than a byte-for-byte reproduction of the recorded outputs.

No API credentials, source-document files, expert identities or confidential Red Cross records are included. The evidence bank does retain contact details reproduced in two quotations from openly accessible source documents; this is documented with the outputs.

## Rights and reuse

The prompts reproduce DEMA framework wording. No public redistribution or open-source licence for that framework material was identified in the research archive. Review [`PUBLICATION_REVIEW_REQUIRED.md`](PUBLICATION_REVIEW_REQUIRED.md) before publishing or licensing this repository.

