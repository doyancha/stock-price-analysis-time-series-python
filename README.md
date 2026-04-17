<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=300&section=header&text=Stock%20Price%20Analytics%20Dashboard&fontSize=46&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Transforming%20Historical%20Market%20Data%20into%20Analytical%20Intelligence&descAlignY=58&descSize=18" width="100%"/>

</div>

<div align="center">
  <a href="https://www.linkedin.com/in/mir-shahadut-hossain/"><img src="https://img.shields.io/badge/LinkedIn-Mir%20Shahadut%20Hossain-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://github.com/doyancha"><img src="https://img.shields.io/badge/GitHub-doyancha-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"></a>
  <a href="mailto:sujon6901@gmail.com"><img src="https://img.shields.io/badge/Email-sujon6901%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://stock-price-analytics.streamlit.app/"><img src="https://img.shields.io/badge/Live%20App-Streamlit%20Deployment-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Live App"></a>

<p>
  <img src="https://img.shields.io/badge/Streamlit-Dashboard-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit">
  <img src="https://img.shields.io/badge/Python-Time%20Series-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Plotly-Interactive%20Visuals-3F4F75?style=flat-square&logo=plotly&logoColor=white" alt="Plotly">
  <img src="https://img.shields.io/badge/NumPy-Analytics-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy">
</p>
</div>

---

<div align="center">

<h2 style="margin-bottom: 14px;">THE CORE QUESTION</h2>

<div style="display: inline-block; padding: 18px 24px; border-radius: 18px; background: linear-gradient(135deg, #0f172a 0%, #111827 100%); border: 1px solid #334155; box-shadow: 0 10px 30px rgba(0,0,0,0.25);">
  <pre style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.5; font-family: Consolas, Monaco, monospace; text-align: left;">
+----------------------------------------------------------------------+
|                                                                      |
|   How do major technology stocks compare on trend, return, risk,     |
|            correlation, and simple strategy behaviour?               |
|                                                                      |
+----------------------------------------------------------------------+
  </pre>
</div>

</div>

---

## Executive Summary

This project transforms five years of historical stock price data into a polished Streamlit analytics dashboard focused on one central question:

> **How do major technology stocks compare on trend, return, risk, correlation, and simple strategy behaviour?**

The app combines exploratory analysis, return diagnostics, volatility measurement, correlation mapping, moving-average signal exploration, and lightweight backtesting into a portfolio-ready analytics experience built around Apple, Amazon, Google, and Microsoft.

---

## Table of Contents

