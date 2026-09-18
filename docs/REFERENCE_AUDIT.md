# Reference audit

Date: 2026-09-18. All 22 inline citation keys were reviewed. The table identifies confirmed discrepancies and candidate matches; a same-title match is not automatic proof that two records are identical. Some Crossref requests were rate-limited. “Unresolved” means verification remains open, not that the work is fabricated.

| Existing key | Finding / corrective lead | Status |
|---|---|---|
| gaspar2022 | Same title appears in IEEE Access 12, 30164–30175 (2024), [DOI](https://doi.org/10.1109/ACCESS.2024.3368377); supplied year differs. | Year/venue correction supported; recheck full author list |
| dritsas2023 | Same e-commerce review title appears in IEEE Access 13, 99048–99067 (2025), [publisher](https://ieeexplore.ieee.org/document/11009009/), not supplied Applied Sciences record. | Bibliographic mismatch |
| madireddy2019 | [DOI](https://doi.org/10.1145/3337821.3337922) resolves to ICPP 2019, pp. 1–11, not SC. Author list also needs completion. | Metadata mismatch |
| yin2024 | Same-title candidate by Aifei Yin and Benli Li, 2025 conference pp. 505–511, [DOI](https://doi.org/10.1145/3768801.3768881). | Candidate; verify intended source |
| sakthivanitha2024 | Same-title candidate in Procedia Computer Science 269 (2025), 309–320, [DOI](https://doi.org/10.1016/j.procs.2025.08.283). | Candidate; author/venue mismatch |
| kumar2025 | Exact claimed title/source not verified. | Unresolved; do not cite until verified |
| sureda2022 | Title/venue/DOI match Computers & Security 120, 102788: [DOI](https://doi.org/10.1016/j.cose.2022.102788). Secondary metadata shows a different author list. | Primary author-list check pending |
| alotaibi2023 | The matched XAI cybersecurity/digital-twin review is by Sarker, Janicke, Mohsin, Gill and Maglaras, ICT Express 10(4), 935–958 (2024). [Publisher](https://www.sciencedirect.com/science/article/pii/S2405959524000572) | Confirmed author/year/venue mismatch |
| wadkar2023 | Related survey title at [arXiv:2409.13723](https://arxiv.org/abs/2409.13723), first posted 2024. | Candidate; verify authors and intended version |
| faker2019 | Full-title candidate in Procedia Computer Science (2024), [DOI](https://doi.org/10.1016/j.procs.2024.04.211), with different authors. | Candidate; do not substitute blindly |
| tanimu2022 | Dragonfly/XGBoost title candidate in Procedia Computer Science 275 (2026), 637–644, [publisher](https://www.sciencedirect.com/science/article/pii/S1877050926000748). | Candidate; claimed 2022 record not verified |
| andresini2023 | Matched DNN/XGBoost stacking title is Villafranca and Cano, Ad Hoc Networks 188, 104227 (2026). [Publisher](https://www.sciencedirect.com/science/article/pii/S1570870526000934) | Confirmed author/year/venue mismatch |
| mirsky2023 | Exact claimed AI-driven cybersecurity title not verified. Do not replace with a different Mirsky paper such as Kitsune merely because the author/topic is similar. | Unresolved |
| barros2022 | Actual closest work is Barnard, Marchetti and DaSilva, IEEE Networking Letters 4(3), 167–171 (2022). [Publisher](https://ieeexplore.ieee.org/document/9807332/) | Confirmed author/venue mismatch; related-work characterization also wrong |
| zago2022 | Extended DNS/DGA SHAP title matches IEEE Access (2023), [DOI](https://doi.org/10.1109/ACCESS.2023.3286313). | Metadata candidate; full authors pending |
| ahmad2024 | Extended CNN/LSTM/GRU title matches Computation 13(9), 222 (2025), [DOI](https://doi.org/10.3390/computation13090222). | Candidate; verify intended source and authors |
| tama2022 | Matching transparency/interpretability title is Mohale and Obagbuwa, Frontiers in Computer Science 7:1520741 (2025). [Publisher](https://doi.org/10.3389/fcomp.2025.1520741) | Confirmed author/year/venue mismatch |
| li2024 | Exact-title metadata points to Guo, Li, Cheng, Yang and Gong, Future Internet 17(10), 456 (2025). [DOI](https://doi.org/10.3390/fi17100456) | Metadata mismatch; content verification pending |
| kundu2024 | Extended-title candidate in Journal of Cloud Computing 15, 58 (2026), [DOI](https://doi.org/10.1186/s13677-026-00878-6). | Candidate; supplied venue/year differ |
| lundberg2020 | Nature Machine Intelligence 2, 56–67 (2020). [Publisher](https://www.nature.com/articles/s42256-019-0138-9) | Core metadata verified |
| sharafaldin2018 | ICISSP 2018, 108–116, [DOI](https://doi.org/10.5220/0006639801080116). | Core metadata verified |
| hassan2024 | Matched SSAE/XGBoost article is Hari Vinayak M. V. and Jarin T., Computers & Security 150, 104212 (2025; online DOI dated 2024). [Publisher](https://www.sciencedirect.com/science/article/pii/S0167404824005182) | Confirmed attribution/volume/article mismatch |

Repair procedure: obtain publisher-exported BibTeX, compare DOI/title/authors/year/venue/pages against the paper itself, then read the source to verify the cited claim. Keep online-first and issue years explicit when different. Do not mechanically replace all entries using fuzzy title matching.

The private `references.bib` is a LaTeX `thebibliography` block ending in `end{document}`, not a valid BibTeX database, and the current manuscript embeds its own bibliography. Consolidate to one valid reference system during the private rewrite. Counts of reviewed papers in the prose/table/bibliography also disagree.
