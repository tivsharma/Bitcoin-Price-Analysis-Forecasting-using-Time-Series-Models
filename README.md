# Quantative Crypto Analytics: Time Series Forecasting & Volatility Modeling 

## Project Overview
This repository contains a rigorous quantitative analysis framework evaluating historical Bitcoin (BTC-USD) daily pricing dynamics across **2,222 trading days** (January 2020 – January 2026). The project applies advanced econometric time-series architectures—including Augmented Dickey-Fuller (ADF) tests, ARIMA, and seasonal SARIMA modeling—coupled with deep statistical residual diagnostics to simulate short-term price vectors and isolate structural volatility patterns.

## Key Metrices & Performance 
* **Stationarity Transformation:** Successfully stabilized a highly non-stationary asset series, shifting the ADF p-value from **0.65** to a stationary **\(~0.000\)** via first-order differencing.
* **Residual Independence:** Validated the mathematical validity of the forecasting models using a Ljung–Box test (p ≈ 0.51), confirming zero remaining autocorrelation within the model residuals.
* **Volatility Discovery:** Isolated strong mathematical evidence of **heteroskedasticity (volatility clustering)** via a Jarque–Bera and ARCH test (p ≈ 0.00), establishing a clear quantitative foundation for future GARCH modeling.

## Data Source
- **Asset:** Bitcoin (BTC-USD)  
- **Frequency:** Daily  
- **Period:** Jan 2020 – Jan 2026  
- **Data Provider:** Yahoo Finance (`yfinance`)  
- **Observations:** 2,222 daily records  

## Technical Stack 
* **Data Engineering Pipeline:** Python, `yfinance` API (Automated daily ingestion pipelines)
* **Time-Series & Econometric Modeling:** `statsmodels.tsa` (ARIMA, SARIMA)
* **Statistical Testing Engines:** SciPy Stats, Statsmodels (ADF, Ljung–Box, Jarque–Bera, ARCH)
* **Exploratory Analytics & Viz:** Matplotlib, Seaborn, Pandas, NumPy
* **Workspace environment:** Google Colab / Jupyter Notebooks

## Mathematical & Modeling Architecture 
### 1. Statistical Profiling & Stationarity Verification
* **Original Series Data Profile:** Visualized extreme right-skewed pricing distributions and high-amplitude macroeconomic market cycles.
* **ADF Test (Raw Baseline):** Test Statistic: `-1.24` (p-value = 0.65) → Formally failed to reject the null hypothesis of a unit root (Non-Stationary).
* **First-Order Transformation:** Applied \(\Delta P_t = P_t - P_{t-1}\). Post-transformation ADF Statistic dropped to `-12.57` (p-value ~ 0.00) → Rejected the null hypothesis, achieving strict stationarity.

### 2. Parameterization & Stochastic Modeling
* **ACF & PACF Diagnostics:** Analyzed lag dependencies to prevent over-differencing and accurately isolate autoregressive bounds.
* **ARIMA Framework:** Deployed an **ARIMA(1,1,0)** model to lock down localized, short-term autoregressive price velocity.
* **SARIMA Framework:** Configured a **SARIMA(1,1,0)(1,1,1)₇** matrix to absorb and model weekly seasonal trading fluctuations inherent to global 24/7 crypto markets.

### 3. Econometric Residual Diagnostics
* **Ljung–Box Test (p ≈ 0.51)::** Confirms that the model successfully captured the structural information, leaving only white noise behind.
* **Jarque–Bera Test (p ≈ 0.00):** Proved the residuals exhibit non-normal distributions, typical of heavy-tailed financial asset anomalies.
* **ARCH Test (p ≈ 0.00):** Formally identified localized volatility clustering, providing mathematical evidence that historical variance influences future market risk.

## Forecasting Output
* Engineered a forward-looking **30-day directional price projection** displaying calculated variance bands against historical trend lines.

## Repository Structure 
```text
bitcoin-time-series-forecasting/
│
├── data/
│   └── btc_usd_historical.csv       # Cached daily API market records
│
├── notebooks/
│   └── crypto_time_series_models.ipynb # Full pipeline from EDA to SARIMA forecasting
│
└── README.md                         # Technical documentation & metrics
```

## Project Assets 
**Google Colab Notebook:**  [Open notebook](https://colab.research.google.com/drive/1J9tx-4n3U7NrgyxyQSWkcTsdzNxzO3HH?usp=sharing#scrollTo=JWYjNBJjiNO6)

## Future Enhancements 
* Integrating a **GARCH(1,1)** framework to model the confirmed heteroskedasticity.
* Deploying multivariate LSTM networks factoring in trading volume indices.

## Author 
* **Tivsha Sharma**
* **Email:** ativshav25@gmail.com
* **LinkedIn:** https://www.linkedin.com/in/tivsha-sharma-3558b72ba/
