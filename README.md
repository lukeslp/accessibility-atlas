<<<<<<< HEAD
---
license: mit
task_categories:
  - tabular-classification
  - visual-question-answering
language:
  - en
tags:
  - accessibility
  - disability
  - wcag
  - screen-readers
  - assistive-technology
  - census
  - who
  - webaim
  - aac
  - sign-language
  - special-education
size_categories:
  - 10K<n<100K
---

# Accessibility Atlas

Disability demographics, web accessibility compliance, assistive technology usage, employment data, education statistics, and AAC resources -- packaged for research and visualization.

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Data Trove](https://img.shields.io/badge/data--trove-dr.eamer.dev-orange)](https://dr.eamer.dev/datavis/data_trove/)
=======
# Accessibility Atlas

55 datasets covering disability demographics, employment gaps, web accessibility compliance, assistive technology patents, special education, healthcare, housing discrimination, transportation, government benefits, and more -- across 16 categories.

Built for researchers, journalists, policy analysts, and anyone building tools for disabled communities.

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Datasets](https://img.shields.io/badge/datasets-55-green)](dataset_index.json)
[![Notebooks](https://img.shields.io/badge/notebooks-10-purple)](notebooks/)
[![Live Site](https://img.shields.io/badge/live-dr.eamer.dev-orange)](https://dr.eamer.dev/datavis/data_trove/)
>>>>>>> master

## What's Inside

### US Disability Demographics (Census Bureau)

<<<<<<< HEAD
| File | Records | Source | Description |
|------|---------|--------|-------------|
| `census_disability_by_county_2022.csv` | 3,222 | Census ACS 5-Year 2022 | County-level disability by 6 types (hearing, vision, cognitive, ambulatory, self-care, independent living) |
| `census_disability_states_2021.csv` | 52 | Census ACS 5-Year 2021 | State-level disability rates and types |
| `census_disability_characteristics_2022.json` | national | Census ACS 1-Year 2022, S1810 | Full national breakdown by sex, race, age, and all 6 disability types with age sub-groups |
| `census_disability_by_race_2022.json` | 9 groups | Census ACS 1-Year 2022, B18101 | Disability rates for 9 race/ethnicity categories with age breakdowns |
| `census_disability_by_age_sex_2022.json` | national | Census ACS 1-Year 2022, B18101 | National disability by 6 age groups and sex |
| `census_disability_national_trends.json` | 5 years | Census ACS 1-Year 2017-2022 | US disability prevalence trend (12.68% to 13.45%) |

### Global Disability & Health

| File | Records | Source | Description |
|------|---------|--------|-------------|
| `who_healthy_life_expectancy.csv` | 185 | WHO GHO API | Healthy life expectancy (HALE) by country, 2000-2021 wide format |
| `who_hale_long.csv` | 4,070 | WHO GHO API | Same data in long format (185 countries x 22 years) |
| `eurostat_disability_eu.json` | 36 countries | Eurostat EU-SILC | EU disability prevalence (GALI indicator) and employment gap by country |

### Disability Employment

| File | Records | Source | Description |
|------|---------|--------|-------------|
| `bls_disability_employment_2024.json` | national | Bureau of Labor Statistics | Employment, labor force participation, unemployment rates by disability status, age, race, sex, education, occupation |

### Special Education

| File | Records | Source | Description |
|------|---------|--------|-------------|
| `idea_special_education_2023.json` | 51 states | US Dept. of Education, IDEA | 7.5M students served under IDEA Part B -- 13 disability categories, state-level data, educational environments |

### Web Accessibility

| File | Records | Source | Description |
|------|---------|--------|-------------|
| `webaim_million_2025.json` | 1M pages | WebAIM Million 2025 | WCAG failure rates across top 1M websites -- error types, CMS/framework performance, yearly trends |
| `webaim_screen_reader_survey_2024.json` | 1,539 | WebAIM Survey #10 | Screen reader preferences, browser combos, problematic elements, mobile usage |
| `ada_digital_lawsuits.json` | 8 years | Multiple trackers | ADA digital accessibility lawsuits (2017-2024), court breakdown, industry targets |
| `section_508_compliance_2024.json` | 245 | GSA FY24 Assessment | Federal Section 508 compliance across 245 reporting entities |

### AAC & Assistive Technology

| File | Records | Source | Description |
|------|---------|--------|-------------|
| `aac_vocabulary_data.json` | 34 libraries | GlobalSymbols, ARASAAC, research | AAC core vocabulary word lists and symbol library catalog -- ARASAAC (13,709), Blissymbolics (6,183), Sclera (11,000), 34 total libraries |
| `wlasl_index.csv` | 2,000 | WLASL Dataset | Word-Level American Sign Language video index -- 2,000 signs with gloss labels |
| `vizwiz_val_annotations.csv` | 4,319 | VizWiz VQA | Visual questions from blind users with crowdsourced answers and answerability labels |

### Reference

| File | Description |
|------|-------------|
| `accessibility_dataset_catalog.json` | Curated catalog of 15 accessibility datasets across 6 categories |
=======
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

| File | What It Covers | Key Stat |
|------|---------------|----------|
| `bls_disability_employment_2024.json` | BLS employment/unemployment by disability status | 24.5% labor force participation (disabled) vs ~67% (non-disabled) |
| `fred_disability_employment.json` | FRED 16-year employment time series (2009-2024) | Gap narrowing from 40pp to 37pp |
| `eeoc_ada_charges.json` | 33 years of ADA discrimination charges (1992-2024) | 679,637 total charges; peaked at 28,073 in FY 2016 |
| `jan_workplace_accommodations.json` | JAN accommodation cost data | 58.7% of accommodations cost $0; median $300 |

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

| File | What It Covers | Key Stat |
|------|---------------|----------|
| `webaim_million_2025.json` | WCAG failures across top 1M pages | 94.8% fail; avg 51 errors/page |
| `webaim_screen_reader_survey_2024.json` | 1,539 respondents on screen reader usage | JAWS 40.5%, NVDA 37.7%, VoiceOver 70.6% (mobile) |
| `ada_digital_lawsuits.json` | ADA digital lawsuits 2017-2024 | 814 (2017) to ~4,000 (2024); 77% target e-commerce |
| `section_508_compliance_2024.json` | Federal agency Section 508 compliance (245 entities) | Only 23% of public websites conform |
| `web_accessibility_metrics.json` | HTTP Archive web a11y trends 2019-2024 | Alt text: 51.8% to 58.5%; ARIA usage doubled |

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

| File | What It Covers | Key Stat |
|------|---------------|----------|
| `ssa_ssdi_ssi_annual.json` | SSDI/SSI beneficiaries 1970-2024 | 7.3M SSDI + 4.9M SSI recipients; $173B+ annual |
| `ssa_state_agency_workload.json` | State-level determination data, approval rates | ~33% initial approval; 13-month avg processing |
| `va_disability_compensation.json` | VA claims 2019-2026, compensation rates by state | 5.7M+ veterans receive disability comp |

### Healthcare & Mental Health

2 datasets on Medicaid disability enrollment and mental health prevalence.

| File | What It Covers | Key Stat |
|------|---------------|----------|
| `cms_medicaid_disability_enrollment.json` | CMS aged/blind/disabled enrollment 2013-2024 (4.7MB) | 10.2M enrollees; 15% of Medicaid, ~45% of spending |
| `samhsa_mental_health.json` | NSDUH mental health prevalence 2008-2023 | 23.1% of adults had mental illness (2023); 37% with SMI got no treatment |

### Housing Discrimination

| File | What It Covers | Key Stat |
|------|---------------|----------|
| `hud_fair_housing_disability.json` | HUD fair housing complaints 2009-2023, by state | Disability is #1 basis (~55% of all complaints) |

### Transportation

| File | What It Covers | Key Stat |
|------|---------------|----------|
| `ntd_paratransit_data.json` | ADA paratransit ridership & costs 2014-2022 | 146M trips at peak (2019); $40-50/trip vs ~$4 fixed-route |

### Education (Civil Rights)

| File | What It Covers | Key Stat |
|------|---------------|----------|
| `crdc_disability_data.json` | Section 504, restraint/seclusion, discipline | 2-3x higher suspension; 81% of restraint incidents |

### Assistive Technology Patents

| File | What It Covers | Key Stat |
|------|---------------|----------|
| `patentsview_assistive_tech.json` | WIPO assistive tech patents 1985-2026 (696KB) | 10 patents (2010-14) to 519 (2020-24); prostheses, hearing, computing |

### Sign Language

| File | Records | Source |
|------|---------|--------|
| `wlasl_index.csv` | 21,083 videos, 2,000 signs | WLASL Dataset |

### Visual Accessibility

| File | Records | Source |
|------|---------|--------|
| `vizwiz_val_annotations.csv` | 4,319 VQA pairs from blind users | VizWiz VQA |

### AAC (Augmentative & Alternative Communication)

| File | Records | Source |
|------|---------|--------|
| `aac_vocabulary_data.json` | 34 symbol libraries, core word lists | GlobalSymbols, ARASAAC, research lit |

### Reference Files

| File | Description |
|------|-------------|
| `dataset_index.json` | Full catalog of all 55 datasets with sources, coverage, and key findings |
| `aac_100words.pdf` | AAC core vocabulary reference |

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
| `sign_language_vision_aac.ipynb` | WLASL, VizWiz, AAC vocab | Sign language coverage, VQA analysis |

Plus `accessibility_atlas_demo.ipynb` in the root as a quick-start sampler.
>>>>>>> master

## Quick Start

```python
import pandas as pd
import json

# County-level disability rates
counties = pd.read_csv("census_disability_by_county_2022.csv")
print(counties.nlargest(10, "disability_rate")[["county_name", "disability_rate"]])

<<<<<<< HEAD
# National disability characteristics
with open("census_disability_characteristics_2022.json") as f:
    chars = json.load(f)
# Disability rates by race
for race, data in chars["by_race_ethnicity"].items():
    print(f"{race}: {data['rate_pct']}%")

# Disability employment gap
with open("bls_disability_employment_2024.json") as f:
    bls = json.load(f)
stats = bls["overall_statistics"]
print(f"Employment rate - Disabled: {stats['with_disability']['employment_population_ratio']}%")
print(f"Employment rate - Non-disabled: {stats['without_disability']['employment_population_ratio']}%")

# IDEA special education
with open("idea_special_education_2023.json") as f:
    idea = json.load(f)
print(f"Students served: {idea['national_summary']['total_students_served']:,}")
for cat in idea["disability_categories"][:5]:
    print(f"  {cat['category']}: {cat['count']:,} ({cat['percentage']}%)")

# EU disability comparison
with open("eurostat_disability_eu.json") as f:
    eu = json.load(f)
print(f"EU27 disability rate: {eu['eu27_summary_2023']['total_disability_rate_pct']}%")
=======
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
>>>>>>> master

# WebAIM Million trends
with open("webaim_million_2025.json") as f:
    webaim = json.load(f)
trends = webaim["yearly_trends"]
for year, pct in zip(trends["years"], trends["pages_with_failures_pct"]):
<<<<<<< HEAD
    print(f"{year}: {pct}% of pages have WCAG failures")

# AAC symbol libraries
with open("aac_vocabulary_data.json") as f:
    aac = json.load(f)
for lib in aac["symbol_libraries"]["libraries"]:
    print(f"{lib['name']}: {lib['total_symbols']} symbols ({lib['license']})")

# WHO healthy life expectancy
hale = pd.read_csv("who_hale_long.csv")
print(hale.groupby("year")["hale_years"].mean().round(1))
```

## Data Highlights

**US Disability Demographics (Census 2022)**
- 44.1 million Americans (13.4%) have a disability
- Ambulatory (6.7%) and cognitive (5.7%) are the most common types
- Rates vary by race: AIAN highest (15.7%), Asian lowest (8.3%)
- Disability rises sharply with age: 0.8% under 5, 45.9% age 75+
- US disability rate increased from 12.68% (2017) to 13.45% (2022)

**Disability Employment (BLS 2024)**
- 24.5% labor force participation for disabled workers vs ~67% without
- 7.5% unemployment rate for disabled vs 3.8% without
- Significant gaps by education, age, race, and disability type

**Special Education (IDEA 2022-23)**
- 7.5 million students served under IDEA Part B
- Specific learning disability is the largest category (32%)
- Autism now represents 13% of IDEA students (rising trend)

**EU Disability (Eurostat 2023)**
- 26.9% of EU27 adults report activity limitations
- 21.4 percentage point employment gap between disabled and non-disabled
- Rates range from ~15% (Bulgaria) to ~35% (Finland, Portugal)

**Web Accessibility (WebAIM 2025)**
- 94.8% of the top 1M websites have WCAG failures
- Average of 51 errors per page
- Low contrast text remains the #1 issue (79% of pages)

**Screen Reader Usage (WebAIM 2024)**
- JAWS (40.5%) and NVDA (37.7%) dominate desktop
- iOS VoiceOver leads mobile (70.6%)
- CAPTCHA is the #1 most problematic element

**AAC Symbol Libraries**
- 34 open symbol libraries cataloged via GlobalSymbols
- ARASAAC leads with 13,709 pictograms (CC BY-NC-SA 4.0)
- Blissymbolics: 6,183 semantic symbols (CC BY-SA 4.0)

**Global Health (WHO)**
- Healthy life expectancy data for 185 countries across 22 years
- Tracks years of healthy life lost to disability worldwide
=======
    print(f"{year}: {pct}% of top 1M pages have WCAG failures")
```

## Key Findings

**44.1 million Americans (13.4%) have a disability** (Census 2022). Rate rose from 11.9% (2010) to 13.6% (2023). Ambulatory (6.7%) and cognitive (5.7%) are the most common types. Rates vary sharply: 0.8% under age 5, 45.9% age 75+.

**The employment gap is massive.** Disabled workers have 24.5% labor force participation vs ~67% without. The OECD average gap is 34 percentage points. Switzerland has the smallest gap (22.6pp); Ireland the largest (40.3pp) among OECD countries.

**Workplace accommodations are cheap.** 58.7% cost nothing. Median cost is $300. 90% of employers report them effective. Yet the EEOC received 679,637 ADA disability discrimination charges since 1992.

**The web is still broken.** 94.8% of the top 1M websites fail WCAG. Average: 51 errors per page. Low contrast text hits 79% of pages. Alt text adoption grew from 51.8% to 58.5% (2019-2024), but it's slow going.

**Disability is the #1 basis for fair housing complaints** (~55% of all HUD complaints). Failure to provide reasonable accommodation is the top issue.

**Paratransit is expensive.** $40-50 per trip vs ~$4 for fixed-route transit. 146M trips at pre-COVID peak (2019).

**Special education is growing.** 15.2% of public school students now served under IDEA. Autism grew 8.5x since 2000. Students with disabilities face 2-3x higher suspension rates.

**Globally, 1.3 billion people (16%) live with significant disability** (WHO). 190 countries have signed the UN CRPD. Assistive tech patents exploded from 10 (2010-2014) to 519 (2020-2024).
>>>>>>> master

## Sources

| Source | License | URL |
|--------|---------|-----|
| US Census Bureau ACS | Public Domain | https://data.census.gov |
<<<<<<< HEAD
| WHO Global Health Observatory | CC BY-NC-SA 3.0 IGO | https://www.who.int/data/gho |
| Bureau of Labor Statistics | Public Domain | https://www.bls.gov/cps/cpsdisability.htm |
| US Dept. of Education (IDEA) | Public Domain | https://sites.ed.gov/idea/data/ |
| Eurostat EU-SILC | Eurostat copyright policy | https://ec.europa.eu/eurostat |
| WebAIM Million | Fair use (structured summary) | https://webaim.org/projects/million/ |
| WebAIM Screen Reader Survey | Fair use (structured summary) | https://webaim.org/projects/screenreadersurvey10/ |
=======
| Bureau of Labor Statistics | Public Domain | https://www.bls.gov/cps/cpsdisability.htm |
| FRED (St. Louis Fed) | Public Domain | https://fred.stlouisfed.org |
| EEOC | Public Domain | https://www.eeoc.gov/data/charge-statistics |
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
>>>>>>> master
| GlobalSymbols | Various CC licenses | https://globalsymbols.com |
| ARASAAC | CC BY-NC-SA 4.0 | https://arasaac.org |
| VizWiz | Research use | https://vizwiz.org |
| WLASL | Research use | https://dxli94.github.io/WLASL/ |
<<<<<<< HEAD
| UsableNet / Accessibility.works | Fair use (summary stats) | https://info.usablenet.com/ada-website-compliance-lawsuit-tracker |
| GSA Section 508 | Public Domain | https://www.section508.gov |
=======
>>>>>>> master

## Record Format Examples

**Census County Disability**
```
fips,county_name,state_fips,county_fips,total_population,disability_total,disability_rate,...
01001,"Autauga County, Alabama",01,001,57443,4759,8.29,...
```

**WHO HALE (Long Format)**
```
country_code,region,year,hale_years
AFG,Eastern Mediterranean,2000,41.0
USA,Americas,2021,65.2
```

<<<<<<< HEAD
**BLS Disability Employment**
```json
{
  "overall_statistics": {
    "with_disability": {
      "labor_force_participation_rate": 24.5,
      "unemployment_rate": 7.5,
      "employment_population_ratio": 22.7
    }
  }
}
```

## Project Home

Part of the [Data Trove](https://dr.eamer.dev/datavis/data_trove/) collection at dr.eamer.dev.

## Author

**Luke Steuber**
- Web: [lukesteuber.com](https://lukesteuber.com)
- Bluesky: [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com)
=======
**OECD Employment Gap**
```json
{
  "country": "United States",
  "disabled_pct": 37.4,
  "non_disabled_pct": 77.2,
  "gap_pp": 39.8
}
```

**SSA SSDI Beneficiaries**
```json
{
  "year": 2023,
  "disabled_workers": 7291000,
  "average_monthly_benefit": 1537
}
```

## About

Part of the [Data Trove](https://dr.eamer.dev/datavis/data_trove/) collection. I built this because disability data is scattered across dozens of federal agencies, international organizations, and advocacy groups. Having it all in one place -- with consistent formatting and analysis notebooks -- makes it actually usable.

**Luke Steuber** • [lukesteuber.com](https://lukesteuber.com) • [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com) • [dr.eamer.dev](https://dr.eamer.dev)
>>>>>>> master

## License

MIT License -- see [LICENSE](LICENSE) for details.

<<<<<<< HEAD
Note: Individual source datasets have their own licenses (see Sources table). Census, BLS, GSA, and IDEA data are public domain. WHO data is CC BY-NC-SA 3.0 IGO. WebAIM data is structured from published reports under fair use. ARASAAC symbols are CC BY-NC-SA 4.0. VizWiz and WLASL are for research use.
=======
Individual datasets carry their own licenses (see Sources table). Most US government data is public domain. WHO data is CC BY-NC-SA 3.0 IGO. WebAIM data is structured from published reports. ARASAAC symbols are CC BY-NC-SA 4.0. VizWiz and WLASL are for research use.
>>>>>>> master
