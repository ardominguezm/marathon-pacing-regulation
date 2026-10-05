# Data provenance and reproducibility

This project analyzes public marathon results with cumulative split times at 5-km checkpoints. The analysis harmonizes Boston, Chicago, New York, and Berlin into a common schema with fields such as age, sex, year, city, cumulative split times, and net finishing time.

## Source configuration used during development

The analysis workflow used the following sources/locations:

```python
urls = {
    "Boston":  "https://raw.githubusercontent.com/bonyejekwe/Marathon_Predictor/main/processed_data/full_data_bos.csv",
    "Chicago": "https://raw.githubusercontent.com/bonyejekwe/Marathon_Predictor/main/processed_data/full_data_chi.csv",
    "NewYork": "https://raw.githubusercontent.com/bonyejekwe/Marathon_Predictor/main/processed_data/full_data_nyc.csv",
    "Berlin":  "/content/berlin_marathon_2021_2024.csv"
}
```

Boston, Chicago, and New York were loaded from the public source above. Berlin was supplied separately during analysis and is therefore **not redistributed in this repository** until its provenance and redistribution terms are documented.

## Harmonized schema

The working dataset contains:

`Name, Age, Sex, 5K, 10K, 15K, 20K, HALF, 25K, 30K, 35K, 40K, Finish Net, Year, City, Finish_hr`

Cumulative split fields are represented in seconds in the harmonized analysis table.

## Quality-control principles

Primary QC retained runners with plausible demographic and performance ranges and complete monotone 5-km checkpoints. The final mechanistic analysis used:

- age 15–80 years;
- finish time below 8 h;
- sex coded M/F;
- complete 5K through 40K cumulative checkpoints;
- monotone cumulative times;
- segment velocity 1.5–7.5 m/s;
- adjacent segment-velocity ratio 0.55–1.55.

A tighter sensitivity filter used 1.8–7.0 m/s and adjacent ratio 0.65–1.40.

## Privacy and redistribution

This repository is intended to contain only analysis code, aggregate outputs, and publication figures. Participant-level source data should only be redistributed when source terms explicitly permit it. Names and other directly identifying fields are not required by the analysis and should not be included in public releases.

## Processed results

`processed_results/` contains only aggregate statistical outputs needed to reproduce paper figures and tables. These are safe to publish with the manuscript repository.
