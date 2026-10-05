# October experiment ledger

Updated 2026-10-05T21:58:43.332653+06:00. Current working title: **Unseen-Attack Detection under Alert Budgets: A Controlled Study of Local Cluster Normalization**.

## Completed evidence

1,422 study fits: 142 earlier fits plus 960 inner candidate fits and 320 outer refits. The latter cover 40 runs, two datasets, eight methods and five seeds. Notebook demo refits are excluded. A matched ablation rescored 80 saved clustering models with identical centroids, k and preprocessing, producing 640 independently verified operating points with no new fits. In the raw-selected CIC regime, normalization changes mean excluded recall from 29.01% to 40.55% and realized FPR from 1.08% to 1.01%. On UNSW it changes recall from 20.46% to 18.35% and FPR from 1.64% to 2.65%. This existing normalization idea helps the measured CIC population but fails to generalize to UNSW; the ablation is exploratory.

- Phase one: 15 fixed-baseline CIC runs, five source/five-minute-block stress runs and seven capacity fits. The archived Transformer is outside the current direction.
- Phase two: corrected CICIDS2017 targets Web, Authentication, DoS/DDoS, Bot and PortScan; separate UNSW-NB15 targets Exploits, Generic and Reconnaissance. Seeds 11,29,47,71,101.
- Each model has three candidates selected using different excluded groups inside outer training. All choices precede outer scores. Equal candidate counts do not mean equal wall-time searches.
- Independently verified: 960 candidate records, 320 choices, 1,280 operating-point records; zero recorded fingerprint/group overlap and zero outer target in fitting. First-seed checks reconstruct the actual medians/scaler moments/vocabularies of 256 preprocessors.
- Phase three: 2,560 paired pooled/conditional operating-point records from unchanged models; no extra model fits. At the nominal 1% budget, protocol-conditional thresholds reduce absolute test-FPR budget error in 164/320 paired cases, reduce excluded-attack recall in 193/320, and reduce budget error without recall loss in 42/320. All eight models remain in the comparison. This is exploratory reuse of saved evaluation scores, not an untouched confirmation. The general-repair hypothesis is not supported; this intervention is retained as a negative result rather than adopted as an improved detector.
- Main private notebook: 16 executed code cells, no error outputs, code and actual results. HTML is its static export. No slides.
- Twenty scientific figure sets have PNG/PDF/SVG exports. The private paper has 20 cited references, compiled with the existing F-drive MiKTeX, with all final PDF pages visually inspected.

## Measured comparison at nominal 1% calibration budget

The following averages weight each excluded group equally within a dataset, then average five seeds. Recall and realized test FPR are separate; these are not matched-achieved-FPR rankings.

| Dataset | Model | Excluded recall (%) | Realized benign FPR (%) |
|---|---|---:|---:|
| CIC | Autoencoder | 12.81 | 1.18 |
| CIC | DenoisingAE | 14.61 | 1.18 |
| CIC | IsolationForest | 10.43 | 1.13 |
| CIC | KMeans | 29.01 | 1.08 |
| CIC | KMeansLocal | 46.97 | 1.05 |
| CIC | LogisticRegression | 6.71 | 1.17 |
| CIC | MLP | 26.48 | 1.03 |
| CIC | XGBoost | 35.75 | 1.21 |
| UNSW | Autoencoder | 21.83 | 1.57 |
| UNSW | DenoisingAE | 17.21 | 1.52 |
| UNSW | IsolationForest | 10.27 | 1.01 |
| UNSW | KMeans | 20.46 | 1.64 |
| UNSW | KMeansLocal | 16.23 | 2.41 |
| UNSW | LogisticRegression | 31.49 | 2.41 |
| UNSW | MLP | 74.38 | 4.07 |
| UNSW | XGBoost | 63.11 | 3.72 |

## Matched normalization ablation

Each pair fixes centroids, k, preprocessing and rows. Both original inner-selection regimes are retained. Phase-four protocol was frozen before computing this ablation but after inspecting earlier outcomes, so it is exploratory. Each score receives a separate threshold from identical benign calibration rows.

| Dataset | k selected by | Score | Recall (%) | Realized FPR (%) |
|---|---|---|---:|---:|
| CIC | KMeans | Normalized | 40.55 | 1.01 |
| CIC | KMeans | Raw | 29.01 | 1.08 |
| CIC | KMeansLocal | Normalized | 46.97 | 1.05 |
| CIC | KMeansLocal | Raw | 37.78 | 1.09 |
| UNSW | KMeans | Normalized | 18.35 | 2.65 |
| UNSW | KMeans | Raw | 20.46 | 1.64 |
| UNSW | KMeansLocal | Normalized | 16.23 | 2.41 |
| UNSW | KMeansLocal | Raw | 19.46 | 1.54 |

The compact/broad-cluster distance-scale problem motivates this existing radius-normalization rule. Its benchmark-specific benefit, failure on UNSW, component-family results and first-seed paired group intervals are preserved. Thirty-two normalization uncertainty records use 1,000 paired resamples; CIC groups are five-minute blocks and UNSW groups are predictor representatives, not sessions. No general robustness or newly invented algorithm is claimed.

