# Handoff for another research assistant

Updated 2026-10-05T23:37:12.825031+06:00. Read CURRENT_STATUS, OCTOBER_EXPERIMENTS, LITERATURE_REVIEW and PUBLICATION_PLAN first. Sections explicitly marked earlier history preserve prior decisions; their old counters and pending-task claims do not override the latest record.

Working title: **R+R: Calibration Transfer and Reference Saturation in Unseen-Attack Detection**. The focus shifted from a proposed hybrid detector to testing calibration-transfer failure and reference saturation. No required Transformer. No slides. Keep reconstruction competitors and negative results.

Completed 1,522 scientific fits: 142 earlier + 960 nested candidates + 320 outer refits + 100 independent-device fits. Display operations and notebook demonstration refits are excluded. The new batch has 20 source configurations, nine scoring methods, 1,440 source/transfer operating points, 1,520 third-device operating points and 960 fixed-centroid floor-ablation points. Reference and floor changes use no new detector fits.

At nominal 1%, reciprocal transfer raises MCDE FPR from 0.64% to 51.27% while recall remains near 100%. On the fixed third device, frozen MCDE has 98.00% FPR. Threshold-only MCDE detects no held-out attacks. Reference-and-threshold refresh achieves 99.91% held-out recall with 3.25% FPR, still above the requested 1%. RePO+ threshold-only achieves 99.82% recall with zero observed false alerts, and plain AE achieves 99.78% with zero observed false alerts. Our repair improves its own failed baseline; reconstruction remains stronger in this tested population.

Local base: `F:/UIU/11th/ML/dep/research_update_2026-10-05/`. Open the canonical notebook HTML for code/output; sections 17-20 contain the new independent-device work. The source `.ipynb`, official-format `.tex`, PDF, RUN_GUIDE and PROTOCOL_NOTES are alongside it. Models, configurations, manifests, scores and audit JSONs are in data/runs/output; figures are in figures. Preserve original manuscript inputs and frozen run namespaces.

Phase5 is a MCDE mechanism reimplementation and author-code-based RePO port on Danmini Doorbell and Ecobee Thermostat, two excluded botnet families and five seeds. Phase6 fixes Philips Baby Monitor before its model outputs and compares frozen, threshold-only and reference/threshold refresh with equal trusted-data access. Phase7 changes only a training-derived radius safeguard, retains both alternatives, and declares weighted median primary before rescoring. Each amendment and protocol hash is saved. No target attack labels choose thresholds.

The weighted radius floor improves third-device mean recall from 35.84% to 61.15% at roughly 0.34% FPR, but is highly seed-sensitive. Seed11 shows no gain; weighted seed means range 35.89-85.80%. It does not outperform reconstruction and is not a stable superiority finding.

Target: the next available ACSAC Reproduction and Replication (R+R) cycle. [Official 2026 CFP](https://www.acsac.org/2026/submissions/papers/) is the latest verified rule set: IEEEtran 1.8b, conference/compsoc, US Letter, anonymous, unchanged class layout, 11 main pages and at most five reference/appendix pages. The 2026 May 26 submission deadline passed; 2027 dates and rules are unverified. Current PDF: 13 pages, comprising 11 main pages and two pages of references/appendix. This is a scientific-fit recommendation, not an acceptance prediction.

No SOTA claim, universal encoder-redundancy claim, discovered zero-day exploit, production FPR guarantee or claim that overfitting is solved. This is a bounded laboratory replication and failure analysis. It does not include timestamp-verified future traffic, all-device replication, a raw64 population rerun or exact unpublished author settings.

Next scientific gates: full raw64/population sensitivity, wider device/capture coverage and timestamp-verified forward validation. Exact MCDE author settings remain unavailable; RePO was ported across software/data. Human authors must review code, claims and citations and complete ACSAC's editorial-use declaration. Do not claim author review already occurred. Any future artifact release is a separate author decision; the manuscript must never enter GitHub.

The manuscript, LaTeX, PDF, code, datasets, notebooks, figures, checkpoints and raw scores remain private on F drive. GitHub receives only these separately written Markdown progress summaries. Never add the private research folder to this repository.

A remote LLM can recover context here. Reproducing private results requires authorized access to local evidence.
