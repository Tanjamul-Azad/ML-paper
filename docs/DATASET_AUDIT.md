# Dataset audit

Measured locally on 2026-09-18. Evidence: private `audit/data_audit.json`, `duplicate_confirmation.json`, source manifest and audit scripts. Counts below describe the supplied files, not every release of CIC data.

## Inventory and provenance

| Source | Rows | Findings |
|---|---:|---|
| Supplied cleaned CICIDS2017 | 2,520,798 | 2,095,057 benign; 425,741 attack; binary label agrees with family label; no missing/infinite numeric values |
| Eight CSVs in supplied CICIDS2017 ZIP | 2,830,743 | 2,867 rows have at least one nonfinite numeric feature; source-file/day provenance recoverable |
| 2018 Wednesday 14 February | 1,048,575 | Benign 667,626; FTP-BruteForce 193,360; SSH-Bruteforce 187,589; 3,824 invalid numeric rows |
| 2018 Thursday 15 February | 1,048,575 | Benign 996,077; GoldenEye 41,508; Slowloris 10,990; 8,027 invalid numeric rows |
| 2018 Friday 16 February | 1,048,575 | Benign 446,772; SlowHTTPTest 139,890; Hulk 461,912; one embedded header row |

The three equal 2018 row counts warrant checking source checksums and export provenance; they do not alone prove truncation. Their total is 3,145,725 rows including the embedded header. They contain no web-attack labels. Official 2018 web-attack sessions are on 22/23 February. Do not claim that this subset validates web-attack transfer. [Official 2018 schedule](https://www.unb.ca/cic/datasets/ids-2018.html)

## Cleaned 2017 class support

| Family | Rows | Family | Rows |
|---|---:|---|---:|
| BENIGN | 2,095,057 | DDoS | 128,014 |
| DoS Hulk | 172,846 | PortScan | 90,694 |
| DoS GoldenEye | 10,286 | FTP-Patator | 5,931 |
| DoS slowloris | 5,385 | DoS Slowhttptest | 5,228 |
| SSH-Patator | 3,219 | Bot | 1,948 |
| Web brute force | 1,470 | Web XSS | 652 |
| Web SQL injection | 21 | Infiltration | 36 |
| Heartbleed | 11 | | |

Web labels contain a replacement character in the supplied encoding. Normalize labels using an explicit mapping and retain the original value. Rare families cannot support precise family-level superiority claims.

## Duplicates and invalid values

Exact equality was checked for candidate duplicate groups in the float32 numeric representation used by the audit:

- 23,536 duplicate excess rows across 23,509 feature groups.
- 718 feature groups have conflicting binary labels, involving 1,444 rows.
- Recreating the original stratified random split yields 7,572 test rows, out of 504,160, with feature hashes also in training (1.50%). This overlap calculation uses pandas 64-bit hashes; it is not an exhaustive original-precision pairwise comparison. Exact duplicate verification was a separate float32 check.

Report the representation when reporting duplicates. Group by model-input features, including after port removal or other transformations; two originally different rows can become identical to the model. Quarantine cross-label conflicts in the primary analysis and report a sensitivity analysis, rather than silently assigning a majority label. Keep group membership across every split.

The cleaned file still contains negative physical quantities: 107 negative flow durations, 2,880 negative minimum flow IAT values, 17 negative forward minimum IAT values, and negative header/minimum-segment values. In contrast, `-1` initial-window values can be extractor sentinels: 911,012 forward and 1,215,625 backward values are negative. A blanket negative-value filter would be wrong. Document each feature's valid domain and missing-value semantics.

Eight columns are constant: backward PSH/URG flags and the six forward/backward bulk statistics. `Fwd Header Length.1` duplicates `Fwd Header Length` exactly. Fit any learned feature removal on training only. The draft's 78 minus 8 arithmetic does not produce 71.

## Required reconstruction

1. Hash and preserve originals; never overwrite them. Record download source, release, extractor version and license.
2. Rebuild from raw per-file CSVs with `source_file`, original row number, original label and normalized family metadata. Metadata must never enter predictors.
3. Strip header whitespace, remove embedded headers, parse numbers, distinguish sentinel values from impossible values, and log every exclusion by family/file.
4. Remove exact duplicate feature columns; calculate feature-group identities for each feature policy; quarantine conflicting groups. Fit imputation/scaling/selection inside training folds.
5. Produce a feature dictionary for 2017/2018 with units, directionality and extraction semantics. An alias match is insufficient proof of compatibility. Never zero-fill absent features to force transfer.
6. Compare supplied data with corrected releases before final experiments. Published audits identify flow construction, labeling and attack-execution defects in both datasets. [2017 audit and tools](https://intrusion-detection.distrinet-research.be/WTMC2021/tools_datasets.html), [2017/2018 audit](https://intrusion-detection.distrinet-research.be/CNS2022/index.html)

The supplied 2017 machine-learning CSVs lack IP/session/timestamp fields. They support file/day-level provenance, not a defensible fine-grained temporal/session split. Obtain richer/corrected data if that claim is central. A random group split is a limited baseline, explicitly labeled as such.

For independent replication, use a second dataset in its native feature space and retrain the same protocol. UNSW-NB15 has different extraction semantics; it is not automatically a drop-in test set for a CIC model. [Official UNSW-NB15](https://research.unsw.edu.au/projects/unsw-nb15-dataset)
