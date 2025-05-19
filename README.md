
# ⚡ Renewable Energy Forecasting using ARIMA and SARIMA

This project applies statistical time series models — ARIMA and SARIMA — to forecast renewable energy production (in MWh) over a 10-year period. Through preprocessing, transformation, and evaluation, SARIMA proved more effective, capturing subtle patterns and delivering more accurate predictions. This project demonstrates the importance of forecasting for energy optimization, grid stability, and sustainability.

---

## 📌 Project Objective

- Forecast monthly renewable energy output using historical data.
- Compare ARIMA and SARIMA for modeling seasonal and non-seasonal components.
- Provide insights that support better planning of energy resources.

---

## 📈 Dataset Overview

- **Observations**: 132 monthly entries (Jan 2010 – Dec 2020)
- **Frequency**: Monthly
- **Target Variable**: `Energy_Production_MWh`
- **Missing Values**: None
- **Outliers**: None
- **Seasonality Strength**: 2.32e-09 (minimal)

---

## 🧹 Data Preprocessing

- Reformatted dates to YYYY-MM-DD
- Log transformation and differencing to achieve stationarity
- Augmented Dickey-Fuller test confirmed non-stationarity (p=0.045), resolved after transformations
- Rolling statistics verified mean and variance stability
- Boxplots and visualizations showed no anomalies

---

## 🔍 ACF & PACF Analysis

- Used to determine `p`, `d`, `q` parameters for ARIMA
- ACF indicated moving average (MA) structure
- PACF indicated autoregressive (AR) structure
- Parameters selected via grid search

---

## 🧠 Model Selection

### ARIMA (p=0, d=2, q=3)
- AIC: 2024.63
- BIC: 2036.10
- RMSE: 531.49
- MAPE: 8.63%
- Residuals passed Ljung-Box test (p=0.721)

### SARIMA (2,1,2)(0,1,1)[12]
- AIC: 1883.11
- BIC: 1899.78
- RMSE: 522.18
- MAPE: 8.02%
- Selected as final model due to better performance and ability to capture weak seasonality

---

## 📊 Forecasting Results

- Forecasts closely matched actual test data
- Confidence intervals (80% & 95%) captured variability
- Visualization showed good alignment with real-world trends

---

## 🧪 Cross-Validation (Rolling-Origin)

- Training Window: 96 months
- Forecast Horizon: 12 months
- RMSE: 572.21
- MAE: 463.42
- MAPE: 9.49%
- Confirmed model’s consistency across time

---

## ✅ Key Takeaways

- Clean dataset with stable structure enabled reliable modeling
- Log transformation and differencing critical for achieving stationarity
- SARIMA outperformed ARIMA despite low seasonal strength
- Confidence intervals provided robust uncertainty estimation
- Rolling validation validated stability and reliability

---

## 🔮 Why SARIMA Outperformed ARIMA

- Captured subtle seasonal trends even with low seasonal strength
- Greater flexibility in handling repetitive patterns
- Lower AIC, BIC, RMSE, and MAPE confirmed improved predictive power
- Regularization via seasonal components reduced over/underfitting

---

## 🚀 Practical Applications

- 📊 Grid Stability: Anticipate energy variability to balance supply-demand
- ⚡ Resource Optimization: Plan energy storage based on forecasts
- 🌍 Sustainability: Support renewable energy adoption and planning

---

## 🌱 Future Work

- Explore Exponential Smoothing (ETS) or hybrid models
- Include external variables (e.g., temperature, weather)
- Build real-time dashboard or forecasting app for energy providers

---

## 📁 Repository Structure

```
├── README.md
├── renewable_energy_forecast.ipynb
├── dataset.csv
└── results/  # Plots, model metrics, validation reports
```

---

## 👤 Author

**Jani Shariff Shaik**  
MS Applied Statistics & Data Science, University of Texas at Arlington  
📧 shaikjanishariff@gmail.com

---

## 📝 Summary

This project demonstrates the value of statistical forecasting in renewable energy. Despite low seasonality, SARIMA provided more accurate and robust predictions. The methodology and results can inform real-world decision-making for energy stability and sustainability.

