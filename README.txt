CAPSTONE PROJECT README
Title: Number of Trips in Cook County, IL
Date of Data: 2019-01-01 until 2023-06-03
Analysis: Time Series
Model: ARIMA and SARIMAX

INTRO:

This README is a guide to use Time Series Analysis to create a model and forecast it's future predictions.

DATASET:

https://www.kaggle.com/datasets/adelanseur/trips-by-distance

SUMMARY:

This jupyter notebook was presented to be simple, showing step-by-step method to help understand the process in data extraction, cleaning, visualization, EDA, transformation, modelling and forecasting. 
Each analysis has it's explanation and it's way around to help other users to understand as well.

METHODOLOGY:

1. Read the csv file into a dataframe.
2. Get to know the dataset, use .head, .info, .describe and .columns.
3. Index the time and date. This is an important step for the whole project.
4. Check null values and understand where does that come from. In this dataset, it presented the sum of trips of county level to state level, leaving county data empty. Hence it's safe to remove null values and ensure it doesn't disrupt the quality of the data. 
5. Visualizations. 
At this point, I decided to focus on 1 county (Cook County in IL).
6. Plot the dataset in time series.
7. Check stationarity using ADF test. 
8. Since data is non stationary, I tried multiple transformation methods (differencing, log, sqrt, cbrt) and different combinations. Choose the one with lowest p-value and proceed to build the model. 
9. I choose ARIMA model because it is common and differencing shows better result. In the beginning, I used parameter p=1, d=1 and q =1. Later I ran hyperparameters for loop to look for best combinations p=6, d=1, q=7.
10. Train and test the data. I split 75% train and 25% test. Run the model, fit and make predictions.
11. Evaluate the model by overlap the predictions on test data and compare the performance by checking the RMSE. 
12. If RMSE looks good, proceed with forecasting using the same model and parameters. Always check the RMSE making sure it's low.
13. Compare with SARIMAX model due to seasonality factor in the dataset. I use the same parameters, in addition to seasonal parameter = 28 (cycle of 1 month). Overlap the predictions on test data and check the RMSE. 
14. Since RMSE is low, proceed with SARIMAX forecast and also check its RMSE.

WORKAROUND:

1. Initially, I used differencing method to proceed with modelling and forecasting. However, both modelling and forecasting gives very high RMSE, I went back to step 8, using log dataset and then differencing. Then I continue until step 14, with new hyperparameters p =5, d=1 and q=5.
2. I am satisfied with the new RMSE (around 0.062) and consider this model as good.

FINDINGS:

REFERENCES:



