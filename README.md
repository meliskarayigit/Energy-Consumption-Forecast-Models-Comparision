# Energy-Consumption-Forecast-Models-Comparision
DAYTON Hourly Electricity Load Forecasting
This project focuses on forecasting hourly electricity demand using the DAYTON dataset. It includes time series preprocessing, feature engineering, statistical testing, and a comparison of multiple models including ARIMA, Holt-Winters, Random Forest, and LSTM.
Dataset
File: DAYTON_hourly.csv

Target Variable: DAYTON_MW (Electric Load in Megawatts)

Time Range: Hourly intervals with timestamps (Datetime column)

 Project Steps
1. Data Preprocessing
-Converted Datetime column to datetime format
-Filled missing hourly timestamps using interpolation
-Detected and clipped outliers using the IQR method

2.  Feature Engineering
-Time-based features: hour, weekday, is_weekend
-Lag features: lag_1, lag_24, lag_168
-Rolling and Exponential Weighted Means: rolling_24h, rolling_168h, ewm_24h

3. Exploratory Data Analysis
-Boxplots, time series plots, hourly/weekly trends
-Correlation heatmaps and scatter plots
-ADF stationarity test, ACF & PACF analysis

Models Used
1. SARIMA
Captures trend and seasonality

Parameters: order=(1,1,1), seasonal_order=(1,1,1,24)

2. Holt-Winters Exponential Smoothing
Seasonal + trend ETS model

3. Random Forest Regressor
Trained using lag and calendar features

4. LSTM (Long Short-Term Memory)
Deep learning-based recurrent model for sequential data

-Used 24-step sequences with a single LSTM layer

Model Performance (MAPE)
Model	MAPE Score
-SARIMA	0.8591
-Holt-Winters	1.6392
-Random Forest	0.0152
-LSTM	0.1442

-Random Forest achieved the best accuracy
-Holt-Winters performed the worst under these settings
-SARIMA and LSTM showed potential but may benefit from parameter tuning

Residual Diagnostics
Residual plots were generated for all models

Histogram and ACF analysis confirmed low autocorrelation for best-performing models

Mean residuals were close to zero for Random Forest and LSTM

Multicollinearity Check (VIF Analysis)
-Features with VIF > 5 were removed iteratively
-Remaining features showed low multicollinearity, ensuring better model interpretability

