# Local compute feasibility

Measured 2026-09-18:

| Component | Observed |
|---|---|
| GPU | NVIDIA GeForce RTX 4060, approximately 8 GiB VRAM |
| Driver | 616.64; nvidia-smi reports CUDA driver capability 13.4 |
| RAM / logical CPU count | 15.62 GiB / 12 |
| Python | 3.13.7 |
| PyTorch | 2.6.0+cu124; runtime CUDA 12.4; CUDA available |
| XGBoost | 3.4.1 installed in the private local virtual environment |
| NumPy / pandas / scikit-learn | 2.3.2 / 2.3.1 / 1.7.1 |

CPU model name could not be obtained through the restricted CIM query; do not invent its marketing name. CUDA capability printed by nvidia-smi is not the installed PyTorch runtime version.

**Feasible:** the proposed tabular study can be developed and run on this machine with controlled memory use. The development pilot actually trained XGBoost on `cuda:0` and a PyTorch AE on CUDA. This is stronger evidence than checking device visibility alone. [Official XGBoost GPU guidance](https://xgboost.readthedocs.io/en/stable/gpu/index.html)

Full-data training and all five-seed experiments have not been benchmarked. The main constraint is likely 16 GiB system RAM and repeated dataframe copies, not the tiny pilot network. A roughly 2.5-million by 68 float32 feature matrix alone occupies about 650 MiB before labels, indices, split copies, dataframe overhead and model structures. CPU RF and SHAP can cost more memory/time than the compact AE.

Use chunked ingestion and cached columnar/numeric artifacts; float32 after checking numerical fidelity; one GPU fit at a time; 4–6 CPU workers initially; bounded batches of 512–2048; stratified/grouped SHAP samples rather than explaining every row. Begin full-data profiling with one split and one model, record peak host/device memory and time, then schedule the grid based on measured values.

A small FT-Transformer is a plausible optional experiment on 8 GiB with compact depth/width and minibatches, but it has not been tested here. Training an LLM from scratch is outside this hardware/project scope. BERT/T5 fine-tuning feasibility depends on model size, sequence lengths and a suitable dataset; these models are not justified by the current flow CSVs.

Environment: `private_work/.venv` uses system-site packages and adds XGBoost locally. No global package replacement was performed. Capture a self-contained locked environment for final runs; the inherited environment is convenient for development but not a portable reproduction specification.