| # | Section |
|---|---------|
| 01 | [Project Intention & Goals](#project-intention--goals) |
| 02 | [Dataset at a Glance](#dataset-at-a-glance) |
| 03 | [Analysis Modules](#analysis-modules) |
| 04 | [Key Findings](#key-findings) |
| 05 | [Technical Pipeline](#technical-pipeline) |
| 06 | [Repository Structure](#repository-structure) |
| 07 | [Run Locally](#run-locally) |
| 08 | [Dashboard Preview](#dashboard-preview) |
| 09 | [About the Author](#about-the-author) |
| 10 | [Suggested Resources](#suggested-resources) |

---

## Project Intention & Goals

> This project was built to go beyond static price charts by treating historical stock data as a decision-support asset for comparative financial analysis.

### What This Project Sets Out To Do

- Compare four major technology stocks through a unified analytical framework
- Measure not just price movement, but return behaviour, volatility, and risk-adjusted performance
- Reveal how strongly the stocks move together through closing-price and return-level correlation
- Explore how moving averages change the interpretation of trend direction
- Detect and visualise moving-average crossover signals in an intuitive dashboard format
- Test a simple strategy against buy-and-hold to demonstrate analytical thinking beyond descriptive charts
- Present the analysis as a polished, stakeholder-ready Streamlit application rather than a notebook alone

### Business Questions Addressed

- Which stock delivered the strongest total return over the common analysis period?
- Which stock produced the best Sharpe Ratio?
- Which stock carried the highest day-to-day volatility?
- Which stocks move most similarly in return terms?
- How useful are moving-average crossover signals as a basic timing framework?
- Does a simple moving-average rule outperform passive buy-and-hold in this universe?

---

## Dataset at a Glance

<div align="center">

| Metric | Value |
|--------|-------|
| Stocks Covered | 4 |
| Companies | Apple, Amazon, Google, Microsoft |
| Raw Dataset Range | Feb 08, 2013 to Feb 07, 2018 |
| Common Comparison Window | Mar 2014 to Feb 2018 |
| Total Rows | 4,752 |
| Data Frequency | Daily |
| Strongest Return | Amazon (+318.6%) |
| Best Sharpe Ratio | Amazon (1.40) |
| Highest Volatility | Amazon (1.844) |
| Strongest Return Correlation Pair | Amazon / Google |

</div>

### Data Sources Used

| File | Purpose |
|------|---------|
| `individual_stocks_5yr/AAPL_data.csv` | Apple historical daily price data |
| `individual_stocks_5yr/AMZN_data.csv` | Amazon historical daily price data |
| `individual_stocks_5yr/GOOG_data.csv` | Google historical daily price data |
| `individual_stocks_5yr/MSFT_data.csv` | Microsoft historical daily price data |
| `Stock_price_analysis.ipynb` | Notebook-based exploratory and analytical workflow |
| `app.py` + `pages_content/` | Streamlit dashboard interface and page routing |

---

## Analysis Modules

The dashboard is organised into a clear analytical journey instead of isolated charts.

### Module 1 - Data Layer

- CSV loading and column normalization
- Date parsing and ticker standardization
- Shared overlapping-date logic for fair comparison
- KPI preparation and reusable metric helpers

### Module 2 - Dataset Overview

- Structural inspection of rows, tickers, date span, and quality
- Schema and preprocessing summary
- Quick validation of what the analytical layer is built on

### Module 3 - Trend Analysis

- Daily closing-price comparison across stocks
- Selectable moving-average overlays
- Trend context through short and long horizon smoothing

### Module 4 - Return Analysis

- Daily return visualization
- Distribution diagnostics
- Cumulative performance comparison
- Best vs. worst day and monthly return exploration

### Module 5 - Risk & Volatility

- Volatility comparison across stocks
- Rolling risk visualization
- Risk-return positioning
- Sharpe Ratio comparison

### Module 6 - Correlation Analysis

- Closing-price correlation heatmap
- Return correlation heatmap
- Pairwise relationship analysis
- Cross-stock dependence interpretation

### Module 7 - Signal Explorer

- Moving-average crossover detection
- Buy and sell signal marking
- Signal tables for stock-level inspection

### Module 8 - Strategy & Backtesting

- Simple moving-average rule backtest
- Strategy vs. buy-and-hold comparison
- Performance framing for analytical demonstration

### Module 9 - Final Insight Layer

- Consolidated takeaways
- Interpretation of leaders, laggards, and risk behaviour
- Limitations and realistic framing

---

## Key Findings

> Here is what the analysis says when the four-stock universe is compared on a consistent basis.

### Finding 1 - Amazon Led on Absolute Return

Across the common comparison window, Amazon produced the strongest total return in the universe at approximately **+318.6%**, making it the clear top performer on absolute growth.

### Finding 2 - Amazon Also Led on Risk-Adjusted Return

Amazon did not only lead on raw return. It also posted the strongest annualised Sharpe Ratio at roughly **1.40**, indicating the most favorable return earned per unit of volatility in this dataset.

### Finding 3 - Higher Reward Came With Higher Risk

Amazon also showed the highest volatility, which reinforces a core financial insight: the strongest return opportunity in the group also came with the greatest instability.

### Finding 4 - Google Lagged Relative to the Group

Google remained positive over the period, but it was the weakest total-return performer within this four-stock universe, making it the relative laggard in the comparison.

### Finding 5 - Amazon and Google Moved Most Closely Together

The strongest return-level correlation pair in the data was **Amazon / Google**, suggesting these two stocks exhibited the most similar daily return behavior among the four.

### Finding 6 - Technical Signals Add Structure, Not Certainty

Moving averages and crossover logic help frame changing momentum conditions, but the dashboard treats them as analytical tools rather than predictive truth. They support interpretation; they do not replace investment judgment.

---

## Technical Pipeline

<div align="center">

<div style="display: inline-block; padding: 20px 24px; border-radius: 18px; background: linear-gradient(135deg, #0f172a 0%, #111827 100%); border: 1px solid #334155; box-shadow: 0 10px 28px rgba(0,0,0,0.22);">
  <pre style="margin: 0; color: #e2e8f0; font-family: Consolas, Monaco, monospace; font-size: 14px; line-height: 1.65; text-align: left;">
Raw CSV Files
      |
      v
Data Loading and Validation
      |
      v
Feature Engineering
(daily returns, moving averages)
      |
      +----------------------+
      |                      |
      v                      v
Comparative Metrics     Signal Generation
(return, risk, corr)    (MA crossover logic)
      |                      |
      +----------+-----------+
                 |
                 v
Interactive Visualisation
(Plotly + Streamlit UI)
                 |
                 v
Portfolio-Style Dashboard
stock-price-analytics.streamlit.app
  </pre>
</div>

</div>

### Tech Stack

<table align="center" style="border-collapse: collapse; width: 90%; max-width: 900px; overflow: hidden; border-radius: 14px;">
  <thead>
    <tr>
      <th style="background: #0f172a; color: #ffffff; padding: 14px; border: 1px solid #334155;">Layer</th>
      <th style="background: #0f172a; color: #ffffff; padding: 14px; border: 1px solid #334155;">Tools</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="background: #f8fafc; padding: 12px 14px; border: 1px solid #cbd5e1;"><strong>Data Wrangling</strong></td>
      <td style="background: #f8fafc; padding: 12px 14px; border: 1px solid #cbd5e1;"><code>pandas</code>, <code>numpy</code></td>
    </tr>
    <tr>
      <td style="background: #eef2ff; padding: 12px 14px; border: 1px solid #cbd5e1;"><strong>Visualization</strong></td>
      <td style="background: #eef2ff; padding: 12px 14px; border: 1px solid #cbd5e1;"><code>plotly</code></td>
    </tr>
    <tr>
      <td style="background: #f8fafc; padding: 12px 14px; border: 1px solid #cbd5e1;"><strong>Dashboard</strong></td>
      <td style="background: #f8fafc; padding: 12px 14px; border: 1px solid #cbd5e1;"><code>streamlit</code></td>
    </tr>
    <tr>
      <td style="background: #eef2ff; padding: 12px 14px; border: 1px solid #cbd5e1;"><strong>Project Utilities</strong></td>
      <td style="background: #eef2ff; padding: 12px 14px; border: 1px solid #cbd5e1;"><code>pathlib</code></td>
    </tr>
    <tr>
      <td style="background: #f8fafc; padding: 12px 14px; border: 1px solid #cbd5e1;"><strong>Notebook Analysis</strong></td>
      <td style="background: #f8fafc; padding: 12px 14px; border: 1px solid #cbd5e1;"><code>jupyter</code></td>
    </tr>
  </tbody>
</table>

---

## Repository Structure

```text
stock-price-analysis-time-series-python/
|
|-- app.py
|-- README.md
|-- requirements.txt
|-- Stock_price_analysis.ipynb
|
|-- assets/
|   |-- profile.jpg
|   |-- stock_price_trend_analysis.png
|   |-- daily_return_analysis.png
|   |-- volatility_comparison.png
|   |-- risk_vs_return.png
|   |-- corr_closing_price.png
|   |-- corr_daily_return.png
|   |-- moving_average_analysis.png
|   |-- golden_cross_and_death_cross_analysis.png
|   `-- app_sell_buy.png
|
|-- individual_stocks_5yr/
|   |-- AAPL_data.csv
|   |-- AMZN_data.csv
|   |-- GOOG_data.csv
|   `-- MSFT_data.csv
|
|-- pages_content/
|   |-- about.py
|   |-- correlation.py
|   |-- dataset.py
|   |-- home.py
|   |-- insights.py
|   |-- returns.py
|   |-- risk.py
|   |-- signals.py
|   |-- strategy.py
|   `-- trend.py
|
`-- utils/
    |-- charts.py
    |-- data.py
    |-- sidebar.py
    `-- styles.py
```

---

## Run Locally

### Step 1 - Clone the Repository

```bash
git clone https://github.com/doyancha/stock-price-analysis-time-series-python.git
cd stock-price-analysis-time-series-python
```

### Step 2 - Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3 - Launch the Dashboard

```bash
streamlit run app.py
```

The app will open locally at `http://localhost:8501`.

### Requirements

```txt
streamlit
pandas
numpy
plotly
```

---

## Dashboard Preview

The repository already includes exported visuals in the [`assets`](./assets) folder, which makes it possible to preview the analytical scope even before launching the app.

<table>
  <tr>
    <td><img src="./assets/stock_price_trend_analysis.png" alt="Trend Analysis" width="100%"></td>
    <td><img src="./assets/daily_return_analysis.png" alt="Return Analysis" width="100%"></td>
  </tr>
  <tr>
    <td><img src="./assets/volatility_comparison.png" alt="Volatility Comparison" width="100%"></td>
    <td><img src="./assets/golden_cross_and_death_cross_analysis.png" alt="Signal Analysis" width="100%"></td>
  </tr>
</table>

<div align="center">

| Page | Description |
|------|-------------|
| **Home** | Executive overview with KPIs and market-wide summary visuals |
| **Dataset Overview** | Structural inspection of rows, dates, coverage, and preprocessing |
| **Trend Analysis** | Price history and moving-average exploration |
| **Return Analysis** | Daily return behavior, distribution, and cumulative performance |
| **Risk & Volatility** | Volatility, Sharpe Ratio, and risk-return positioning |
| **Correlation Analysis** | Closing-price and return-level correlation mapping |
| **Signal Explorer** | Moving-average crossover events and stock-level signal tracking |
| **Strategy & Backtesting** | Simple MA strategy comparison versus buy-and-hold |
| **Key Insights** | Consolidated takeaways for interpretation and storytelling |
| **About Project** | Author profile, project context, and technology stack |

</div>

---

## About the Author

<div align="center">

<div style="display: inline-block; padding: 20px 24px; border-radius: 18px; background: linear-gradient(135deg, #0f172a 0%, #111827 100%); border: 1px solid #334155; box-shadow: 0 10px 28px rgba(0,0,0,0.22);">
  <pre style="margin: 0; color: #e2e8f0; font-family: Consolas, Monaco, monospace; font-size: 14px; line-height: 1.65; text-align: left;">
+---------------------------------------------------------+
|                                                         |
|               MIR SHAHADUT HOSSAIN                      |
|          Data Analyst | Streamlit Developer             |
|                                                         |
|    Turning historical data into structured insight.     |
|                                                         |
+---------------------------------------------------------+
  </pre>
</div>

<br>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mir%20Shahadut%20Hossain-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mir-shahadut-hossain/)
[![GitHub](https://img.shields.io/badge/GitHub-doyancha-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/doyancha)
[![Email](https://img.shields.io/badge/Email-sujon6901%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sujon6901@gmail.com)
[![Live App](https://img.shields.io/badge/Live%20App-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://stock-price-analytics.streamlit.app/)

</div>

---

## Suggested Resources

### Documentation and Libraries Used

| Resource | Link |
|----------|------|
| Streamlit Docs | [docs.streamlit.io](https://docs.streamlit.io) |
| Pandas Documentation | [pandas.pydata.org/docs](https://pandas.pydata.org/docs) |
| NumPy Documentation | [numpy.org/doc](https://numpy.org/doc/) |
| Plotly Python Docs | [plotly.com/python](https://plotly.com/python/) |
| Python pathlib Docs | [docs.python.org/pathlib](https://docs.python.org/3/library/pathlib.html) |

### Dataset and Domain References

| Resource | Link |
|----------|------|
| Kaggle Stock Price Dataset Concepts | [kaggle.com](https://www.kaggle.com/) |
| Investopedia Sharpe Ratio Guide | [investopedia.com/sharpe-ratio](https://www.investopedia.com/terms/s/sharperatio.asp) |
| Investopedia Correlation Guide | [investopedia.com/correlation](https://www.investopedia.com/terms/c/correlation.asp) |
| Streamlit Community Cloud | [docs.streamlit.io/streamlit-community-cloud](https://docs.streamlit.io/streamlit-community-cloud/get-started) |

---

<div align="center">

<div style="display: inline-block; padding: 16px 22px; border-radius: 16px; background: linear-gradient(135deg, #111827 0%, #0f172a 100%); border: 1px solid #334155; box-shadow: 0 8px 24px rgba(0,0,0,0.18);">
  <pre style="margin: 0; color: #e2e8f0; font-family: Consolas, Monaco, monospace; font-size: 14px; line-height: 1.7; text-align: center;">
---------------------------------------------------------
 Built by Mir Shahadut Hossain | 2025-2026
 Data Analyst | Python Developer | Streamlit Builder
---------------------------------------------------------
  </pre>
</div>

<br><br>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer" width="100%"/>

</div>
