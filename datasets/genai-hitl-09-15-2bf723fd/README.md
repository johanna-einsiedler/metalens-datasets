# Generative AI - Human in the Loop

**AI-only** · 10 papers · 16 records · published anonymously

## How to cite

> Haus, Martin (2026). Generative AI - Human in the Loop (version 1) [Data set]. Metalens. https://beta.metalens.tech/dataset?id=2bf723fd-1bdf-4cd1-92e3-4dafa9970cd5

## About this dataset

## What is in here

Performance of humans alone, generative AI alone, and humans working with generative AI on the same decision task, extracted from 10 empirical studies published 2024–2026 (Baek et al., Choi & Schwarcz, Everett et al., Goh et al., Kramer, Qazi et al., Wang et al. 2024, Wang et al. 2025, Woelfle et al., Zöller et al.). The dataset extends the Vaccaro, Almaatouq & Malone (2024) human–AI synergy meta-analysis to large language models.

## Structure

One row per **experiment × human–AI condition × performance measure** (131 rows, 16 experiments). Each row carries the mean, SD and N of the three arms — human alone, AI alone, human + AI — on one metric, plus the study design, the task, the participants and how the AI was presented (`Interaction_Mode`, `AI_Expl_Incl`, `LLM_Model`). Field names follow the original codebook so the rows merge with the 2024 data; `LLM_Model`, `Interaction_Mode` and `N_AI` are additions.

## Coding conventions

- `N_Human` and `N_HumanAI` count human participants; `N_AI` counts independent AI runs (1 for a single deterministic pass). Item counts stay in `Notes`.
- Several AI configurations evaluated alone (for example four prompting methods) are separate rows.
- A human-alone or AI-alone value shared across conditions is repeated in every row it belongs to; a missing arm is null and explained in `Exp_Notes`.
- SDs are recorded only when printed; values computed from CIs or figures are marked `Est_ES = true` with the computation in `Notes`.

## Provenance and verification

Extracted with the Metalens `human-ai-collab` preset (schema id in `metadata.json`) and checked by hand against the source PDFs. Every value has a verbatim evidence quote with its page. Notable decisions: Zöller et al. report no numbers, so all means were recovered from the vector coordinates of their Fig. 3; Baek et al. Mode A is coded as the human baseline, as the authors do; the two within-subject assistance conditions of Wang et al. 2024 were dropped because no AI-alone value exists on the same items.

## Files

`metadata.json` — recipe, preset specification, statistics, credibility badge, this README. `results.json` — one entry per paper with its records, evidence quotes and per-paper provenance (model, prompt hash, extraction time).

## Provenance

- Preset / schema: `human-ai-collab@193067f7`
- Engine: Metalens 0.1.0
- Files: `metadata.json` (recipe, preset spec, stats, credibility), `results.json` (one entry per paper with its records, evidence quotes and per-paper provenance)
- Every value was extracted from the source PDF with a verbatim evidence quote and page; the credibility badge is computed from human verification events.
