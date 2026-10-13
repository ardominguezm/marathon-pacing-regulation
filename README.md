# Marathon Pacing Regulation

**Research software and aggregate-results archive** for the submitted manuscript *A Quadratic Functional for Quantifying Pacing Regulation and Its Information Horizon in Marathon Running* (submitted to *European Journal of Applied Physiology*, October 2026). Manuscript and supplementary source files are maintained separately in Overleaf and are **not included** here.

This repository documents a quadratic functional of successive normalized marathon split velocities, numerical summaries from the study, figure-generation code, and an experimental validation notebook. **It does not currently reproduce the complete analysis from individual runner records.**

## Study and interpretation

The submitted analysis reports **551,337 retained finishers** from Berlin, Boston, Chicago and New York City (16 race-year cohorts, 2021–2024), subject to the original study's quality-control criteria. These are reported study totals, **not independently reconstructed by the currently archived notebooks**.

| Horizon | APRC coefficient (primary LCP outcome) | Incremental R² | Negative race-year cohorts |
| --- | ---: | ---: | ---: |
| 15 km | -0.00131 | 0.00018 | 11/16 (reported in manuscript) |
| 20 km | -0.00977 | 0.00939 | 16/16 |
| 25 km | -0.02575 | 0.06288 | 16/16 |

The **20-km information horizon** is defined operationally for the primary ratio outcome by incremental R² ≥ 0.005, a negative pooled coefficient, and negative coefficients in at least 75% of the 16 race-year cohorts. It is not a physiological transition or a demonstrated out-of-sample prediction threshold. With an alternative absolute late-velocity outcome, the 20-km incremental R² is **0.002267**, below the same cutoff, even though all 16 coefficients at 20 and 25 km are negative.

**Temporal availability:** The normalization reference uses the median of segment velocities ending at 10, 15 and 20 km. Hence the reported 15-km APRC was calculated **retrospectively**; it should not be described as available at the 15-km checkpoint in real time. APRC is a dimensionless local-variation functional and **not** a measure of metabolic energy expenditure.

## Repository map

| Path | Contents | Reproduction scope |
| --- | --- | --- |
| [data/processed_results/](data/processed_results/) | Six frozen aggregate CSV result tables | Reported summary estimates only |
| [notebooks/04_final_EJAP_figures.ipynb](notebooks/04_final_EJAP_figures.ipynb) | Manuscript figure generation from frozen, partly embedded estimates | Figures, not participant-level reanalysis |
| [notebooks/05_temporal_normalization_validation.ipynb](notebooks/05_temporal_normalization_validation.ipynb) | Attempt to reconstruct input/QC and test timing of normalization | **Unresolved validation experiment; stops on a QC mismatch** |
| [data/README.md](data/README.md) | Source provenance, variables, and QC specification | Documentation, not hosted runner records |
| [AUDIT.md](AUDIT.md) | Evidence crosswalk and unresolved limitations | Audit notes |
| [requirements.txt](requirements.txt) | Python dependencies | Execution environment |

## Reproducing figures

Install the dependencies in `requirements.txt`, then run notebook **04** in Jupyter or Colab. Its default figure output directory is `/content/final_ejap_figures`; adapt the path as needed. The notebook uses frozen/embedded estimates and therefore does not independently establish participant-level analytical reproducibility.

## Validation notebook status

Notebook **05** was executed against retrievable sources but halted at its QC reproduction gate. In that run, **572,004 input records** and **403,161 retained records** did not match the manuscript's **570,843 input** and **551,337 retained**. Its captured `AssertionError` is a diagnostic **failure to reproduce the original assembly/QC**, not a new or validated study result. Do not interpret any hypothetical downstream normalisation comparison as completed. Reconciliation requires identifying the exact original inputs, column harmonization, exclusion order and processing code.

## Data access and rights

Original race timing information is associated with the marathon organizers, but the development workflow also referenced third-party **processed** CSV exports for Boston, Chicago and New York City. The Berlin source was supplied as a local file and its retrieval provenance is not yet fully documented. See [data/README.md](data/README.md). No participant-level tables, names, or personal identifiers are distributed in this repository. Check organizer/source terms before reusing records.

## Citation and release scope

Software citation metadata are provided in [CITATION.cff](CITATION.cff). This is a **software and aggregate-results archive accompanying a submitted manuscript**, not a published article, not a full raw-to-results replication package, and not a repository of manuscript source files. Scientific caveats and outstanding audit items are listed in [AUDIT.md](AUDIT.md).
