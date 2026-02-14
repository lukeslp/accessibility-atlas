# Data Quality Summary - Accessibility Atlas

**Audit Date**: 2026-02-14
**Status**: ✅ READY FOR PUBLICATION (with cleanup)
**Overall Grade**: A-

---

## Quick Stats

| Metric | Value |
|--------|-------|
| Total Files | 41 data files |
| Total Size | 53 MB |
| Largest File | 24.98 MB (who_disability_prevalence.json) |
| Date Range | 1970-2026 |
| Geographic Coverage | County, State, National, International (194 countries) |
| Record Counts Verified | ✅ All match README claims |
| File Integrity | ✅ 100% valid (no corruption) |
| Source Attribution | ✅ 100% (all files documented) |

---

## Pre-Publication Checklist

**REQUIRED (Blocking)**:
- [ ] Fix `dataset_index.json` - remove `wlasl_index.csv` and `aac_vocabulary_data.json` local_file references
- [ ] Update README badge: "55 datasets" → "53 datasets"
- [ ] Update `dataset_index.json` line 6: `"total_datasets": 53`
- [ ] Add `CHANGELOG.md` documenting removed restricted-license files

**RECOMMENDED (Quality)**:
- [ ] Refresh 5 Census 2022 files with ACS 2023 1-Year data
- [ ] Update `un_crpd_ratification.json` (currently 2012, very stale)
- [ ] Add `NCES_SCHEMA.md` for XLSX table column definitions

---

## Issues Found

### Critical (Must Fix)

1. **Index References Deleted Files**: `dataset_index.json` claims 43 local files, but only 41 exist
   - Missing: `wlasl_index.csv`, `aac_vocabulary_data.json`
   - These were removed for licensing restrictions but still referenced

### Warnings (Should Fix)

2. **Stale Data** - 5 files contain data from 2022 or earlier:
   - `census_disability_by_age_sex_2022.json`
   - `census_disability_by_race_2022.json`
   - `census_disability_characteristics_2022.json`
   - `census_disability_national_trends.json`
   - `un_crpd_ratification.json` (2012) ⚠️ 14 years old!

3. **Aging Data** - 2 files from 2023:
   - `census_disability_trends_2010_2023.json`
   - `census_disability_trends_clean.json`

---

## Strengths

✅ **Excellent Data Quality**
- Natural variation in numeric fields (no synthetic patterns)
- Realistic distributions (county disability rates CV=54.3%)
- 305 unique values across 3,222 counties

✅ **Strong Documentation**
- All JSON files have source metadata
- Clear provenance for all datasets
- License compliance verified

✅ **File Integrity**
- All large files (up to 25MB) parse correctly
- No corruption detected in 46 files
- CSV, JSON, XLSX all valid

✅ **Comprehensive Coverage**
- 16 categories (demographics, employment, web, international, etc.)
- 41 local datasets + 12 external references
- Time series data spanning 54 years (1970-2024)

---

## Enrichment Opportunities

### High Priority (Before Publication)
1. Refresh Census 2022 data → ACS 2023 (available now)
2. Update UN CRPD ratification (2012 → current)
3. Add CHANGELOG for transparency

### Medium Priority (Post-Publication)
4. Add ACS 5-Year 2023 county data (released Dec 2024)
5. Integrate CDC BRFSS disability module
6. Add Medicare disability enrollment (CMS)

### Low Priority (Future)
7. Historical EEOC backfill (1980s)
8. DOT vehicle complaints
9. FCC accessibility data

---

## Publication Targets

### Kaggle
- **Slug**: `lucassteuber/accessibility-atlas`
- **Title**: Accessibility Atlas
- **Subtitle**: 53 datasets on disability demographics, employment, web accessibility
- **Status**: Ready after index cleanup
- **Strategy**: Create as PRIVATE, review, then make public

### HuggingFace
- **Repo**: `lukeslp/accessibility-atlas`
- **Tags**: disability, accessibility, census, employment, web-accessibility, wcag, ada, healthcare, education, international
- **Status**: Ready
- **Enhancement**: Add dataset loading script for Datasets library

---

## Validation Commands

```bash
# Verify file counts
find . -type f \( -name "*.csv" -o -name "*.json" -o -name "*.xlsx" \) | wc -l
# Expected: 46 (41 data + 5 metadata)

# Confirm removed files are gone
ls wlasl_index.csv aac_vocabulary_data.json 2>&1
# Expected: "No such file or directory"

# Check JSON integrity
for f in *.json; do python3 -c "import json; json.load(open('$f'))" && echo "✅ $f" || echo "❌ $f"; done

# Verify record counts
wc -l census_disability_by_county_2022.csv  # 3223 (3222 + header)
wc -l vizwiz_val_annotations.csv            # 4320 (4319 + header)
```

---

## Next Steps

1. **Immediate** (15 min): Fix dataset_index.json references
2. **Quick** (30 min): Update README badges and add CHANGELOG
3. **Optional** (4-6 hrs): Refresh Census 2022 → 2023 data
4. **Publish** (1 hr): Upload to Kaggle (private) and HuggingFace
5. **Review** (1 day): Test downloads, verify metadata
6. **Release** (5 min): Make Kaggle dataset public

**Total estimated effort**: 2-3 hours (cleanup only) or 6-9 hours (with Census refresh)

---

**Full Reports**:
- Data Quality: `/home/coolhand/geepers/reports/by-date/2026-02-14/data-accessibility-atlas.md`
- Recommendations: `/home/coolhand/geepers/recommendations/by-project/accessibility-atlas.md`
- Citations Audit: `/home/coolhand/geepers/reports/by-date/2026-02-14/citations-accessibility-atlas.md`
