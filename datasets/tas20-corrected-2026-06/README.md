# TAS-20 factor-analytic results: LLM extractions with curator corrections

Dataset ID: `tas20-corrected-2026-06`
Schema version: `masem-cfa-v1`
Created: 2026-06-16
Verification: **human-verified against a manually-curated coding sheet**

Curated factor-analytic extractions from 20 primary TAS-20 (Toronto Alexithymia Scale-20) studies covering 30 distinct samples. Each entry carries the model-extracted factor loadings (up to 5 factors × 20 items), factor correlations, and study/sample metadata, plus a `human_overrides[]` array that records every cell where the curator-corrected ground-truth Excel disagrees with the LLM extraction. Extracted with GPT-5.5 via the MetaPaperLens MASEMiner CFA preset; ground truth from Schroeders & Gnambs' corrected coding sheet.

## Authors

- Ulrich Schroeders
- Timo Gnambs

## Contents

- `results.json` — 20 primary-study extractions, 30 samples in total. One entry per sample; corrections live in `paper.human_overrides[]`.
- `prompt.md` — verbatim MASEMiner CFA extraction prompt rendered with TAS-20 parameters (sha256 `cb7053af8678…`).
- `metadata.json` — donor + provenance metadata.
- `CITATION.cff` — machine-readable citation block.

## Per-sample output shape

Each entry under `paper.entries[]` carries:

- **Study/sample metadata** — `country`, `lang`, `n`, `female`, `age`, `clinical`, `res`, `nfac`, `cfa`, `met`, `rot`
- **`factor_loadings`** — dict keyed `F<f>.<i>` (f∈1..5, i∈1..20). `null` means "not loaded on this factor" or "factor not extracted"; `0` is the curator's convention for "item does not load on this factor in a CFA with fixed simple structure".
- **`factor_correlations`** — dict keyed `R<a>.<b>` (e.g. `R1.2` = correlation between factor 1 and factor 2). 10 cells max for a 5-factor model.
- **`evidence`** — verbatim snippets from the PDF supporting each extracted value (where present).
- **`extraction_confidence`** — per-block self-rating from the model.

At the paper level, `paper.human_overrides[]` carries every cell where the curator-corrected coding disagrees with the LLM extraction:

```json
{
  "entry_index":    0,
  "field_path":     "factor_loadings.F3.10",
  "original_value": 2.08,
  "final_value":    0.208,
  "human_override": true
}
```

## Accuracy summary (LLM vs. curator-corrected ground truth)

| Block | Cells | LLM-correct | Errors | Rate |
|---|---|---|---|---|
| Factor loadings (any cell with a printed value, including 0) | 2,020 | 2,019 | 1 | **99.95%** |
| Factor correlations (sensitivity, denominator = curator-reported cells) | 127 | 118 | 9 | sensitivity **0.929** |
| Factor correlations (precision, denominator = LLM-extracted cells) | 124 | 118 | 6 | precision **0.952** |

Remaining errors (10 cells across 3 papers):
- `gülec2009` F3.10 — decimal-point misread (LLM=2.08 vs Excel=0.208)
- `joukamaa2001` — 6 correlation cells where the LLM swapped values between the two sub-samples (male/female)
- `thorberg2010` — 3 correlation cells the LLM missed entirely (R1.2, R1.3, R2.3)

Additional 103 metadata-level overrides are LLM omissions on the `clinical/res/rot/met/female/country` fields where the LLM returned `null` and the curator has a value — these are systematic non-extractions, not value disagreements.

## Citation

```
Schroeders, U., & Gnambs, T. (2026).
TAS-20 factor-analytic results: LLM extractions with curator corrections.
MetaPaperLens dataset `tas20-corrected-2026-06`.
```

## Reproducibility

The extractions in `results.json` were produced by passing each primary study's PDF through the MASEMiner CFA prompt (see `prompt.md`) and the `gpt-5.5` model. `prompt_sha256` in `metadata.json` is the integrity hash of `prompt.md`; any rerun using the same prompt body and model family can be checked against this hash for fidelity.

The 20 source papers cover the TAS-20 multilingual validation literature: Bagby 1994, Besharat 2008, Bolat 2017, Boutemy 2000, Chung 2003, De Gucht 2004, Erni 1997, Fukunishi 1997, Gülec 2009, Joukamaa 2001, Kamm 2016, Loiselle 2001, Moriguchi 2007, Müller 2003, Pinaquy 2002, Popp 2008, Preece 2018, Seo 2009, Thorberg 2010, Watters 2019.

## License

CC-BY-4.0.
