# Register-data claims — agent (Danish)

Stated causal claims from nine economics papers that use Danish administrative register data, extracted by a four-pass agentic pipeline: each claim is anchored to a sentence of the abstract, refined by the introduction, and linked to the printed table and figure results that support it, with verbatim evidence quotes throughout.

**AI-only** · 9 papers · 62 records · by Johanna Einsiedler

Keywords: causal claims, Danish register data, administrative data, economics, labor supply, taxation, evidence extraction

## How to cite

> Johanna Einsiedler (2026). Register-data claims — agent (Danish) (version 1) [Data set]. Metalens. https://github.com/johanna-einsiedler/metalens-datasets/tree/main/datasets/register-data-claims-agent-danish-4d724d9c

## About this dataset

Stated causal claims from nine economics papers that use Danish administrative register data, extracted by an agentic pipeline (prompt `stated_claims_v3_agent.md` in the danish-register-econ repository): the abstract decides which claims exist, the introduction refines them, and every supporting table or figure result is recorded with its printed value and a verbatim quote. One of the nine papers prints no abstract and therefore yields no claims under the anchor rule, so the dataset holds 62 claims from eight papers. Result timings carry numeric horizons (years since the event) where the paper's labels allow it. Cited table values were cross-checked deterministically against an independently extracted regression-tables dataset: of 147 table-cited values, 141 match exactly and 0 mismatch (6 cite a table the companion extraction did not transcribe); 56 further results cite figures. Cause and effect phrases resolve into a reviewed concept vocabulary (v1).

**Verification status: none of the records has been individually human-verified yet.** The verification ledger in this release records machine extraction and withdrawn spot checks only; full human review is in progress.

## Included papers

- Henrik Jacobsen Kleven, Martin B. Knudsen, Claus Thustrup Kreiner, Søren Pedersen, Emmanuel Saez (2011). Unwilling or Unable to Cheat? Evidence From a Tax Audit Experiment in Denmark. Econometrica. https://doi.org/10.3982/ecta9113 — 11 records
- Henrik Jacobsen Kleven, Esben Anton Schultz (2014). Estimating Taxable Income Responses Using Danish Tax Reforms. American Economic Journal Economic Policy. https://doi.org/10.1257/pol.6.4.271 — 4 records
- Claus Thustrup Kreiner, Søren Leth-Petersen, Peer Ebbesen Skov (2016). Tax Reforms and Intertemporal Shifting of Wage Income: Evidence from Danish Monthly Payroll Records. American Economic Journal Economic Policy. https://doi.org/10.1257/pol.20140233 — 7 records
- Petter Lundborg, Erik Plug, Astrid Würtz Rasmussen (2017). Can Women Have Children and a Career? IV Evidence from IVF Treatments. American Economic Review. https://doi.org/10.1257/aer.20141467 — 10 records
- Henrik Kleven, Camille Landais, Jakob Egholt Søgaard (2019). Children and Gender Inequality: Evidence from Denmark. American Economic Journal Applied Economics. https://doi.org/10.1257/app.20180010 — 10 records
- Itzik Fadlon, Torben Heien Nielsen (2021). Family Labor Supply Responses to Severe Health Shocks: Evidence from Danish Administrative Records. American Economic Journal Applied Economics. https://doi.org/10.1257/app.20170604 — 8 records
- Wolfgang Keller, Hale Utar (2023). International trade and job polarization: Evidence at the worker level. Journal of International Economics. https://doi.org/10.1016/j.jinteco.2023.103810 — 7 records
- Mathias Fjællegaard Jensen, Ning Zhang (2026). Effects of Parental Death on Labor Market Outcomes. American Economic Review. https://doi.org/10.1257/aer.20240432 — 5 records

## Provenance

- Preset / schema: `register-claims@f7387875`
- Engine: Metalens 0.1.0 (commit 514313878dab)
- Files: `metadata.json` (recipe, preset spec, stats, credibility), `results.json` (one entry per paper with its records, evidence quotes and per-paper provenance)
- Every value was extracted from the source PDF with a verbatim evidence quote and page; the credibility badge is computed from human verification events.
