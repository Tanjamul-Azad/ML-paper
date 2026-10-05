# Current status

Updated 2026-10-06T00:03:21.280378+06:00. The independent-device comparison and conference-format draft are complete for supervisor review. Submission readiness is not established.

Working title: **Unseen-Attack Detection Across Devices: Calibration Failures and Reference Refresh**.

Completed 1,522 scientific fits: 142 earlier + 960 nested candidates + 320 outer refits + 100 independent-device fits. Display operations and notebook demonstration refits are excluded. The new batch has 20 source configurations, nine scoring methods, 1,440 source/transfer operating points, 1,520 third-device operating points and 960 fixed-centroid floor-ablation points. Reference and floor changes use no new detector fits.

At nominal 1%, reciprocal transfer raises MCDE FPR from 0.64% to 51.27% while recall remains near 100%. On the fixed third device, frozen MCDE has 98.00% FPR. Threshold-only MCDE detects no held-out attacks. Reference-and-threshold refresh achieves 99.91% held-out recall with 3.25% FPR, still above the requested 1%. RePO+ threshold-only achieves 99.82% recall with zero observed false alerts, and plain AE achieves 99.78% with zero observed false alerts. Our repair improves its own failed baseline; reconstruction remains stronger in this tested population.

Target: the next available ACSAC Reproduction and Replication (R+R) cycle. [Official 2026 CFP](https://www.acsac.org/2026/submissions/papers/) is the latest verified rule set: IEEEtran 1.8b, conference/compsoc, US Letter, anonymous, unchanged class layout, 11 main pages and at most five reference/appendix pages. The 2026 May 26 submission deadline passed; 2027 dates and rules are unverified. Current PDF: 12 pages, comprising 11 main pages and one reference page. All six tables and five figures precede the bibliography; there is no trailing appendix. The working title omits the track prefix. Add R+R: only if actually submitting to that ACSAC track, where the prefix is required. This is a scientific-fit recommendation, not an acceptance prediction.

Canonical private files: `SUPERVISOR_NOTEBOOK.html`, `SUPERVISOR_NOTEBOOK.ipynb`, `paper_rewrite.tex` and `output/manuscript/paper_rewrite.pdf`, under `F:/UIU/11th/ML/dep/research_update_2026-10-05/`. One notebook contains 20 executed code cells and no error outputs. There are 28 Matplotlib PNG/PDF/SVG figure sets and 22 resolved cited references. All 12 final PDF pages were visually inspected. HTML export and notebook execution passed; HTML browser screenshot inspection was blocked by automatic approval policy.

No SOTA claim, universal encoder-redundancy claim, discovered zero-day exploit, production FPR guarantee or claim that overfitting is solved. This is a bounded laboratory replication and failure analysis. It does not include timestamp-verified future traffic, all-device replication, a raw64 population rerun or exact unpublished author settings.

Important data caveats: precision conversion collapses many nearly identical attack vectors; overlap removal leaves as few as 267 target attack representatives. Seeds reuse the same observations. Trusted adaptation assumes clean released benign labels, and some source-based comparisons have different residual populations. Full supports, uncertainty and provenance are retained locally. Read OCTOBER_EXPERIMENTS.md and START_HERE.md before interpreting rounded means.

The manuscript, LaTeX, PDF, code, datasets, notebooks, figures, checkpoints and raw scores remain private on F drive. GitHub receives only these separately written Markdown progress summaries. Never add the private research folder to this repository.
