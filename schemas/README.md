# Output definitions

The final model calls did not use Pydantic models or an API-enforced JSON
Schema. The OpenAI Responses API returned JSON objects; output structure was
specified in each frozen prompt and then checked by the internal runtime
validator retained in the complete research archive.

For transparency, this directory contains:

- `stage1_output_template.txt` and `stage2_output_template.txt`: the original
  human-readable output templates copied from the frozen prompt wording.
- `stage1_output_schema.reconstructed.json` and
  `stage2_output_schema.reconstructed.json`: machine-readable Draft 2020-12
  schemas reconstructed from the prompt templates and runtime validation rules.

The JSON schemas are documentary aids. They were **not** passed to the model in
the canonical run and must not be described as original API-enforced schemas.
The runtime validator imposed additional cross-record checks that JSON Schema
cannot fully express, including exact contiguous quotation matching, complete
indicator coverage, evidence-ID resolution, and the Phase 1 documentary-gap
exception.

