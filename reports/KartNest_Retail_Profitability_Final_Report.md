# KartNest Retail Profitability Report
**2025 order analysis | Prepared for the VP of Category and Pricing**  
**Currency:** Indian Rupees (INR)  
**Status:** Draft for decision-maker review

---

## Executive summary: decisions requested

KartNest should make five changes based on the analysis of 6,000 orders from 2025:

1. **Set a discount cap for each product category.** Use the proposed caps of **10% for Electronics, 30% for Fashion, 10% for Grocery and 20% for Home**. Deeply discounted orders are often loss-making, while customers do not buy more units at higher discount levels. The estimated yearly profit improvement is **₹11.1 lakh to ₹20.1 lakh**, depending on how returned goods are treated and how many customers continue buying after prices change.
2. **Investigate and fix the South × Fashion return problem.** Its return rate is **25.6%**, compared with **6.8% for all other orders**. Review sizing, product quality, product listings and courier handling. The estimated yearly profit improvement is **₹0.9 lakh to ₹2.8 lakh** if the segment's return rate falls to the rate seen elsewhere.
3. **Prepare operations for the October–December surge.** Average daily orders rise from **12.9 to 27.0**, around **2.1 times** the rest-of-year level. The analysis found no clear evidence that this increase was driven by deeper discounts. Plan inventory and delivery capacity rather than relying on extra promotions.
4. **Run a controlled discount experiment before making bigger promotion decisions.** Compare 0%, 10% and 20% discounts. The current data is observational, so it cannot prove whether discounts bring in additional customers.
5. **Do not introduce region-specific pricing based on this analysis.** Regional margin differences are small and are not meaningful after accounting for category and discount.

The strongest immediate financial opportunity is discount control. The return hotspot is the next operational priority. These recommendations are based on the available order data and the assumptions listed below; they should be reviewed with Finance and Operations before implementation.

---

## 1. Business question and scope

KartNest is a fictional online retailer selling Electronics, Fashion, Grocery and Home products across North, South, East and West India. The business uses promotional discounts to drive orders.

The VP of Category and Pricing asked the analytics team to answer:

**Where does KartNest make or lose money, why is it happening, and what actions could improve profit?**

This report uses the 2025 order dataset described in the project brief. It contains approximately 6,000 order records and includes order date, region, category, unit price, quantity, discount, revenue, cost and return status. All monetary values are in INR.

The analysis focuses on five questions:
- Do larger discounts reduce profit, and do they increase basket size?
- Should discount limits differ by product category?
- Is the return problem concentrated in one category-region segment?
- Is the October–December order increase genuine demand or promotion-driven?
- Are some regions meaningfully more profitable than others?

The report uses descriptive analysis and statistical tests to separate clear patterns from differences that may be due to random variation.

## 2. Key assumptions and how to read the numbers

The findings depend on several assumptions that should be confirmed before final decisions.

| Assumption | Treatment in this report | Why it matters |
|---|---|---|
| Returned goods | Scenario A: returned goods are a total loss. Scenario B: returned goods are restocked and resold at cost. | Estimated net profit changes from **₹17.5 lakh (A)** to **₹40.2 lakh (B)**. |
| Other operating costs | Shipping, handling and overhead are not included because they are not in the data. | Actual business profit will be lower than the profit shown here. |
| Safe discount cap | Defined as the highest standard discount level (0%, 5%, 10%, 20%, 30% or 40%) that still leaves a positive margin. | The proposed operating caps are deliberately more cautious than the calculated break-even discounts. |
| Currency | INR, as stated in the project brief. | All financial values are shown in rupees. |

### Profit and returns

Profit before accounting for returns is **₹44.5 lakh**. After deducting profit lost on returned orders, profit is **₹40.2 lakh** under Scenario B. If the cost of returned goods is also written off, profit is **₹17.5 lakh** under Scenario A.

The report estimates that returns remove **61% of paper profit in Scenario A** or **10% in Scenario B**.

