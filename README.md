# KartNest | Retail Profitability & Pricing Analytics

> **A business analytics case study on identifying profit leakage, evaluating pricing decisions, and improving retail profitability through data-driven recommendations.**

## Executive Overview

KartNest is a simulated e-commerce retailer operating across four regions in India and selling Electronics, Fashion, Grocery, and Home products.

The business provided approximately 6,000 order records covering 2025. The objective was to understand where profitability was being lost and recommend practical changes to pricing, promotions, and operations.

Instead of focusing only on sales and revenue, this project investigates a more important business question:

**Are the retailer's sales generating healthy profits, and what decisions could improve profitability?**

The analysis identified two major areas of concern:

- Excessive discounts were reducing order-level margins without clear evidence of increasing basket size.
- South × Fashion had a substantially higher return rate than the rest of the business.

It also investigated the Q4 order surge and whether regional profitability differences justified different pricing strategies.

## Business Problem

The VP of Category and Pricing wanted answers to five questions:

1. Are larger discounts actually improving business performance?
2. Should discount strategies differ across product categories?
3. Which categories or regions are experiencing unusually high returns?
4. Was the Q4 increase in orders driven by stronger demand or deeper promotions?
5. Are regional profitability differences large enough to justify regional pricing decisions?

The objective was to turn order-level data into actionable recommendations supported by statistical evidence.

## Dataset

| Attribute | Details |
|---|---|
| Business | Simulated e-commerce retailer |
| Period | January–December 2025 |
| Records | Approximately 6,000 orders |
| Regions | North, South, East, West |
| Categories | Electronics, Fashion, Grocery, Home |
| Data type | Structured order-level data |
| Currency | Indian Rupees (INR) |

Key variables included order date, region, category, unit price, quantity, discount percentage, revenue, cost, and return status.

**Data note:** This is a simulated business case, not an actual engagement with a real retailer.

## Analytical Approach

The project followed a business-first analytical workflow.

### 1. Business understanding

- Defined the profitability problem and the decisions management needed to make.
- Converted the problem statement into five testable business hypotheses.
- Identified the metrics required to evaluate discounts, margins, returns, and demand.

### 2. Data preparation and validation

- Inspected the dataset structure and relevant fields.
- Prepared the data for order-level profitability analysis.
- Defined how returns would be treated in the profitability calculation.
- Documented assumptions and limitations rather than treating missing business rules as known facts.

### 3. Exploratory data analysis

Investigated:

- Discount distribution across product categories.
- Order-level margins and loss-making orders.
- Units purchased at different discount levels.
- Return rates across category-region combinations.
- Monthly and quarterly order trends.
- Regional profitability patterns.

### 4. Statistical hypothesis testing

Used statistical tests to evaluate whether observed patterns were meaningful or could plausibly reflect random variation.

The analysis included:

- Kruskal–Wallis tests for comparing distributions.
- Mann–Whitney U tests for comparing daily order counts.
- Chi-square tests for categorical associations.
- Two-proportion z-tests for return-rate comparisons.
- Regression analysis to evaluate the contribution of category, discount, and region.
- Confidence intervals and effect sizes to assess practical importance.
- Holm correction to account for multiple hypothesis tests.

The choice of test depended on the question and the structure of the data.

## Key Findings

### 1. Discounts reduced profitability without increasing basket size

Order-level margin declined from 24.8% at zero discount to −25.5% at a 40% discount.

At the 40% discount level, 71% of orders were loss-making. However, the number of units purchased per order remained broadly similar across discount levels.

**Business implication:** Deeper discounts were eroding margins without clear evidence of larger baskets.

### 2. Discount economics differed by category

The estimated break-even discount levels varied across categories:

| Category | Break-even discount |
|---|---:|
| Electronics | 18% |
| Fashion | 40% |
| Grocery | 12% |
| Home | 30% |

The existing discount mix did not show evidence of being tailored to category economics.

**Business implication:** A single discount policy is not suitable for products with different cost structures.

### 3. South × Fashion was a return-rate hotspot

The South × Fashion combination recorded a return rate of 25.6%, compared with 6.8% across the remaining orders.

The difference was statistically significant, and the pattern remained elevated across the months examined.

