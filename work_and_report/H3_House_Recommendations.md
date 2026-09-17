# House Recommendations for William Rodriguez

**Based on H3 Analysis: Floors vs Lot Size (City House)**

## Hypothesis

**H3 - Floors vs lot size:**
Houses in more central, city-like areas tend to have more floors but smaller lot sizes. This compact, vertical style is what William's city house should look like.

Population: Urban houses only (RUCA-classified), IQR-cleaned on sqft_lot, deduplicated by house id. 18,404 houses analyzed.

## Statistical Result

- Spearman correlation (floors vs sqft_lot): **r = -0.316**
- p-value: < 0.0001 (highly significant, p << 0.05)

**Interpretation:** a negative, statistically significant correlation - houses with more floors do tend to sit on smaller lots for Urban houses. H3 is **supported** by the data.

## Criteria Used

- **Location type:** Urban (William wants a city house)
- **Floors:** >= 2 (a genuinely multi-story, vertical layout)
- **Lot size:** at or below the Urban median (7,200 sqft) - compact rather than average-or-larger
- Sorted by price descending, top 2 selected

> Note: William wants to buy fast, and ranking by price descending assumes (per his stated business rule) that more expensive houses sell faster. This assumption is not verified against the data - there is no days-on-market or listing-date column available to check it.

4,706 houses matched the floors/lot-size criteria out of 18,404 Urban houses.

## House #1

| Field | Value |
|---|---|
| House ID | 1176001310 |
| Zipcode | 98107 |
| Price | $2,950,000 |
| Living Area | 4,340 sqft |
| Floors | 3.0 |
| Lot Size | 5,722 sqft |
| Bedrooms | 5 |
| Bathrooms | 4.5 |

**Why William will love it:**
- Urban location = fast, central city living
- 3 floors = genuinely vertical, compact footprint
- Compact lot (5,722 sqft) well below the Urban median
- Tied for the highest price among matches - assumed to sell fastest

## House #2

| Field | Value |
|---|---|
| House ID | 1370800515 |
| Zipcode | 98199 |
| Price | $2,950,000 |
| Living Area | 4,470 sqft |
| Floors | 2.0 |
| Lot Size | 5,884 sqft |
| Bedrooms | 4 |
| Bathrooms | 4.25 |

**Why William will love it:**
- Urban location = fast, central city living
- Compact lot (5,884 sqft) well below the Urban median
- Slightly larger living area than House #1, at the same price
- Tied for the highest price among matches - assumed to sell fastest

## Comparison

| Feature | House #1 (98107) | House #2 (98199) |
|---|---|---|
| Price | $2,950,000 | $2,950,000 |
| Floors | 3.0 | 2.0 |
| Lot Size (sqft) | 5,722 | 5,884 |
| Living Area (sqft) | 4,340 | 4,470 |
| Bedrooms | 5 | 4 |
| Bathrooms | 4.5 | 4.25 |

## H3 Conclusion

H3 is **supported** for Urban houses:

> "Houses with more floors tend to have smaller lots"

- Spearman correlation: r = -0.316 (p < 0.0001, highly significant)
- Both suggested properties are compact-lot, multi-floor city homes at the top of William's price-ranked candidate pool.

---

*H3 Analysis - Source: `notebooks/04a_H3_eda.ipynb` (cells 20, 26)*
