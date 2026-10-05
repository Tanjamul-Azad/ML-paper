# Handoff for another research assistant

Read CURRENT_STATUS.md, OCTOBER_EXPERIMENTS.md, DECISIONS.md and LITERATURE_REVIEW.md first. September AUDIT/DATASET_AUDIT/PILOT_RESULTS are historical; do not treat their pending tasks as current status.

User wants meaningful, useful intrusion-detection research, not an architecture pile-up. No required Transformer; no slides. Show real executed notebook code and outputs. Academic prose must be natural, accurate, and avoid em dashes. Existing algorithms and closest work must receive proper credit.

Working title: Unseen-Attack Detection under Alert Budgets: A Controlled Study of Local Cluster Normalization.

1,422 study fits: 142 earlier fits plus 960 inner candidate fits and 320 outer refits. The latter cover 40 runs, two datasets, eight methods and five seeds. Notebook demo refits are excluded. A matched ablation rescored 80 saved clustering models with identical centroids, k and preprocessing, producing 640 independently verified operating points with no new fits. In the raw-selected CIC regime, normalization changes mean excluded recall from 29.01% to 40.55% and realized FPR from 1.08% to 1.01%. On UNSW it changes recall from 20.46% to 18.35% and FPR from 1.64% to 2.65%. This existing normalization idea helps the measured CIC population but fails to generalize to UNSW; the ablation is exploratory.

At the nominal 1% budget, protocol-conditional thresholds reduce absolute test-FPR budget error in 164/320 paired cases, reduce excluded-attack recall in 193/320, and reduce budget error without recall loss in 42/320. All eight models remain in the comparison. This is exploratory reuse of saved evaluation scores, not an untouched confirmation. The general-repair hypothesis is not supported; this intervention is retained as a negative result rather than adopted as an improved detector.

Local base: `F:/UIU/11th/ML/dep/research_update_2026-10-05/`. Main deliverables are one notebook (.ipynb and static .html), one manuscript source and its compiled PDF. Supporting artifacts stay under code/data/runs/output/figures/cache. Original inputs are preserved. Use the F-drive existing Python environment and RUN_GUIDE.md; do not overwrite frozen protocols/results.

No universal winner, SOTA claim, real zero-day discovery, production false-alarm guarantee, or claim that overfitting is solved. Protocol-conditional calibration is established prior art. Exact MCDE/specialized reconstruction baselines and independent forward-time traffic remain publication gates.

Next: supervisor review, an untouched forward-time confirmation of the calibration intervention, exact closest baselines, sensitivity to curation, and target-venue formatting after the venue is chosen. Distinguish completed exploratory results from independently confirmed improvements. Benchmark rows are not newly discovered zero-day vulnerabilities.

The manuscript, LaTeX, PDF, code, datasets, notebooks, figures, checkpoints, raw scores and detailed artifacts remain private on F drive. Only independently written Markdown progress notes belong in this Git repository.

A remote LLM can recover decisions from these notes; it cannot independently reproduce private unpublished files without authorized local access.
