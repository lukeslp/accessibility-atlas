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

## What's Inside

### US Disability Demographics (Census Bureau)

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

## Quick Start

```python
import pandas as pd
import json

# County-level disability rates
counties = pd.read_csv("census_disability_by_county_2022.csv")
print(counties.nlargest(10, "disability_rate")[["county_name", "disability_rate"]])

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

# WebAIM Million trends
with open("webaim_million_2025.json") as f:
    webaim = json.load(f)
trends = webaim["yearly_trends"]
for year, pct in zip(trends["years"], trends["pages_with_failures_pct"]):
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

## Sources

| Source | License | URL |
|--------|---------|-----|
| US Census Bureau ACS | Public Domain | https://data.census.gov |
| WHO Global Health Observatory | CC BY-NC-SA 3.0 IGO | https://www.who.int/data/gho |
| Bureau of Labor Statistics | Public Domain | https://www.bls.gov/cps/cpsdisability.htm |
| US Dept. of Education (IDEA) | Public Domain | https://sites.ed.gov/idea/data/ |
| Eurostat EU-SILC | Eurostat copyright policy | https://ec.europa.eu/eurostat |
| WebAIM Million | Fair use (structured summary) | https://webaim.org/projects/million/ |
| WebAIM Screen Reader Survey | Fair use (structured summary) | https://webaim.org/projects/screenreadersurvey10/ |
| GlobalSymbols | Various CC licenses | https://globalsymbols.com |
| ARASAAC | CC BY-NC-SA 4.0 | https://arasaac.org |
| VizWiz | Research use | https://vizwiz.org |
| WLASL | Research use | https://dxli94.github.io/WLASL/ |
| UsableNet / Accessibility.works | Fair use (summary stats) | https://info.usablenet.com/ada-website-compliance-lawsuit-tracker |
| GSA Section 508 | Public Domain | https://www.section508.gov |

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

## License

MIT License -- see [LICENSE](LICENSE) for details.

Note: Individual source datasets have their own licenses (see Sources table). Census, BLS, GSA, and IDEA data are public domain. WHO data is CC BY-NC-SA 3.0 IGO. WebAIM data is structured from published reports under fair use. ARASAAC symbols are CC BY-NC-SA 4.0. VizWiz and WLASL are for research use.
