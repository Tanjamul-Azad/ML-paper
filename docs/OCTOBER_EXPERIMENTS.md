# October experiment ledger

Updated 2026-10-05 (Asia/Dhaka). This is a progress record, not manuscript text. The user reconfirmed that the paper must never reach GitHub. Public scope remains these Markdown notes only.

## Scope and decisions

- Supervisor meeting: 2026-10-06. Show code with executed notebook outputs; user explicitly rejected slides.
- Transformer is no longer required. Fifteen primary runs had completed with its baseline; preserve this history, but follow-ups use six core alternatives without it.
- Direction: test reconstruction necessity, model capacity and excluded-family detection under benign false-alarm constraints. No confirmed new algorithm, SOTA or deployment claim.
- The original draft's e-commerce/adaptation narrative is superseded by a flow-IDS empirical study. A complete manuscript rewrite exists privately; final-test evidence and compilation/layout are not complete.

## Measured work and provenance

| Item | Record |
|---|---|
| Author-corrected source | [CNS2022 release](https://intrusion-detection.distrinet-research.be/CNS2022/Dataset_Download.html), CICIDS2017 improved ZIP |
| Source SHA256 | `97fdb91d339e2d8cf5627f981b831e5e7e400b981c58181c451a38fd03c48883` |
| Source / prepared rows | 2,099,976 / 251,547 |
| Predictors | 82; exclude identity, IPs, ports, timestamp, label and attempted flags |
| Corrected attempted policy | 11,979 attempted rows mapped to benign following release guidance |
| Quality exclusions | 598 invalid/nonfinite physical rows; label-conflicting groups and duplicate representatives also removed |
| Primary namespace | `corrected-cic2017-v1`: five excluded groups × seeds42/123/2026 =15 runs,105 model fits |
| Stress namespace | `corrected-cic2017-blocks-v1`: five groups × seed42 =5 runs,30 fits |
| Sensitivity namespace | `web-sensitivity`: three AE widths and four additional cluster counts =7 fits |
| Total | 20 main runs;142 study fits; a separate notebook KMeans refit is a demonstration, not independent evidence |
| Verification | 1,300 main metric records plus7 sensitivity records recomputed from saved scores |
| Notebook | 10 code cells successfully executed; includes real training, displayed outputs, tables and plots |
| Evidence inventory | 628 private experiment files hashed; manuscript excluded from that inventory |
| Inventory SHA256 | `a3690af64dbc44d2f24ba069edc187fc306b67b8c7deee920cf4bdb87bbc9234` |
| Hardware | RTX4060,8GiB GPU;15.62GiB RAM; all research files/cache on F drive |

## Protocol summary

All target-group rows stay out of train, validation, benign reference mapping and calibration. Primary known-data allocation is50/10/10/10/20; training capped at80,000. Models share supervised training rows; anomaly models use the benign subset. Preprocessing is fitted on the corresponding training data. Four nominal FPR budgets:0.1%,0.5%,1%,2%. The actual test FPR is always a separate measurement.

The primary population is fingerprint-deduplicated. The secondary split separates source-file/five-minute blocks and puts all target-containing blocks entirely in test. This changes the population and is not chronological, host-independent or a causal split-only ablation. Stress analysis, MLP fusion and capacity checks are exploratory additions after inspecting earlier results.

Full-source conflict exclusion and label-dependent sampling are benchmark-curation choices. They can alter difficulty and prevalence; do not describe the pipeline as universally leakage-free or its precision as a deployment estimate. Three seeds reuse the same excluded examples.

## Findings that change the research decision

1. Primary Web MLP recall averaged93.91%; paired seed42 was97/104. Block stress detects10/104. Thus the apparent primary advantage is not robust to this grouping change.
2. Baseline KMeans32 detects89/104 Web flows in both paired settings. Baseline AE latent16 detects0/104. These are not universal model rankings: performance varies substantially across the five target groups.
3. Longer-training sensitivity weakens any claim that AE is useless: latent4 detects70/104 at0.847% actual FPR. Latent16/32 remain at0. KMeans8/16 also detect0.
4. Exploratory KMeans64 detects89/104 at0.815% actual FPR; KMeans128 detects90/104 at0.954%. Neither catches any of13 SQL-injection examples. The best-looking inspected setting is not a confirmed selected model.
5. AE latent4's recovered rows are exclusively brute force: pooled Web recall67.31%, within-Web family-macro recall31.96%. Report family failures alongside pooled scores.
6. Primary XGBoost--MLP rank fusion has promising complementary coverage, but was added post-hoc. Established rank aggregation is not algorithmic novelty. The high-recall block XGBoost--KMeans fusion exceeds the nominal FPR on test and must not be sold as an achieved1% result.

## Private evidence map

Workspace subfolder: `research_update_2026-10-05/` (outside this Git repository).

- `SUPERVISOR_NOTEBOOK.ipynb`: executed notebook. Its `.html` is the same notebook's easy-to-open static view.
- `paper_rewrite.tex`: private rewritten research draft; **never publish**.
- `runs/`: five partition manifests per main run, fitted scalers/models, raw scores, neural histories, configs and result/verification JSON.
- `data/preparation_report.json`: complete counts, feature list, quality rules and source hash.
- `output/`: derived metrics, live-demo checks and notebook execution record.
- `figures/`: ten consistent PNG/PDF/SVG figure sets. No figure upload is authorized.

The notebook may be viewed with saved outputs elsewhere, but rerunning needs the private supporting data/code/artifacts. Cloud execution has not been tested. The public notes do not themselves provide full reproducibility.

## Remaining gates

Freeze nested family/model selection and untouched external or forward-time evaluation. Compare tuning budgets; test attempted-label/conflict-curation policy; quantify family/block uncertainty; investigate SQL-injection failures. Finish full-text comparison with the closest hybrid and clustering studies. Review authorship and every rewritten claim. The built-in LaTeX compiler returned `Unable to find standard directories for platform`; no successful manuscript compile or rendered layout review is claimed.

Original files remain preserved. Existing slide-style preview was abandoned after the user's steering and is not a deliverable. Do not upload artifacts or manuscript to Kaggle, Colab, GitHub, or another service without a separate explicit instruction.

Final local checks matched all 30 primary manuscript table entries and all seven sensitivity rows against recorded results. Eleven in-text reference keys resolve to bibliography entries; the revised manuscript contains no em dashes. This is a source/arithmetic check, not a successful PDF compile. Notebook preview screenshot QA was rejected by automatic approval policy; its actual code execution and metrics were verified.
