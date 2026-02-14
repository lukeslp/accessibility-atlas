---
license: other
license_name: mixed-licenses
license_link: https://github.com/lukeslp/accessibility-atlas
task_categories:
  - tabular-classification
  - feature-extraction
language:
  - en
tags:
  - accessibility
  - disability
  - wcag
  - employment
  - census
  - who
  - assistive-technology
  - special-education
  - screen-readers
  - health
  - demographics
  - web-accessibility
pretty_name: Accessibility Atlas
size_categories:
  - 10K<n<100K
---

# Accessibility Atlas

42 datasets covering disability demographics, employment gaps, web accessibility compliance, assistive technology patents, special education, healthcare, housing discrimination, transportation, government benefits, and more -- across 15 categories.

Built for researchers, journalists, policy analysts, and anyone building tools for disabled communities.

## What's Inside

### US Disability Demographics (Census Bureau)
8 datasets from the American Community Survey covering county, state, and national disability rates.

- County-level: 3,100+ counties (ACS 5-Year 2022)
- State-level: 50 states + DC (ACS 5-Year 2021)
- National trends: 13-year trend (11.9% to 13.6%)
- Demographics: by race, age, sex, and 6 disability types

### Disability Employment
4 datasets on the employment gap, discrimination charges, and workplace accommodations.

- BLS employment/unemployment by disability status
- FRED 16-year time series (gap narrowing from 40pp to 37pp)
- 679,637 ADA discrimination charges (1992-2024)
- JAN accommodation cost data (58.7% cost $0)

### Special Education (IDEA)
6 datasets from the National Center for Education Statistics on 7.5M students served under IDEA Part B.

- 13 disability categories
- 51 states
- 1976-2023 historical data
- Demographics, environments, state-level breakdowns

### Web Accessibility
5 datasets on WCAG compliance, lawsuits, screen reader usage, and Section 508.

- WebAIM Million: 94.8% of top 1M pages fail WCAG
- Screen reader survey: 1,539 respondents
- ADA digital lawsuits: 814 (2017) to ~4,000 (2024)
- Section 508: 245 federal entities, only 23% conform
- HTTP Archive a11y trends 2019-2024

### International Disability
8 datasets covering 194+ countries.

- WHO: disability prevalence, DALYs/YLDs, healthy life expectancy
- OECD: 34 countries, prevalence/employment/spending
- Eurostat: 36 EU countries
- World Bank: 10 socioeconomic indicators
- UN CRPD: 199 countries ratification status

### Government Benefits
- SSA: SSDI/SSI annual data (7.3M + 4.9M beneficiaries)
- VA: disability compensation by state (5.7M+ veterans)

### Healthcare & Mental Health
- CMS: Medicaid disability enrollment (10.2M enrollees)
- SAMHSA: mental health prevalence 2008-2023

### Housing, Transportation, Education
- HUD: fair housing complaints (disability is #1 basis, ~55%)
- NTD: paratransit ridership/costs ($40-50/trip)
- CRDC: Section 504, restraint/seclusion, discipline

### Assistive Technology Patents
- WIPO: patent data 1985-2026 (10 → 519 patents)

### Visual Accessibility
- VizWiz: 4,319 VQA pairs from blind users (CC BY 4.0)

## Key Findings

**44.1 million Americans (13.4%) have a disability** (Census 2022). Rate rose from 11.9% (2010) to 13.6% (2023). Ambulatory (6.7%) and cognitive (5.7%) are most common.

**The employment gap is massive.** 24.5% labor force participation (disabled) vs ~67% (non-disabled). OECD average gap: 34 percentage points.

**Workplace accommodations are cheap.** 58.7% cost nothing. Median: $300. Yet 679,637 ADA charges filed since 1992.

**The web is still broken.** 94.8% of top 1M websites fail WCAG. Average: 51 errors/page.

**Disability is #1 basis for fair housing complaints** (~55% of all HUD complaints).

**Special education is growing.** 15.2% of public school students now served under IDEA. Autism grew 8.5x since 2000.

**Globally, 1.3 billion people (16%) live with significant disability** (WHO). 190 countries signed UN CRPD.

## Notebooks

10 Jupyter notebooks in `notebooks/` that load the data, run analysis, and produce charts:

- `census_disability_demographics.ipynb`: Maps, trends, demographic breakdowns
- `disability_employment.ipynb`: Employment gap over time, discrimination charges
- `web_accessibility.ipynb`: WCAG failure trends, screen reader market share
- `international_disability.ipynb`: Cross-country comparisons
- `special_education_idea.ipynb`: Enrollment trends, discipline disparities
- `government_benefits.ipynb`: Benefit trends, state-level processing
- `healthcare_mental_health.ipynb`: Enrollment, treatment gaps
- `housing_transportation_education.ipynb`: Fair housing, transit costs
- `assistive_technology.ipynb`: Patent growth by category
- `sign_language_vision_aac.ipynb`: Visual question answering

Plus `accessibility_atlas_demo.ipynb` in root as a quick-start sampler.

## Data Sources & Licenses

Most data is from US government (public domain) and international organizations (open licenses). Individual datasets carry their own licenses:

| Source | License |
|--------|---------|
| US Census Bureau | Public Domain |
| Bureau of Labor Statistics | Public Domain |
| US Dept. of Education | Public Domain |
| SSA, VA, CMS, SAMHSA | Public Domain |
| HUD, NTD, CRDC | Public Domain |
| WHO Global Health Observatory | CC BY-NC-SA 3.0 IGO |
| OECD, Eurostat, World Bank | Open licenses (see sources) |
| WebAIM | Fair use (structured summaries) |
| VizWiz | CC BY 4.0 |

Full source table with URLs in main README.

## File Format

Data files: JSON, CSV, Excel (XLSX)
Notebooks: Jupyter (.ipynb)

## About

Part of the [Data Trove](https://dr.eamer.dev/datavis/data_trove/) collection. I built this because disability data is scattered across dozens of federal agencies, international organizations, and advocacy groups. Having it all in one place -- with consistent formatting and analysis notebooks -- makes it actually usable.

**Luke Steuber** • [lukesteuber.com](https://lukesteuber.com) • [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com)

## Citation

```bibtex
@misc{steuber2026accessibility,
  title={Accessibility Atlas: Disability Demographics and Web Accessibility Dataset Collection},
  author={Steuber, Luke},
  year={2026},
  url={https://huggingface.co/datasets/lukeslp/accessibility-atlas}
}
```

## License

MIT License for the collection. Individual datasets have their own licenses (see table above). Public domain data can be used freely. WHO data is CC BY-NC-SA 3.0 IGO. VizWiz is CC BY 4.0.
