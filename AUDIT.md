# Scientific and reproducibility audit

Audit date: 2026-10-12. Examined supplied manuscript and the repository's tracked results, figures notebook and provenance documentation. This is an **evidence audit of versioned artifacts**, not an independent recomputation from participant-level split records.

## Claim-to-evidence crosswalk

| Manuscript claim | File | Assessment |
| --- | --- | --- |
| Main coefficients, confidence intervals, incremental R², horizons 15/20/25/30 | `data/processed_results/information_horizon.csv` | Values agree after rounding |
| Absolute late-velocity model; baseline R² 0.805789; horizons 15/20/25 | `data/processed_results/decoupled_absolute_late_velocity.csv` | Values agree after rounding |
| APRC vs same-horizon CV correlations and incremental R² | `data/processed_results/aprc_vs_cv.csv` | Values agree after rounding; *ordering-specific* contribution not isolated |
| Negative race-year slopes (16/16 at both 20 and 25 km), CIs | `data/processed_results/horizon_city_year_replication.csv` | Verified for 20 and 25 km; 15-km cohort-level table not archived |
| Four within-stratum performance quartiles and coefficients | `data/processed_results/performance_horizon.csv` | Values agree after rounding |
| Regional PRC means, medians, interquartile values | `data/processed_results/spatial_prc_progression.csv` | Values agree after rounding |
| 551,337 from 570,843 after QC | Manuscript and data README | Claimed consistently; cannot independently reproduce without raw-data processing pipeline |
| All race-specific model computations, HC3 confidence intervals, age/covariate encodings | No full estimator notebook tracked | **Not independently reproducible here** |
| Tighter QC sensitivity results | Data README documents thresholds | No corresponding archived sensitivity output |
| Figure production from frozen outputs | `notebooks/04_final_EJAP_figures.ipynb` | Figure notebook available; some numerical series are embedded rather than read directly from CSVs |

## Scientific qualifications requiring resolution

1. **Future-informed normalization at 15 km.** APRC normalizes all horizons by median velocity of segments ending at 10, 15 and 20 km. Thus the 15-km metric indirectly uses the 15–20-km segment. Either redefine the 15-km assessment explicitly as retrospective or recompute horizon-specific causally normalized variants before claiming an online information onset.
2. **Different operational criteria for outcome variants.** For primary LCP, the first horizon meeting incremental R² ≥ 0.005, negative pooled beta and ≥75% negative cohorts is 20 km. In the absolute-velocity sensitivity outcome, the 20-km incremental R² is 0.00226668, below 0.005. It replicates directional sign and relative progression, **not the identical three-part decision rule**.
3. **APRC vs CV.** Positive incremental R² after conditioning on CV is supported. It does not uniquely attribute the signal to order or adjacency; assess with matched nonordered features and/or segment permutations if this stronger inference is desired.
4. **Meaning of coefficients.** Confirm exactly which outcomes and predictors were standardized in the original regression scripts; distinguish coefficients for standardized predictors from fully standardized betas. The archived coefficient CSV alone does not prove the coding convention.
5. **Time windows and averages.** Specify whether outcome-window velocity is arithmetic mean of 5-km segment speeds versus distance/time aggregate speed; document the actual implementation.
6. **Independence and validation.** Cohort-level sign replication within the development dataset does not establish held-out external performance prediction, causal effect or a physiological cutoff.
7. **Original data provenance.** Third-party CSVs for Boston, Chicago, NYC are identified in `data/README.md`; Berlin's separately supplied input lacks a verified origin and retrieval protocol.
8. **Incomplete evidence archive.** 15-km per-cohort results, individual-level data QC audit log, regression fitting code, stricter QC outputs, and an automated results-to-manuscript verification test are not versioned here.
9. **Ethics and declarations.** Check institutional requirements and statements prior to journal submission. Publicly accessible individual race records do not automatically imply documented ethics exemption.
10. **Repository claims.** The current figure notebook uses frozen and partly inlined numeric inputs; describe it as figure reproducibility, not full analytical reproducibility.

## Submission-readiness assessment

**Numerical alignment of currently archived principal aggregate results: confirmed.**
**End-to-end reproducibility: not demonstrated.**
**Prospective interpretation of the 15-km information horizon: not established.**
**External predictive validation: not performed.**
**Physiological mechanism or causality: not established.**

The manuscript should be revised to remove claims exceeding these bounds or supplemented with additional analyses and archived code. No findings were recomputed from raw individual records in this audit.
