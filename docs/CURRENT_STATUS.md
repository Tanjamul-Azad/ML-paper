# Current status

Updated: 2026-09-18. Phase: **audit and experiment design complete; development pilot complete; publication experiments pending**.

## Completed

- Read the complete local LaTeX source, both bibliography representations, and all 38 notebook cells, including saved outputs/metadata.
- Inspected every supplied figure and both diagrams from the ZIP.
- Inspected the public Kaggle notebook: Version 1, failed at `KeyError: 'Label'`, zero output files. Its UI reports dual T4; local notebook metadata reports no accelerator. Neither proves the later reported experiments ran in that saved version.
- Audited all 2,520,798 cleaned 2017 rows, all eight raw 2017 CSVs, and all three supplied 2018 CSVs.
- Confirmed float32 feature duplicates and contradictory labels by exact feature comparison.
- Reconstructed the notebook's seed-42 stratified split and counted cross-split feature-hash overlap.
- Searched primary literature and publisher/author records; identified close prior work and multiple bibliographic discrepancies.
- Executed a fresh development pilot with XGBoost, scaled logistic regression, MiniBatchKMeans, Isolation Forest, AE, and three budget-split unions.
- Verified CUDA training on the local RTX 4060 and recorded runtime/environment.
- Prepared methodology, metric definitions, experimental matrix, figure specification, publication gates, and portable handoff notes.

## Findings that control the next phase

| Finding | Status |
|---|---|
| Original feature selection leaks test-label information | Verified from code |
| 23,536 extra duplicate float32 feature rows; 718 conflicting binary-label groups | Verified exact comparisons |
| 7,572 / 504,160 reconstructed test rows share feature hashes with training | Verified hash overlap; not an exact pairwise cross-split comparison |
| Supplied 2018 subset has no web-attack labels | Verified full label counts |
| AE, SHAP and PSI generation code missing from supplied/public notebook | Verified in the available version; other private versions may exist |
| Prior XGBoost/SHAP/AE and clustering-based unknown-attack work exists | Verified primary literature |
| Pilot clustering replaces AE without loss | **Not supported** |
| Overfitting/generalization solved | **Not established** |
| Manuscript ready for submission | **No** |

## Remaining work

1. Corrected dataset acquisition, semantic schema checks, capture/session grouping and production provenance.
2. Locked multi-family, temporal and external-dataset experiments with fair tuning and at least five seeds.
3. Calibration/false-alarm tradeoff analysis, explanation stability, drift controls and failure-case analysis.
4. Complete original-reference verification; rebuild the bibliography from verified metadata.
5. Generate final tables/figures from one immutable result store, then rewrite manuscript privately.
6. Compile and inspect the complete final PDF. A local compile attempt was blocked by an uninitialized MiKTeX profile; no PDF layout pass has been claimed.

## Missing evidence

No saved original predictions, trained models, split indices, AE training code, SHAP sampling code, 2018 column map, or PSI bins were supplied. These gaps prevent independent confirmation of legacy scores. Full production data/compute runs have not been completed. The provided audio was preserved; the supervisor assessment uses the user's written account, not an independent transcription.
