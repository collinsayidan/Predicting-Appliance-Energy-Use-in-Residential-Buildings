# Predicting Appliance Energy Use in Residential Buildings
A Machine Learning Approach to Residential Energy Forecasting
Author: Collins Ayidan
Program: MSc Mathematics & Data Science, University of Stirling

## Overview
This project applies machine learning techniques to predict appliance energy consumption in residential buildings using the widely‑studied UCI Appliance Energy Prediction Dataset.
It explores feature engineering, evaluates eight machine learning models, and identifies the most effective model based on RMSE, MAE, R², and MAPE.
This work was originally completed as my Research Project for the MSc program and has been refined for open‑source publication.

## Objectives

- Build and compare multiple machine‑learning models for energy‑use prediction.
- Engineer temporal, seasonal, and environmental features for performance improvement.
- Optimize hyperparameters using HalvingRandomSearchCV.
- Identify the best‑performing algorithm and key drivers of energy consumption.

## Dataset
### Source: UCI Machine Learning Repository — Appliance Energy Prediction Dataset
The dataset includes:
- Indoor and outdoor temperature & humidity
- Weather conditions (windspeed, pressure, Tdewpoint, etc.)
- Timestamp (date, time)
- Appliance energy consumption readings (target variable)

## Methods & Techniques
1. Data Preprocessing
- Date formatting
- Handling missing values
- Standardization (for models requiring scaling)

2. Feature Engineering
Engineered features include:
- NSM (Number of Seconds from Midnight)
- Weekday/Weekend classification
- Day of Week (categorical)
- Hour, Month, Day
- Season (Winter/Spring/Summer/Autumn)
 
Cyclical encoding for Hour:
Hour_sin = sin(2π * Hour / 24)
Hour_cos = cos(2π * Hour / 24)

3. Models Evaluated
- Linear Regression
- Support Vector Regression (SVR)
- Decision Tree Regressor
- Random Forest Regressor
- Extra Trees Regressor
- Gradient Boosting Regressor
- XGBoost Regressor
- Neural Network (MLPRegressor)
  
4. Hyperparameter Tuning
Successive Halving via HalvingRandomSearchCV

5. Evaluation Metrics
- RMSE (Root Mean Square Error)
- MAE (Mean Absolute Error)
- R² Score
- MAPE (Mean Absolute Percentage Error)

## Key Results
Top Performing Models

| Model         | RMSE  | R²   | Notes          |
|---------------|-------|------|----------------|
| Extra Trees   | 63.28 | 0.60 | Best performer |
| Random Forest | 65.51 | 0.57 | Strong, stable |
| XGBoost       | 64.36 | 0.57 | Competitive    |

## Underperforming Models
- Decision Tree
- Linear Regression

## Feature Importance (Extra Trees)
Most influential predictors:
- NSM (time of day)
- Hour of the day
- Environmental conditions (temperature, humidity)

## Least influential:
- Season
- WeekStatus

## Conclusion
- Extra Trees Regressor delivered the best predictive performance.
- Time‑based features (NSM, Hour) were highly influential, demonstrating strong temporal patterns in appliance energy use.
- Environmental data also played a major role.

## Future Work

- Improve performance of SVR and Neural Networks
- Integrate socio‑demographic and behavioural data
- Incorporate real‑time sensor streams for smart‑home applications
- Explore deep learning (LSTM, Temporal CNN)

# Repo Structure
## Energy-prediction

## data
- energydata_complete.csv

## src
- preprocessing.py
- eda.py
- modeling.py
- utils.py

## outputs
- pairplot_1.png
- pairplot_2.png
- pairplot_3.png
- pairplot_4.png
- appliances_trend.png
- histogram_boxplot.png
- heatmap_week3.png
- model_results.csv

## notebooks
- analysis.ipynb

## Project Root
- README.md
- requirements.txt

## Acknowledgements
University of Stirling – MSc Mathematics & Data Science program |
UCI Machine Learning Repository |
Supervisors and contributors
