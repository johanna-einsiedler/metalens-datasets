# Claims in Danish register-data economics papers — release v1

Frozen on 2026-10-20 · content sha256 `a895eef0f4a508959ae3d4ae9be2e47c2267f4352dc563418b5fd11db80f1314` · AI-only · 238 papers · DOI [10.5281/zenodo.23514504](https://doi.org/10.5281/zenodo.23514504)

## How to cite

[author] (2026). Claims in Danish register-data economics papers (version 1) [Data set]. Metalens. https://doi.org/10.5281/zenodo.23514503 https://doi.org/10.5281/zenodo.23514504

## Files

- `release.json` — what this release is, and per row layout the columns it offers
- `tables/entries.json` — one row per stated claim (1832 rows)
- `tables/results.json` — one row per table result (11121 rows)
- `evidence.json` — the quote, page and source behind every cell that has one (`cells[unit][row index][column]` → `items`)

Quotations are cut to at most 200 characters around the extracted value, the snippet length publishers' text-and-data-mining terms allow for published output; a cut end is marked with an ellipsis. The full quotations are kept with the dataset on Metalens, where its owner reviews them against the papers.

Every value was extracted from the cited paper; columns marked `derived` are computed from extracted values by the stated formula. Made with Metalens.
