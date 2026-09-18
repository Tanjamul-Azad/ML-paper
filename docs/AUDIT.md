# Scientific and implementation audit

Evidence: complete private `main.tex`, `references.bib`, `mlpaper.ipynb`, supplied figure images, full streaming data audit, and public [Kaggle Version 1](https://www.kaggle.com/code/tanjamulazad/mlpaper), inspected 2026-09-18. Notebook cell indices below are zero-based.

## Blocking issues

| ID | Evidence / defect | Consequence | Required repair |
|---|---|---|---|
| A01 | Cell 18 computes feature correlations and correlations with all labels; cell 20 splits afterward | Test labels influence feature selection and later CV | Split first; fit every learned transform within each training fold |
| A02 | Cleaned float32 features retain exact duplicates and label conflicts | Exact overlap and ambiguous targets undermine evaluation | Canonicalize before grouping; quarantine conflicts transparently; keep duplicate groups in one partition |
| A03 | Random row split mixes the same capture days/campaigns | Generalization may reflect campaign/host artifacts | Preserve source file, session/host and time; evaluate blocked splits and external data |
| A04 | Cell 24 passes test labels to `eval_set`; no early stopping or separate validation appears | Test is monitored during training; manuscript's 10% validation and patience 20 are unsupported | Use a dedicated validation partition; final test is evaluated once. Passing eval_set alone is not gradient training on the test set |
| A05 | Cells 30 onward fit LR/MLP on unscaled values; StandardScaler imported but never used; cost-sensitive tuning differs across models | Poor baselines do not establish XGBoost superiority | Fit scaling inside folds; tune each model fairly; report convergence and class weighting |
| A06 | No withheld attack family in original protocol | Benign-only AE training does not prove unknown-family or zero-day coverage | Leave attack families out of all fitting, tuning, feature selection, pretraining and calibration |
| A07 | No AE, SHAP, PSI implementation in the available notebook; post-cell-8 saved execution absent | Results cannot be traced to a complete run | Recover full artifacts or independently reimplement with provenance |
| A08 | TreeSHAP described as explaining both tree and neural anomaly decisions | Explanations assigned to the wrong model/score | TreeSHAP explains XGBoost; AE requires reconstruction contributions or an appropriate explainer of its scalar score |
| A09 | Three 2018 days contain FTP/SSH brute force and DoS, no web attacks | Cross-year web-attack validation is absent | Acquire relevant web days and corrected provenance; report the actual subset |
| A10 | Large PSI called significant concept drift and actionable adaptation | Neither conditional-label drift nor adaptation benefit is demonstrated | Say distribution/attribution shift; calibrate alarms, add controls, test downstream impact |
| A11 | Close prior work and many citation metadata mismatches | Novelty gap matrix is unreliable | Rebuild from primary literature, distinguishing unknown entries from absent capabilities |

## Claim corrections

- **Unknown is operationally defined relative to training**, not to all human knowledge. A held-out family experiment is a proxy for novelty, not proof of detection of real zero-day vulnerabilities.
- Binary aggregate F1 is not web-family recall. DoS and scan volume can dominate the metric while rare web attacks fail.
- E-commerce framing is not an algorithmic contribution. CIC is a general laboratory network dataset; the current data do not support production e-commerce security claims.
- The actual labels do not include CSRF. Do not add it to the dataset description.
- SHAP feature effects describe a model under a specified explanation convention. They are not causal evidence about attack mechanisms. Similarity of category averages does not validate attack-type inference by an analyst.
- A rounded AUROC of 1.0000 is not necessarily perfect ranking. Store and report unrounded values and uncertainty.
- A zero-day detector cannot discover an attack absent from every observed sample. It may flag a novel sample when such a sample arrives; labeling it malicious requires evidence.
- A score over different datasets is affected by capture design, feature extraction and prevalence. It cannot be attributed solely to an evolution in attack strategies.
- Updating selected features is not a demonstrated safe way to retrain a tree ensemble or prevent catastrophic forgetting.

## Internal consistency

| Item | Observation |
|---|---|
| Feature arithmetic | 78 numeric input columns minus 8 constants = 70, not 71; one duplicate header feature is also present |
| Search space | Notebook uses estimators {200,300,500}; methodology lists {100,200,500} |
| Final parameters | Hard-coded in cell 24 rather than taken from saved `best_params_`; search outputs unavailable |
| LR AUROC | Separate ROC figure/table: .8466; combined ROC/PR image: .8482 |
| MLP AUROC | Separate ROC/table: .6875; combined ROC/PR: .6933 |
| SHAP sample | Text alternates between all test rows and 5,000; sampling artifact unavailable |
| Global/drift importance | Claim that both highest-PSI features also top global importance conflicts with image: Packet Length Variance is not in its top 20 |
| Review count | Nineteen/twenty-one in prose; 20 rows of compared studies and 22 inline bibliography entries |
| Bibliography file | `references.bib` contains a LaTeX bibliography environment and an end-document command, not BibTeX records; main.tex uses a separate inline bibliography |
| Diagram captions | Claimed hybrid AE/drift architecture is absent from both supplied conceptual diagrams |
| Environment | Package installation warnings and inconsistent saved accelerator metadata prevent a trusted environment reconstruction |

## Legacy confusion-matrix arithmetic

The displayed matrix contains TN=418606, FP=406, FN=27, TP=85121; N=504160. Its arithmetic is internally coherent: accuracy=.99914115, precision=.99525296, recall=.99968291, F1=.99746301 and benign FPR=.00096895. This verifies arithmetic only, not provenance or validity. That FPR corresponds to approximately **969 false alarms per million benign flows**, so calling 406 false positives operationally negligible requires a workload and alert-aggregation model.

Overfitting remains unresolved: no learning curves, across-seed variance, robust temporal test, family holdouts or external predictive evaluation were supplied. Existing leakage is confirmed; the magnitude of its impact on scores has not been measured by a controlled ablation.
