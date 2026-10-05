# Decision record

## D09 - October evidence and user steering (2026-10-05)

Corrected data and 142 study fits now exist; read OCTOBER_EXPERIMENTS before interpreting the older pilot. Transformer is no longer required. Keep completed results but omit it from required follow-up work. Deliver one executed notebook with a static HTML view, not slides. The complete paper rewrite stays private. Notebook, manuscript, figures, models and data must never be staged or pushed.

AE/clustering necessity remains empirical: clustering32 survives Web block stress, smaller AE capacity recovers attacks, and successful clustering still misses SQL injection. Do not present post-hoc selection as independent confirmation. Next selection needs inner families with fresh outer evidence. No new architecture is established as novel. Prose must be natural, precise and citation-supported, without em dashes or generic AI-style claims.

## D01 - Rebuild evaluation before editing performance claims (2026-09-18)

Reason: label-aware feature selection precedes the split, remaining duplicates cross the reconstructed split, baselines are unevenly prepared, and saved execution is incomplete. Keep legacy figures as historical evidence only. A high score alone does not diagnose model overfitting; the protocol is already sufficient reason to rerun.

## D02 - Use flow-based NIDS as the supported scope

Current inputs are numerical network-flow statistics. E-commerce is a possible motivating application, not a validated deployment domain. Remove claims of detecting SQL payload semantics, CSRF, preventing named breaches, or protecting a production shop unless appropriate new data/evidence is collected.

## D03 - Supervisor advice becomes a falsifiable comparison

Clustering is a sensible low-cost baseline. Its unsupervised nature does not make AE redundant: distance-to-prototype and reconstruction error model different properties. Keep AE as a comparator; do not require it in the final framework. Include an anomaly branch only if its incremental unseen-family detection justifies its false alerts and cost. The first pilot does not support automatic AE-to-clustering substitution.

## D04 - Transformer is optional, NLP models are deferred

For current tabular features, test a compact FT-Transformer only after tree, linear, MLP and anomaly baselines are correct. BERT/T5/LLM use requires a defensible input representation and task, such as request text or packet sequences, with new provenance and leakage controls. No architecture inherently guarantees unknown-attack detection.

## D05 - Narrow the candidate contribution

Candidate research question: **When does adding an anomaly detector improve unseen-family intrusion detection at a fixed false-alert budget, and does that gain survive dataset repair and distribution shift?**

This is an empirical hypothesis, not an established novel algorithm. The possible contribution is a rigorous, reproducible answer with failure analysis, budget allocation controls, and explanation checks. Do not claim that clustering, SHAP, conformal calibration, union fusion, or their combination is new without a closer literature comparison.

## D06 - Treat the current pilot as development only

All three web-attack categories were withheld together, but other flows came from the same capture week; flow hashes cannot replace host/session/time independence. Original dataset errors, one seed, fixed untuned models and only 21 SQL-injection examples limit conclusions. Freeze these results and do not repeatedly tune against this fold as though it were unseen final evidence.

## D07 - Separate public notes from private research artifacts

Only named Markdown notes and a restrictive `.gitignore` belong in the public repository. Manuscript, datasets, notebook, source figures, audio, model files and row-level predictions remain outside the repository. Preserve original files. No automatic future scheduling was requested or configured; updates are made during actual work sessions.

## D08 - Diagnose shift before proposing adaptation

PSI is a distribution discrepancy statistic; 0.2 is not a calibrated significance test. Between-dataset SHAP changes can result from schema/extractor differences, class mix or benign-network differences. Use fixed references and controls. Adaptation and any claimed benefit require a separate prequential evaluation with explicit label delay and training cost.

## 5 October completion and narrower direction

1,422 study fits: 142 earlier fits plus 960 inner candidate fits and 320 outer refits. The latter cover 40 runs, two datasets, eight methods and five seeds. Notebook demo refits are excluded. A matched ablation rescored 80 saved clustering models with identical centroids, k and preprocessing, producing 640 independently verified operating points with no new fits. In the raw-selected CIC regime, normalization changes mean excluded recall from 29.01% to 40.55% and realized FPR from 1.08% to 1.01%. On UNSW it changes recall from 20.46% to 18.35% and FPR from 1.64% to 2.65%. This existing normalization idea helps the measured CIC population but fails to generalize to UNSW; the ablation is exploratory.

At the nominal 1% budget, protocol-conditional thresholds reduce absolute test-FPR budget error in 164/320 paired cases, reduce excluded-attack recall in 193/320, and reduce budget error without recall loss in 42/320. All eight models remain in the comparison. This is exploratory reuse of saved evaluation scores, not an untouched confirmation. The general-repair hypothesis is not supported; this intervention is retained as a negative result rather than adopted as an improved detector.

Simple classifier/clustering fusion is already close prior art, including [MCDE](https://www.mdpi.com/1099-4300/28/9/1026). The current intervention instead audits an observable protocol-specific calibration rule, an established conditional-calibration idea. It is an application and failure analysis, not invented mathematics. Claims require joint recall/FPR reporting and unsupported-group disclosure.

No universal winner, SOTA claim, real zero-day discovery, production false-alarm guarantee, or claim that overfitting is solved. Protocol-conditional calibration is established prior art. Exact MCDE/specialized reconstruction baselines and independent forward-time traffic remain publication gates.

Native compiler failure is superseded for actual PDF delivery by the working existing F-drive MiKTeX route. All final PDF pages were inspected. The full private notebook executed with 16 cells. The manuscript and supporting artifacts remain private.
