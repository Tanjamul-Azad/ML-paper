# Current status

Updated 2026-10-05T21:58:43.337412+06:00. **Local experiments, executed notebook, manuscript rewrite, successful PDF compilation and final PDF visual inspection are complete. Conference submission readiness remains subject to the limits below.**

Working title: **Unseen-Attack Detection under Alert Budgets: A Controlled Study of Local Cluster Normalization**.

1,422 study fits: 142 earlier fits plus 960 inner candidate fits and 320 outer refits. The latter cover 40 runs, two datasets, eight methods and five seeds. Notebook demo refits are excluded. A matched ablation rescored 80 saved clustering models with identical centroids, k and preprocessing, producing 640 independently verified operating points with no new fits. In the raw-selected CIC regime, normalization changes mean excluded recall from 29.01% to 40.55% and realized FPR from 1.08% to 1.01%. On UNSW it changes recall from 20.46% to 18.35% and FPR from 1.64% to 2.65%. This existing normalization idea helps the measured CIC population but fails to generalize to UNSW; the ablation is exploratory.

The model comparison has 40 outer runs, 960 candidate records, 320 choices and 1,280 independently verified operating points. Preprocessing checks passed for 256 fitted transformers in the first seed across eight groups. The private notebook has 16 executed cells. No slides and no required Transformer.

The current focus is the compact/broad-cluster distance-scale problem, tested by matched local-radius normalization. The separate protocol-calibration experiment is a negative result: At the nominal 1% budget, protocol-conditional thresholds reduce absolute test-FPR budget error in 164/320 paired cases, reduce excluded-attack recall in 193/320, and reduce budget error without recall loss in 42/320. All eight models remain in the comparison. This is exploratory reuse of saved evaluation scores, not an untouched confirmation. The general-repair hypothesis is not supported; this intervention is retained as a negative result rather than adopted as an improved detector.

Read [October ledger](OCTOBER_EXPERIMENTS.md) for measured tables, provenance, caveats and private artifact paths. The older September audit/pilot files remain historical evidence and are superseded for completed-task status.

No universal winner, SOTA claim, real zero-day discovery, production false-alarm guarantee, or claim that overfitting is solved. Protocol-conditional calibration is established prior art. Exact MCDE/specialized reconstruction baselines and independent forward-time traffic remain publication gates.

The manuscript, LaTeX, PDF, code, datasets, notebooks, figures, checkpoints, raw scores and detailed artifacts remain private on F drive. Only independently written Markdown progress notes belong in this Git repository.
