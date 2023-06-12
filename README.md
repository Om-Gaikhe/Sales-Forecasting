# Sales Forecasting: Using Prophet and LSTM Models

## Introduction

This repository focuses on forecasting sales performance using two models: the Prophet and Long Short-Term Memory (LSTM) models. The original data, formatted in wide format with each month as a separate column, is reshaped into long format with each row representing a single time-based observation.

## Assumptions

### Prophet Model
1. Assumes the time series data is composed of trends, seasonality, and holiday effects that can be modeled separately.
2. The average monthly performance can represent the overall sales trend.

### LSTM Model
1. Assumes there's a temporal dependence between time steps which is a reasonable assumption in sales data context.
2. Assumes that the past 10 data points are useful for predicting the next data point.

## Workflow

1. **Data Loading & Cleaning:** The data is loaded and cleaned by dropping unnecessary columns and missing values.
2. **Data Transformation:** Transform the data from wide to long format and convert the performance metric to a floating-point number.
3. **Prophet Model:** Initialize and fit the model to the data, forecast for the next two years.
4. **LSTM Model:** Construct and train the model on the reshaped and normalized dataset, make predictions for the test set.

## Implementation Steps

1. **Data Exploration:** Load the data and check the head, tail, and missing values.
2. **Data Cleaning:** Drop unnecessary columns and rows.
3. **Data Preparation for Modelling:** Melt data into long format and convert data types as necessary.
4. **Prophet Model Building & Evaluation:** Fit the model, make predictions, plot results, and evaluate the model performance using MAE, MSE, and RMSE.
5. **LSTM Model Building & Evaluation:** Normalize the data, split into training and testing sets, reshape the data, create the LSTM model, fit the model, make predictions, evaluate model performance, and plot the results.

## Results

The performance of the Prophet and LSTM models on the forecasting task is evaluated using error metrics.

1. **Prophet Model Performance:** 
    - Mean Absolute Error (MAE): 0.4382
    - Mean Squared Error (MSE): 0.2445
    - Root Mean Squared Error (RMSE): 0.4945
    
    These metrics indicate that the Prophet model's predictions were on average around 0.44 units away from the actual values, and the square root of the average squared differences between the predicted and actual values was approximately 0.49.

2. **LSTM Model Performance:**
    - Training set RMSE: 0.15
    - Test set RMSE: 0.67
    
    The discrepancy between the LSTM model's performance on the training and test sets suggests potential overfitting. The model performed well on the training data with a lower error rate but performed worse on the unseen test data.

In conclusion, while the LSTM model shows overfitting, the Prophet model demonstrates a more balanced performance between the training and testing sets.
