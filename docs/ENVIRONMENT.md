# Historical software and model environment

The table distinguishes recorded configuration from information reconstructed from historical dependency files and installed-package metadata.

| Component | Best-supported value | Evidence status |
|---|---:|---|
| Model/deployment | `gpt-4.1-students` | Recorded in the canonical-run manifest and final prompt configurations |
| Temperature | `0` | Recorded prompt and pipeline configuration |
| Python | 3.14 | Historical pipeline documentation; exact patch version not recorded by the canonical run |
| Docling | `2.94.0` | Exact historical dependency pin |
| OpenAI Python SDK | `2.41.0` | Exact historical dependency pin and matching pre-run installation metadata |
| Langfuse Python SDK | `4.9.0` locally installed | Matching pre-run installation metadata and final-workspace minimum requirement; not recorded in the canonical manifest |
| Azure Identity | `1.25.3` | Exact historical pipeline pin for optional Entra authentication |

The implementation used the OpenAI Python SDK through an Azure OpenAI-compatible endpoint, rather than the legacy `azure-ai-openai` package. No endpoint, deployment credential, API key or local environment file is included here.

The hosted prompt versions were Stage 1 version 6 and Stage 2 version 1 (the P5 strategy). These are prompt-management versions and must not be confused with the Langfuse SDK package version.

