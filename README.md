# S&P 500 Sector Performance & 2026 Investment Outlook

**Tools:** Python · pandas · SQL (SQLite) · scikit-learn · matplotlib · seaborn · Tableau Public  
**Period:** January 2020 – December 2025 | **Universe:** 30 S&P 500 stocks · 6 sectors  
**Author:** Derren Winata · [LinkedIn](https://www.linkedin.com/in/derren-winata) · [Tableau Dashboard](https://public.tableau.com/app/profile/derren.winata/viz/SP500SectorAnalysis5-YearPerformance2026Outlook/Dashboard1)

---

## Overview

This project performs a full-stack financial data analysis on 30 S&P 500 stocks across 6 sectors (Technology, Healthcare, Finance, Energy, Consumer, Utilities) covering January 2020 through December 2025. It answers five core investment questions using Python, SQL, machine learning, and interactive Tableau visualizations — and produces a 2026 sector investment outlook.

---

## Business Questions Answered

1. Which sectors delivered the best risk-adjusted returns over 5 years?
2. Does higher volatility lead to higher returns across sectors?
3. Are there seasonal patterns in market returns?
4. How correlated are stocks within vs. across sectors?
5. Which sectors should investors OVERWEIGHT, NEUTRAL, or UNDERWEIGHT in 2026?

---

## Key Findings

- **Technology** was the dominant sector over 2020–2025, returning **+319% cumulatively** — far ahead of Consumer (+52%) and Finance (+16%). Healthcare (-2%), Utilities (-19%), and Energy (-31%) all finished negative or near flat.
- **Energy** carried the highest risk, with average annualized volatility of **24.9%**. CVX and SLB sustained maximum drawdowns of **-74% and -78%** respectively. Energy's worst year was 2022, coinciding with global oil supply shocks.
- **Within-sector correlations averaged ~0.69** vs cross-sector **~0.00** — near zero. This confirms that sector allocation, not individual stock selection, is the dominant driver of portfolio variance. Diversifying across sectors is far more effective than holding multiple stocks within the same sector.
- **January seasonality is inconsistent**: the January rebound effect appeared in 3 of 6 years (2021, 2023, 2024). January 2023 was the single strongest month (+1.11%), while January 2025 was the weakest (-1.17%).
- **2026 Outlook**: Linear trend regression forecasts **Technology as OVERWEIGHT** (predicted +240%) and **Healthcare as UNDERWEIGHT** (predicted -68%). Finance and Utilities show narrow confidence intervals near flat growth.

---

## Methodology

| Step | Detail |
|---|---|
| Data source | Yahoo Finance via `yfinance` API — 45,000+ daily price rows |
| Feature engineering | Annualized return, annualized volatility, Sharpe ratio, maximum drawdown |
| SQL analysis | SQLite queries for top performers by Sharpe ratio, worst drawdown months, sector-level yearly pivots |
| Forecasting | Linear regression (year → annual return) per sector, 500-sample bootstrap confidence intervals |
| Visualization | 9 publication-quality charts (matplotlib/seaborn) + 4-sheet Tableau Public dashboard |

**Forecast limitations:** Small sample (n=6 annual data points per sector), no macro factors (interest rates, earnings, inflation), assumes linear continuation of past trends. Wide confidence intervals are intentional and disclosed.

---

## Charts

![Cumulative Returns](plots/plot_01_cumulative_returns.png)
![Risk vs Return](plots/plot_02_risk_return.png)
![Sharpe Ratio](plots/plot_03_sharpe_ratio.png)
![Correlation Heatmap](plots/plot_04_correlation_heatmap.png)
![Seasonality](plots/plot_05_seasonality.png)
![Return Distribution](plots/plot_06_return_distribution.png)
![Rolling Volatility](plots/plot_07_rolling_volatility.png)
![2026 Forecast](plots/plot_08_2026_prediction.png)
![Historical vs Forecast](plots/plot_09_historical_vs_forecast.png)

---

## Interactive Tableau Dashboard

**[View Live Dashboard →](https://public.tableau.com/app/profile/derren.winata/viz/SP500SectorAnalysis5-YearPerformance2026Outlook/Dashboard1)**

Four linked views:
- **Cumulative Returns 2020–2025** — sector performance over time
- **Risk vs. Return Scatter** — annualized return vs. volatility by stock and sector
- **2026 Sector Forecast** — predicted returns with OVERWEIGHT / UNDERWEIGHT recommendations
- **Market Seasonality Heatmap** — monthly return patterns across 2020–2025

---

## Project Structure

```
sp500-sector-analysis/
├── README.md
├── requirements.txt
├── sp500_sector_analysis_FINAL.ipynb
├── data/
│   ├── tableau_daily_returns.csv
│   ├── tableau_stock_summary.csv
│   ├── tableau_sector_cumret.csv
│   ├── tableau_seasonality.csv
│   ├── tableau_2026_predictions.csv
│   └── tableau_sector_yearly.csv
└── plots/
    ├── plot_01_cumulative_returns.png
    ├── plot_02_risk_return.png
    ├── plot_03_sharpe_ratio.png
    ├── plot_04_correlation_heatmap.png
    ├── plot_05_seasonality.png
    ├── plot_06_return_distribution.png
    ├── plot_07_rolling_volatility.png
    ├── plot_08_2026_prediction.png
    └── plot_09_historical_vs_forecast.png
```

---

## How to Run

```bash
git clone https://github.com/darderrdur17/sp500-sector-analysis
cd sp500-sector-analysis
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
jupyter notebook sp500_sector_analysis_FINAL.ipynb
```

Run all cells top-to-bottom. Data downloads automatically from Yahoo Finance (~30 seconds).

---

## Requirements

```
yfinance>=0.2.36
pandas>=2.0.0
numpy>=1.25.0
matplotlib>=3.7.0
seaborn>=0.13.0
scikit-learn>=1.3.0
jupyter>=1.0.0
```

---

*Derren Winata · [linkedin.com/in/derren-winata](https://www.linkedin.com/in/derren-winata) · [Tableau Public](https://public.tableau.com/app/profile/derren.winata/viz/SP500SectorAnalysis5-YearPerformance2026Outlook/Dashboard1)*
