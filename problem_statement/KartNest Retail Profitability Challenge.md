# KartNest Retail Profitability Challenge

*Data Analytics Hackathon brief (simulated). KartNest is a fictional company, and the brief is written for practice with orders.csv.*

## About the company

KartNest is a fast-growing online retailer selling Electronics, Fashion, Grocery and Home products across four regions of India (North, South, East, West). It ships a few thousand orders per month and relies on promotional discounts to drive sales.

## Background

Leadership wants to know whether the business is making money in the right places. The VP of Category and Pricing has asked the analytics team to review the 2025 order data and recommend where to change pricing, promotions, and operations. The team lacks the time to do this manually, so they have turned to you.

## Problem statement

> Analyse KartNest's 2025 order data to identify where the business makes and loses money, explain why, and recommend specific actions with a quantified impact on profit.

## Dataset

File: `orders.csv`, about 6,000 order records covering January to December 2025. All monetary values are in **Indian Rupees (INR)**.

| Column | Description |
| --- | --- |
| order\_id | Unique order identifier |
| order\_date | Date the order was placed |
| region | Sales region of the customer |
| category | Product category (Electronics, Fashion, Grocery, Home) |
| unit\_price | List price per unit before discount |
| quantity | Units in the order |
| discount\_pct | Promotional discount applied, as a % of list price |
| revenue | Order value after discount |
| cost | Total cost of goods for the order |
| returned | TRUE if the customer returned the order (a full refund is issued) |

**Data notes:** the data was compiled from the order system and manual spreadsheets. Quality is not guaranteed, and the file is provided as-is. No profit column is provided.

## Your tasks

1. **Prepare the data:** assess quality, clean the dataset, and document every decision.
2. **Explore:** find patterns across categories, regions, time, discounts and returns.
3. **Analyse:** use statistical methods to separate real patterns from random variation.
4. **Visualise:** build clear charts or an interactive dashboard that support your story.
5. **Recommend:** give 3-5 specific, prioritised actions with an estimated impact on profit. State your assumptions.

## Deliverables

- Google Colab notebook that runs top to bottom
- Analysis report (maximum 5 pages)
- 3-minute video covering the analysis, key insights, and recommendations

## Evaluation criteria

| Criterion | Weight |
| --- | --- |
| Problem understanding | 10% |
| Data cleaning and documentation | 15% |
| Depth and rigour of analysis | 25% |
| Visualisation quality | 15% |
| Insights and recommendations | 25% |
| Communication (report and video) | 10% |

## Rules

- Work solo or in a team of two.
- AI tools are allowed, but you are responsible for the correctness of every number and claim.
- State all assumptions clearly. Unsupported claims will lose marks.
- Submit before the deadline. Late submissions are not evaluated.

## How to use this brief

1. Paste the brief into the first markdown cell of your notebook.
2. Spend 30 minutes on it, as in the real hackathon. Use the "understand the problem statement" prompt (A3) from the prompt library, then write your own Project Brief cell and questions.
3. Notice that the brief now gives the currency (INR) and defines returns as fully refunded. Your current charts say "USD ($)", so those labels need fixing first. The brief is your source of truth for units and definitions.
4. Notice what the brief doesn't say, like how returned goods are treated or what a good result looks like. Those gaps are your assumptions register.

**Next action:** write one sentence in your own words for the problem, the decision-maker, and the success metric.
