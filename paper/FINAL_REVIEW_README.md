# EJAP final-review bundle

Canonical manuscript: `paper/main.tex`.

## Compile
From the `paper/` directory:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

The manuscript keeps full figure captions in the text, following the submission-ready workflow in which artwork is uploaded separately.

## Final artwork
Run `notebooks/04_final_EJAP_figures.ipynb` in Google Colab. It is self-contained and exports Figures 1–6 and Supplementary Figure S1 as vector PDF, editable SVG, and 600-dpi PNG.

The first code cell exposes typography controls:
`BASE_FONT`, `LABEL_FONT`, `TITLE_FONT`, `ANNOT_FONT`, `DPI`, and `DOUBLE_W`.

## Figure design
The final design intentionally uses concise in-panel headings and annotations, generous whitespace, minimal chart ink, vector output, and full explanatory captions in the manuscript. Figure 2 and Figure 6 use two panels so that incremental explained variance and standardized coefficient estimates are shown without crowding.

## Files for editorial review
- `main.tex`
- `references.bib`
- `Supplementary_Table_S1.tex`
- `Supplementary_Table_S1_evidence_map.csv`
- `BIBLIOGRAPHIC_AUDIT.md`
- `../notebooks/04_final_EJAP_figures.ipynb`

Before submission, complete the author details, funding, author contributions, ethics determination, consent language if applicable, and final publisher-compliant AI-use statement.
