# Global Sports Footwear Sales — Exploratory Data Analysis

An exploratory data analysis of global sports footwear sales (2018–2026), examining
whether brand, category, discounting, geography, sales channel, customer income level,
and time actually drive purchasing behavior.

## Datasets

- **Original dataset:** [Sports Footwear Sales & Consumer Behavior](https://www.kaggle.com/datasets/aliiihussain/sports-footwear-sales-and-consumer-behavior) by Ali Hussain
- **Cleaned & enriched dataset (this project):** [Global Sports Footwear Sales 2018–2026 (Cleaned & Enriched)](https://www.kaggle.com/datasets/rahulagrawal1025/global-sports-footwear-sales-20182026-cleaned/data) — adds `order_year`, `order_month`, and `discount_bucket` columns for analysis. All original values are unchanged.

## Tools

Python, pandas, Jupyter Notebook

## Approach

Rather than exploring the dataset randomly, this analysis was structured around six
specific business questions an actual footwear retailer would care about:

1. Which brand + category combination sells best — by volume and by revenue?
2. Does discounting actually increase purchase volume, or just reduce revenue?
3. Does the online vs. retail-store sales split vary meaningfully by country?
4. Does customer income level predict price paid, category choice, or brand choice?
5. Are lower-income customers more discount-sensitive than higher-income customers?
6. How do sales trend over time (2018–2026) — growth, seasonality, or anomalies?

## Key Findings

**1. Brand and category performance is unusually balanced.** Revenue across the top 10
brand/category combinations ranges narrowly between ~$305K–$330K, with no combination
dominating. ASICS (Lifestyle) and New Balance (Training) lead marginally in both units
and revenue, but rankings shift slightly further down the list depending on the metric used.

**2. Discounting does not increase purchase volume.** Average units sold per order stays
nearly flat across all discount levels (2.49 at no discount vs. 2.51 at 21%+ discount),
while average revenue per order drops steadily by ~29% as discount increases. Discounting
functions purely as a revenue reducer in this dataset, not a volume driver.

**3. Sales channel split shows no variation by country.** Every country sits within ~1
percentage point of a 50/50 online/retail split (49.2%–50.7%) — real-world markets
typically show more regional variation in e-commerce adoption.

**4. Income level does not predict purchasing behavior.** Average price paid varies by
only $1.31 across income levels. Category preference, brand preference, and discount
sensitivity all show similarly flat distributions regardless of income bracket.

**5. No meaningful time trend across 2018–2026.** Yearly revenue fluctuates narrowly
between $970K–$1.03M with no growth trajectory. Notably, 2020 — a year when real-world
footwear retail was significantly disrupted by COVID-19 — posts the *highest* revenue in
the dataset rather than a dip, and monthly totals show no holiday-season spike in
November/December.

## Overall Conclusion

Every dimension tested — brand, category, discount response, geography, sales channel,
income level, and time — shows unusually uniform, near-random distributions with no
patterns consistent with real-world consumer behavior. This provides strong, consistent
evidence that the dataset was synthetically generated with randomized values across all
fields, rather than reflecting organic market data.

This conclusion matters beyond just describing the data: it demonstrates that meaningful
analysis isn't only about finding patterns — recognizing when a dataset *lacks* real
patterns, and being able to show that rigorously across multiple independent tests, is
an important part of working with data honestly.

## Techniques Used

- Multi-column `groupby()` aggregation (`.sum()`, `.mean()`)
- Binning continuous data into categories with `pd.cut()`
- Cross-tabulation with `pd.crosstab()`
- Datetime extraction and time-series grouping
- Comparative analysis across multiple independent dimensions to test a single hypothesis

## Author

Rahul Agrawal — [Portfolio](https://rahulagrawal.com.np) | [GitHub](https://github.com/Rahul5021) | [LinkedIn](https://www.linkedin.com/in/agrawalrahul1025/)
