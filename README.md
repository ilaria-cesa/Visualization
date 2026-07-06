# Closing the Gap? Gender and Tertiary Education in Europe (2015–2024)

Data visualization project for the *Data Visualization* course — MSc Data Science.

## Overview

This project explores gender representation among tertiary education students
across the EU27, using Eurostat data from 2015 to 2024. It looks beyond the
EU27-wide average to ask whether the gender gap has actually closed, whether it
behaves the same way across degree levels and countries, and what structural
factors might explain the countries that stand out from the rest.

## Research questions

1. **Has the gender gap in tertiary education actually closed?**
   Tracking the evolution of the female share of EU27 tertiary students, by degree
   level, from 2015 to 2024.
2. **Is the "leaky pipeline" a universal EU27 pattern, or does it vary by country?**
   Comparing the gap between Bachelor's and Doctoral female share across all 27
   member states.
3. **What explains the outliers?**
   Investigating whether countries with the widest gender gap are also structurally
   different in how "advanced-education-intensive" their systems are.

## Data source

- **Dataset:** Eurostat [*educ_uoe_enrt03*](https://ec.europa.eu/eurostat/databrowser/view/educ_uoe_enrt03/default/table?lang=en) — Students enrolled in tertiary education by education level, sex and country.
- **Coverage:** EU27 member states, 2015–2024.
- **License:** Eurostat open data license (free reuse with attribution).
- Data was downloaded directly from the Eurostat Data Browser in May 2026.

## Repository structure

```
.
├── data/
│   └── educ_uoe_enrt03.csv          # raw Eurostat export (wide format)
├── notebook/
│   └── analysis.ipynb               # full analysis notebook
├── charts/
│   ├── chart1_female_share_trend.png
│   ├── chart2_pipeline_by_level.png
│   ├── chart3_female_share_by_country.png
│   ├── chart4_pipeline_gap_by_country.png
│   ├── chart_advanced_intensity.png
│   ├── chart_composition_area.png
│   └── chart7_map_female_share.png  # Datawrapper export
├── slides/
│   └── presentation.pptx
├── README.md
└── LICENSE
```

## How to reproduce

1. Download the dataset from the Eurostat link above (or use the copy in `data/`).
2. Install dependencies:
   ```
   pip install pandas numpy matplotlib seaborn plotly kaleido
   ```
3. Run `notebook/analysis.ipynb` top to bottom. It will:
   - clean and reshape the raw Eurostat export from wide to long format,
   - compute the female share of students by country, year and degree level,
   - generate all charts saved to `charts/`.
4. The choropleth map was built separately in [Datawrapper](https://www.datawrapper.de/); the underlying CSV (`female_share_for_datawrapper.csv`) is exported by the notebook.

## Key findings

- The EU27 female share of tertiary students (all levels) declined slightly from
  ≈62.5% in 2015 to ≈59.8% in 2024, even as every individual degree level trended
  upward — a composition effect explained by short-cycle tertiary programs not
  broken out separately in the aggregate.
- Doctoral is the level closest to gender parity (≈51.6% in 2024) and the one that
  moved the least over the decade.
- The pipeline gap (Bachelor's minus Doctoral female share) ranges from ≈+13
  percentage points in France to ≈−10 in Latvia, the only country where the pattern
  reverses.
- The countries furthest from gender parity overall (France, Austria, Cyprus,
  Luxembourg) are, with one exception, also the EU27's most
  advanced-education-intensive systems, suggesting a structural rather than purely
  cultural explanation.

## Tools & libraries

- **Python:** `pandas`, `numpy`, `matplotlib`, `seaborn` — data cleaning, reshaping and static charts.
- **Plotly / Datawrapper:** interactive and choropleth mapping.
- **Claude (Anthropic):** used as an AI assistant to support the writing of data-cleaning and visualization code, and to help structure the analysis and presentation content.

## License

- **Code and analysis:** shared under the MIT License (see `LICENSE`).
- **Data:** Eurostat, reused under the Eurostat open data license, with attribution.
- **Slides:** "Closing the Gap? Gender and Tertiary Education in Europe"
