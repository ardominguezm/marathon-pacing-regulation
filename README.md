# Marathon Pacing Regulation

**Working paper:** *Quantifying Pacing Regulation in Marathon Running: A Field-Derived Functional and Its Information Horizon*

This repository contains the reproducible analysis workflow, processed result tables, and publication-quality figures for a population-scale study of marathon pacing regulation across four major marathons.

## Scientific idea

We model the runner's split-by-split velocity trajectory using a quadratic pacing-regulation functional. For normalized segment velocity $r(x)$, the observed regulation cost through distance $x$ is

$$
\mathcal{R}(x)=\frac{1}{m(x)}\sum_{j\le m(x)}[r(x_{j+1})-r(x_j)]^2.
$$

The main empirical result is an **information horizon**: the earliest race distance at which pacing-regulation structure contains reproducible information about subsequent late-race capacity preservation. In the analyzed cohorts, this signal is weak at 15 km, emerges reproducibly by approximately 20 km, and strengthens markedly by 25 km.

## Study scale

- 551,337 marathon finishers after quality control
- Boston, Chicago, New York, and Berlin
- 16 marathon-year cohorts
- 5-km cumulative split structure
- primary late-race outcome: 30–40 km capacity preservation

## Repository structure

```text
.
├── README.md
├── CITATION.cff
├── LICENSE
├── requirements.txt
├── .gitignore
├── data/
│   ├── README.md
│   └── processed_results/
├── notebooks/
│   ├── 01_mechanistic_test.ipynb
│   ├── 02_information_horizon.ipynb
│   └── 03_reproduce_final_figures.ipynb
├── figures/
│   ├── main/
│   └── supplementary/
├── docs/
│   └── analysis_notes.md
└── paper/
    └── README.md
```

## Main findings

The information-horizon analysis showed:

| Horizon | Standardized APRC coefficient | Incremental R² | Cohorts with negative coefficient |
|---:|---:|---:|---:|
| 15 km | -0.00131 | 0.00018 | 11/16 |
| 20 km | -0.00977 | 0.00939 | 16/16 |
| 25 km | -0.02575 | 0.06288 | 16/16 |

The 30-km horizon is treated as a boundary sensitivity analysis because the primary late-race outcome begins at 30 km.

## Interpretation

The pacing-regulation functional is a **field-derived quadratic descriptor of spatial pacing roughness/regulation**. It is not interpreted as thermodynamic entropy production, metabolic energy dissipation, Joules, kcal, or direct physiological work. The study asks whether the organization of the pacing trajectory contains reproducible information about later-race capacity preservation.

## Reproducibility

The analysis notebooks generate the processed result tables used by the manuscript. The final figure notebook reproduces the paper figures from frozen CSV outputs and exports PDF, SVG, and 600-dpi PNG files.

Raw participant-level data are not redistributed here unless licensing and provenance explicitly allow it. See `data/README.md` for source and reproducibility details.

## Status

Manuscript in preparation for submission to a physiology / applied physiology journal.