Under Scenario A, category profit is:
- Electronics: **−₹0.9 lakh**
- Grocery: **−₹1.6 lakh**
- Fashion: **+₹10.7 lakh**
- Home: **+₹9.3 lakh**

Finance and Operations should confirm what happens to returned goods. This single policy detail has a large effect on the profit estimate.

### Statistical terms in plain English

- **p-value:** Helps assess whether a result like the one observed could reasonably happen by chance if there were no real difference. This report generally uses 0.05 as the significance level.
- **Effect size:** Shows how large a difference is. A result can be statistically significant but too small to matter to the business.
- **95% confidence interval:** Gives a range of values that are reasonably consistent with the data and method used.
- **Holm correction:** Adjusts p-values when several tests are run, reducing the chance of declaring a false finding simply because many tests were performed.

A finding is treated as important when the statistical evidence and the size of the business impact both support it.

---

## 3. Findings and evidence

### H1. Larger discounts reduce profit but do not increase basket size

**Business question:** Are deeper discounts reducing profit, and do customers buy more units in return?

**Method:** Kruskal–Wallis tests compare several groups without requiring the data to follow a normal, bell-shaped distribution. This is suitable for the margin data in this analysis.

**What the data shows**

Average profit margin falls from **24.8% with no discount** to **−25.5% at a 40% discount**.

The share of orders that lose money also rises sharply:
- Up to 10% discount: **0%**
- 20% discount: **48%**
- 30% discount: **50%**
- 40% discount: **71%**

The reported effect size for the relationship between discount level and margin is **0.43**, described in the draft analysis as large.

The analysis also checked whether higher discounts lead to larger baskets. Average units per order stay between **2.40 and 2.56** across discount levels. The effect is negligible, and the reported Holm-adjusted p-value is **0.15**.

**Conclusion:** The data supports the view that deeper discounts hurt profit. It does not show that customers buy more units when discounts increase.

**Business meaning:** KartNest is giving away margin without seeing a meaningful increase in units per order. However, this dataset cannot tell us whether discounts attract customers who would otherwise not have ordered. A controlled experiment is needed to answer that question.

### H2. Discount limits should reflect each category's cost structure

**Business question:** Does each category have a different break-even point, and are discounts currently tailored to those differences?

**Method:** Check the cost share of list price, calculate break-even discount levels, use regression to examine factors linked to margin, and use a Chi-square test to check whether category and discount mix are associated.

**What the data shows**

Cost is a fixed share of list price in each category:

| Category | Cost as a share of list price | Calculated break-even discount |
|---|---:|---:|
| Electronics | 82% | 18% |
| Fashion | 60% | 40% |
| Grocery | 88% | 12% |
| Home | 70% | 30% |

The share of orders above break-even is **35% for Electronics**, **35% for Grocery**, **9% for Home** and **0% for Fashion**.

The regression analysis reports that category and discount explain approximately **100% of the differences in margin**. Adding region, month and quantity adds **0.000%** explanatory power.

The Chi-square test finds no meaningful difference in discount mix across categories (**p = 0.67**). In other words, the discount mix is similar even though the categories have different cost structures.

**Conclusion:** The current discount mix does not reflect the different cost structures of the categories.

**Business meaning:** A discount that is safe for Fashion may cause a loss in Electronics or Grocery. KartNest should set category-specific limits rather than use one broad discount policy.

**Proposed operating caps:** Electronics **10%**, Fashion **30%**, Grocery **10%**, Home **20%**. These are the conservative caps recommended in the draft analysis. They sit below the calculated break-even levels and are intended to protect margin.

### H3. Returns are concentrated in South × Fashion

**Business question:** Are returns a broad problem across the business, or is one segment responsible for most of the issue?

**Method:** The analysis first compares return patterns by category and region using Chi-square tests. It then compares South × Fashion with all other orders using a two-proportion z-test and a 95% confidence interval. It also repeats the analysis after removing the hotspot and checks the hotspot by month.

**What the data shows**

| Segment | Return rate |
|---|---:|
| South × Fashion | **25.6%** |
| All other orders | **6.8%** |

