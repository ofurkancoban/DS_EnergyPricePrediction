# German Energy Price Prediction (2020-2026)

This repository contains a comprehensive Data Science project for the University of Oldenburg (Winter 2025/2026) focused on forecasting hourly Day-Ahead electricity prices in the German market. The project integrates automated ETL pipelines, exploratory data analysis (EDA), and advanced machine learning models to capture the dynamics of the European energy grid.

## Project Overview
The objective is to model and predict energy prices by accounting for the Merit Order Effect - the mechanism where low-marginal-cost renewable energy (Wind/Solar) displaces expensive thermal generation (Gas/Coal/Lignite).

### Key Features
- Automated ETL: Real-time data fetching from SMARD, Open-Meteo, and Yahoo Finance.
- Geographic Weather Clustering: Using 5 strategic clusters (Hamburg, Helgoland, Munich, Berlin, Cologne) to proxy national generation and demand.
- Statistical and ML Modeling: Comparison between classical ARIMAX, Linear Ridge Regression, and non-linear XGBoost models.
- Time-Series Engineering: Implementation of 24h and 168h lags to capture diurnal and weekly cycles.

---

## Tech Stack
- Data Handling: Pandas, NumPy
- Visualization: Matplotlib, Seaborn
- APIs: requests, yfinance, openmeteo-requests
- Modeling: Scikit-Learn, XGBoost, Statsmodels

---

## Project Structure

### 1. Phase 1: Data Engineering (ETL)
The pipeline (fetch_smard_data, fetch_weather_clusters, fetch_commodity_data) pulls data from 2020 to Jan 2026:
- SMARD: Market prices, grid load, and generation by fuel type.
- Open-Meteo: Hourly weather for strategic German regions.
- Yahoo Finance: Commodity benchmarks (Natural Gas TTF, Carbon EUA, Rotterdam Coal).

### 2. Phase 2: Exploratory Data Analysis (EDA)
- Missing Value Analysis: Handling gaps from API downtime or Daylight Savings.
- Market Dynamics: Visualizing the correlation between net_load and price spikes.
- Seasonality: Analysis of daily and weekly patterns.

### 3. Phase 3: Modeling
- Ridge Regression: Linear baseline to establish fundamental market trends.
- ARIMAX(2,0,1): Statistical time-series model incorporating exogenous variables like net load and wind generation.
- XGBoost: Advanced Gradient Boosting model to capture non-linearities and the "step-function" nature of the Merit Order curve.

---

## Getting Started

### Installation
Ensure you have the required dependencies:
```bash
pip install pandas numpy matplotlib seaborn xgboost statsmodels yfinance openmeteo-requests requests-cache retry-requests
```

### Main Files
- 2025_ds1_project_report_coban.ipynb: The consolidated project report, containing the ETL pipeline, EDA, and model benchmarking.
- automated_germany_energy_data.csv: The dataset used for modeling (automatically generated/refreshed by the notebook).

---

## Course Information
- University: University of Oldenburg
- Course: Data Science I (Winter Semester 2025/2026)
- Author: Furkan Çoban

## License
This project is developed for academic purposes at the University of Oldenburg.
