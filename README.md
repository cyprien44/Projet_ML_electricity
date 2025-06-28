# 🔌 Predicting Intraday vs SPOT Electricity Price Spread – Elmy Challenge (ENS)

## 📌 Context

This project was developed as part of the [ENS Challenge – Elmy](https://challengedata.ens.fr/participants/challenges/140/), aiming to support Elmy in optimizing electricity trading on the SPOT and Intraday markets.

## 🎯 Objective

The goal is to build a supervised model to predict whether **Intraday electricity prices** will be **higher or lower than SPOT prices**.

This task can be approached in two ways:
- **Regression**: Predict the numerical price spread
- **Classification**: Predict only the direction (positive or negative)

The key metric is not just accuracy but the ability to **correctly predict the direction**, especially for large spreads.

## 🧪 Dataset

### 📁 Files
- `X_train.csv`: Training features
- `y_train.csv`: Training target (Intraday - SPOT)
- `X_test.csv`: Test features
- `y_random.csv`: Control targets

### ⏱️ Index
- `DELIVERY_START`: Timestamp for electricity delivery

### 🔍 Features
- `load_forecast`: Forecasted electricity demand in France  
- `coal_power_available`, `gas_power_available`, `nucelear_power_available`: Available capacity by energy source  
- `wind_power_forecasts_average`, `solar_power_forecasts_average`: Mean forecast for wind/solar production  
- `wind_power_forecasts_std`, `solar_power_forecasts_std`: Std deviation of wind/solar forecasts  
- `predicted_spot_p
