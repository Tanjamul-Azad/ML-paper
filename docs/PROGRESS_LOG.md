# Research progress log

## 2026-10-05 - Corrected data, executed notebook and private rewrite

Obtained corrected2017 data and prepared 251,547 distinct examples. Completed 15 primary runs, 5 block stress runs and 7 capacity fits: 142 fitted study models. Verified 1,307 score-derived evaluation records. Executed 10 notebook cells including a fresh clustering refit matching saved decisions. Generated ten consistent figure sets and a notebook HTML view. Rewrote the manuscript privately as a preliminary empirical draft. Built-in compilation failed with a platform-directory error; no compiled-layout claim.

User requests code/output in a notebook, rejects slides, removes Transformer as a requirement, and reconfirms absolute manuscript privacy. User also requests natural academic writing, no em dashes or generic AI style, and proper references. Original files are preserved; research files stay on F drive outside this repository. Public updates contain progress Markdown only.

MLP Web performance collapses under block grouping; clustering preserves 89/104 coverage; narrower AE reaches 70/104 while larger AEs fail at this budget. Clustering64/128 miss all 13 SQL injections. See OCTOBER_EXPERIMENTS for provenance, definitions and remaining gates.

## 2026-09-18 — Initial audit, protocol design and GPU development pilot

User requested a full research audit, assessment of AE/clustering/Transformer suggestions, literature and publication planning, local compute feasibility and portable GitHub context. Explicit constraint: never publish the main paper.

Completed: workspace inventory; private ZIP extraction; full manuscript/bibliography/notebook reading; visual inspection of all figures; public Kaggle version inspection; complete scans of supplied 2017/2018 data; float32 duplicate/conflict confirmation; reconstructed random-split overlap check; focused primary-source literature/reference review; local CUDA pilot; methodology/experiment/figure/publication plans.

Key findings: supervised preprocessing before split leaks labels; original run is not reproducible from available notebook; supplied public Kaggle version fails at the label column; cross-split feature duplicates occur; 2018 subset lacks web attacks; prior hybrid/XAI work undercuts broad novelty; multiple references are misattributed; no evidence yet that overfitting/generalization or unknown detection is solved.

Measured new evidence: RTX 4060 successfully trained GPU XGBoost and a small AE. At a 1% nominal calibration budget, XGB alone recovered 1,954/2,143 held-out web rows in the development sample; KMeans and IF alone recovered none; AE alone recovered 86. Half-budget unions underperformed full-budget XGB. These results are exploratory and must not become final paper numbers.

Decisions: rebuild evaluation first; use flow-IDS scope; test branch value at a matched total false-alert budget; retain AE/clustering as alternatives pending proper comparison; defer generic LLMs; keep all original artifacts private and publish documentation only.

Limitations: literature review is focused rather than systematic; some reference identities/full texts remain unresolved; corrected-data acquisition and production experiments are pending; audio was not independently transcribed; no compiled-PDF visual inspection because MiKTeX initialization failed; original files were not rewritten.

Next action: inspect corrected-data release formats and closest recent full papers, freeze contribution/protocol, then build production provenance and split manifests. See CURRENT_STATUS for the current checklist and REPRODUCIBILITY for local artifacts.

## 5 October completion and narrower direction

1,422 study fits: 142 earlier fits plus 960 inner candidate fits and 320 outer refits. The latter cover 40 runs, two datasets, eight methods and five seeds. Notebook demo refits are excluded. A matched ablation rescored 80 saved clustering models with identical centroids, k and preprocessing, producing 640 independently verified operating points with no new fits. In the raw-selected CIC regime, normalization changes mean excluded recall from 29.01% to 40.55% and realized FPR from 1.08% to 1.01%. On UNSW it changes recall from 20.46% to 18.35% and FPR from 1.64% to 2.65%. This existing normalization idea helps the measured CIC population but fails to generalize to UNSW; the ablation is exploratory.

At the nominal 1% budget, protocol-conditional thresholds reduce absolute test-FPR budget error in 164/320 paired cases, reduce excluded-attack recall in 193/320, and reduce budget error without recall loss in 42/320. All eight models remain in the comparison. This is exploratory reuse of saved evaluation scores, not an untouched confirmation. The general-repair hypothesis is not supported; this intervention is retained as a negative result rather than adopted as an improved detector.

Simple classifier/clustering fusion is already close prior art, including [MCDE](https://www.mdpi.com/1099-4300/28/9/1026). The current intervention instead audits an observable protocol-specific calibration rule, an established conditional-calibration idea. It is an application and failure analysis, not invented mathematics. Claims require joint recall/FPR reporting and unsupported-group disclosure.

No universal winner, SOTA claim, real zero-day discovery, production false-alarm guarantee, or claim that overfitting is solved. Protocol-conditional calibration is established prior art. Exact MCDE/specialized reconstruction baselines and independent forward-time traffic remain publication gates.

Native compiler failure is superseded for actual PDF delivery by the working existing F-drive MiKTeX route. All final PDF pages were inspected. The full private notebook executed with 16 cells. The manuscript and supporting artifacts remain private.
