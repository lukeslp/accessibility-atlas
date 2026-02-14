# Pre-Publication TODO - Accessibility Atlas

**Target**: Kaggle + HuggingFace
**Deadline**: Before public release
**Status**: 4 tasks remaining

---

## BLOCKING ISSUES (Must Fix)

### 1. Fix dataset_index.json References

**Problem**: Index references 2 files that were removed for licensing restrictions

**Files to Edit**: `dataset_index.json`

**Changes**:

```json
// Line ~314 - sign_language category
// BEFORE:
{
  "name": "WLASL (Word-Level ASL)",
  "local_file": "wlasl_index.csv",
  "url": "https://dxli94.github.io/WLASL/",
  ...
}

// AFTER:
{
  "name": "WLASL (Word-Level ASL)",
  "url": "https://dxli94.github.io/WLASL/",
  "hf_url": "https://huggingface.co/datasets/Voxel51/WLASL",
  "access": "Public download (not included - download separately)",
  "note": "Removed from local collection due to licensing restrictions",
  ...
}
```

```json
// Line ~362 - aac category
// BEFORE:
{
  "name": "AAC Vocabulary Data",
  "local_file": "aac_vocabulary_data.json",
  "source": "Compiled from AAC research literature",
  ...
}

// AFTER:
{
  "name": "AAC Vocabulary Data",
  "url": "https://globalsymbols.com",
  "access": "Various CC licenses (not included - see GlobalSymbols)",
  "note": "Removed from local collection due to mixed licensing",
  ...
}
```

**Also update**:
- Line 6: `"total_datasets": 53` (was 55)

---

### 2. Update README.md Badges

**File**: `README.md`

**Line 8**: Change from:
```markdown
[![Datasets](https://img.shields.io/badge/datasets-55-green)](dataset_index.json)
```

To:
```markdown
[![Datasets](https://img.shields.io/badge/datasets-53-green)](dataset_index.json)
```

**Line 3**: Change from:
```markdown
55 datasets covering disability demographics...
```

To:
```markdown
53 datasets covering disability demographics...
```

---

### 3. Create CHANGELOG.md

**File**: `CHANGELOG.md` (new file)

**Content**:
```markdown
# Changelog - Accessibility Atlas

## 2026-02-14 - Pre-Publication Cleanup

### Removed
- `wlasl_index.csv` - Removed due to licensing restrictions (available separately at https://dxli94.github.io/WLASL/)
- `aac_vocabulary_data.json` - Removed due to mixed licensing (see GlobalSymbols at https://globalsymbols.com)
- `aac_100words.pdf` - Removed branded PDF (core vocabulary lists available in research literature)

### Changed
- Updated dataset count from 55 to 53 (41 local files + 12 external references)
- Cleaned up dataset_index.json to reflect removed files
- All remaining datasets verified for licensing compliance

### Rationale
To ensure the dataset collection is fully compliant with Kaggle and HuggingFace terms of service, we removed files with restrictive licenses or unclear provenance. Users can still access these datasets directly from their original sources (linked in dataset_index.json).

## 2026-02-13 - Initial Collection

### Added
- 55 datasets across 16 categories
- 10 analysis notebooks
- Comprehensive documentation and metadata
```

---

### 4. Add License Clarification

**File**: `LICENSE` (check if exists, or add to README)

Add section to README after line 306:

```markdown
## Dataset Licenses

This repository contains datasets from multiple sources with different licenses:

**Public Domain** (U.S. Government):
- All U.S. Census Bureau data
- Bureau of Labor Statistics
- EEOC, SSA, VA, CMS, SAMHSA
- Department of Education (IDEA, CRDC)
- HUD, DOT, FTC, GSA

**Creative Commons**:
- WHO data: CC BY-NC-SA 3.0 IGO
- World Bank: CC-BY 4.0
- HTTP Archive: CC BY 4.0
- VizWiz: CC BY 4.0

**Permissive Terms**:
- OECD: OECD Terms and Conditions (non-commercial use allowed)
- Eurostat: Eurostat copyright policy (research use allowed)

**Fair Use / Structured Summaries**:
- WebAIM Million: Structured summary of public report
- WebAIM Screen Reader Survey: Structured summary of public report
- UsableNet lawsuit tracker: Publicly reported statistics

See individual dataset metadata for specific license information.
```

