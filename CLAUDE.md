# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

42 disability-related datasets from 25+ sources (Census, WHO, SSA, VA, EEOC, BLS, NCES, CMS, HUD, WIPO, etc.) unified into a single collection with 10 Jupyter analysis notebooks. Has its own git repo at `lukeslp/accessibility-atlas`.

## Directory Layout

```
accessibility-atlas/
├── *.json, *.csv, *.xlsx       # 47 data files in the root
├── notebooks/                  # 10 category-specific Jupyter notebooks
│   ├── census_disability_demographics.ipynb
│   ├── disability_employment.ipynb
│   ├── web_accessibility.ipynb
│   ├── international_disability.ipynb
│   ├── special_education_idea.ipynb
│   ├── government_benefits.ipynb
│   ├── healthcare_mental_health.ipynb
│   ├── housing_transportation_education.ipynb
│   ├── assistive_technology.ipynb
│   └── sign_language_vision_aac.ipynb
├── accessibility_atlas_demo.ipynb   # Quick-start sampler notebook
├── dataset_index.json               # Master catalog of all 42 datasets
├── DATA_QUALITY_SUMMARY.md          # Known data quality notes
└── accessibility_dataset_catalog.json  # Structured catalog metadata
```

## Data Categories

| Category | Files | Key Data |
|----------|-------|----------|
| Census Demographics | 8 | County, state, national disability rates (ACS) |
| Employment | 4 | BLS employment gap, EEOC ADA charges, JAN accommodations |
| Special Education | 6 | IDEA Part B enrollment, NCES tables (xlsx) |
| Web Accessibility | 5 | WebAIM Million, screen reader survey, Section 508 |
| International | 8 | WHO (194 countries), OECD, Eurostat, World Bank, CRPD |
| Government Benefits | 3 | SSA SSDI/SSI, VA disability compensation |
| Healthcare | 2 | CMS Medicaid enrollment (4.7MB), SAMHSA mental health |
| Housing/Transport | 2 | HUD fair housing complaints, NTD paratransit |
| Other | 4 | CRDC education, WIPO patents, VizWiz VQA, ADA lawsuits |

## Key File: `census_disability_by_county_2022.csv`

This file is used by the interactive inequality atlas at `~/html/datavis/interactive/atlas/` as the `disability` layer. 3,100+ counties with FIPS codes, disability rates, and 6 disability types.

## Integration Points

- **Inequality Atlas**: `census_disability_by_county_2022.csv` is symlinked into `data_trove/` and served as a choropleth layer
- **Data Trove**: Several files referenced by the data trove catalog
- **Kaggle**: Published as `lucassteuber/accessibility-atlas`
- **HuggingFace**: Ready for publishing (blocked by write token)

## Platforms

- **GitHub**: `lukeslp/accessibility-atlas` (own repo)
- **Kaggle**: Ready to publish
- **HuggingFace**: Ready to publish

## License

MIT for the collection. Individual datasets carry their source licenses (public domain for US gov, CC BY-NC-SA 3.0 IGO for WHO, CC BY 4.0 for World Bank/VizWiz).
