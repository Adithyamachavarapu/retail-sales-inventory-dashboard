# Retail Sales & Inventory Dashboard

A Power BI report built on 1.07 million real invoice lines from a UK online giftware wholesaler (UCI Online Retail II dataset). Covers sales performance, product importance, slow-moving stock and returns.

## What it does

The report answers three questions for the buying team:
1. Did the business actually grow from FY2010 to FY2011?
2. Which products matter most and how predictable is their demand?
3. What has stopped selling and might be sitting in the warehouse?

## Data

- **Source:** UCI Machine Learning Repository, Online Retail II (Chen, 2019)
- **Licence:** CC BY 4.0
- **Period:** 1 Dec 2009 to 9 Dec 2011
- **Size:** 1,067,371 raw invoice lines, 8 columns
- **After cleaning:** 1,021,248 lines, 4,736 products, 5,875 customers, 43 countries

## Key findings

| Finding | Detail |
|---------|--------|
| FY2011 growth | Flat. Revenue up 1.9% but paired t-test p = 0.57 |
| Seasonal peak | Sep-Nov earns 37.5% of yearly revenue |
| A products | 830 (21.9%) earn 80% of revenue |
| Dormant products | 640 sold in FY2011 but not in the last 90 days |
| Return rate | 2.35%, down from 2.56% |
| Price vs volume | Spearman -0.33, cheaper products sell more |

## Cleaning decisions

- Removed 34,335 exact duplicates
- Removed postage/fee codes, zero-price lines, bad-debt adjustments
- Found and removed two giant orders cancelled minutes later (74,215 and 80,995 units). Left in, they would inflate the return rate from 2.35% to 3.13%
- Kept 22.2% of lines with no customer ID — they are real guest sales

## Tools used

- **Python** (pandas, SciPy): download, cleaning, weekly demand table, product classification, statistics
- **Power BI Desktop**: star schema (4 tables, 3 relationships), 33 DAX measures, 3 pages

## Report pages

- **Sales Overview** — net revenue, orders, AOV, customers, return rate, YoY changes
- **Products & ABC** — Pareto curve, ABC-XYZ matrix, top 10 products with CV
- **Stock Movement & Returns** — dormant products, seasonality, most-returned products

## Limitations

- No stock-on-hand, cost, or supplier lead-time data
- Categories are keyword-based, not the company's own
- Data is from 2009-2011
- 22% of lines have no customer ID

## Dataset

UCI Online Retail II. CC BY 4.0 licence.
