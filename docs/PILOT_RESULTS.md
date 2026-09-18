# Local development pilot — measured results

Run date: 2026-09-18. **Development evidence only; not final paper results.** Private source: `private_work/run_pilot.py`; machine-readable output: `private_work/pilot/results.json`. This is a new run, not a reproduction or validation of the original figures.

## Protocol

One seed (42), fixed untuned settings. The sample retains approximately 4% of feature-hash groups plus every web-attack row: 103,191 input rows. It quarantines 110 physically invalid rows and 613 rows in conflicting binary-label groups under the port-free input representation. Known rows sharing a held-out web group are excluded. Final split counts: training 60,142; calibration 20,085; evaluation 22,241. Evaluation contains 16,706 benign, 3,392 known-attack and 2,143 held-out web-attack rows.

All web families are absent from fitting and calibration. Feature groups do not cross partitions. Destination port and duplicate header feature are excluded; constants are removed using training only, leaving 68 features. The known groups use approximately 60/20/20 train/calibration/evaluation allocation. Calibration contains 16,987 benign rows. This is not temporal or session-independent validation.

XGBoost uses raw features; logistic regression uses signed-log1p and training-fitted scaling. Anomaly models use benign-training-fitted signed-log1p/scaling. Single models receive a 1% nominal benign false-positive budget. OR unions assign 0.5% to each branch, for a total 1% nominal budget. Order-statistic thresholds are fixed from benign calibration only. Realized test FPR can exceed the nominal budget.

| Model | Fixed pilot configuration | Fit seconds |
|---|---|---:|
| XGBoost | CUDA histogram; 200 trees, depth 6, learning rate 0.1, subsample 0.85, column fraction 0.9, class weight ratio | 0.618 |
| Logistic regression | Balanced classes, C=1, max iterations 1000, scaled inputs | 0.620 |
| MiniBatchKMeans | 32 centroids, batch 2048, 3 initializations; minimum centroid distance | 0.721 |
| Isolation Forest | 100 trees, max samples 256; negative score_samples | 0.154 |
| Autoencoder | 68→64→16→64→68, ReLU hidden layers, Adam 0.001, batch 1024, 15 fixed epochs | 2.336 |

## Observed performance

| Model | Actual benign FPR | Held-out web recall | Known-attack recall | Average precision |
|---|---:|---:|---:|---:|
| XGBoost | 0.910% | 91.18% (1,954/2,143) | 99.88% | 0.9869 |
| Logistic regression | 1.065% | 0.05% (1/2,143) | 91.98% | 0.9236 |
| MiniBatchKMeans | 1.143% | 0% | 15.01% | 0.5904 |
| Isolation Forest | 1.185% | 0% | 0.97% | 0.5452 |
| Autoencoder | 1.161% | 4.01% (86/2,143) | 49.53% | 0.7264 |
| XGB OR KMeans, half-budget branches | 0.904% | 7.65% (164/2,143) | 99.82% | Not defined for this binary-only fusion output |
| XGB OR IF, half-budget branches | 0.928% | 7.65% (164/2,143) | 99.82% | Not defined |
| XGB OR AE, half-budget branches | 0.982% | 11.06% (237/2,143) | 99.85% | Not defined |

Why do unions perform worse? The XGB threshold rises from 0.009830 at the full 1% budget to 0.037522 at the 0.5% branch budget. Many web scores lie between those thresholds. KMeans and IF recover none of these missed web attacks. AE adds 73 unknown detections relative to **XGB at the same 0.5% branch threshold**, but this does not offset losing detections relative to the full-budget XGB baseline. This illustrates why counting rescued attacks without accounting for budget allocation is misleading.

The XGB-only confusion matrix is TN=16,554, FP=152, FN=193, TP=5,342. Its AUROC is 0.9943 and F1 is 0.9687. These pooled values reflect an enriched web-attack test distribution and must not be presented as deployment precision or population-level performance.

## What this supports

- Local CUDA execution works for both boosting and a small AE.
- In this limited configuration, neither replacing AE with centroid clustering nor adding an untuned anomaly branch improves the selected unknown-recall objective over full-budget XGBoost.
- Threshold sensitivity and branch complementarity deserve explicit experiments.

It does **not** establish that all clustering methods fail, all AEs are redundant, unknown attacks are solved, or XGBoost will generalize to a new network. The study uses original-data defects, one sample, one seed, no hyperparameter selection, no external test and correlated flow data. No significance claim is made. SQL injection has only 21 rows. The final study needs independent selection/calibration, stronger splits and corrected-data sensitivity.

Reported elapsed script time is 5.638 seconds after process/library startup, including the script's sample loading, model work and output. It excludes prior full-data audits and cannot estimate total study duration. Peak process working set was 1,426 MiB. PyTorch peak allocated AE tensors were 34.17 MiB; this excludes CUDA context, XGBoost allocations and other GPU users.

Saved: scores, partition manifests, metrics, XGBoost model/config and AE weights. The pilot does not serialize all preprocessing objects or the LR/KMeans/IF estimators; complete artifact packaging remains required before a final experiment. Its script permits rerunning the prototype, but GPU/platform changes may affect exact reproducibility.