There were **110 returns among 429 South × Fashion orders**. The difference between the two rates is **18.8 percentage points**. The reported 95% confidence range for this difference is **14.8 to 23.2 percentage points**.

When South × Fashion is removed, category differences are no longer significant (**p = 0.51**) and the remaining regional effect is negligible.

The hotspot remains throughout the year. Its monthly return rate ranges from **15% to 32%**, and the reported test across months gives **p = 0.95**. This does not show a meaningful month-to-month change.

**Conclusion:** The return issue is concentrated in South × Fashion and is present throughout the year, rather than being limited to one unusual month.

**Business meaning:** Start the investigation with this segment. Check product sizing, quality, listing accuracy and the delivery experience in the South. These are possible causes to investigate, not causes proven by the order data.

If the segment's return rate falls to the **6.8%** rate seen elsewhere, the report estimates around **81 fewer returns** and a yearly profit improvement of **₹0.9 lakh to ₹2.8 lakh**, depending on the returned-goods scenario.

### H4. October–December has a real order surge, not a clear discount-driven surge

**Business question:** Does the Q4 increase reflect higher demand, or is it being driven by heavier promotions?

**Method:** The analysis compares daily order counts using the Mann–Whitney U test and uses bootstrap resampling to estimate a confidence range for the order-volume ratio. It also compares discount mix, return rate and profit margin between Q4 and the rest of the year.

**What the data shows**

| Measure | Rest of year | October–December |
|---|---:|---:|
| Average daily orders | **12.9** | **27.0** |
| Return rate | **7.8%** | **8.4%** |
| Profit margin | **11.6%** | **11.7%** |

Daily orders increase by approximately **2.1 times**. The reported 95% confidence range for this ratio is **2.0 to 2.2 times**.

The analysis finds no statistically significant change in discount mix (**p = 0.14**), return rate (**p = 0.38**) or profit margin (**p = 0.84**).

**Conclusion:** Q4 has a strong increase in daily orders. The data does not show that the increase was bought through deeper discounts.

**Business meaning:** Prepare inventory and delivery capacity for the higher order volume. The report does not support using extra discounts as the main response to the Q4 surge.

### H5. Regional profit differences are too small to justify regional pricing

**Business question:** Are some regions more profitable after differences in category and discount are considered?

**Method:** The analysis uses a Kruskal–Wallis test to compare margin across regions, then compares regression models with and without region after accounting for category and discount.

**What the data shows**

Average margins across regions range from **11.5% to 12.8%**. The initial regional comparison gives **p = 0.24**, with a negligible effect.

In the regression comparison, region adds **0.000%** explanatory power after category and discount are included. The raw p-value is **0.0115**, but the result is not significant after Holm correction (**adjusted p = 0.09**) and the added effect is too small to matter.

**Conclusion:** The data does not support meaningful regional differences in profitability after the other factors are considered.

**Business meaning:** Do not build region-specific pricing based on these results. Focus on category economics and discount control instead.

---

## 4. Statistical test scoreboard

The table below shows the 11 tests in the analysis and their Holm-adjusted p-values.

| Test | Finding | Holm-adjusted p-value |
|---|---|---:|
| H1a: Discount level and profit margin | **Real relationship** | **<0.0001** |
| H1b: Discount level and basket size | No meaningful evidence of a difference | 0.15 |
| H2a: Region, month and quantity add to margin explanation | No meaningful additional contribution | 0.36 |
| H2b: Discount mix differs by category | No; discount mix is not tailored | 1.00 |
| H3: South × Fashion return hotspot | **Real difference** | **<0.0001** |
| H3 check: Category after removing hotspot | No meaningful difference | 1.00 |
| H3 check: Region after removing hotspot | No meaningful effect | 0.26 |
| H4a: October–December order surge | **Real increase** | **<0.0001** |
| H4b: October–December uses deeper discounts | No meaningful evidence of a difference | 0.56 |
| H5a: Margin differs by region | No meaningful difference | 0.72 |
| H5b: Region adds value after controls | Not significant after correction | 0.09 |

