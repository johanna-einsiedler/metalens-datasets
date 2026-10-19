# Claims in Danish register-data economics papers — release v1

Frozen on 2026-10-19 · content sha256 `7da9e34889e9166b52697509a79fe12d8341e89ff219961ea7de2e8fab357712` · AI-only · 238 papers

## How to cite

Johanna Einsiedler (2026). Claims in Danish register-data economics papers (version 1) [Data set]. Metalens. https://metalens.tech/dataset?id=6d23ec08-85a5-471a-93d5-a8edc1aae41e

## Files

- `release.json` — what this release is, and per row layout the columns it offers
- `tables/entries.json` — one row per stated claim (1837 rows)
- `tables/results.json` — one row per table result (11137 rows)
- `evidence.json` — the quote, page and source behind every cell that has one (`cells[unit][row index][column]` → `items`)

Quotations are cut to at most 200 characters around the extracted value, the snippet length publishers' text-and-data-mining terms allow for published output; a cut end is marked with an ellipsis. The full quotations are kept with the dataset on Metalens, where its owner reviews them against the papers.

Every value was extracted from the cited paper; columns marked `derived` are computed from extracted values by the stated formula. Made with Metalens.
