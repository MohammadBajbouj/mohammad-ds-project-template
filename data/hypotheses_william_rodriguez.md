# Hypotheses — Persona: William Rodriguez (Buyer)

*2 people, wants two houses: one in the country (best timing, non-renovated) and one in the city (fast, central location). Houses should be reasonably close to each other.*

---

## Country House — William Rodriguez

**Persona context:** William isn't in a hurry, doesn't care about neighbors, needs a quiet place to unwind, and owns a dog — so space, privacy, and price matter more than polish or central location.

### H1 – Price vs. Renovation Status

*"Non-renovated houses (`yr_renovated = 0`) are, on average, cheaper than renovated houses of comparable size and location."*

Reflects William's preference for an unrenovated, functional, affordable property rather than a move-in-ready showpiece.

- **Data:** `price`, `yr_renovated`, `sqft_living`, `zipcode`
- **Test:** compare median `price` for `yr_renovated = 0` vs. `> 0`, controlling for similar `sqft_living`/`zipcode` — simple groupby + median comparison

### H2 – Lot Size vs. Distance from Downtown

*"The larger the lot size (`sqft_lot`), the greater the distance from downtown (King County's urban core) — reflecting properties further out in the countryside."*

Supports William's need for space, privacy, and a quiet retreat with room for his dog — larger, more remote lots typically deliver exactly that.

- **Data:** `sqft_lot`, `lat`, `long`
- **Test:** calculate a simple straight-line distance from a fixed downtown reference point:
  `distance = sqrt((lat - lat_downtown)² + (long - long_downtown)²)`
  then plot against `sqft_lot` and check correlation

---

## City House — William Rodriguez

**Persona context:** William also needs a second home for daily life — close to his job, quick access to transit or the highway, and near cafés/bars for after-work activities.

### H3 – Price per Sqft by Zip Code

*"Zip codes with a higher average price per `sqft_living` represent more central, in-demand locations — William should target these zip codes for his city house."*

Uses a simple, purely tabular approach: group by `zipcode`, compute average price/sqft, and rank zip codes — directly usable to shortlist areas fitting the "fast & central" requirement, without needing lat/long distance math.

- **Data:** `price`, `sqft_living`, `zipcode`
- **Test:** `groupby("zipcode")`, compute `price / sqft_living`, sort descending

### H4 – Transaction Density vs. Price Level

*"Zip codes with a higher number of sales in the dataset (as a demand/desirability proxy) tend to have different average prices than lower-transaction zip codes."*

Connects to William's lifestyle needs — busier zip codes plausibly correlate with better transit access and nightlife/social amenities, even without a direct column for these.

- **Data:** `zipcode` (sales count), `price`
- **Test:** `groupby("zipcode").size()` vs. average `price` — simple counting and aggregation
- **Limitation:** no direct transit/amenities data — the demand proxy must be stated explicitly as an assumption

---

## Notes & Assumptions

- `price` is not part of the `king_county_house_details` table shown in the schema — it is assumed to come from the second table via the JOIN.
- No price-segment figures (e.g. "$250k–$450k") are used, since this range is not derivable from the dataset or given in the assignment.
- H3 and H4 intentionally avoid lat/long-based distance calculations in favor of simple `zipcode`-level aggregations, per the "keep it to simple calculations" guidance.
- The geographic-proximity constraint ("houses should be close to each other") is not yet covered by a dedicated hypothesis — can be added separately if needed.
