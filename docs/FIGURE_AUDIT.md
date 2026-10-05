# 2026-10-05 independent-device completion

There are28 standard Matplotlib PNG/PDF/SVG figure sets. New sets21-28 cover independent-device recall/FPR, transfer direction, score distributions, reconstruction histories, equal-data adaptation, source-specific results, reference saturation and radius-floor control. All eight were visually inspected; the raw-score axis was repaired to avoid an offset/label collision. Final paper uses consistent scientific figures; all13 rendered pages inspected. Some mean plots omit seed error bars, so full per-seed tables and uncertainty remain in the notebook and captions disclose instability. No generated illustrative images or slides.

---

## Earlier record, preserved for history

# Figure audit and design specification

Every supplied PNG and both LaTeX-ZIP diagrams were visually inspected. Existing figures are private legacy evidence; source predictions and plotting code are missing for most of them. Do not repair unsupported numerical plots by manually editing image labels.

| Figure | Finding | Required revision |
|---|---|---|
| Intro diagram | E-commerce/deployment icons imply operations that were not validated; AE/drift absent despite surrounding claims | Replace privately after scope is settled; show actual inputs and outputs |
| Methodology diagram | Omits actual split, calibration, AE and drift; mixes offline evaluation with inference | Use the frozen protocol diagram; distinguish fit-only, calibration and test paths |
| fig1 confusion matrix | Counts are internally coherent, but do not validate split or unseen detection | Regenerate by task/holdout; show counts and denominator; include false alerts per million benign |
| fig2 ROC vs fig4 ROC/PR | LR AUC 0.8466 versus 0.8482; MLP 0.6875 versus 0.6933; source of discrepancy unknown | One immutable score file per run; distinguish AP from trapezoidal PR area |
| Two fig3 comparison bars | Different styles; near-ceiling bars obscure differences; highlighted region and zoomed/clipped bars can mislead | Replace with point/interval estimates and family/budget comparisons |
| fig5 global SHAP | Supports model attribution only; Packet Length Variance is not in displayed top 20 despite textual claim | Declare background, units, aggregation, sample counts and seed |
| fig6 beeswarm | Requires output-space and feature-distribution context | Consistent feature naming and units; include correlated-feature limitations |
| fig7 waterfall | Output 13.951 is not a probability; likely margin/log-odds, requiring code verification | Label verified model-output units and baseline; include errors, not only a successful attack |
| fig8 signatures | Brute-force and XSS profiles appear very similar; axes differ and counts/uncertainty absent | Use common axes, counts, stability/error bars; do not claim automatic family discovery |
| fig9 AE errors | Extreme tail near 140,000 and dense near-zero region obscure both distributions and threshold | ECDF or log1p-error plot, quantiles and threshold; disclose outliers rather than hiding them |
| PSI figure | 0.2 is treated as significance; normalized label conflicts with values above 2; only 15 of claimed 47 features displayed | Report exact PSI definition/bins/smoothing, all feature results and calibrated null variability |

## Unified final design

Use vector PDF/SVG masters, white background, one font family and consistent sizes (at least 8–9 pt at final print size). Match actual venue column dimensions; do not impose IEEE formatting on a venue using another template. Keep the same model colors everywhere: XGBoost blue `#0072B2`, logistic regression gray `#666666`, RF green `#009E73`, MLP purple `#CC79A7`, clustering orange `#E69F00`, IF brown `#8C564B`, AE vermilion `#D55E00`. Distinguish lines with markers/styles as well as color. No stars or “proposed” highlight blocks that suggest significance without a test.

Print metric definitions, support, aggregation and uncertainty method in captions. Identify run/protocol IDs in generated metadata. Use percentage units consistently, do not round AUROC to 1.0000 when that hides errors, and show exact counts for rare attacks. If an axis is truncated, label it plainly and retain comparable axes across panels.

Proposed final figure set: protocol and partition flow; family support/data exclusions; unknown recall versus false-alert budget; paired branch-complementarity results; quality/port/split ablations; explanation stability and preselected error cases. Drift gets a separate figure only if the optional controlled experiment is completed. Eliminate redundant metric bar charts.

Figures have been audited and specified, **not regenerated as final paper evidence**. Regeneration follows validated experiments. Final LaTeX/PDF layout inspection is still pending because the installed MiKTeX profile is not initialized and the compile attempt could not create its configuration directory.

## 5 October completion and narrower direction

1,422 study fits: 142 earlier fits plus 960 inner candidate fits and 320 outer refits. The latter cover 40 runs, two datasets, eight methods and five seeds. Notebook demo refits are excluded. A matched ablation rescored 80 saved clustering models with identical centroids, k and preprocessing, producing 640 independently verified operating points with no new fits. In the raw-selected CIC regime, normalization changes mean excluded recall from 29.01% to 40.55% and realized FPR from 1.08% to 1.01%. On UNSW it changes recall from 20.46% to 18.35% and FPR from 1.64% to 2.65%. This existing normalization idea helps the measured CIC population but fails to generalize to UNSW; the ablation is exploratory.

At the nominal 1% budget, protocol-conditional thresholds reduce absolute test-FPR budget error in 164/320 paired cases, reduce excluded-attack recall in 193/320, and reduce budget error without recall loss in 42/320. All eight models remain in the comparison. This is exploratory reuse of saved evaluation scores, not an untouched confirmation. The general-repair hypothesis is not supported; this intervention is retained as a negative result rather than adopted as an improved detector.

Simple classifier/clustering fusion is already close prior art, including [MCDE](https://www.mdpi.com/1099-4300/28/9/1026). The current intervention instead audits an observable protocol-specific calibration rule, an established conditional-calibration idea. It is an application and failure analysis, not invented mathematics. Claims require joint recall/FPR reporting and unsupported-group disclosure.

No universal winner, SOTA claim, real zero-day discovery, production false-alarm guarantee, or claim that overfitting is solved. Protocol-conditional calibration is established prior art. Exact MCDE/specialized reconstruction baselines and independent forward-time traffic remain publication gates.

Native compiler failure is superseded for actual PDF delivery by the working existing F-drive MiKTeX route. All final PDF pages were inspected. The full private notebook executed with 16 cells. The manuscript and supporting artifacts remain private.
