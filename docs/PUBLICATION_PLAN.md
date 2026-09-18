# Publication plan and readiness gates

Current decision: do not submit the existing draft. Rebuild evidence and bibliography before polishing prose. Neither a high random-split score nor adding a Transformer establishes a publishable contribution.

## Work packages

| Order | Deliverable | Completion condition | Current state |
|---|---|---|---|
| 1 | Audit and focused literature map | Read available artifacts; list verified defects and closest prior work | Complete initial pass |
| 2 | Dataset and novelty decision | Inspect corrected releases; full-text comparison of closest work; choose defensible research question | Pending |
| 3 | Production pipeline | Provenance, strict manifests, fitted preprocessing, saved models/scores, leakage assertions | Prototype only |
| 4 | Core experiments | Fair baselines, family holdouts, matched alert budgets, five seeds, uncertainty | Development pilot only |
| 5 | Generalization and ablations | Harder source/time split, corrected data, independent replication, port/quality/fusion controls | Pending |
| 6 | Explanations and optional drift | Branch-specific interpretation, stability, errors; controlled drift if retained | Pending |
| 7 | Private manuscript rewrite | Evidence-backed claims, verified references, generated figures/tables, limitations and reproducibility | Pending |
| 8 | Submission package | Venue template, rendered PDF visual QA, artifact/privacy review and author approval | Pending |

Planning allowance: several weeks of research and iteration, not a promise of an overnight paper. Full-data timing and corrected-data access must be measured before giving a reliable completion date. If the core hypothesis fails, a careful negative/replication result is preferable to inventing gains.

## Venue fit checked on 2026-09-18

| Venue | Fit and realistic condition | Current deadline information |
|---|---|---|
| RAID | Strong fit for rigorous intrusion-detection/security measurement, but substantial novelty and methodological rigor required | 2026 paper deadline April 16 has passed. Consider a future cycle only after a strong result. [Official CFP](https://raid2026.org/call.html) |
| ACSAC | Applied security contribution; rigorous replication work can fit its replication/reproduction track when requirements are met | 2026 main deadline May 26 has passed. Future dates not assumed. [Official submissions](https://www.acsac.org/2026/submissions/papers/) |
| ICISSP 2027 | More attainable security-conference option for a sound, bounded empirical contribution; acceptance is not guaranteed | Current CFP lists an extended regular-paper deadline September 29, 2026 and a later October 22 entry for position/regular papers. Confirm the applicable round directly before planning submission. Conference February 22–24, 2027. [Official CFP](https://icissp.scitevents.org/CallforPapers.aspx) |

Do not compress the needed experiments into an imminent deadline. Choose venue after the actual finding, author/supervisor preferences, registration/travel budget and format are known. Indexing statements such as “submitted for indexing” are not guarantees. No submission, registration or payment is authorized or performed by this plan.

## Private rewrite outline

Introduction: concrete flow-IDS problem, alert budget and what is empirically unknown. Related work: closest hybrid/open-set/data-quality studies, accurate comparison table. Method: threat model, provenance, partitions, scoring and calibration. Evaluation: research questions, fair controls, family support, uncertainty and compute. Results: measured findings including failures. Discussion: dataset realism, rare families, label quality, non-independent flows, domain transfer and explanation limits. Conclusion: only what experiments support.

Remove or qualify unsupported e-commerce deployment, CSRF detection, universal unknown-attack/zero-day, statistical-significance-from-PSI and adaptation claims. Replace unverifiable security-incident anecdotes or verify their causal claims from authoritative sources. A mechanism can be useful without being novel; the contribution must be stated at the level the evidence supports.

Ready-to-submit gate: all reported numbers trace to frozen artifacts; final test never used for selection; closest 2026 work is accounted for; every citation resolves and supports its sentence; figures match results and venue dimensions; a complete PDF has been visually inspected; all authors approve the final claims.
