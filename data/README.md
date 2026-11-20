# Documentary corpus and split

[`SOURCE_LIST.csv`](SOURCE_LIST.csv) is the authoritative source register for the documentary corpus described in Chapter 5 of the report. It records the stable source ID, development/held-out assignment, source title, publisher or owner, source type, number of processing units and original URL.

| Subset | Sources | Processing units | Role in the workflow |
|---|---:|---:|---|
| Development | 8 | 30 | Stage 1 prompt calibration and initial evidence bank used during Stage 2 calibration |
| Held-out | 14 | 30 | Evaluation of the frozen Stage 1 prompt on previously unseen sources |
| Combined | 22 | 60 | Final evidence bank supplied to the frozen Stage 2 prompt |

The split was made at source level. “Held-out” refers specifically to exclusion from prompt development: after both prompts had been frozen, the retained evidence from both subsets was combined for final scoring. The final bank contains 390 development records and 232 held-out records (622 total). The frozen Stage 1 prompt initially returned 238 held-out candidates; six failed the predefined validation rule and were excluded.

The source-document files themselves are not redistributed in this repository. The URLs are provided for provenance; continued availability and unchanged content at those external locations cannot be guaranteed. `Webpage/PDF` identifies a webpage-origin source for which a PDF representation was retained for processing.
