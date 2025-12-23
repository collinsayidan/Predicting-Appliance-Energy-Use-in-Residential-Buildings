# Predicting Appliance Energy Use in Residential Buildings

A Machine Learning Project by Collins Ayidan
-
This repository contains my MSc research project from the University of Stirling, focused on predicting appliance energy consumption using advanced feature engineering, visualization, and machine learning models.
The study uses the UCI Appliance Energy Prediction Dataset and evaluates multiple models to determine the best predictors of energy use in a residential setting.

# Project Overview
Residential energy consumption is a critical component of global energy use. By understanding and predicting appliance energy demand, we can support:

Smarter home‑energy management
Improved energy efficiency
Better resource planning

This project develops and compares eight machine‑learning models, optimized using HalvingRandomSearchCV, and enhanced through extensive feature engineering and exploratory data analysis (EDA).

# Repository Structure

## Energy-prediction

## data
- energydata.csv

## notebooks
- analysis.ipynb

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

## models
- best_model.pk1
- README.md

## Project Root
- README.md
- requirements.txt
## docs
- overview
- methodology
- results
- README.md

 # Methodology
- Data Preprocessing

Parsing and formatting timestamps
Cleaning and selecting relevant variables
Converting categorical values
Dropping irrelevant or redundant features

- Feature Engineering
Engineered variables include:
FeatureDescriptionNSMNumber of seconds from midnightWeekStatusWeekend vs WeekdayDay_of_weekMonday–SundaySeasonBased on monthHour_sin, Hour_cosCyclical encoding for 24‑hour periodicityMonth, Day, HourExtracted from timestamp
These were shown to improve predictive power significantly.

 ## Exploratory Data Analysis (EDA)
The notebook generates:
✔ Pair Plots (4 subsets)
Visualizing relationships between temperature, humidity, and environmental variables.
✔ Time‑Series Trends

## Full consumption profile
One‑week zoomed‑in view
✔ Histogram & Boxplot
Distribution and outlier detection for the target variable (Appliances).
✔ Weekly Heatmap
Hourly consumption (0–23h) across days of the week, for Week 3 of the dataset.
These graphics help uncover patterns in user behaviour and environmental influences.

## Models Implemented
### Eight models were evaluated:

Linear Regression |
Support Vector Regression (SVR) |
Decision Tree Regressor |
Random Forest Regressor |
Extra Trees Regressor |
Gradient Boosting Regressor |
XGBoost Regressor |
Neural Network (MLPRegressor)

## Hyperparameter Tuning
HalvingRandomSearchCV used for efficient optimization

## Evaluation Metrics
RMSE
MAE
R² Score
MAPE

## Key Findings
Top Performing Models:
ModelRMSER²Extra Trees63.280.60Random Forest65.510.57XGBoost64.360.57

##Underperforming
Linear Regression
Decision Tree

## Feature Importance
Highly influential:
NSM (time of day)
Hour
Temperature & humidity sensors

## Low influence:
Season
WeekStatus

### Future Work
Improve deep learning approaches (LSTM/CNN for time series)
Add socio‑demographic variables
Integrate real‑time IoT sensor feeds
Deploy prediction model via API or dashboard


## Acknowledgements
University of Stirling – MSc Mathematics & Data Science program |
UCI Machine Learning Repository |
Supervisors and contributors