The scoreboard supports three main conclusions: discount level is strongly related to margin, South × Fashion has an unusually high return rate, and Q4 daily orders are much higher. The other tested differences do not provide a strong basis for changing business policy.

---

## 5. Recommended actions and estimated impact

| Priority | Recommended action | Evidence and estimated impact |
|---|---|---|
| 1 | **Set category discount caps:** Electronics 10%, Fashion 30%, Grocery 10%, Home 20%. | **₹11.1 lakh to ₹20.1 lakh** estimated yearly profit improvement. |
| 2 | **Investigate and reduce South × Fashion returns.** Review sizing, quality, listings and courier handling. | **₹0.9 lakh to ₹2.8 lakh** estimated yearly profit improvement if the return rate reaches 6.8%; around 81 fewer returns. |
| 3 | **Prepare a Q4 operations plan.** Plan stock and delivery capacity for around twice the daily order volume. | Supports the Q4 demand increase. The benefit is not separately quantified; it is not an additional amount to add to Action 1. |
| 4 | **Run a controlled discount test** comparing 0%, 10% and 20% discounts. | No separate profit estimate. It will help establish whether discounts bring in additional customers and protect the discount policy decision. |
| 5 | **Do not introduce regional pricing at this stage.** | Avoids spending time and effort on a strategy not supported by the current evidence. |

### How the discount improvement is estimated

The report identifies **1,467 orders (24% of all orders)** with discounts above the proposed category caps. Together, these orders currently lose **₹16.7 lakh under Scenario A** or **₹11.1 lakh under Scenario B**.

The analysis estimates the result of repricing these orders at the relevant category cap under different customer-retention assumptions:

| Share of customers who still buy | Profit change, Scenario A | Profit change, Scenario B |
|---|---:|---:|
| 100% | +₹20.1 lakh | +₹20.1 lakh |
| 75% | +₹19.2 lakh | +₹17.8 lakh |
| 50% | +₹18.4 lakh | +₹15.6 lakh |
| 25% | +₹17.5 lakh | +₹13.3 lakh |
| 0% | +₹16.7 lakh | +₹11.1 lakh |

The estimated improvement remains positive even if none of these customers continues buying, because the report finds that no order above the proposed cap earns positive profit.

These are scenario estimates, not guaranteed future results. Actual impact will depend on customer behaviour, implementation and the returned-goods policy.

For returns overall, the report estimates that every **1 percentage-point reduction** in the return rate is worth approximately **₹0.5 lakh (Scenario B) to ₹3.3 lakh (Scenario A) per year**.

---

## 6. Limitations and decisions to confirm

The findings should be used with the following limits in mind:

1. **The data is observational.** It shows patterns and relationships, but it cannot prove that one factor caused another. A controlled discount experiment is needed to measure the effect of discounts on customer demand.
2. **Returned-goods treatment is unknown.** Scenario A assumes returned goods are written off. Scenario B assumes they are restocked and resold at cost. Operations must confirm the actual policy.
3. **Cost ratios are unusually exact.** Cost is exactly 82% of list price for Electronics, 60% for Fashion, 88% for Grocery and 70% for Home. Finance should confirm whether these costs are actual values or estimates.
4. **Some practical-significance thresholds are judgment calls.** The thresholds used for effect sizes, including 0.01 and Cramér's V of 0.05, reflect the analysis team's choices.
5. **Some costs are missing.** Shipping, handling and overhead are not included. Actual profit will therefore be lower than the estimates in this report.
6. **The recommendations depend on the assumptions and calculations in the analysis.** Confirm the cost structure, returned-goods policy and discount rules before changing live pricing.

---

## 7. Final decision

The analysis points to a clear order of action:

**First, protect margin by introducing category-specific discount caps. Second, investigate the South × Fashion return hotspot. Third, prepare inventory and delivery operations for Q4 demand.**

Run a controlled discount experiment to understand the effect of promotions on customer demand, and avoid region-specific pricing until stronger evidence supports it.

These actions address the largest issues identified in the 2025 order data and provide a practical starting point for improving KartNest's profitability.
