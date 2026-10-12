# Source data and analytical reproducibility

The study uses official marathon timing information from Berlin, Boston, Chicago and New York City as represented in a harmonized research dataset. The tracked repository contains **aggregate result tables**, not raw individual-level marathon records or the complete data-to-estimate regression pipeline.

## Development-stage inputs

The original data assembly referenced third-party public CSV exports:

```python
urls = {
    "Boston":  "https://raw.githubusercontent.com/bonyejekwe/Marathon_Predictor/main/processed_data/full_data_bos.csv",
    "Chicago": "https://raw.githubusercontent.com/bonyejekwe/Marathon_Predictor/main/processed_data/full_data_chi.csv",
    "NewYork": "https://raw.githubusercontent.com/bonyejekwe/Marathon_Predictor/main/processed_data/full_data_nyc.csv",
    "Berlin":  "/content/berlin_marathon_2021_2024.csv"
}
```

The Boston, Chicago and New York locations are third-party processed exports, not direct official organizer endpoints. **Berlin was loaded from a separate local file, whose original provenance, extraction procedure and redistribution terms have not been fully recorded.** This should be resolved before describing all inputs as independently retrievable from the repository.

## Harmonized variables

`Name, Age, Sex, 5K, 10K, 15K, 20K, HALF, 25K, 30K, 35K, 40K, Finish Net, Year, City, Finish_hr`. Cumulative split fields were harmonized in seconds. The published analysis must not expose participant names.

## Primary quality-control specification

- Age 15–80 years and finish time below 8 h.
- Sex recorded as M/F in source tables.
- Complete cumulative split times from 5 to 40 km in 5-km increments and strictly increasing times.
- Each segment velocity within 1.5–7.5 m/s; adjacent velocity ratios within 0.55–1.55.
- Development-stage stricter filters: 1.8–7.0 m/s and adjacent ratio 0.65–1.40.

Reported retained records: 551,337 of 570,843 (96.6%). The input-level QC code and exclusion log are **not currently tracked**, so retention cannot be independently recomputed from this repository.

## Frozen aggregate results

`processed_results/` contains the summary CSVs used in the manuscript and figure-generation notebook. See repository [AUDIT.md](../AUDIT.md) for the itemized claims and known limitations.

## Privacy and access

Do not upload participant-level tables or names without explicitly verifying source terms and privacy considerations. The current repository is private and does not offer public access to its notebooks or aggregate outputs. If public release is intended, review all data rights and notebook outputs before changing visibility.
