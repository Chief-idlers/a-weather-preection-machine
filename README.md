# a-weather-prediction-machine
The notebook provides a step-by-step process for analysis of historical weather data and training a machine learning model to predict daily maximum temperature. The notebook incorporates data collection, cleaning, feature engineering, training the model, evaluation, and visualization, with a focus on time-series forecasting. The notebook provides a complete process for analyzing and predicting weather data through the assistance of machine learning algorithms. The description of the key components is provided below:

Data Collection Instructions for retrieving past weather data from NOAA's Climate Data Online website

Recommends starting with data from 1970 for robust analysis

Provides guidance for selecting weather stations (airports preferred) and downloading CSV format

Data Processing Initial Setup:

Imports necessary libraries (pandas, numpy, scikit-learn, matplotlib)

Loads weather data with DATE column as datetime index

Data Cleaning:

Selects primary weather measures (precipitation, temperature, wind speed, fog)

Handles missing values:

Precipitation filled with 0 (assuming no rain)

Interpolated wind speed and temperature

Fog with 0 (assuming no fog)

Drops snow columns due to Oakland having low variability

Feature Engineering:

Creates range of temperature (max - min)

Appends rolling 7-day mean temp

Appends month and day-of-year means

Appends cyclical date features w/ sin/cos transformations

Creates target variable (max temperature for tomorrow)

Modeling Utilizes Random Forest Regressor for prediction

Utilizes time-series cross-validation (TimeSeriesSplit) for robust evaluation

Calculates Mean Absolute Error (MAE) as primary metric

Appends feature importance analysis

Visualizes actual vs predicted temperatures

Results Analysis Analyzes prediction errors (absolute differences)

Identifies top 10 worst predictions

Shows correlation between predictors and target

Visualization Visualize actual vs predicted temperatures over time

Next Steps Recommended Multi-day forecasting (week-ahead forecasts)

With regional weather station data

Experimenting with advanced models (XGBoost, LSTM)

With additional derived features

Hyperparameter tuning

Seasonal error analysis

This notebook provides an end-to-end flow from data acquisition to prediction modeling, taking special care of how time-series weather data needs to be handled. The method can be quite readily adapted for other places by modifying the source data.


