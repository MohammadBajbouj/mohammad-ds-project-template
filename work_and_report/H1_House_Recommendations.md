# House Recommendations for William Rodriguez

**Based on H1 Analysis: Price vs Renovation Status (Country House)**

## Hypothesis

**H1 - Price vs renovation status:**
Non-renovated houses (yr_renovated = 0) are on average cheaper than renovated houses of comparable size and location.

## Criteria Used

- **Location type:** Rural, classified via USDA/WWAMI RUCA codes (same authoritative source used for H3), not a hardcoded zip list — 849 houses across 49 zip codes qualify as Rural out of 21,597 total
- **Renovation status:** Non-Renovated (matches William's "polish doesn't matter" preference)
- **Size range:** Medium (1,740 - 2,550 sqft living, middle tertile of Rural homes)
- Sorted by price ascending, lowest two selected as best value

## Statistical Result (Medium tier)

- Non-Renovated median: $449,950  ·  Renovated median: $451,500 (n = 279: 227 non-renovated, 52 renovated)
- Mann-Whitney U p-value: 0.752 — **not statistically significant**
- Across all three size tiers, the direction is inconsistent: Non-Renovated is pricier for Small (+$5,845) and Large (+$12,500), and only marginally cheaper for Medium (-$1,550). **H1 is not supported** by the data once Rural is defined properly via RUCA codes.

## House #1

| Field | Value |
|---|---|
| Zipcode | 98014 |
| Price | $265,000 |
| Living Area | 1,850 sqft |
| Bedrooms | 3 |
| Bathrooms | 2.0 |
| Year Built | 1992 |
| Lot Size | 16,535 sqft |
| Renovation Status | Non-Renovated |

**Why William will love it:**
- Genuinely rural (RUCA-classified) = quiet, no close neighbors
- Non-renovated = lower price, matches "polish doesn't matter" preference
- Generous lot size for space and privacy
- Lowest price in the matching candidate pool

## House #2

| Field | Value |
|---|---|
| Zipcode | 98045 |
| Price | $271,000 |
| Living Area | 1,800 sqft |
| Bedrooms | 4 |
| Bathrooms | 1.5 |
| Year Built | 1977 |
| Lot Size | 9,576 sqft |
| Renovation Status | Non-Renovated |

**Why William will love it:**
- Genuinely rural (RUCA-classified) = quiet, no close neighbors
- Non-renovated = lower price, matches "polish doesn't matter" preference
- More bedrooms (4) for a similar price to House #1
- Second-lowest price in the matching candidate pool

## Comparison

| Feature | House #1 | House #2 |
|---|---|---|
| Zipcode | 98014 | 98045 |
| Price | $265,000 | $271,000 |
| Living Area (sqft) | 1,850 | 1,800 |
| Bedrooms | 3 | 4 |
| Bathrooms | 2.0 | 1.5 |
| Year Built | 1992 | 1977 |
| Lot Size (sqft) | 16,535 | 9,576 |

## Note

Earlier versions of this analysis used a hardcoded list of 3 zip codes to define "Rural," which produced a much smaller, less representative sample. This version uses the same RUCA-code classification as H3 for consistency and rigor. The corrected result is more honest: William's "non-renovated = cheaper" assumption doesn't hold up once measured properly, so price alone shouldn't be the deciding factor between these two homes — both are reasonable, similarly-priced options rather than one being a clear "better value."

---

*H1 Analysis - Source: `notebooks/04a_H1_eda.ipynb` (cells 12, 23, 27)*
