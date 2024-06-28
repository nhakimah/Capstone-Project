CAPSTONE PROJECT README

Title: Trips in Cook County, IL
Date of Data: 2019-01-01 until 2023-06-03
Analysis: Time Series
Model: ARIMA and SARIMAX

INTRO:

This README is a guide to use Time Series Analysis to create a model and forecast it's future predictions specifically for Trip by Distance dataset.

PROJECT DESCRIPTION:

It is interesting to understand why Chicago becomes

DATASET:

https://www.kaggle.com/datasets/adelanseur/trips-by-distance.
Dataset is in csv file.

SUMMARY:

This project consists of 3 Jupyter Notebooks, Executive Summary & Final Report. 
The Notebooks were separated to :
	1. Data Visualization, 
	2. Data Transformation 
	3. Capstone Project_Final Analysiss. 

They were presented to be simple, showing step-by-step method to help understand the process in data extraction, cleaning, visualization, EDA, transformation, modelling and forecasting. 
Each analysis has it's explanation and it's way around to help other users to understand as well.

METHODOLOGY:

1. Download the dataset from Kaggle. Read the csv file into a dataframe.
2. Get to know the dataset, use .head, .info, .describe and .columns.
3. Index the time and date. This is an important step for the whole project.
4. Check null values and understand where does that come from. In this dataset, it presented the sum of trips of county level to state level, leaving county data empty. Hence it's safe to remove null values and ensure it doesn't disrupt the quality of the data. 
5. Visualizations. Chicago is in state of Illinois, USA. Even though the state rank number 5 in the total number of trips, but it ranks world second in congestion level.
6. Plot the dataset in time series.
7. Check stationarity using ADF test. 
8. Since data is non stationary, I tried multiple transformation methods (differencing, log, sqrt, cbrt) and different combinations. Choose the one with lowest p-value and proceed to build the model. 
9. Train and test the data. I split 75% train and 25% test. Run the model, fit and make predictions. 
10. I choose ARIMA model because it is common and differencing shows better result. In the beginning, I used parameter p=1, d=1 and q =1. Later I ran hyperparameters for loop to look for best combinations p=7, d=1, q=7.
11. Evaluate the model by overlapping the predictions on test data and compare the performance by checking the RMSE. 
12. If RMSE looks good, proceed with forecasting using the same model and parameters. Always check the RMSE making sure it's low.
13. Compare with SARIMAX model due to seasonality factor in the dataset. I use the same parameters, in addition to seasonal parameter = 52 (cycle of 1 year). Overlap the predictions on test data and check the RMSE. 
14. Since RMSE is low, and the trend looks more promising than ARIMA, I proceed with SARIMAX forecast and also check its RMSE.
15. Compare both results of ARIMA and SARIMAX. Visually, SARIMAX plot resembles the trend of original dataset than ARIMA. Given both RMSEs are low, I choose SARIMAX model and forecast as my final product.

WORKAROUND:

1. Initially, I used differencing method to proceed with modelling and forecasting. However, both modelling and forecasting gives very high RMSE, I went back to step 8, adding weekly resampling, then log and differencing the dataset. Furthermore, I continued until step 15, with new hyperparameters p =7, d=1 and q=7.
2. I am satisfied with the new RMSEs (less than 0.07) and consider this model as good.

FINDINGS:

SARIMAX Model gives much better clarity visually, backed up with low RMSEs.

REFERENCESS:

1. Trips by Distance (US). (2023, August 3). 	Kaggle. https://www.kaggle.com/datasets/adelanseur/trips-by-distance
2. Chandler-Wilde, H. (2023, January 10). Bloomberg - These are the 	world’s most congested cities. www.bloomberg.com. Retrieved 	May 31, 2024, 	from https://www.bloomberg.com/news/articles/2023-01-10/these-are-the-world-s-most-congested-cities
3. INRIX 2022 Global Traffic Scorecard: London Tops List as Most Congested City, U.S. 	Cities Inch Closer. (2023). In https://inrix.com. Retrieved May 25, 2024, 	from https://inrix.com/press-releases/2022-global-traffic-scorecard-uk/
4. Learnerea. (2022, December 8). Time Series Analysis using Python| ARIMA 	& SARIMAX Model Implementation | Stationarity Handling [Video]. 	YouTube. https://www.youtube.com/watch?v=O5pataOw33Y



