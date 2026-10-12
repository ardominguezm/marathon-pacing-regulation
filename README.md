# Marathon Pacing Regulation

Research code and frozen aggregate results accompanying the study **Quantifying Pacing Regulation in Marathon Running: A Field-Derived Functional and Its Information Horizon**.

**Study scope:** 551,337 retained finishers; Berlin, Boston, Chicago and New York City; 16 race-year cohorts (2021–2024). This repository is an **analysis-results and figure-reproduction archive**, not yet an end-to-end reproduction pipeline from individual race records.

## Main findings (within-sample associations)

| Horizon | APRC coefficient, LCP outcome | Incremental R² | Cohorts with negative coefficients |
| --- | ---: | ---: | ---: |
| 15 km | -0.00131 | 0.00018 | 11/16 (reported; not in cohort CSV) |
| 20 km | -0.00977 | 0.00939 | 16/16 |
| 25 km | -0.02575 | 0.06288 | 16/16 |

The *operational information horizon* of 20 km applies to the **primary ratio outcome** under the selected criteria (incremental R² ≥ 0.005, negative pooled coefficient, ≥75% negative cohort estimates). The alternative absolute-velocity outcome shows negative coefficients in all cohorts at 20 and 25 km but its 20-km incremental R² (0.002267) does **not** satisfy the same 0.005 cutoff.

**Interpretation caveat:** APRC uses median segment velocity over 5–10, 10–15 and 15–20 km for normalization. The retrospectively calculated 15-km APRC therefore depends on a future (15–20 km) segment. These results must not be described as a prospectively available real-time 15-km metric until a causal normalization is implemented and results recomputed. APRC is a dimensionless quadratic trajectory-roughness descriptor, not metabolic energy.

## Repository contents

- `data/processed_results/`: frozen aggregate outputs for horizon models, race-year replication, performance quartiles, spatial progression, CV comparison and absolute-velocity sensitivity analysis.
- `notebooks/04_final_EJAP_figures.ipynb`: figure-generation notebook built from frozen summary statistics (partly embedded in the notebook). It does **not** rerun QC or regression analyses from raw race records.
- `data/README.md`: source-data locations, data schema, QC filters, and provenance limitations.
- `AUDIT.md`: claim-to-evidence crosswalk and outstanding validation tasks.
- `requirements.txt`: Python environment dependencies.

Manuscript and supplementary LaTeX source are maintained **outside** this analysis repository.

## Figure workflow

Run `notebooks/04_final_EJAP_figures.ipynb` in Google Colab or a notebook environment with the dependencies in `requirements.txt`. Figures are written to `/content/final_ejap_figures` in the notebook's current Colab configuration. Paths may need adapting for local execution. Figures are generated from frozen summaries, not recomputed individual-level analyses.

## Data and responsible use

Source data include public third-party marathon tables; see `data/README.md`. Participant-level records (including names) are not redistributed here. Berlin was provided through a separate local file; its source provenance and redistribution permission remain to be documented. A public release must not overstate end-to-end reproducibility or direct availability of all source records.

## Status

**Audit status: numerical cross-check of frozen aggregate results completed; full computational reproducibility and prospective interpretation not yet verified.** See [AUDIT.md](AUDIT.md) before submitting or publicly releasing scientific claims.
