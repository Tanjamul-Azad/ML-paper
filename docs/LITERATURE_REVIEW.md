# Focused literature review and novelty assessment

Search date: 2026-09-18. This is an initial primary-source review, not a completed systematic review. Sources were checked through publisher/author pages, abstracts and relevant accessible text; full-text extraction and a forward/backward citation search remain necessary. Bibliographic repair is tracked separately.

## Closest evidence and implications

| Work and primary source | Relevant evidence | Implication for this project |
|---|---|---|
| [Barnard, Marchetti & DaSilva, 2022](https://ieeexplore.ieee.org/document/9807332/) — Robust Network Intrusion Detection Through XAI | Combines tree-based detection, SHAP representations and an autoencoder for robustness; includes instance-level explanations. Author [preprint](https://d197for5662m48.cloudfront.net/documents/publicationstatus/175681/preprint_pdf/eaab508cb8e67a505dec1c9f53f627aa.pdf) provides method detail. | Closest direct prior work. Combining XGBoost, SHAP and AE is not sufficient novelty. Their AE input differs from a raw-feature AE; compare accurately. |
| [Lundberg et al., 2020](https://www.nature.com/articles/s42256-019-0138-9) — From local explanations to global understanding with explainable AI for trees | Tree explanations support both individual interpretation and aggregated analysis, including explanation embeddings. | Global/local SHAP and signature plots are established techniques. |
| [Antwarg et al., preprint 2019](https://arxiv.org/abs/1903.02407) — Explaining Anomalies Detected by Autoencoders Using SHAP | Develops explanations for reconstruction anomalies. | TreeSHAP on XGBoost cannot simply be presented as explaining AE alerts. |
| [Farrukh et al., preprint 2023](https://arxiv.org/abs/2309.07461) — Detecting Unknown Attacks in IoT Environments | Open-set classifier uses benign subclustering in a packet-image/stacking setup. | Clustering for unknown-attack detection is prior art, not an automatic new contribution; inputs and protocol differ. |
| [Saxena & Mittal, 2025](https://www.ijpe-online.com/EN/10.23940/ijpe.25.01.p4.3647) — CluSHAPify | Uses SHAP-based selection and hierarchical clustering for network-traffic interpretation. | SHAP plus clustering alone is a weak novelty claim. This is not necessarily the same anomaly-detection mechanism. |
| [Nugraha & Bauschert, E2D2 author artifact, 2026](https://github.com/DLTeamTUC/E2D2) | Modular explanation-based drift evaluation for intrusion detection; author repository reports a 2026 workshop publication. | Explanation drift monitoring already exists. Verify publisher proceedings before citing the venue as confirmed. |
| [Maseno, Sun & Wang, 2026](https://link.springer.com/article/10.1007/s11416-026-00664-7) — Reliability auditing of explanations for ML-based IDS | Studies explanation reliability quantitatively. | Stability measurements also require comparison with existing methods; adding a stability plot is not sufficient novelty. |
| [Evaluating Explainable Hybrid Intrusion Detection Models Under Zero-Day Conditions, 2026](https://www.mdpi.com/2673-2688/7/9/346) | Search-visible abstract describes held-out attacks, hybrid detection and explanation checks. Full text was not retrieved in this session. | High-priority novelty threat. Read full text before committing to a method claim; do not infer exact equivalence from the abstract. |
| [Engelen, Rimmer & Joosen, 2021](https://intrusion-detection.distrinet-research.be/WTMC2021/tools_datasets.html) | Audits CICIDS2017 construction, labels and attack execution and provides corrective resources. | Original CSV performance can reflect dataset defects; corrected-data sensitivity is essential. |
| [Liu et al., 2022](https://intrusion-detection.distrinet-research.be/CNS2022/index.html) — Error Prevalence in NIDS Datasets | Extends reliability scrutiny to CIC2017 and CSE-CIC2018. | Two related CIC datasets do not constitute two independent proofs of reliable deployment. |
| [Arp et al., 2022](https://www.usenix.org/conference/usenixsecurity22/presentation/arp) — Dos and Don'ts of ML in Computer Security | Catalogs methodological pitfalls in security ML. | Threat model, valid splits, representative baselines and operational metrics take priority over another architecture. |
| [Pendlebury et al., 2019](https://www.usenix.org/conference/usenixsecurity19/presentation/pendlebury) — TESSERACT | Demonstrates spatial and temporal evaluation bias in malware research. | Transfer the evaluation lesson, without treating malware results as direct NIDS evidence. |
| [Gorishniy et al., 2021](https://arxiv.org/abs/2106.11959) — Revisiting Deep Learning Models for Tabular Data | Introduces strong tabular neural baselines including FT-Transformer and compares against boosting. | A small tabular Transformer is a relevant optional baseline. No architecture wins universally. |
| [Lin et al., 2022](https://arxiv.org/abs/2202.06335) — ET-BERT | Pretrains contextual representations of traffic datagrams. | Relevant to packet/sequence data; does not justify feeding numeric CIC flow rows to generic BERT/T5. |
| [Bates et al., 2023](https://doi.org/10.1214/22-AOS2244) — Testing for outliers with conformal p-values | Statistical calibration of outlier evidence under assumptions. | Calibration is useful existing theory; exchangeability is not guaranteed under traffic drift. |

## Candidate research question

**When does an anomaly branch add held-out-family detection beyond a strong supervised flow detector, at a fixed total false-alert budget, after controlling dataset shortcuts and split leakage?**

This is a candidate empirical contribution, not a confirmed novel algorithm. Useful results could include a reproducible failure analysis: apparent hybrid gains disappear when alert budgets, duplicates, ports and family overlap are controlled. It must show something not already established by the closest studies, on more than one trustworthy setting.

Potential contribution package: (1) reproducible grouped/family-held-out evaluation with data-quality sensitivity; (2) branch-complementarity and threshold-budget analysis; (3) robust explanation/error analysis supporting the measured finding. Each component alone is established. Do not use “first,” “zero-day capable,” or “e-commerce protection” without the required evidence.

## Complete before final method freeze

Read the closest six full papers and record dataset version, exact unknown definition, split unit, threshold tuning, false-alarm control, duplicate handling, branch fusion, feature inputs and code availability. Search cited/citing work with combinations of `open set intrusion detection`, `held-out attack family`, `hybrid anomaly supervised detector false positive budget`, `SHAP autoencoder intrusion`, and `CICIDS leakage corrected dataset`. Record inclusion/exclusion reasons, dates and DOI metadata. Compare the proposed finding with the September 2026 hybrid paper before claiming a gap.

If that comparison closes the gap, pivot toward a rigorous replication/measurement study or a different validated question. Do not add an LLM merely to make the architecture appear novel.
