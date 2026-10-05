# ML research: context and progress

Updated 2026-10-06T00:03:21.280622+06:00. Read [Current status](docs/CURRENT_STATUS.md), [October evidence](docs/OCTOBER_EXPERIMENTS.md) and [Handoff](docs/START_HERE.md).

Working title: **Unseen-Attack Detection Across Devices: Calibration Failures and Reference Refresh**.

Completed 1,522 scientific fits: 142 earlier + 960 nested candidates + 320 outer refits + 100 independent-device fits. Display operations and notebook demonstration refits are excluded. The new batch has 20 source configurations, nine scoring methods, 1,440 source/transfer operating points, 1,520 third-device operating points and 960 fixed-centroid floor-ablation points. Reference and floor changes use no new detector fits.

At nominal 1%, reciprocal transfer raises MCDE FPR from 0.64% to 51.27% while recall remains near 100%. On the fixed third device, frozen MCDE has 98.00% FPR. Threshold-only MCDE detects no held-out attacks. Reference-and-threshold refresh achieves 99.91% held-out recall with 3.25% FPR, still above the requested 1%. RePO+ threshold-only achieves 99.82% recall with zero observed false alerts, and plain AE achieves 99.78% with zero observed false alerts. Our repair improves its own failed baseline; reconstruction remains stronger in this tested population.

Target: the next available ACSAC Reproduction and Replication (R+R) cycle. [Official 2026 CFP](https://www.acsac.org/2026/submissions/papers/) is the latest verified rule set: IEEEtran 1.8b, conference/compsoc, US Letter, anonymous, unchanged class layout, 11 main pages and at most five reference/appendix pages. The 2026 May 26 submission deadline passed; 2027 dates and rules are unverified. Current PDF: 12 pages, comprising 11 main pages and one reference page. All six tables and five figures precede the bibliography; there is no trailing appendix. The working title omits the track prefix. Add R+R: only if actually submitting to that ACSAC track, where the prefix is required. This is a scientific-fit recommendation, not an acceptance prediction.

This notes-only repository records decisions, experiments, numeric summaries, source links and remaining limitations. Code and executed outputs are retained privately for supervisor review. It does not contain the paper or a copy of its abstract.

No SOTA claim, universal encoder-redundancy claim, discovered zero-day exploit, production FPR guarantee or claim that overfitting is solved. This is a bounded laboratory replication and failure analysis. It does not include timestamp-verified future traffic, all-device replication, a raw64 population rerun or exact unpublished author settings.

The manuscript, LaTeX, PDF, code, datasets, notebooks, figures, checkpoints and raw scores remain private on F drive. GitHub receives only these separately written Markdown progress summaries. Never add the private research folder to this repository.
