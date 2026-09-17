# House Recommendations for William Rodriguez

**Based on H1 Analysis: Price vs Renovation Status (Country House)**

## Hypothesis

**H1 - Price vs renovation status:**
Non-renovated houses (yr_renovated = 0) are on average cheaper than renovated houses of comparable size and location.

## Criteria Used

- **Location type:** Rural — zip codes 98038, 98042, 98023 (William's known Rural zip codes)
- **Renovation status:** Non-Renovated (matches William's "polish doesn't matter" preference)
- **Size range:** Medium (1,677 - 2,260 sqft living, middle tertile of Rural homes)
- Sorted by price ascending, lowest two selected as best value

## Statistical Result (Medium tier)

- Non-Renovated median: $300,000  ·  Renovated median: $308,000 (n = 539: 448 non-renovated, 91 renovated)
- Mann-Whitney U p-value: 0.377 — **not statistically significant**
- Across all three size tiers, the direction is inconsistent: Non-Renovated is pricier for Small (+$2,500), and cheaper for Medium (-$8,000) and Large (-$21,750). The overall picture is mixed rather than a clean confirmation of H1.

## House #1

| Field | Value |
|---|---|
| Zipcode | 98023 |
| Price | $182,700 |
| Living Area | 1,740 sqft |
| Bedrooms | 3 |
| Bathrooms | 2.25 |
| Year Built | 1978 |
| Lot Size | 6,650 sqft |
| Renovation Status | Non-Renovated |

**Why William will love it:**
- Rural location = quiet, no close neighbors
- Non-renovated = lower price, matches "polish doesn't matter" preference
- Medium-size living area, more bathrooms than House #2
- Lowest price in the matching candidate pool

## House #2

| Field | Value |
|---|---|
| Zipcode | 98023 |
| Price | $185,000 |
| Living Area | 1,990 sqft |
| Bedrooms | 5 |
| Bathrooms | 1.75 |
| Year Built | 1955 |
| Lot Size | 27,810 sqft |
| Renovation Status | Non-Renovated |

**Why William will love it:**
- Rural location = quiet, no close neighbors
- Non-renovated = lower price, matches "polish doesn't matter" preference
- Much larger lot (27,810 sqft) = extra space and privacy for William and his dog
- More bedrooms (5) for near-identical price to House #1

## Comparison

| Feature | House #1 | House #2 |
|---|---|---|
| Zipcode | 98023 | 98023 |
| Price | $182,700 | $185,000 |
| Living Area (sqft) | 1,740 | 1,990 |
| Bedrooms | 3 | 5 |
| Bathrooms | 2.25 | 1.75 |
| Year Built | 1978 | 1955 |
| Lot Size (sqft) | 6,650 | 27,810 |

## Note

Both properties fall in the same zipcode (98023) — worth double-checking whether this reflects a genuine concentration of matching Rural/Non-Renovated/Medium-size homes in that area, or a narrow candidate pool worth widening. This version uses the same 3-zip-code Rural definition as the original dataset's `location_type` column (98038, 98042, 98023). A RUCA-code-based alternative was also tested — see project history — and gave a materially different result (5 different zip codes, different candidates). Kept here for comparison while a final decision is made on which classification to use going forward.

---

*H1 Analysis - Source: `notebooks/04a_H1_eda.ipynb` (cells 12, 21, 25)*
