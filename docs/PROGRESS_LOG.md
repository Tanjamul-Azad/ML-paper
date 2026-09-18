# Research progress log

## 2026-09-18 — Initial audit, protocol design and GPU development pilot

User requested a full research audit, assessment of AE/clustering/Transformer suggestions, literature and publication planning, local compute feasibility and portable GitHub context. Explicit constraint: never publish the main paper.

Completed: workspace inventory; private ZIP extraction; full manuscript/bibliography/notebook reading; visual inspection of all figures; public Kaggle version inspection; complete scans of supplied 2017/2018 data; float32 duplicate/conflict confirmation; reconstructed random-split overlap check; focused primary-source literature/reference review; local CUDA pilot; methodology/experiment/figure/publication plans.

Key findings: supervised preprocessing before split leaks labels; original run is not reproducible from available notebook; supplied public Kaggle version fails at the label column; cross-split feature duplicates occur; 2018 subset lacks web attacks; prior hybrid/XAI work undercuts broad novelty; multiple references are misattributed; no evidence yet that overfitting/generalization or unknown detection is solved.

Measured new evidence: RTX 4060 successfully trained GPU XGBoost and a small AE. At a 1% nominal calibration budget, XGB alone recovered 1,954/2,143 held-out web rows in the development sample; KMeans and IF alone recovered none; AE alone recovered 86. Half-budget unions underperformed full-budget XGB. These results are exploratory and must not become final paper numbers.

Decisions: rebuild evaluation first; use flow-IDS scope; test branch value at a matched total false-alert budget; retain AE/clustering as alternatives pending proper comparison; defer generic LLMs; keep all original artifacts private and publish documentation only.

Limitations: literature review is focused rather than systematic; some reference identities/full texts remain unresolved; corrected-data acquisition and production experiments are pending; audio was not independently transcribed; no compiled-PDF visual inspection because MiKTeX initialization failed; original files were not rewritten.

Next action: inspect corrected-data release formats and closest recent full papers, freeze contribution/protocol, then build production provenance and split manifests. See CURRENT_STATUS for the current checklist and REPRODUCIBILITY for local artifacts.
