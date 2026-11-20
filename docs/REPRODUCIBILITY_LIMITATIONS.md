# Reproducibility limitations

This public supplement provides the complete baseline and final prompts for both workflow stages, their checksums, calibration records, output definitions, the complete evidence bank and the validated final Stage 2 output. It allows readers to inspect the instructions and recorded outputs and verify that the final prompt files match the recorded identities.

It does not contain:

- the 22-document research corpus or archived third-party source files;
- expert-review material or stakeholder workshop records;
- API credentials or hosted-service configuration;
- a complete historical Python lockfile;
- the full pipeline implementation.

Consequently, this archive supports methodological and output inspection but not standalone end-to-end rerunning. Exact output regeneration is also not guaranteed because hosted model and service behaviour may change. The saved outputs, rather than a future rerun, remain the authoritative record of the evaluated workflow.

The exact Python patch version and imported Langfuse SDK version were not captured by the canonical-run manifest. The environment document reports the strongest historical evidence without presenting it as a complete run lockfile.

The reconstructed JSON Schemas were not passed to the model. They document the combined prompt and runtime-validation contract. The original prompt-level templates are supplied separately in `schemas/`.