## Calibration intervention

| Dataset | Model | Rule | Recall (%) | FPR (%) | Unsupported target (%) |
|---|---|---|---:|---:|---:|
| CIC | Autoencoder | Pooled | 12.81 | 1.18 | 0.00 |
| CIC | Autoencoder | ProtocolConditional | 8.48 | 1.03 | 0.18 |
| CIC | KMeans | Pooled | 29.01 | 1.08 | 0.00 |
| CIC | KMeans | ProtocolConditional | 13.94 | 0.91 | 0.18 |
| CIC | MLP | Pooled | 26.48 | 1.03 | 0.00 |
| CIC | MLP | ProtocolConditional | 18.75 | 0.92 | 0.18 |
| CIC | XGBoost | Pooled | 35.75 | 1.21 | 0.00 |
| CIC | XGBoost | ProtocolConditional | 22.05 | 1.17 | 0.18 |
| UNSW | Autoencoder | Pooled | 21.83 | 1.57 | 0.00 |
| UNSW | Autoencoder | ProtocolConditional | 32.42 | 1.86 | 0.22 |
| UNSW | KMeans | Pooled | 20.46 | 1.64 | 0.00 |
| UNSW | KMeans | ProtocolConditional | 25.70 | 1.73 | 0.22 |
| UNSW | MLP | Pooled | 74.38 | 4.07 | 0.00 |
| UNSW | MLP | ProtocolConditional | 75.34 | 4.01 | 0.22 |
| UNSW | XGBoost | Pooled | 63.11 | 3.72 | 0.00 |
| UNSW | XGBoost | ProtocolConditional | 63.71 | 3.78 | 0.22 |

The observable group is transport protocol. Each threshold uses only benign calibration scores in that group. A missing group or insufficient support for a finite order-statistic threshold gives infinity: its traffic cannot trigger an automatic alert, and its unsupported fraction is a reported blind spot. No test label chooses a threshold or a winner. Conditional exchangeability is required; arbitrary shift within a protocol remains unresolved.

## Dataset provenance and caveats

- Corrected CICIDS2017 author release: 2,099,976 source rows, 251,547 curated distinct float32 representatives, 82 numeric predictors. Global label-conflict curation and label-dependent sampling are benchmark policies, not deployable preprocessing. Five-minute blocks are neither full sessions nor forward-time evaluation.
- Corrected archive SHA256: `97fdb91d339e2d8cf5627f981b831e5e7e400b981c58181c451a38fd03c48883`.
- UNSW released roles pinned by official counts and independent mirror agreement: 175,341 development / 82,332 evaluation original rows. Curated development 99,268 / evaluation 52,644. Some mirror filenames are reversed. No author checksum certification is claimed.
- UNSW evaluation removes predictor overlap with the full development source and duplicates without consulting test labels. Float32 conversion merged no distinct source predictor groups.
- A later ambiguity audit found 361 remaining test family-conflict groups, four binary-conflicting. Removing these representatives from frozen predictions changes target recall by at most 0.357 percentage points at the 1% budget. Primary results remain unchanged; this is post-hoc changed-population sensitivity.
- UNSW is a separate within-dataset replication with another feature schema; it is not transfer of CIC-trained models. Its released rows do not establish session/host independence. Both sources are laboratory collections.

## Private entry points and verification

Base: `F:/UIU/11th/ML/dep/research_update_2026-10-05/`.

Open `SUPERVISOR_NOTEBOOK.html` or `SUPERVISOR_NOTEBOOK.ipynb`; private manuscript source is `paper_rewrite.tex`, compiled PDF `output/manuscript/paper_rewrite.pdf`. Reproduction commands are in `RUN_GUIDE.md`. `output/final_checks.json`, `nested_verification.json`, `fitted_preprocessing_checks.json`, protocol calibration CSVs and `evidence_manifest.json` preserve checks. The manifest excludes manuscript sources/prose/PDFs and original source archives.

Private manifest SHA256: `98f14a8bc697722fa2d6aa2e533f5e02e34c91da3979d9dc433c881d50befa97`; 7273 hashed private experiment files. The manifest's contents are not published here.

The native editor compiler still has its platform-directory error; successful PDF compilation uses an already-installed F-drive compiler with F-drive cache/config/temp paths. No compiler/plugin was installed. HTML contents/execution were verified; browser screenshot QA was blocked by automatic approval policy, so visual browser QA is not claimed.

No universal winner, SOTA claim, real zero-day discovery, production false-alarm guarantee, or claim that overfitting is solved. Protocol-conditional calibration is established prior art. Exact MCDE/specialized reconstruction baselines and independent forward-time traffic remain publication gates.

The manuscript, LaTeX, PDF, code, datasets, notebooks, figures, checkpoints, raw scores and detailed artifacts remain private on F drive. Only independently written Markdown progress notes belong in this Git repository.
