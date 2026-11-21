Healthy Foods — Analysis and Project Pitch
Team: Will, Mauro, Ehsanul, Kyle
Dataset: Open Food Facts. Investigations 1 and 3 used 33,125 records labeled Snacks. Investigation 2 used sweet snacks (Snacks-sucres) with usable Eco-scores. All nutrient amounts are per 100 g.
Guided Results
Investigation 1 — Category baseline. Sugar had a mean of 18.44 g, median of 9.38 g, and variance of 378.584. Sodium had a mean of 0.446 g, median of 0.322 g, and variance of 0.519. These results show that snacks in the same aisle can differ a lot. Variance is measured in squared units.

Sugar’s 25th, 50th, and 75th percentiles were 3.57, 9.38, and 31.11 g. Our parent guide would use 3.57 g of sugar or less per 100 g as its cutoff. Ties at 3.57 g meant 36.3% of snacks with sugar data met the cutoff. The 75th percentile was 21.73 g above the median, showing a large difference in sugar content.

Investigation 2 — Health halo. Our null hypothesis was equal mean sodium. Our alternative was less sodium in A/B sweet snacks than D/E. We used α = 0.05. The A/B group (91 products) averaged 204.74 mg, compared with 177.78 mg for D/E (48 products). A one-sided permutation test gave p = 0.792721. We failed to reject the null hypothesis and found insufficient evidence of less sodium in A/B sweet snacks.

Investigation 3 — Nutritional trade-offs. Fat and sugar had a covariance of −137.355 and correlation of r = −0.413. Snacks with less fat tended to have more sugar. This pattern was stronger for Meijer (r = −0.526), followed by Roundy’s (r = −0.333) and Utz (r = −0.159). Shoppers buying lower-fat snacks should check sugar too. We can’t tell from this whether companies added sugar when they reduced fat.
Project Pitch and Analytical Strategy
1. Do health-sounding names match the nutrient amounts? Product names can affect what shoppers buy. We’ll look for phrases like “low fat” and “no added sugar” in product_name and study each phrase separately. We’ll compare mean and median fat_100g or sugars_100g with snacks without those words in their names. A one-sided permutation test will check whether the “low fat” group has less fat. The sugar data only give total sugar, so we can’t tell how much was added.

2. Do lower-sugar snacks contain more sodium? Parents may want to watch both sugar and sodium. We’ll compare mean sodium_100g in snacks with sugars_100g at or below 3.57 and at or above 31.11. We’ll use a one-sided permutation test to check whether the lower-sugar group has more sodium. We’ll also calculate the sugar–sodium correlation using snacks with both values.

3. Do better Nutri-Scores go with fewer additives? Shoppers might expect a snack with a better nutrition rating to have fewer additives. We’ll calculate the correlation between nutriscore_score and additives_n. We’ll also split scores into three groups at the 33rd and 67th percentiles, keeping equal scores together, and compare average additive counts. Lower scores mean better nutrition ratings. Counting additives alone won’t tell us how healthy a product is.

Before submitting, we’ll restart the kernel and run every cell. We’ll list packages and the CSV location, keep the permutation seed, and keep the CSV in .gitignore. Missing nutrient values stay missing.