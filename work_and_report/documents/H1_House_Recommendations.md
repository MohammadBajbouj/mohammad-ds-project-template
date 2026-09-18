# House Recommendations for William Rodriguez

**Based on H1 Analysis: Price vs Renovation Status (Country House)**

## Hypothesis

**H1 - Price vs renovation status:**
Non-renovated houses (yr_renovated = 0) are on average cheaper than renovated houses of comparable size and location.

## Criteria Used

- **Location type:** Rural — zip codes 98010, 98014, 98019, 98022, 98024, 98045, 98070, identified from housing density (sales per km², using the bounding box of each zip code's lat/long) computed directly from the original dataset — no external classification (e.g. RUCA) or hardcoded list used. See Methodology below.
- **Renovation status:** Non-Renovated (matches William's "polish doesn't matter" preference)
- **Size range:** Medium (1,570 - 2,280 sqft living, middle tertile of Rural homes)
- Sorted by price ascending, lowest two selected as best value

## Statistical Result (by size tier)

| Size Tier | n (non-renovated / renovated) | Non-Renovated median | Renovated median | Difference | Mann-Whitney U p-value |
|---|---|---|---|---|---|
| Small | 355 (263 / 92) | $278,000 | $275,000 | +$3,000 | 0.621 — not significant |
| Medium | 354 (277 / 77) | $375,000 | $370,000 | +$5,000 | 0.918 — not significant |
| Large | 355 (284 / 71) | $535,000 | $540,000 | -$5,000 | 0.976 — not significant |

None of the three size tiers show a statistically significant difference (all p > 0.6). The direction of the price gap is inconsistent (non-renovated is pricier for Small and Medium, cheaper for Large) and the magnitudes are small relative to typical price levels — **the data does not support H1** for Rural properties in this dataset.

## House #1

| Field | Value |
|---|---|
| Zipcode | 98022 |
| Price | $195,000 |
| Living Area | 1,580 sqft |
| Bedrooms | 3 |
| Bathrooms | 1.75 |
| Year Built | 1979 |
| Lot Size | 7,875 sqft |
| Renovation Status | Non-Renovated |

**Why William will love it:**
- Rural location = quiet, no close neighbors
- Non-renovated = lower price, matches "polish doesn't matter" preference
- Medium-size living area, tied for lowest price in the matching candidate pool

## House #2

| Field | Value |
|---|---|
| Zipcode | 98022 |
| Price | $195,000 |
| Living Area | 1,570 sqft |
| Bedrooms | 3 |
| Bathrooms | 1.75 |
| Year Built | 1991 |
| Lot Size | 8,459 sqft |
| Renovation Status | Non-Renovated |

**Why William will love it:**
- Rural location = quiet, no close neighbors
- Non-renovated = lower price, matches "polish doesn't matter" preference
- Newer build (1991 vs 1979) and slightly larger lot, at the same price as House #1

## Comparison

| Feature | House #1 | House #2 |
|---|---|---|
| Zipcode | 98022 | 98022 |
| Price | $195,000 | $195,000 |
| Living Area (sqft) | 1,580 | 1,570 |
| Bedrooms | 3 | 3 |
| Bathrooms | 1.75 | 1.75 |
| Year Built | 1979 | 1991 |
| Lot Size (sqft) | 7,875 | 8,459 |

## Note

Both properties fall in the same zip code (98022) — it's the only Rural zip code (under this density-based definition) with matching Non-Renovated/Medium-size candidates at this price point. This is a narrow candidate pool; widening the criteria (e.g. adjacent size tiers) would surface more options if needed.

## Methodology: Identifying Rural vs Urban from the Original Dataset

Earlier attempts to classify Rural vs Urban from single features already in the housing data — lot size, distance from downtown, or sales count per zip — did not work: no single-feature threshold reliably separated the two groups (see project history for details).

Instead, we used **housing density**: for each zip code, we approximate its land area from the bounding box of its houses' lat/long coordinates (using the original dataset's own `zipcode`, `lat`, and `long` columns — no external data), then compute sales per km². The idea: sparser areas (fewer sales per km²) are more likely Rural.

The Rural/Urban split point itself is also found directly from the data, not chosen by hand: we sort all 70 zip codes by density and look for the largest natural gap in the (log-scale) distribution among the sparsest third of zip codes. This gap falls at 1.04 houses/km², separating 7 zip codes (98010, 98014, 98019, 98022, 98024, 98045, 98070) as Rural from the remaining 63.

**Validation (for reporting only — not used to build the classification):** compared against the official RUCA rural/urban classification, this density-based method correctly identifies 4 of the 5 RUCA-Rural zip codes (80% recall) and reaches 94.3% overall accuracy — beating the naive "always guess Urban" baseline of 92.9%. This is a real, if imperfect, improvement over single-feature approaches, and unlike the 3-zip-code hardcoded list used in earlier drafts of this analysis, it is derived entirely from patterns in the original dataset rather than picked by hand.

---

*H1 Analysis - Source: `notebooks/04a_H1_eda.ipynb` (density-based Rural/Urban classification, renovation-effect boxplots, Mann-Whitney U tests, and candidate selection)*