---

## RECOMMENDED (Quality Improvements)

### 5. Refresh Stale Census Data (Optional - 4-6 hours)

**Files to Update**:
- `census_disability_by_age_sex_2022.json` → 2023
- `census_disability_by_race_2022.json` → 2023
- `census_disability_characteristics_2022.json` → 2023
- `census_disability_national_trends.json` → 2023

**Source**: https://data.census.gov/table/ACSST1Y2023.S1810

**Command** (if using census API):
```bash
python ~/shared/data_fetching/clients/census_client.py --year 2023 --table S1810
```

### 6. Update UN CRPD Data (Optional - 1 hour)

**File**: `un_crpd_ratification.json`

**Current**: 2012 data (14 years old!)
**Source**: https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=IV-15

---

## VALIDATION CHECKLIST

Before publication, verify:

- [ ] `dataset_index.json` has no `local_file` references to wlasl_index.csv or aac_vocabulary_data.json
- [ ] `dataset_index.json` line 6 shows `"total_datasets": 53`
- [ ] README badge shows "53" datasets
- [ ] CHANGELOG.md exists and documents removed files
- [ ] All JSON files validate: `for f in *.json; do python3 -c "import json; json.load(open('$f'))"; done`
- [ ] Record counts verified: `wc -l census_disability_by_county_2022.csv` shows 3223
- [ ] Removed files confirmed gone: `ls wlasl_index.csv 2>&1` shows "No such file"
- [ ] Git status clean (all changes committed)

---

## PUBLICATION STEPS

### Kaggle

1. **Create dataset metadata**:
   ```bash
   cd /home/coolhand/datasets/accessibility-atlas
   kaggle datasets init -p .
   ```

2. **Edit dataset-metadata.json**:
   ```json
   {
     "title": "Accessibility Atlas",
     "id": "lucassteuber/accessibility-atlas",
     "subtitle": "53 datasets on disability demographics, employment, web accessibility",
     "description": "[Use first 3 paragraphs of README]",
     "licenses": [{"name": "other"}],
     "keywords": ["disability", "accessibility", "census", "employment", "wcag", "ada"]
   }
   ```

3. **Create as private**:
   ```bash
   kaggle datasets create -p . --dir-mode zip
   ```

4. **Review on web UI**: Check files uploaded correctly, metadata displays properly

5. **Make public**: Click "Make Public" after review

### HuggingFace

1. **Create repo**:
   ```bash
   huggingface-cli repo create accessibility-atlas --type dataset
   ```

2. **Add dataset card** (copy README.md to repo root)

3. **Upload files**:
   ```python
   from huggingface_hub import HfApi
   api = HfApi()
   api.upload_folder(
       folder_path="/home/coolhand/datasets/accessibility-atlas",
       repo_id="lukeslp/accessibility-atlas",
       repo_type="dataset"
   )
   ```

4. **Add tags** in web UI: disability, accessibility, census, employment, web-accessibility, wcag, ada, healthcare, education, international

5. **Optional**: Create dataset loading script for `datasets` library integration

---

## ESTIMATED TIME

- **Minimum (just fixes)**: 30 minutes
  - dataset_index.json edits: 10 min
  - README badge update: 2 min
  - CHANGELOG creation: 10 min
  - Validation: 5 min
  - Kaggle upload: 3 min

- **With Census refresh**: 5-6 hours
  - Census API calls + data processing: 4 hours
  - Testing notebooks: 1 hour
  - Re-validation: 30 min

- **Full quality (Census + UN CRPD)**: 6-7 hours

**Recommendation**: Do minimum fixes now, publish, then update stale data in v1.1 release

---

## COMPLETION CHECKLIST

When complete, verify:

✅ dataset_index.json cleaned
✅ README updated
✅ CHANGELOG added
✅ All files validate
✅ Git committed
✅ Kaggle uploaded (private)
✅ Kaggle reviewed and made public
✅ HuggingFace uploaded
✅ Both platforms tested (download + load)

Then announce on Bluesky/X/LinkedIn!
