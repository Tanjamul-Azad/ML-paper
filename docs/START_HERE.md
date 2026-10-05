# Handoff for a new research assistant

## User objective and hard boundary

Improve an existing network intrusion detection paper to a defensible conference submission. Audit novelty, data mining, dataset quality, methodology, overfitting, metrics, explanations, and figures. Evaluate a supervisor's suggestion to replace the autoencoder with clustering, or consider Transformers/BERT/T5 for unknown attacks. Keep portable research context on GitHub. **Never upload the manuscript, LaTeX ZIP/source, paper PDF, original figures, audio, or a copy of manuscript prose.**

## Read in order

1. CURRENT_STATUS.md, OCTOBER_EXPERIMENTS.md and DECISIONS.md.
2. AUDIT.md, DATASET_AUDIT.md, and PILOT_RESULTS.md (September history).
3. LITERATURE_REVIEW.md, METHODOLOGY.md, and EXPERIMENT_PLAN.md.
4. REFERENCE_AUDIT.md, FIGURE_AUDIT.md, and PUBLICATION_PLAN.md.

## Evidence labels

- **Verified local:** source/code inspected or an audit actually executed.
- **Reported legacy:** number printed in an old figure/draft; original execution not recovered.
- **Pilot:** newly measured, exploratory, limited-scope result; never substitute for final experiments.
- **Proposed:** a design or experiment not yet completed.
- **Unresolved:** requires additional evidence; do not fill gaps with plausible guesses.

## Critical scientific context

The original task is binary benign-vs-attack classification on numeric CIC flow features. It is not HTTP payload analysis, e-commerce transaction analysis, or verified exploit identification. Dataset-year change alone is not proof of concept drift. A benign-only anomaly detector is not automatically a detector of previously unseen attack families. A supervised classifier can also generalize to held-out families; model type does not settle this question.

The local draft and public Kaggle notebook do not provide a complete reproducible experiment. Full-data target-aware feature selection precedes splitting. Exact float32 feature duplicates and conflicting binary labels remain. Both clustering and AE must earn a place through incremental benefit at a matched false-alarm budget. No method has yet earned a final novelty claim.

## Local workspace map

Base directory: `F:/UIU/11th/ML/dep`.

- `ML-paper/`: this documentation-only Git repository.
- `private_work/manuscript_original/`: privately extracted source and original figures.
- `private_work/audit/`: JSON provenance, full data audits, reference metadata, pilot sample.
- `private_work/pilot/`: development scores, split manifests, model artifacts, results.
- `private_work/*.py`: local audit and pilot tools; commands in REPRODUCIBILITY.md.
- `research_update_2026-10-05/`: corrected-data results, executed notebook and private manuscript rewrite. Never put this directory in Git. The HTML notebook preview is the supervisor entry point; no slides.
- Original ZIPs, CSVs, notebook, figures and audio remain at their original locations. They have not been overwritten or reorganized destructively.

A remote LLM can understand the decisions from this repository but cannot independently reproduce unpublished private files without local access. Do not pretend otherwise.

## Next concrete action

Corrected data, 20 main runs and 7 sensitivity fits are complete. Next: a new nested family-selection protocol followed by untouched temporal/external tests. Treat inspected October folds as development evidence. Finish closest-work comparison before claiming novelty. User removed Transformer as a requirement and rejected slides. The complete private rewrite remains a preliminary research draft; built-in compilation failed on a platform error. User requires natural academic prose, no generic AI style or em dashes, and accurate supporting citations.

Update CURRENT_STATUS, PROGRESS_LOG, and DECISIONS after every meaningful session. Add run IDs, source hashes, configuration, failure logs, and result locations. Never mark a planned run complete without artifacts. Do not create manuscript prose in this repository.
