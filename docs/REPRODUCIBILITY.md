# 2026-10-05 independent-device completion

Canonical private files: `SUPERVISOR_NOTEBOOK.html`, `SUPERVISOR_NOTEBOOK.ipynb`, `paper_rewrite.tex` and `output/manuscript/paper_rewrite.pdf`, under `F:/UIU/11th/ML/dep/research_update_2026-10-05/`. One notebook contains 20 executed code cells and no error outputs. There are 28 Matplotlib PNG/PDF/SVG figure sets and 22 resolved cited references. All 13 final PDF pages were visually inspected. HTML export and notebook execution passed; HTML browser screenshot inspection was blocked by automatic approval policy.

Local run commands are in private RUN_GUIDE.md. Use F-drive Python with -B. New trainers skip completed run metrics. Preserve immutable protocol files and old run namespaces. Reproduction in a clean environment or Kaggle/Colab is not yet tested.

New verification files: output/independent_verification.json, output/reference_refresh_verification.json, output/radius_floor_training_audit.json, output/nbaiot_precision_audit.json and output/final_checks.json. Model configs and all raw scores are preserved; the final manifest identifies experiment files and excludes manuscript sources/prose/PDF.

The native editor compiler is unavailable due to platform standard-directory failure. Existing F-drive MiKTeX compiles the official IEEE source in two passes, with package installation disabled. Do not run the historical write_paper_v2.py to rebuild the current paper: use build_conference_paper.py. Reinspect every rendered PDF page after any source change.

---

## Earlier record, preserved for history

# Local runbook and public/private boundary

**October update:** start with `research_update_2026-10-05/SUPERVISOR_NOTEBOOK.html` for displayed code and executed outputs, or its `.ipynb` to run cells. The private `RUN_GUIDE.md` lists verification commands. Complete model, score and partition artifacts exist for 20 main runs and 7 capacity fits. See [October ledger](OCTOBER_EXPERIMENTS.md). September commands below are historical and should not overwrite newer work.

The rewritten manuscript, notebook and support artifacts stay outside this repository. Hashing establishes identity, not independent reproduction without private files. Public notes alone cannot reproduce the study. Never upload the parent workspace.

Workspace root: `F:\UIU\11th\ML\dep`. Original files remain where supplied. The `ML-paper` child directory is the documentation-only repository; do not initialize or publish the entire parent workspace.

| Location relative to workspace | Contents | Publication policy |
|---|---|---|
| Original root files / `cic2018 csv files` | Data, notebook, figures, audio and LaTeX ZIP | Private, preserved |
| `private_work/manuscript_original` | Extracted manuscript and figure sources | Never commit/push |
| `private_work/notebook_readable.txt` | Notebook cells and saved output | Private |
| `private_work/audit` | Hash manifest, full data counts, reference checks, sampled data | Private |
| `private_work/pilot` | New scores, models, split manifests and metrics | Private |
| `private_work/.venv` | Development Python environment | Private |
| `ML-paper/README.md`, `ML-paper/docs/*.md` | Original audit summaries, plans and progress | Explicitly authorized public records |

## Commands

Run from the workspace root in PowerShell. The audit/sample commands read large files and replace generated outputs in their own private directories; preserve a dated copy before comparing runs.

```powershell
& .\private_work\.venv\Scripts\python.exe .\private_work\audit_data.py
& .\private_work\.venv\Scripts\python.exe .\private_work\confirm_and_sample.py
& .\private_work\.venv\Scripts\python.exe .\private_work\run_pilot.py
```

The audit ran in approximately 57 seconds in this session; that is an observation, not a performance guarantee. Scripts use supplied local file paths. Read script headers and check available memory before extending them to other datasets. The pilot is explicitly not the final protocol.

Known limitations: the venv inherits installed system packages; not all fitted pilot objects were serialized; data splits are grouped random splits, not session/time splits; duplicate checks use a defined float32 representation; no final independent test is sealed yet. These are recorded limitations to repair, not claims of a finished reproducibility package.

## Final artifact contract

Use a private `runs/<protocol>/<run-id>/` directory containing config, environment lock, source hashes, code revision, split manifests, feature schema, fitted transforms, models, calibration thresholds, score tables, metric JSON and resource logs. Include a schema/version for each table. Build manuscript tables/figures directly from this store. Record failed and negative runs as well as successful ones.

For a new assistant: read START_HERE, CURRENT_STATUS, DECISIONS, DATASET_AUDIT, LITERATURE_REVIEW and EXPERIMENT_PLAN first. Evidence labels must remain intact. Do not turn pending plans into completed results, copy legacy scores into new tables, or treat a preprint as a verified conference publication.

## Publication guard

The repository `.gitignore` defaults to ignoring everything and explicitly allows only named documentation files. This is a convenience, not a security boundary: force-add/API uploads can bypass it. Before every push, inspect staged paths and contents; allow only the approved list. Never use a recursive workspace upload, `git add -f`, or a parent-directory push. Do not publish `.tex`, `.bib`, PDF/manuscript text, ZIPs, raw data, notebooks, images, audio, model weights or credentials.

Every substantive session should update CURRENT_STATUS, DECISIONS for changed choices, and PROGRESS_LOG with work done, evidence/artifact paths, limitations and the next action. Publish only reviewed summaries. This session creates records for continuity; it does not establish an automatic background scheduler.

## 5 October completion and narrower direction

1,422 study fits: 142 earlier fits plus 960 inner candidate fits and 320 outer refits. The latter cover 40 runs, two datasets, eight methods and five seeds. Notebook demo refits are excluded. A matched ablation rescored 80 saved clustering models with identical centroids, k and preprocessing, producing 640 independently verified operating points with no new fits. In the raw-selected CIC regime, normalization changes mean excluded recall from 29.01% to 40.55% and realized FPR from 1.08% to 1.01%. On UNSW it changes recall from 20.46% to 18.35% and FPR from 1.64% to 2.65%. This existing normalization idea helps the measured CIC population but fails to generalize to UNSW; the ablation is exploratory.

At the nominal 1% budget, protocol-conditional thresholds reduce absolute test-FPR budget error in 164/320 paired cases, reduce excluded-attack recall in 193/320, and reduce budget error without recall loss in 42/320. All eight models remain in the comparison. This is exploratory reuse of saved evaluation scores, not an untouched confirmation. The general-repair hypothesis is not supported; this intervention is retained as a negative result rather than adopted as an improved detector.

Simple classifier/clustering fusion is already close prior art, including [MCDE](https://www.mdpi.com/1099-4300/28/9/1026). The current intervention instead audits an observable protocol-specific calibration rule, an established conditional-calibration idea. It is an application and failure analysis, not invented mathematics. Claims require joint recall/FPR reporting and unsupported-group disclosure.

No universal winner, SOTA claim, real zero-day discovery, production false-alarm guarantee, or claim that overfitting is solved. Protocol-conditional calibration is established prior art. Exact MCDE/specialized reconstruction baselines and independent forward-time traffic remain publication gates.

Native compiler failure is superseded for actual PDF delivery by the working existing F-drive MiKTeX route. All final PDF pages were inspected. The full private notebook executed with 16 cells. The manuscript and supporting artifacts remain private.
