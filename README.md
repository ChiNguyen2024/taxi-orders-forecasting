# Taxi Orders Forecasting

Time series forecasting model for predicting hourly taxi orders to optimize driver shift planning during peak hours.

## Data
- **Source:** taxi company internal data
- **Coverage:** airport orders, March — August 2018
- **Size:** ~26,000 records at hourly intervals
- **Features:** datetime, num_orders (target variable)

## Workflow
- Hourly resampling, rolling average analysis
- Time series decomposition: daily and weekly seasonality, trend, residuals
- Feature engineering: lag features (1–5 hours, 24 hours, 168 hours), rolling mean, calendar features (hour, day, day of week)
- Two models trained: Linear Regression and LightGBM
- Cross-validation with TimeSeriesSplit (5 folds)
- Final testing of the best model

## Key Findings
- **Final model:** Linear Regression, RMSE = 35.2 (threshold ≤ 48)
- **Daily seasonality:** order peak — evening (18:00–22:00), minimum — night (0:00–6:00)
- **Weekly seasonality:** drop at the start of the week, rise toward weekends
- **Trend:** steady order growth from March to August, accelerating in summer
- **Recommendation:** increase driver availability during evening hours and weekends; use the model for automated shift planning

## Tech Stack
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-lightgrey)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-lightgrey)
![LightGBM](https://img.shields.io/badge/LightGBM-lightgrey)
![Statsmodels](https://img.shields.io/badge/Statsmodels-lightgrey)
![Matplotlib](https://img.shields.io/badge/Matplotlib-lightgrey)

## Repository Structure
```
├── taxi_orders_forecasting.ipynb  # main notebook
└── README.md
```
