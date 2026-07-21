SECTION C: MINI PROJECT DELIVERABLES & COST-SAVING RECOMMENDATIONS

1. EXECUTIVE SUMMARY & KEY METRICS

- Total Sales: $2.30M
- Total Profit: $286.40K
- Total Loss: -$156.13K
- Profit Margin %: 12.5%

2. TOP 3 COST-SAVING RECOMMENDATIONS

RECOMMENDATION 1: Restructure or Phase Out High-Deficit Sub-Categories (Tables & Bookcases)

- Finding: Sub-categories like Tables (-$17.7K) and Bookcases (-$3.5K) drive severe net operational losses despite generating high overall sales volume.
- Action: Renegotiate vendor pricing, limit promotional discount allowances on bulky furniture, or adjust baseline retail prices to protect gross margin baselines.

RECOMMENDATION 2: Mitigate Regional Supply Chain & Freight Losses (Central & East Regions)

- Finding: The Central (-$56K) and East (-$50K) regions account for the majority of overall business losses, heavily inflated by express freight usage (Same Day / First Class) on heavily discounted orders.
- Action: Enforce minimum order value thresholds for expedited shipping options and restrict premium shipping methods when order discounts exceed 10%.

RECOMMENDATION 3: Cap Regional Promotional Discounts in High-Risk States

- Finding: Specific states (such as Texas, Ohio, and Pennsylvania) display severe profit deficits due to unmanaged regional discounting policies.
- Action: Implement a strict 15% cap on regional promotional discount allowances in high-deficit states to preserve net profit margins across all product lines.


3. DAX MEASURES CREATED IN POWER BI

1. Total Sales = SUM('Sample - Superstore'[Sales])
2. Total Profit = SUM('Sample - Superstore'[Profit])
3. Total Loss = CALCULATE(SUM('Sample - Superstore'[Profit]), 'Sample - Superstore'[Profit] < 0)
4. Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
