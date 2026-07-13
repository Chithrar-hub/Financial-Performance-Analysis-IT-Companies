# Financial Performance Analysis — Indian IT Companies

A study of how five major Indian IT companies — TCS, Infosys, Wipro, HCL Technologies,
and Tech Mahindra — performed financially between FY2021-22 and FY2025-26.

## Why this project

The IT sector is one of the biggest contributors to India's economy, but it's not
always easy to tell which companies are actually performing well financially, beyond
just looking at revenue numbers. This project pulls apart five years of financial data
for five leading companies and compares them properly — using ratio analysis, some
statistical testing, and a bit of machine learning to round things out.

## What's in here

The analysis starts with the basics: profitability, liquidity, solvency, and efficiency
ratios calculated from each company's financial statements. From there, it goes a step
further —

- **Ranking** — all six ratios are combined into a single composite score, so companies
  can be ranked overall rather than compared ratio-by-ratio.
- **Significance testing** — ANOVA was used to check whether the differences between
  companies are actually meaningful, not just random variation.
- **Correlation** — looked at how ratios relate to each other (for example, whether
  higher profit margins actually translate to better returns).
- **Prediction** — a simple linear regression estimates each company's next year's
  profit based on its 5-year trend, with an honest R² check on how reliable that
  estimate actually is.
- **Clustering** — K-Means groups the companies into performance tiers automatically,
  based on their overall ratio profile.

## What I found

TCS came out on top pretty much across the board — highest composite score, highest
average ROE (47.5%), and the most reliable growth trend of the five. Wipro was
consistently at the other end, both in current performance and in how volatile its
year-to-year numbers were. Profitability and efficiency ratios (Net Profit Margin,
Asset Turnover) turned out to be strongly linked to ROE, which lines up with the idea
that operational efficiency drives shareholder returns in this sector.

## Tools used

Excel for the initial data cleaning and ratio calculations, Python (pandas, scipy,
scikit-learn) for the statistical tests, prediction, and clustering, and matplotlib
for the charts.

## Files in this repo

| File | What it is |
|---|---|
| `Full_Analysis_Code_FINAL.py` | The complete analysis script — ratios, ANOVA, correlation, ranking, prediction, and clustering |
| `Master_Financial_Data.xlsx` | The underlying data and calculated ratios |
| `Final_Charts.png` | Ranking, prediction, and cluster visualizations |
| `Study_Guide.md` | A section-by-section breakdown of the code, for anyone learning from it |

## Data source

All financial figures were sourced from [screener.in](https://www.screener.in), based
on the companies' published consolidated financial statements.

## Honest limitations

Five companies and five years is a fairly small sample, so the statistical power here
is limited. The regression-based predictions are also a lot less reliable for Wipro and
Tech Mahindra (R² of 0.35 and 0.07) than for TCS or Infosys (R² above 0.9) — their
year-to-year profit just doesn't follow as clean a trend. The Current Ratio is also an
approximation, since screener.in doesn't separate current and non-current liabilities.
