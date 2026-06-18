# AI at Work: empirical findings on AI's labour-market effects

Dataset ID: `ai-at-work-2026-06`
Schema version: `ai-jobs-v1`
Created: 2026-06-14T00:00:00Z
Verification: **raw model output — no comprehensive human review performed**

Curated extraction of effect-size findings from 77 research papers studying how generative AI and adjacent technologies affect labour productivity, performance inequality, entry-level employment, and human-AI substitution/complementarity. Each paper contributes one or more quantitative findings (metric · value · comparison · p-value), tagged with subtopic and finding type, plus a paper-level qualitative summary across the four core subtopics. Extracted with Gemini 2.5 Pro via the AI Labour Dashboard pipeline, normalised to the MetaPaperLens ai-findings preset schema.

## Authors

- Ole Teutloff
- Johanna Einsiedler

## Contents

- `results.json` — 77 primary-study extractions (4 conceptual papers with no quantitative findings), 504 effect-size findings in total, 1244 evidence snippets.  One entry per paper.
- `prompt.md` — verbatim ai-findings preset prompt used as the canonical extraction template (sha256 `5bc94c12d611…`).
- `metadata.json` — donor + provenance metadata (authors, dates, schema version, prompt SHA).
- `CITATION.cff` — machine-readable citation block.

## Per-paper output shape

Each paper's `result` object carries:

- `paper_metadata` — title, doi, year, authors, domain, study type, sample, n, technology flag (`is_genai`)
- `subtopics` — paper-level qualitative summary across four canonical subtopics (productivity / inequality / entry_level / substitute_complement), each with `relevance` (strong/moderate/weak) + a one-sentence `finding`
- `findings[]` — every reported quantitative finding as a flat record: `metric`, `value`, `ci_low`, `ci_high`, `unit`, `direction`, `comparison`, `p_value`, `metric_definition`, `note`, `finding_type`, `subtopic`, `evidence_idx[]`
- `evidence[]` — verbatim snippets with `snippet`, `page`, `source`, `field` — `evidence_idx` on each finding indexes into this array
- `extraction_confidence` — three-block self-rating (`paper_metadata` · `findings` · `subtopics`) with `level` + optional `notes`
- `one_line` + `qual_notes` — short and long paper summaries

## Citation

```
Teutloff, O., & Einsiedler, J. (2026).
AI at Work: empirical findings on AI's labour-market effects.
MetaPaperLens dataset `ai-at-work-2026-06`.
```

## Reproducibility

The extractions in `results.json` were produced by passing each primary
study's PDF through the ai-findings preset prompt (see `prompt.md`) and
the `gemini-2.5-pro` model.  `prompt_sha256` in `metadata.json` is the
integrity hash of `prompt.md`; any rerun using the same prompt body and
model family can be checked against this hash for fidelity.

The dataset was assembled via the AI Labour Dashboard project
(<https://github.com/...>) and aligned with the MetaPaperLens canonical
ai-findings schema before donation.

## License

Released under **CC-BY 4.0** — reuse permitted with attribution to the
authors listed above.
