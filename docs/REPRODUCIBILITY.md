# Local runbook and public/private boundary

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
