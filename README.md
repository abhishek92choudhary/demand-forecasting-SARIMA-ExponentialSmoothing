# Demand Forecasting | Time Series Analysis Pipeline

A structured, end-to-end time series forecasting pipeline for supply chain demand prediction, built as a capstone project for Industrial Engineering studies. The project compares classical statistical models — ARIMA, SARIMA, and Exponential Smoothing — using real-world revenue data.

---

## Project Overview

This project builds a reproducible forecasting pipeline that:

- Loads and preprocesses monthly time series data
- Decomposes the series into **trend**, **seasonality**, and **residuals**
- Tests for **stationarity** using the Augmented Dickey-Fuller (ADF) test
- Identifies model orders using **ACF** and **PACF** plots
- Benchmarks baseline models (MA, AR, ARMA, ARIMA)
- Performs a **SARIMA grid search** to find the optimal seasonal model
- Compares all models using standard forecast evaluation metrics

---

## Pipeline Sections

| Section | Description |
|---------|-------------|
| **1. Data Loading & EDA** | Load time series, visualize raw data and rolling statistics |
| **2. Stationarity Testing** | ADF test — checks if differencing is needed |
| **3. ACF / PACF Analysis** | Identifies AR order `p` and MA order `q` |
| **4. Baseline Models** | Fits MA, AR, ARMA, ARIMA variants; compares AIC scores |
| **5. SARIMA Grid Search** | Exhaustive search over `(p,d,q)(P,D,Q)[12]` combinations |
| **6. Best SARIMA Model** | Fits and evaluates the optimal SARIMA configuration |
| **7. Exponential Smoothing** | Fits Holt-Winters model as an alternative approach |
| **8. Model Comparison** | Evaluates all models on the test set using RMSE, MAE, MAPE |

---

## ACF and PACF plot

<img width="1389" height="390" alt="ACF_PACF" src="https://github.com/user-attachments/assets/93b68993-1829-438f-a533-1a711b6d2f88" />


## Models Compared

| Model | Type | Notes |
|-------|------|-------|
| `MA(0,0,1)` | Moving Average | Baseline |
| `AR(1,0,0)` | Autoregressive | Baseline |
| `ARMA(1,0,1)` | Mixed | Baseline |
| `ARIMA(1,1,1)` | Integrated | Best baseline (AIC: 518.75) |
| `SARIMA(0,1,0)(0,1,0)[12]` | Seasonal | Best from grid search (AIC: 182.546) |
| Holt-Winters | Exponential Smoothing | Seasonal triple smoothing |

---

## SARIMA Forecast

<img width="1389" height="490" alt="SARIMA" src="https://github.com/user-attachments/assets/54d516f2-9cf1-4c72-9762-3605747df1fc" />


---

## Exponential Smoothing Forecast

<img width="1389" height="490" alt="Exponential_Smoothing" src="https://github.com/user-attachments/assets/73bd6ccd-592a-41a8-bafe-6e0aaf996655" />


## Evaluation Metrics

| Metric | Description |
|--------|-------------|
| **RMSE** | Root Mean Squared Error — penalizes large errors |
| **MAE** | Mean Absolute Error — average forecast deviation |
| **MAPE** | Mean Absolute Percentage Error — scale-independent accuracy |
| **AIC** | Akaike Information Criterion — used for model selection during training |

---

## Skills & Concepts Applied

- Time Series Decomposition (Additive / Multiplicative)
- Stationarity Testing (ADF Test)
- ACF & PACF for order identification
- ARIMA & SARIMA modeling (`statsmodels`)
- Grid search for hyperparameter tuning
- Holt-Winters Exponential Smoothing
- Model evaluation on a held-out test set

---

## Author

**Abhishek Choudhary**  
Master's in Industrial Engineering Student | Supply Chain & Logistics  

