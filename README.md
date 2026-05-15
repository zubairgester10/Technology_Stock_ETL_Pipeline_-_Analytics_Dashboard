# Technology_Stock_ETL_Pipeline_-_Analytics_Dashboard
An end-to-end ETL pipeline that extracts AAPL stock market data from the Alpha Vantage API, transforms it into analytical datasets using Python and pandas, and visualizes performance, returns, and volatility insights through a Power BI dashboard.

## 📌 Project Overview

A financial firm needs a lightweight analytics system to monitor the performance and risk exposure of a technology stock portfolio. This project replaces manual reporting with a structured, repeatable data pipeline that tracks daily stock performance, measures volatility, and surfaces trends through visual dashboards.

The primary asset analysed is **AAPL**, with a simulated portfolio structure for comparative analysis.

---

## 🎯 Problem Statement

The firm needed a system to:
- Track daily performance of technology stocks
- Understand volatility and risk exposure over time
- Replace manual reporting with an automated data pipeline

---

---

## 🛠️ Tools & Technologies

| Category | Tool |
|---|---|
| Language | Python |
| Data Manipulation | pandas |
| API Integration | requests |
| Data Source | Alpha Vantage API |
| Visualisation | Microsoft Power BI |

## 🔄 ETL Pipeline

### 1. Extract
- Daily stock market data is pulled from the **Alpha Vantage API** using Python
- The JSON response is converted into a structured **pandas DataFrame**
- Time series data is isolated for downstream processing

### 2. Transform

**Data Cleaning:**
- Standardised column names
- Converted string values to numeric types
- Sorted data chronologically
- Removed duplicate records
- Handled missing values using forward fill

**Feature Engineering:**
| Metric | Description |
|---|---|
| `daily_return` | Percentage change in daily closing price |
| `rolling_avg_7` | 7-day rolling average to smooth short-term noise |
| `volatility` | Rolling standard deviation of daily returns |
| `weighted_return` | Return adjusted by portfolio allocation weight |

### 3. Load
Two structured CSV datasets are exported:
- **`stock_prices.csv`** — full time-series dataset for trend analysis
- **`portfolio_summary.csv`** — aggregated metrics for portfolio comparison

Both datasets are loaded into **Power BI** for visual analytics.


The dashboard contains four core visuals:

| Chart | Type | Purpose |
|---|---|---|
| Stock Price Trend | Line Chart | Tracks closing price over time to identify market direction |
| Daily Returns | Bar Chart | Shows daily % gains and losses to evaluate short-term fluctuations |
| Volatility Analysis | Line Chart | Measures variability in returns to assess risk exposure over time |
| Rolling Average | Line Chart | Smooths price movement to highlight underlying trends |

---

## 🔍 Key Insights (AAPL — Dec 2025 to May 2026)

- **Price:** AAPL dropped to a low of **$247** in mid-January before recovering strongly to a high of **$299** by mid-May
- **Daily Returns:** The worst single day was **-5.0%** in mid-February; the best was **+4.1%** in early February
- **Volatility:** Risk peaked at **0.027 in early March**, the most turbulent period, before calming to **0.007 in late March**
- **Trend:** The 7-day rolling average confirmed a sustained recovery from April onwards, reaching **$291 by May**

---
