# Accessibility Atlas

53 datasets on disability in the US and globally. Demographics, employment, web accessibility, assistive tech patents, special education, healthcare, housing discrimination, transportation, government benefits, and more.

Disability data is scattered across dozens of federal agencies, international organizations, and advocacy groups. This repo puts it all in one place with consistent formatting so you can actually use it.

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Datasets](https://img.shields.io/badge/datasets-53-green)](dataset_index.json)
[![Notebooks](https://img.shields.io/badge/notebooks-10-purple)](notebooks/)
[![Live Site](https://img.shields.io/badge/live-dr.eamer.dev-orange)](https://dr.eamer.dev/datavis/data_trove/)

## What's Inside

### US Disability Demographics (Census Bureau)

8 datasets from the American Community Survey covering county, state, and national disability rates.

| File | Coverage | Source |
|------|----------|--------|
| `census_disability_by_county_2022.csv` | 3,100+ counties | ACS 5-Year 2022 |
| `census_disability_states_2021.csv` | 50 states + DC | ACS 5-Year 2021 |
| `census_disability_characteristics_2022.json` | National (sex, race, age, 6 types) | ACS 1-Year 2022, S1810 |
| `census_disability_by_race_2022.json` | 9 race/ethnicity groups | ACS 1-Year 2022, B18101 |
| `census_disability_by_age_sex_2022.json` | National (6 age groups x sex) | ACS 1-Year 2022, B18101 |
| `census_disability_national_trends.json` | 5-year trend (12.68% to 13.45%) | ACS 1-Year 2017-2022 |
| `census_disability_trends_clean.json` | 13-year trend (11.9% to 13.6%) | ACS 1-Year 2010-2023 |
| `census_disability_trends_2010_2023.json` | Raw S1810 + B18101 tables | ACS 1-Year 2010-2023 |

### Disability Employment

4 datasets on the employment gap, discrimination charges, and workplace accommodations.

| File | What It Covers |
|------|---------------|
| `bls_disability_employment_2024.json` | BLS employment/unemployment by disability status |
| `fred_disability_employment.json` | FRED 16-year employment time series (2009-2024) |
| `eeoc_ada_charges.json` | 33 years of ADA discrimination charges (1992-2024) |
| `jan_workplace_accommodations.json` | JAN accommodation cost data |

### Special Education (IDEA)

6 datasets from the National Center for Education Statistics on students served under IDEA Part B.

| File | Format | Coverage |
|------|--------|----------|
| `idea_special_education_enriched.json` | JSON | 7.5M students, 51 states, 13 disability categories, 1976-2023 |
| `idea_special_education_2023.json` | JSON | Original NCES data |
| `nces_204_30_disability_type.xlsx` | Excel | NCES Table 204.30 |
| `nces_204_50_demographics.xlsx` | Excel | NCES Table 204.50 |
| `nces_204_60_environments.xlsx` | Excel | NCES Table 204.60 |
| `nces_204_70_state.xlsx` | Excel | NCES Table 204.70 |

### Web Accessibility

5 datasets on WCAG compliance, lawsuits, screen reader usage, and federal Section 508 conformance.

| File | What It Covers |
|------|---------------|
| `webaim_million_2025.json` | WCAG failures across top 1M pages |
| `webaim_screen_reader_survey_2024.json` | 1,539 respondents on screen reader usage |
| `ada_digital_lawsuits.json` | ADA digital lawsuits 2017-2024 |
| `section_508_compliance_2024.json` | Federal agency Section 508 compliance (245 entities) |
| `web_accessibility_metrics.json` | HTTP Archive web a11y trends 2019-2024 |

### International Disability

8 datasets covering global disability prevalence, health metrics, and policy across 194+ countries.

| File | Coverage | Source |
|------|----------|--------|
| `who_disability_prevalence.json` | 194 countries + SDG indicators (25MB) | WHO, World Bank, UN SDG |
| `who_gho_disability_indicators.json` | DALYs/YLDs 2000-2021, 194 countries (13MB) | WHO Global Health Estimates |
| `who_healthy_life_expectancy.csv` | 185 countries, HALE 2000-2021 (wide) | WHO GHO API |
| `who_hale_long.csv` | Same, long format (4,070 rows) | WHO GHO API |
| `eurostat_disability_eu.json` | 36 EU countries, GALI indicator | Eurostat EU-SILC |
| `oecd_disability_data.json` | 34 OECD countries: prevalence, employment, spending | OECD SOCX, EU-SILC |
| `world_bank_disability_indicators.json` | 4,406 records, 10 socioeconomic indicators (2010-2023) | World Bank Open Data |
| `un_crpd_ratification.json` | 199 countries: CRPD ratification status | UN Treaty Collection |

### Government Benefits (SSA & VA)

3 datasets on Social Security disability, SSI, and VA compensation.

| File | What It Covers |
|------|---------------|
| `ssa_ssdi_ssi_annual.json` | SSDI/SSI beneficiaries 1970-2024 |
| `ssa_state_agency_workload.json` | State-level determination data, approval rates |
| `va_disability_compensation.json` | VA claims 2019-2026, compensation rates by state |

### Healthcare & Mental Health

2 datasets on Medicaid disability enrollment and mental health prevalence.

| File | What It Covers |
|------|---------------|
| `cms_medicaid_disability_enrollment.json` | CMS aged/blind/disabled enrollment 2013-2024 (4.7MB) |
| `samhsa_mental_health.json` | NSDUH mental health prevalence 2008-2023 |

### Housing Discrimination

| File | What It Covers |
|------|---------------|
| `hud_fair_housing_disability.json` | HUD fair housing complaints 2009-2023, by state |

### Transportation

| File | What It Covers |
|------|---------------|
| `ntd_paratransit_data.json` | ADA paratransit ridership & costs 2014-2022 |

### Education (Civil Rights)

| File | What It Covers |
|------|---------------|
| `crdc_disability_data.json` | Section 504, restraint/seclusion, discipline |

### Assistive Technology Patents

| File | What It Covers |
|------|---------------|
| `patentsview_assistive_tech.json` | WIPO assistive tech patents 1985-2026 (696KB) |

### Visual Accessibility

| File | Records | Source |
|------|---------|--------|
| `vizwiz_val_annotations.csv` | 4,319 VQA pairs from blind users | VizWiz VQA |

### Reference Files

| File | Description |
|------|-------------|
| `dataset_index.json` | Full catalog of datasets with sources, coverage, and key findings |

## Notebooks

10 Jupyter notebooks in `notebooks/` that load the data, run basic analysis, and produce charts. Each covers a category:

| Notebook | Datasets | What It Does |
|----------|----------|--------------|
| `census_disability_demographics.ipynb` | 8 Census files | Maps, trends, demographic breakdowns |
| `disability_employment.ipynb` | BLS, FRED, EEOC, JAN | Employment gap over time, discrimination charges |
| `web_accessibility.ipynb` | WebAIM, ADA lawsuits, Section 508 | WCAG failure trends, screen reader market share |
| `international_disability.ipynb` | WHO, OECD, Eurostat, World Bank, CRPD | Cross-country prevalence and policy comparisons |
| `special_education_idea.ipynb` | IDEA Part B, CRDC | Enrollment trends, discipline disparities |
| `government_benefits.ipynb` | SSA SSDI/SSI, VA disability | Benefit trends, state-level processing |
| `healthcare_mental_health.ipynb` | CMS Medicaid, SAMHSA | Enrollment, treatment gaps |
| `housing_transportation_education.ipynb` | HUD, NTD paratransit, CRDC | Fair housing complaints, transit costs |
| `assistive_technology.ipynb` | WIPO patents | Patent growth by category |
| `sign_language_vision_aac.ipynb` | VizWiz | Visual question answering analysis |

Plus `accessibility_atlas_demo.ipynb` in the root as a quick-start sampler.

## Quick Start

```python
import pandas as pd
import json

# County-level disability rates
counties = pd.read_csv("census_disability_by_county_2022.csv")
print(counties.nlargest(10, "disability_rate")[["county_name", "disability_rate"]])

# 13-year disability trend
with open("census_disability_trends_clean.json") as f:
    trends = json.load(f)
for year in trends["annual_trends"]:
    print(f"{year['year']}: {year['disability_rate_pct']}%")

# Employment gap over time (FRED)
with open("fred_disability_employment.json") as f:
    fred = json.load(f)
for row in fred["annual_data"]:
    print(f"{row['year']}: disabled {row['disabled_employment_ratio']}% vs {row['overall_employment_ratio']}%")

# OECD country comparison
with open("oecd_disability_data.json") as f:
    oecd = json.load(f)
for c in oecd["oecd_disability_statistics"]["employment_rates_by_country"]:
    print(f"{c['country']}: {c['disabled_pct']}% employed (gap: {c['gap_pp']}pp)")

# SSA disability benefits
with open("ssa_ssdi_ssi_annual.json") as f:
    ssa = json.load(f)
print(f"SSDI beneficiaries: {ssa['ssdi']['current_beneficiaries']:,}")

# ADA workplace discrimination
with open("eeoc_ada_charges.json") as f:
    eeoc = json.load(f)
print(f"Total ADA charges filed: {eeoc['summary']['total_charges']:,}")

# WebAIM Million trends
with open("webaim_million_2025.json") as f:
    webaim = json.load(f)
trends = webaim["yearly_trends"]
for year, pct in zip(trends["years"], trends["pages_with_failures_pct"]):
    print(f"{year}: {pct}% of top 1M pages have WCAG failures")
```

## What the Data Shows

The notebooks in `notebooks/` run through the numbers with charts and breakdowns. Start with `accessibility_atlas_demo.ipynb` for a sampler, or dive into the category-specific ones listed above.

## Sources

| Source | License | URL |
|--------|---------|-----|
| US Census Bureau ACS | Public Domain | https://data.census.gov |
| Bureau of Labor Statistics | Public Domain | https://www.bls.gov/cps/cpsdisability.htm |
| FRED (St. Louis Fed) | Public Domain | https://fred.stlouisfed.org |
| EEOC | Public Domain | https://www.eeoc.gov/data/enforcement-and-litigation-statistics-0 |
| Job Accommodation Network (JAN) | Public Domain | https://askjan.org |
| US Dept. of Education (IDEA/NCES) | Public Domain | https://sites.ed.gov/idea/data/ |
| Civil Rights Data Collection (CRDC) | Public Domain | https://ocrdata.ed.gov |
| WHO Global Health Observatory | CC BY-NC-SA 3.0 IGO | https://www.who.int/data/gho |
| OECD SOCX Database | OECD Terms | https://stats.oecd.org |
| World Bank Open Data | CC BY 4.0 | https://data.worldbank.org |
| United Nations Treaty Collection | Public Domain | https://treaties.un.org |
| Eurostat EU-SILC | Eurostat copyright policy | https://ec.europa.eu/eurostat |
| CMS Medicaid/Medicare | Public Domain | https://data.cms.gov |
| SAMHSA NSDUH | Public Domain | https://www.samhsa.gov/data |
| SSA DI/SSI Reports | Public Domain | https://www.ssa.gov/policy |
| VA Benefits Administration | Public Domain | https://www.va.gov/disability |
| HUD Fair Housing | Public Domain | https://www.hud.gov/program_offices/fair_housing_equal_opp |
| National Transit Database (NTD) | Public Domain | https://www.transit.dot.gov/ntd |
| WIPO PATENTSCOPE | Public Domain | https://patentscope.wipo.int |
| HTTP Archive / Web Almanac | CC BY 4.0 | https://httparchive.org |
| WebAIM Million | Fair use (structured summary) | https://webaim.org/projects/million/ |
| WebAIM Screen Reader Survey | Fair use (structured summary) | https://webaim.org/projects/screenreadersurvey10/ |
| GSA Section 508 | Public Domain | https://www.section508.gov |
| UsableNet / Accessibility.works | Fair use (summary stats) | https://info.usablenet.com/ada-website-compliance-lawsuit-tracker |
| GlobalSymbols | Various CC licenses | https://globalsymbols.com |
| ARASAAC | CC BY-NC-SA 4.0 | https://arasaac.org |
| VizWiz | CC BY 4.0 | https://vizwiz.org |

## Record Format Examples

Census County Disability:
```
fips,county_name,state_fips,county_fips,total_population,disability_total,disability_rate,...
01001,"Autauga County, Alabama",01,001,57443,4759,8.29,...
```

WHO HALE (Long Format):
```
country_code,region,year,hale_years
AFG,Eastern Mediterranean,2000,41.0
USA,Americas,2021,65.2
```

OECD Employment Gap:
```json
{
  "country": "United States",
  "disabled_pct": 37.4,
  "non_disabled_pct": 77.2,
  "gap_pp": 39.8
}
```

SSA SSDI Beneficiaries:
```json
{
  "year": 2023,
  "disabled_workers": 7291000,
  "average_monthly_benefit": 1537
}
```

## Author

Luke Steuber

[dr.eamer.dev](https://dr.eamer.dev) | [dr.eamer.dev/datavis](https://dr.eamer.dev/datavis) | [dr.eamer.dev/code](https://dr.eamer.dev/code)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Luke%20Steuber-blue?logo=linkedin)](https://www.linkedin.com/in/lukesteuber/)
[![Bluesky](https://img.shields.io/badge/Bluesky-@lukesteuber.com-1DA1F2?logo=bluesky)](https://bsky.app/profile/lukesteuber.com)
[![CodePen](https://img.shields.io/badge/CodePen-lukeslp-black?logo=codepen)](https://codepen.io/lukeslp)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-lukeslp-yellow?logo=huggingface)](https://huggingface.co/lukeslp)
[![Kaggle](https://img.shields.io/badge/Kaggle-lucassteuber-20BEFF?logo=kaggle)](https://www.kaggle.com/lucassteuber)

Part of the [Data Trove](https://dr.eamer.dev/datavis/data_trove/) collection.

## Distribution

- **HuggingFace**: [lukeslp/accessibility-atlas](https://huggingface.co/datasets/lukeslp/accessibility-atlas)
- **Kaggle**: [lucassteuber/accessibility-atlas](https://www.kaggle.com/datasets/lucassteuber/accessibility-atlas)

## License

MIT License -- see [LICENSE](LICENSE) for details.

Individual datasets carry their own licenses (see Sources table). Most US government data is public domain. WHO data is CC BY-NC-SA 3.0 IGO. WebAIM data is structured from published reports under fair use. VizWiz is CC BY 4.0.

### Related Resources

- [Awesome Accessibility](https://github.com/lukeslp/awesome-accessibility) - A curated list of accessibility tools, articles, and resources for accessibility.
