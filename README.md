# Currency Sensitivity to Market Volatility: An Econometric Analysis of FX Rates and the VIX

## Overview
This project investigates the relationship between foreign exchange (FX) rates and global market volatility, as measured by the VIX index (the "fear gauge"). Using a panel dataset of 25 currencies from 1990 to 2021, it estimates the sensitivity of each currency to changes in the VIX through country-specific regressions.

The main goal is to quantify how much exchange rates move, on average, when global market volatility changes, and to identify which currencies are more or less sensitive to these shifts.

---

## Workflow

### 1. Data Collection
- FX rates (quarterly) against USD for 25 currencies.
- VIX index values (daily), aggregated to quarterly averages.

### 2. Data Cleaning & Preparation
- Converting quarterly strings to proper date objects.
- Merging FX and VIX datasets into a single panel dataset.
- Handling missing values and aligning time frames.
- Transforming variables to log values and computing quarterly log differences.

### 3. Exploratory Data Analysis (EDA)
- Plotting FX and VIX time series for each currency.
- Checking distribution of missing data and data ranges.

### 4. Econometric Analysis
Running OLS regressions for each currency:

\[
\Delta \log(FX) = \alpha + \beta \, \Delta \log(VIX) + \epsilon
\]

- **β** is interpreted as the % change in FX for a 1% change in VIX.
- Statistical significance, R² values, and confidence intervals are reported.

### 5. Key Findings
- Several currencies show strong, statistically significant reactions to VIX changes (e.g., BRL, MXN, ZAR).
- Others (e.g., CHF, CNY, EUR, JPY) show little to no statistically significant response.

### 6. Econometric Considerations
- Review of OLS assumptions and potential violations (e.g., omitted variable bias, reverse causality).
- Alternative approaches for causal inference: Instrumental Variables (IV), Fixed Effects, Difference-in-Differences (DiD).

---

## Requirements
Python 3.x with the following packages:
```bash
pandas
numpy
matplotlib
seaborn
statsmodels
yfinance
linearmodels
openpyxl
