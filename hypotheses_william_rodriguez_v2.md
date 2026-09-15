# Hypotheses - Persona William Rodriguez (Buyer)

2 people, wants two houses: one in the country (best timing, non-renovated) and one in the city (fast, central location). Houses should be reasonably close to each other.

## Country House

William isn't in a hurry, doesn't care about neighbors, needs a quiet place to unwind, and owns a dog. Space, privacy and price matter more than polish or central location.

**H1 - Price vs renovation status**

Non-renovated houses (`yr_renovated` = 0) are on average cheaper than renovated houses of comparable size and location.

Data: `price`, `yr_renovated`, `sqft_living`, `zipcode`

Test: compare the median price of non-renovated houses against renovated ones, keeping size and zip code roughly similar so the comparison is fair

**H2 - Lot size vs distance from downtown**

The larger the lot size (`sqft_lot`), the greater the distance from downtown (King County's urban core) - reflecting properties further out in the countryside.

Data: `sqft_lot`, `lat`, `long`

Test: work out each house's distance from a fixed downtown reference point, then check whether lot size grows as that distance increases

## City House

William needs a second home for daily life - close to his job, quick access to transit or the highway, and near cafés/bars for after-work activities. "Fast" here specifically means easy to reach / good public transport access.

**H3 - Floors vs lot size (maps to "central")**

Houses in more central, city-like areas tend to have more floors but smaller lot sizes - this compact, vertical style is what William's city house should look like, in contrast to his spacious country house.

Data: `floors`, `sqft_lot`

Test: check whether houses with more floors tend to sit on smaller lots

**H4 - Lot density as a transit proxy (maps to "fast / easy to reach")**

Houses with a smaller lot size relative to living space sit in denser, more urbanized areas - which typically have better public transport coverage, fitting William's need for an easy-to-reach city house.

Data: `sqft_living`, `sqft_lot`

Test: build a density measure (living space relative to lot size) and see whether higher-density areas line up with the zip codes expected to be more central/urban
