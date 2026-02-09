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
size_categories:
  - 10K<n<100K
---

# Accessibility Atlas

Disability demographics, web accessibility compliance, assistive technology usage, and related datasets -- packaged for research and visualization.

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Data Trove](https://img.shields.io/badge/data--trove-dr.eamer.dev-orange)](https://dr.eamer.dev/datavis/data_trove/)

## What's Inside

### Disability Demographics

| File | Records | Source | Description |
|------|---------|--------|-------------|
| `census_disability_by_county_2022.csv` | 3,222 | Census ACS 5-Year 2022 | US county-level disability by type (hearing, vision, cognitive, ambulatory, self-care, independent living) |
| `census_disability_states_2021.csv` | 52 | Census ACS 5-Year 2021 | US state-level disability rates and types |
| `who_healthy_life_expectancy.csv` | 185 | WHO GHO API | Healthy life expectancy (HALE) by country, 2000-2021 wide format |
| `who_hale_long.csv` | 4,070 | WHO GHO API | Same data in long format (185 countries x 22 years) |

### Web Accessibility

| File | Records | Source | Description |
|------|---------|--------|-------------|
| `webaim_million_2025.json` | 1M pages | WebAIM Million 2025 | WCAG failure rates across top 1M websites -- error types, CMS/framework performance, yearly trends |
| `webaim_screen_reader_survey_2024.json` | 1,539 | WebAIM Survey #10 | Screen reader preferences, browser combos, problematic elements, mobile usage patterns |
| `ada_digital_lawsuits.json` | 8 years | Multiple trackers | ADA digital accessibility lawsuits by year (2017-2024), court breakdown, industry targets |
| `section_508_compliance_2024.json` | 245 | GSA FY24 Assessment | Federal Section 508 compliance rates across 245 reporting entities |

### Assistive Technology Research

| File | Records | Source | Description |
|------|---------|--------|-------------|
| `wlasl_index.csv` | 2,000 | WLASL Dataset | Word-Level American Sign Language video index -- 2,000 signs with video IDs and gloss labels |
| `vizwiz_val_annotations.csv` | 4,319 | VizWiz VQA | Visual questions from blind users with crowdsourced answers -- images + questions + answerability |

### Reference

| File | Description |
|------|-------------|
| `accessibility_dataset_catalog.json` | Curated catalog of 15 accessibility datasets across 6 categories with access info and URLs |

## Quick Start

```python
import pandas as pd
import json

# County-level disability rates
counties = pd.read_csv("census_disability_by_county_2022.csv")
# Highest disability rate counties
print(counties.nlargest(10, "disability_rate")[["county_name", "disability_rate"]])

# WebAIM Million trends
with open("webaim_million_2025.json") as f:
    webaim = json.load(f)
# Year-over-year improvement
trends = webaim["yearly_trends"]
for year, pct in zip(trends["years"], trends["pages_with_failures_pct"]):
    print(f"{year}: {pct}% of pages have WCAG failures")

# Screen reader market share
with open("webaim_screen_reader_survey_2024.json") as f:
    survey = json.load(f)
for sr in survey["primary_screen_reader"]:
    print(f"{sr['name']}: {sr['pct']}%")

# WHO healthy life expectancy over time
hale = pd.read_csv("who_hale_long.csv")
# Global average by year
print(hale.groupby("year")["hale_years"].mean().round(1))
```

## Data Highlights

**US Disability Demographics (Census 2022)**
- 3,222 counties with disability breakdowns by 6 types
- Ambulatory disability is most common, followed by cognitive
- County disability rates range from 0% to over 9%

**Web Accessibility (WebAIM 2025)**
- 94.8% of the top 1M websites have WCAG failures
- Average of 51 errors per page
- Low contrast text remains the #1 issue (79% of pages)
- .gov sites average 19.6 errors vs 49.8 for .com

**Screen Reader Usage (WebAIM 2024)**
- JAWS (40.5%) and NVDA (37.7%) dominate desktop
- iOS VoiceOver leads mobile (70.6%)
- CAPTCHA is the #1 most problematic element
- 78% say free screen readers are viable alternatives to commercial ones

**Global Health (WHO)**
- Healthy life expectancy data for 185 countries across 22 years (2000-2021)
- Tracks years of healthy life lost to disability worldwide

## Sources

| Source | License | URL |
|--------|---------|-----|
| US Census Bureau ACS | Public Domain | https://data.census.gov |
| WHO Global Health Observatory | CC BY-NC-SA 3.0 IGO | https://www.who.int/data/gho |
| WebAIM Million | Fair use (structured summary) | https://webaim.org/projects/million/ |
| WebAIM Screen Reader Survey | Fair use (structured summary) | https://webaim.org/projects/screenreadersurvey10/ |
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
AFG,Eastern Mediterranean,2001,41.0
...
USA,Americas,2021,65.2
```

## Project Home

Part of the [Data Trove](https://dr.eamer.dev/datavis/data_trove/) collection at dr.eamer.dev.

## Author

**Luke Steuber**
- Web: [lukesteuber.com](https://lukesteuber.com)
- Bluesky: [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com)

## License

MIT License -- see [LICENSE](LICENSE) for details.

Note: Individual source datasets have their own licenses (see Sources table above). Census and GSA data are public domain. WHO data is CC BY-NC-SA 3.0 IGO. WebAIM data is structured from published reports under fair use. VizWiz and WLASL are for research use.
