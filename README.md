# Bitcoin Price Analysis & Forecasting using Time-Series Models

## Project Overview
This project analyzes historical Bitcoin (BTC-USD) daily price data to understand market behaviour, price dynamics, and volatility patterns. The study applies time-series techniques including stationarity testing, differencing, autocorrelation analysis, ARIMA, and SARIMA modelling to evaluate short-term forecasting performance.

## Objectives
- Analyze Bitcoin daily closing price behaviour  
- Examine stationarity characteristics  
- Apply differencing to stabilize the series  
- Study autocorrelation & partial autocorrelation patterns  
- Build ARIMA and SARIMA forecasting models  
- Evaluate residual diagnostics  
- Generate short-term price forecasts  

## Data Source
- **Asset:** Bitcoin (BTC-USD)  
- **Frequency:** Daily  
- **Period:** Jan 2020 – Jan 2026  
- **Data Provider:** Yahoo Finance (`yfinance`)  
- **Observations:** 2,222 daily records  

## Data Preprocessing
Steps performed:
- Downloaded BTC-USD daily data using `yfinance`
- Selected **closing prices**
- Handled missing values (`dropna`)
- Ensured chronological ordering

## Exploratory Analysis
Visualized:
- Bitcoin daily closing price trend  
- Histogram of closing prices  
**Observations:**
- Strong upward and downward price cycles  
- High volatility and large price swings  
- Right-skewed price distribution  

## Stationarity Testing
### Augmented Dickey-Fuller (ADF) Test
- **Original Series:**
  - ADF Statistic: -1.24  
  - p-value: 0.65  
Series **non-stationary**

### First-Order Differencing
Applied differencing:
\[
P_t - P_{t-1}
\]
- **Differenced Series:**
  - ADF Statistic: -12.57  
  - p-value: ~0.000  
Series became **stationary**

## Autocorrelation Analysis
Analyzed:
- ACF (Autocorrelation Function)  
- PACF (Partial Autocorrelation Function)  
Purpose:
- Identify lag dependencies  
- Support ARIMA parameter selection  

## Time-Series Modelling
### ARIMA Model
- **Specification:** ARIMA(1,1,0)  
- Captured short-term autoregressive behaviour  

### SARIMA Model
- **Specification:** SARIMA(1,1,0)(1,1,1,7)  
- Incorporated weekly seasonality  

## Model Diagnostics
Performed residual analysis:
- Residual plots  
- Ljung–Box test  
- Jarque–Bera test  
- ARCH test  

### Ljung–Box Test
- p-value ≈ 0.51  
No strong autocorrelation in residuals

### Jarque–Bera Test
- p-value ≈ 0.00  
Residuals not normally distributed

### ARCH Test
- p-value ≈ 0.00  
Presence of heteroskedasticity (volatility clustering)

## Forecasting
Generated:
- **Next 30-day Bitcoin price forecast**
Visualized:
- Observed vs Forecasted prices  

## Tools & Technologies
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Statsmodels  
- yFinance API  
- Google Colab  

## Key Insights
- Bitcoin closing prices are **non-stationary**
- Differencing stabilizes the time-series
- ARIMA/SARIMA models capture trend structure
- Residual diagnostics indicate **volatility clustering**
- Forecasting reflects short-term price behaviour patterns

## Future Enhancements
- GARCH volatility modelling  
- Advanced ML forecasting models  
- Multivariate crypto market analysis  
- Real-time price tracking dashboard  

## Project Link
**Google Colab Notebook:**  [Open notebook](https://colab.research.google.com/drive/1J9tx-4n3U7NrgyxyQSWkcTsdzNxzO3HH?usp=sharing#scrollTo=JWYjNBJjiNO6)

## Author
**Tivsha Sharma**  
Applied Statistics | Data Analytics | Time-Series & Forecasting
