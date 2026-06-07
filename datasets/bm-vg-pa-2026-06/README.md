# Pairwise effect sizes: body mass, video gaming, physical activity (10 studies)

Dataset ID: `bm-vg-pa-2026-06`
Schema version: `masem-effect-sizes-v2`
Created: 2026-06-07T00:00:00Z
Verification: **raw model output — no human review performed**

Direct-information MASEMiner extraction of pairwise effect sizes between body-mass measures (BMI, fat mass, waist), video-game use, and physical activity, from 10 primary studies. Sample-level metadata (sample size, country, mean age, % female, clinical status) is included. Extracted with the Marker 2022 prompt and gpt-5.5 — provided as the first worked example for the metalens-datasets repository.

## Authors

- Caroline Marker — Human-Computer-Media Institute, University of Würzburg, Germany
- Timo Gnambs — Johannes Kepler University Linz, Austria; Leibniz Institute for Educational Trajectories, Bamberg, Germany
- Markus Appel — Human-Computer-Media Institute, University of Würzburg, Germany

## Source paper

This dataset corresponds to the meta-analytic synthesis published as:

> Marker, C., Gnambs, T., & Appel, M. (2022). Exploring the myth of the chubby gamer: A meta-analysis on sedentary video gaming and body mass. Social Science & Medicine, 301, Article 112325.
> DOI: 10.1016/j.socscimed.2019.05.030
> https://doi.org/10.1016/j.socscimed.2019.05.030

The 10 primary-study JSON files in `results.json` are the per-paper
extractions that feed that meta-analysis.

## Contents

- `results.json` — 10 primary-study extractions, 17 samples in total, 53 pairwise effect-size records.  One entry per paper; samples within a paper are reported as separate analytic groups where the study disaggregated them.
- `prompt.md` — the verbatim prompt used for extraction (sha256 `49f9dcd66dfe…`).
- `metadata.json` — donor + provenance metadata (authors, dates, schema version, prompt SHA).
- `CITATION.cff` — machine-readable citation block.

## Citation

```
Marker, C., Gnambs, T., & Appel, M. (2026).
Pairwise effect sizes: body mass, video gaming, physical activity (10 studies).
MetaPaperLens dataset `bm-vg-pa-2026-06`.
```

## Reproducibility

The extractions in `results.json` were produced by passing each primary
study's PDF through the Marker 2022 prompt (see `prompt.md`) and the
`gpt-5.5` model.  `prompt_sha256` in `metadata.json` is the integrity
hash of `prompt.md`; any rerun using the same prompt body and model
family can be checked against this hash for fidelity.

## License

Released under **CC-BY 4.0** — reuse permitted with attribution to the
authors listed above.