**Business implication:** Investigate product sizing, product quality, listing accuracy, and delivery-related factors before applying a broad return-reduction strategy.

These are possible causes to investigate, not causes established by this analysis.

### 4. Q4 order volume increased substantially

Average daily orders increased from 12.9 to 27.0 in October–December, approximately 2.1 times the earlier-period level.

The analysis did not find statistically significant evidence of a deeper discount mix or a meaningful margin change driving this increase.

**Business implication:** Prepare inventory and delivery capacity for higher seasonal demand rather than assuming additional discounts are necessary.

### 5. Regional profitability differences were not practically meaningful

Although raw regional figures differed, the analysis did not find strong evidence that region independently explained profitability after accounting for other variables.

**Business implication:** Avoid introducing region-specific pricing without stronger evidence.

## Business Recommendations

| Priority | Recommendation | Estimated annual impact |
|---|---|---:|
| 1 | Introduce category-specific discount caps | +₹11.1L to +₹20.1L |
| 2 | Investigate and reduce South × Fashion returns | +₹0.9L to +₹2.8L |
| 3 | Prepare inventory and delivery capacity for Q4 demand | Operational opportunity; not separately quantified |
| 4 | Run controlled discount experiments before deeper promotions | To be measured through experiments |
| 5 | Avoid region-specific pricing without stronger evidence | Avoids unsupported policy changes |

### Proposed operating discount caps

| Category | Proposed cap |
|---|---:|
| Electronics | 10% |
| Fashion | 30% |
| Grocery | 10% |
| Home | 20% |

These are proposed operational caps, not the calculated break-even values. They are intended as conservative starting points for management review and controlled testing.

## Financial Impact and Assumptions

The discount recommendation estimates an annual profit improvement of ₹11.1 lakh to ₹20.1 lakh under the scenarios modelled.

The return analysis estimates an additional ₹0.9 lakh to ₹2.8 lakh annual improvement if the South × Fashion return rate can be reduced towards the rate observed in the remaining business.

These are **modelled estimates, not realised savings or guaranteed outcomes**.

Profitability depends on how returned goods are treated. Two scenarios were considered:

- Scenario A: returned goods are treated as a total loss.
- Scenario B: returned goods are restocked and resold at cost.

The report also notes that shipping, handling, and overhead costs were not available in the dataset. Actual business profit could therefore be lower.

The Q4 operational opportunity is not added to the discount improvement estimate, avoiding double-counting.

## Tools and Methods

- **Python:** Data analysis and statistical testing.
- **Pandas:** Data preparation and analysis.
- **Jupyter Notebook / Google Colab:** Reproducible analytical workflow.
- **Statistical methods:** Hypothesis testing, regression, confidence intervals, effect sizes, and multiple-testing correction.
- **Git and GitHub:** Project documentation and version control.

Only tools actually used in the submitted notebook should be retained in this list.

## What This Project Demonstrates

This project demonstrates more than the ability to generate charts or run statistical tests.

It demonstrates the ability to:

- Translate a broad business problem into testable analytical questions.
- Evaluate data and business assumptions before interpreting results.
- Select statistical methods based on the question being investigated.
- Distinguish statistical significance from practical business importance.
- Avoid making causal claims from observational data.
- Estimate financial impact under explicit assumptions.
- Communicate findings as prioritised management decisions.

## Limitations and Next Steps

This analysis uses observational data, so it cannot prove that discounts caused changes in customer demand or that a particular operational issue caused returns.

Before implementing the recommendations, management should:

1. Validate category cost assumptions with Finance.
2. Confirm the accounting treatment of returned products.
3. Include shipping, handling, and overhead costs in a fuller profit model.
4. Investigate the South × Fashion return reasons at SKU and order level.
5. Run controlled discount experiments to measure incremental demand and contribution profit.

## Final Takeaway

**Higher sales do not always mean higher profits.**

The most important outcome of this project was identifying where the business could improve profitability without simply relying on more promotions.

The analysis connected customer behaviour, pricing decisions, return patterns, statistical evidence, and financial assumptions to a practical set of management recommendations.

---

*This is an independent, simulated business analytics case study created for learning and portfolio demonstration.*
