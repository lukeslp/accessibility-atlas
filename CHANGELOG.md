# Changelog - Accessibility Atlas

## 2026-02-19 - Pre-Publication Cleanup

### Removed
- `wlasl_index.csv` - Removed due to licensing restrictions (available separately at https://dxli94.github.io/WLASL/).
- `aac_vocabulary_data.json` - Removed due to mixed licensing (see GlobalSymbols at https://globalsymbols.com).

### Changed
- Updated dataset count from 55 to 53.
- Cleaned up `dataset_index.json` to reflect removed files.
- All remaining datasets verified for licensing compliance.

### Rationale
To ensure the dataset collection is fully compliant with Kaggle and HuggingFace terms of service, I removed files with restrictive licenses or unclear provenance. Users can still access these datasets directly from their original sources (linked in `dataset_index.json`).

## 2026-02-13 - Initial Collection

### Added
- 55 datasets across 16 categories.
- 10 analysis notebooks.
- Full documentation and metadata.

## 2026-02-19 - Data Update

### Added
- `census_disability_states_2023.json` - ACS 2023 1-Year S1810 disability by state (52 records).
- `census_disability_by_age_2023.json` - ACS 2023 1-Year B18101 disability by age and state (52 records).
- `bls_disability_employment_2025.json` - BLS 2025 CPS disability employment data (5 series).
- `cdc_dhds_disability_prevalence.csv` + `.json` - CDC DHDS state disability prevalence from BRFSS (3,592 records). New category.
- `cms_medicaid_enrollment_2026.csv` + `.json` - CMS Medicaid enrollment, Jan 2026 release (10,302 records).
- `ntd_paratransit_latest.json` - NTD paratransit 2022-2023 from data.transportation.gov (5,000 records).
- `world_bank_ddh_disability.json` - World Bank Disability Data Hub (500 records). New dataset.

### Updated
- `world_bank_disability_indicators.json` - Refreshed with 2020-2024 data (3,526 records, up from 4,406 for 2010-2023).
- `dataset_index.json` - Version 4.0, now 62 datasets across 17 categories.
- README updated with all new files, counts, and sources.

### Not Updated (Blocked)
- FRED: Requires API key. BLS data covers the same underlying CPS series.
- SSA: Returns 403 on all automated requests. Existing data through 2024 remains current.
- EEOC: FY2025 data not yet released. FY2024 data (33,668 charges) already in repo.
- HUD: 2024 fair housing report not yet available in structured form. 2023 data current.
