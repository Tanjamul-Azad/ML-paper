# 2026-10-05 independent-device completion

Updated 2026-10-06T00:03:21.295987+06:00. Latest counts, manuscript identity and interpretation supersede earlier completion sections below. These are original progress notes, not manuscript text.

Completed 1,522 scientific fits: 142 earlier + 960 nested candidates + 320 outer refits + 100 independent-device fits. Display operations and notebook demonstration refits are excluded. The new batch has 20 source configurations, nine scoring methods, 1,440 source/transfer operating points, 1,520 third-device operating points and 960 fixed-centroid floor-ablation points. Reference and floor changes use no new detector fits.

Canonical private files: `SUPERVISOR_NOTEBOOK.html`, `SUPERVISOR_NOTEBOOK.ipynb`, `paper_rewrite.tex` and `output/manuscript/paper_rewrite.pdf`, under `F:/UIU/11th/ML/dep/research_update_2026-10-05/`. One notebook contains 20 executed code cells and no error outputs. There are 28 Matplotlib PNG/PDF/SVG figure sets and 22 resolved cited references. All 12 final PDF pages were visually inspected. HTML export and notebook execution passed; HTML browser screenshot inspection was blocked by automatic approval policy.

## Independent traffic and direct published-method comparison

UCI author N-BaIoT release: [dataset](https://archive.ics.uci.edu/dataset/442/detection+of+iot+botnet+attacks+n+baiot), [dataset DOI](https://doi.org/10.24432/C5RC8J). The three devices have 1,018,298 / 835,876 / 1,098,677 valid original rows; prepared populations have 132,849 / 87,393 / 252,104 rows and 115 predictors. All benign data and a fixed 12% attack fingerprint sample are retained before first-float32-representative deduplication. Identities, labels and original row positions are metadata, not predictors.

Two source devices, Gafgyt/Mirai exclusions, seeds11/29/47/71/101. Target devices never enter source model/preprocessor fitting. Overlap is removed against the entire valid source fingerprint inventory without consulting target labels. Row guards do not establish chronological or session independence. Model settings are fixed; MCDE unspecified settings are documented choices rather than exact author equivalence.

| Method | Source recall / FPR (%) | Device-transfer recall / FPR (%) |
|---|---:|---:|
| RawCluster | 50.08 / 1.85 | 50.00 / 63.74 |
| LocalRadius | 49.96 / 1.62 | 49.96 / 78.50 |
| DiagonalCluster | 99.39 / 0.24 | 99.69 / 64.51 |
| HGB | 99.95 / 0.75 | 100.00 / 51.79 |
| MCDE | 99.95 / 0.64 | 100.00 / 51.27 |
| IsolationForest | 90.51 / 0.82 | 89.02 / 28.96 |
| Autoencoder | 99.98 / 1.51 | 99.98 / 64.04 |
| RePO | 99.98 / 0.91 | 99.98 / 52.78 |
| RePOPlus | 99.98 / 0.85 | 99.98 / 53.28 |

Third-device results, nominal 1%. All methods share the trusted-pool budget within each source condition. Zero observed FPR is not a future guarantee.

| Method / adaptation | Held-out recall (%) | Known recall (%) | FPR (%) |
|---|---:|---:|---:|
| MCDE / Frozen | 100.00 | 100.00 | 98.00 |
| MCDE / ThresholdOnly | 0.00 | 0.00 | 0.00 |
| MCDE / ReferenceAndThreshold | 99.91 | 99.96 | 3.25 |
| HGB / ThresholdOnly | 96.48 | 99.94 | 0.53 |
| Autoencoder / ThresholdOnly | 99.78 | 99.78 | 0.00 |
| RePO / ThresholdOnly | 99.79 | 99.79 | 0.00 |
| RePOPlus / ThresholdOnly | 99.82 | 99.82 | 0.00 |

## Controlled interventions and mechanism

MCDE source empirical ranks saturate: values beyond each reference maximum share a terminal score. All 20 third-device threshold-only cases set that terminal threshold and suppress held-out detection. Splitting the same trusted benign pool into reference and threshold roles restores rank ordering, while keeping every detector fixed. No clean-traffic contamination defense or distribution-free drift guarantee is tested.

Global-floor / unweighted-median / observation-weighted-median third-device recall: 35.84 / 43.48 / 61.15%; achieved FPR rounds to 0.34% for each. Radius changes keep identical centroids, assignments and fitted transformations. Weighted results depend heavily on seed, including no seed11 gain. All alternatives and failures remain visible.

## Population and uncertainty limits

Full precision audit finds 185,207 / 186,870 / 185,518 additional distinct raw64 vectors merged into float32 groups, across Doorbell/Thermostat/Philips respectively. This is not a raw64 model rerun. After complete source overlap exclusion, the Philips target has Doorbell-source residual Gafgyt286/Mirai267 and Thermostat-source Gafgyt660/Mirai20,000 (cap); each case has 40,000 target benign rows. Macro averages weight cases equally and are not full natural-traffic effectiveness. Five seeds repeat these observations.

First-seed uncertainty uses 1,000 source-file/original-row-block resamples and is descriptive, not independent-device or multiplicity-adjusted inference. Independently verified: 1,440 phase5 decisions, 1,520 phase6 decisions, 960 phase7 decisions, 1,200 direct-count rank checks, source configuration identity and target-role separation. Paper checks reproduce 64 historical table pairs, 18 new source/transfer pairs and 30 target-adaptation cells from CSVs.

Protocols phase5/6/7 and all pre-score amendments are saved with SHA256. Private output/final_checks.json and evidence_manifest.json identify the final evidence. The manifest excludes every manuscript source/PDF and manuscript-prose generator. The PDF SHA256 is 163436aa7faaa4d7c15ac4272804dc345517843d360aeb77ce8c31503a3d2dd0. Old hashes below are historical and superseded.

Target: the next available ACSAC Reproduction and Replication (R+R) cycle. [Official 2026 CFP](https://www.acsac.org/2026/submissions/papers/) is the latest verified rule set: IEEEtran 1.8b, conference/compsoc, US Letter, anonymous, unchanged class layout, 11 main pages and at most five reference/appendix pages. The 2026 May 26 submission deadline passed; 2027 dates and rules are unverified. Current PDF: 12 pages, comprising 11 main pages and one reference page. All six tables and five figures precede the bibliography; there is no trailing appendix. The working title omits the track prefix. Add R+R: only if actually submitting to that ACSAC track, where the prefix is required. This is a scientific-fit recommendation, not an acceptance prediction.

No SOTA claim, universal encoder-redundancy claim, discovered zero-day exploit, production FPR guarantee or claim that overfitting is solved. This is a bounded laboratory replication and failure analysis. It does not include timestamp-verified future traffic, all-device replication, a raw64 population rerun or exact unpublished author settings.

The manuscript, LaTeX, PDF, code, datasets, notebooks, figures, checkpoints and raw scores remain private on F drive. GitHub receives only these separately written Markdown progress summaries. Never add the private research folder to this repository.

---

## Earlier record, preserved for history

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
