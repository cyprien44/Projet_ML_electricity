 Predicting Intraday vs SPOT Electricity Price Spread – Elmy Challenge (ENS)
📌 Context
This project was developed as part of the ENS Challenge – Elmy which aims to support Elmy’s electricity trading activities on the SPOT and Intraday markets.

🎯 Objective
To build a supervised learning model to predict the direction of the price spread between:

the SPOT market (day-ahead auctions), and

the Intraday market (same-day continuous trading).

The task can be approached as:

a regression problem (predicting the spread),

or a classification problem (predicting the sign of the spread).

The key goal is to correctly forecast whether Intraday prices will be higher or lower than SPOT prices.

🧪 Dataset
📁 Files Provided:
X_train.csv: Features for training

y_train.csv: Target values (Intraday – SPOT) for training

X_test.csv: Features for testing

y_random.csv: Randomized control targets

⏱️ Index
DELIVERY_START: Delivery timestamp (date & hour)

🔍 Features
Demand forecast:
load_forecast – forecasted electricity demand in France

Available generation capacity:

coal_power_available

gas_power_available

nucelear_power_available

Renewable production forecasts:

wind_power_forecasts_average, wind_power_forecasts_std

solar_power_forecasts_average, solar_power_forecasts_std

Internal forecast:
predicted_spot_price – SPOT price forecast by Elmy’s internal model

🎯 Target Variable
spot_id_delta = Intraday – SPOT

If positive → Intraday > SPOT

If negative → Intraday < SPOT

⚙️ Benchmark
A simple benchmark assumes that Intraday prices are always higher than SPOT prices (i.e. always predicting a positive spread).
Historically, this assumption holds more often than not.

📊 Evaluation Metric
The performance is evaluated using Weighted Accuracy:

The proportion of predictions with correct sign (positive or negative), weighted by the absolute value of the actual spread.

This emphasizes correct predictions on large spreads.

🛠️ Tools & Libraries
python
Copier
Modifier
import os
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
📂 Project Structure (so far)
Data loading: CSVs from datas/ directory

Exploratory Data Analysis (EDA): visualizing the distribution of features and target

Preprocessing & Feature Engineering: to be added

Modeling: regression and/or classification models

Evaluation: via custom Weighted Accuracy metric

