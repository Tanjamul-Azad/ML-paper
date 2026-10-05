# ML research: context and progress

Updated 5 October 2026, Asia/Dhaka. Start with [Current status](docs/CURRENT_STATUS.md), [October experiment ledger](docs/OCTOBER_EXPERIMENTS.md) and [Handoff](docs/START_HERE.md).

Working title: **Unseen-Attack Detection under Alert Budgets: A Controlled Study of Local Cluster Normalization**.

1,422 study fits: 142 earlier fits plus 960 inner candidate fits and 320 outer refits. The latter cover 40 runs, two datasets, eight methods and five seeds. Notebook demo refits are excluded. A matched ablation rescored 80 saved clustering models with identical centroids, k and preprocessing, producing 640 independently verified operating points with no new fits. In the raw-selected CIC regime, normalization changes mean excluded recall from 29.01% to 40.55% and realized FPR from 1.08% to 1.01%. On UNSW it changes recall from 20.46% to 18.35% and FPR from 1.64% to 2.65%. This existing normalization idea helps the measured CIC population but fails to generalize to UNSW; the ablation is exploratory. The notebook shows actual executed code/results; the rewritten private PDF compiles and has been visually checked. No slides. Transformer is outside the current direction.

Specific problem: one absolute distance scale can poorly represent departures from compact and broad benign clusters. The matched normalization test improves CIC and worsens UNSW. We also tested protocol-specific calibration as a potential alert-budget repair. At the nominal 1% budget, protocol-conditional thresholds reduce absolute test-FPR budget error in 164/320 paired cases, reduce excluded-attack recall in 193/320, and reduce budget error without recall loss in 42/320. All eight models remain in the comparison. This is exploratory reuse of saved evaluation scores, not an untouched confirmation. The general-repair hypothesis is not supported; this intervention is retained as a negative result rather than adopted as an improved detector.

No universal winner, SOTA claim, real zero-day discovery, production false-alarm guarantee, or claim that overfitting is solved. Protocol-conditional calibration is established prior art. Exact MCDE/specialized reconstruction baselines and independent forward-time traffic remain publication gates.

[Literature](docs/LITERATURE_REVIEW.md), [decisions](docs/DECISIONS.md), [methodology](docs/METHODOLOGY.md), [publication gates](docs/PUBLICATION_PLAN.md), and [progress log](docs/PROGRESS_LOG.md) explain the decisions. September audit/pilot records remain historical.

The manuscript, LaTeX, PDF, code, datasets, notebooks, figures, checkpoints, raw scores and detailed artifacts remain private on F drive. Only independently written Markdown progress notes belong in this Git repository.
