# Experiment plan — preregistration draft v0.1

Status: proposed final study. No full production experiment or final result has been completed. Freeze this protocol after the closest-paper review and corrected-data inspection; record every subsequent deviation.

## Evaluation partitions

| Track | Purpose | Partition rule and constraint |
|---|---|---|
| R0 | Reproduce original score as a diagnostic | Original random row split; explicitly contaminated/non-primary. Do not use its score as evidence of deployment readiness. |
| R1 | Remove exact-feature leakage | Group split on final predictor representation; train/selection/calibration/test disjoint. Report raw and effective group counts. |
| R2 | Unknown-family evaluation | Exclude each target family or predefined related-family group from all fitting/selection/calibration. Inner pseudo-unknown families support model selection. |
| R3 | Harder source/time generalization | Source-file/day/session/time splits where provenance supports them. Do not relabel random row ordering as time. Match feasible known/unknown coverage and report missing families. |
| R4 | Dataset-quality sensitivity | Repeat central comparisons on corrected data using a documented version; explain changes in label support. |
| R5 | Independent replication | Repeat protocol in a second dataset's native schema; separate from direct cross-dataset transfer. |
| R6 | Optional CIC2017-to-2018 transfer | Only after semantic feature mapping. Freeze 2017 model and calibration. Report zero-shot transfer separately from target-benign recalibration. Current 2018 subset is not a web-attack test. |

Primary unknown groups: web attacks together; DoS-related families together; brute-force authentication families together; Bot; PortScan; DDoS. Report both individual-family and grouped-family holdouts when support permits. Related-family holdouts reduce the chance of calling a close sibling “unknown.” Heartbleed/Infiltration/SQL injection have limited support; show counts and uncertainty without sweeping ranking claims. Freeze taxonomy and label mappings before final runs.

For each outer split, set aside final evaluation first. Allocate remaining eligible known groups to training, inner selection and benign calibration; a starting allocation is 60/20/20 of non-test known groups, adjusted only for documented support constraints. Unknown outer families appear only in final evaluation. A group cannot straddle partitions. Final evaluation includes representative held-out benign groups, eligible known attacks and excluded unknown attacks. No arbitrary class balancing in primary test metrics.

The development pilot differs from this final design: it uses fixed hyperparameters and a 60/20/20 train/calibration/test split of known groups, with all web attacks added to test. It lacks an independent tuning split and uses enriched prevalence.

## Minimum comparisons and controls

| Experiment | Models/changes | Required output |
|---|---|---|
| Supervised controls | Logistic regression, RF, XGBoost, MLP | Same outer manifests, adequate scaling, class policy and tuning budget |
| Anomaly controls | KMeans, Isolation Forest, AE | Benign-only fitting; calibrated scores, known/unknown performance |
| Fusion | XGB alone, each anomaly alone, XGB OR each anomaly | Total-budget matching; 50/50 baseline plus inner-selected allocation; extra detections/extra false alerts |
| Input shortcuts | Port-free primary vs port included | Paired split comparison; recompute groups after feature changes |
| Quality | Original vs corrected labels/flows; conflict policy | Exclusion flowchart, support changes and effects |
| Explanation robustness | Seed/background/feature-group variation | Top-k Jaccard, rank correlation, representative error explanations |
| Optional neural comparison | Small FT-Transformer | Only after stronger controls; equal selection discipline and compute disclosure |
| Optional drift | Frozen PSI + simple comparator | Stationary false alarms, shift type, chronology, delay if available |

Use five seeds (42, 123, 2026, 3407, 8675309) for primary comparisons. Seeds alone do not make correlated flows independent. For model selection, start with at most 12 predeclared configurations per family on development data; expand only with an explicit rationale and equal disclosure. Keep one GPU fit at a time. Early stopping uses validation only. No test-set eval callback, iterative test inspection or best-seed reporting.

## Metrics and uncertainty

Primary: held-out-family recall and macro-family recall at calibrated total FPR budgets of 0.1%, 0.5%, 1%, 2%. Also report realized FPR, false alerts per million benign flows, family support, known-attack recall and additional unknown detections per additional benign alert. An undefined ratio must stay undefined.

Secondary: average precision, AUROC, precision, recall, F1, balanced accuracy, MCC and a fully counted confusion matrix. Distinguish average precision from trapezoidal PR area. Show deployment-prevalence sensitivity for precision; enriched case-control test precision is not operational precision. Never infer precision under a new prevalence without stating assumptions about conditional rates.

Use paired bootstrap intervals over the actual independent grouping unit when available; document the remaining within-source dependence. Report seeds and per-family distributions, not only a mean across millions of correlated rows. For very rare attacks, include raw numerators/denominators and avoid overconfident asymptotic intervals. Predeclare comparisons and effect sizes; if formal multiple testing is used, correct it and explain the family of tests.

At alpha=0.001, small benign calibration/test samples may not resolve the tail adequately. Aim for at least tens of thousands of benign observations and report effective group counts; more correlated rows do not substitute for independent units. A conformal rank with n too small can imply an infinite threshold.

Compute: wall-clock fit/score time including preprocessing, batch size, warm-up policy, median/p95 latency, CPU/GPU/RAM peaks and hardware/software versions. Measure throughput separately from single-flow latency. Do not extrapolate pilot timing linearly to a complete study.

## Required assertions and saved artifacts

Every run must assert: no group overlap; no target held-out family in fitting/selection/calibration; label/source metadata absent from features; transforms fitted only on allowed rows; feature order identical; finite model inputs/scores; exact threshold provenance; all confusion counts sum to test size. Check unknown-family score extraction never influences tuning.

Save configuration, environment lock, source hashes, row/group manifests, fitted transformations, feature order, every model, calibration scores/thresholds, test scores/labels/family/source IDs, timing/memory logs and metrics JSON. Figures must read these artifacts, not typed numbers. Store all raw artifacts privately; publish only authorized summaries here.

## Stop/go criteria

1. Data gate: exact provenance, feature mapping, group overlap and label quality are understood. Otherwise stop final model comparisons.
2. Novelty gate: closest recent work does not already answer the same question with the same controls. Otherwise change the contribution claim.
3. Branch gate: a hybrid must improve the chosen unknown-recall target at the same total alert budget across multiple eligible holdouts/seeds, with uncertainty and costs reported. Otherwise remove it from the claimed method and report the negative finding.
4. Generalization gate: central findings survive a harder split and independent/corrected-data test. Otherwise narrow claims to the demonstrated setting.
5. Writing gate: reproducible outputs, corrected citations and figures exist before the main experimental narrative is rewritten.
