# Crop Yield Estimation Using Time Series Models

## Overview

Agriculture is heavily influenced by environmental factors such as rainfall, temperature, and water availability. Accurate crop yield forecasting is essential for agricultural planning, food security, resource allocation, and policy formulation.

This project develops a crop yield forecasting framework using **ARIMAX (Auto-Regressive Integrated Moving Average with Exogenous Variables)** models. The framework incorporates climatic and hydrological variables to improve prediction accuracy across multiple crops and Indian states.

The study analyzes historical agricultural data spanning more than two decades and demonstrates how time series models can be used to generate reliable yield forecasts for data-driven agricultural decision-making.

---

## Problem Statement

Crop yields are affected by numerous environmental and climatic factors. Traditional forecasting approaches often fail to capture these external influences effectively.

This project aims to:

- Forecast crop yields using historical agricultural data.
- Incorporate climatic and hydrological variables as external predictors.
- Evaluate the effectiveness of ARIMAX models across different crops and regions.
- Develop a scalable forecasting pipeline that can be extended to other agricultural datasets.

---

## Dataset Description

The dataset contains crop yield observations collected across multiple Indian states over a period of approximately 24 years.

### Crops Included

- Gram
- Wheat
- Mustard
- Masoor
- Potato
- Rabi Rice

### Exogenous Variables

- Rainfall
- Minimum Temperature
- Maximum Temperature
- Reservoir Storage Levels

The data was analyzed on a weekly basis to capture seasonal and temporal variations in crop production.

---

## Objectives

- Perform exploratory data analysis on agricultural time series data.
- Identify trends and stationarity properties.
- Develop ARIMAX forecasting models.
- Assess the impact of environmental variables on crop yields.
- Evaluate forecasting performance using standard metrics.
- Create a generalized forecasting framework applicable across crops and states.

---

## Methodology

### 1. Data Preprocessing

The raw dataset required extensive preprocessing before modeling.

#### Steps Performed

- Missing value treatment
- Outlier handling
- Chronological sorting
- Data cleaning
- Temporal filtering
- Train-test splitting

The final dataset was divided into training and testing periods while preserving temporal ordering.

---

### 2. Exploratory Data Analysis

To understand the statistical characteristics of the data, several analyses were performed.

#### Trend Analysis

Historical yield trends were visualized for each crop-state combination.

#### Stationarity Testing

Time series stationarity was examined using:

- Augmented Dickey-Fuller (ADF) Test
- KPSS Test

Differencing was applied whenever non-stationarity was detected.

---

### 3. Time Series Modeling

The primary forecasting framework used was:

## ARIMAX

Auto-Regressive Integrated Moving Average with Exogenous Variables

The model combines:

- Autoregressive terms (AR)
- Differencing (I)
- Moving Average terms (MA)
- External variables (X)

This allows the model to capture both temporal dependencies and environmental influences.

---

### 4. Parameter Selection

The optimal values of:

- p (Autoregressive Order)
- d (Differencing Order)
- q (Moving Average Order)

were selected using:

- ACF Plots
- PACF Plots
- AIC Scores
- BIC Scores

A grid search procedure was used to identify the best model specification.

---

### 5. Feature Selection

The significance of climatic variables was evaluated using statistical tests.

Variables with insignificant contributions were candidates for removal.

The final models retained only meaningful predictors.

---

### 6. Forecast Generation

The trained ARIMAX models were used to forecast crop yields for the most recent years.

Predictions were generated separately for each crop-state combination.

---

## Evaluation Metrics

Model performance was assessed using:

### Mean Absolute Error (MAE)

Measures average prediction error.

\[
MAE=\frac{1}{n}\sum |y_i-\hat{y_i}|
\]

---

### Root Mean Squared Error (RMSE)

Measures the magnitude of forecasting deviations.

\[
RMSE=\sqrt{\frac{1}{n}\sum (y_i-\hat{y_i})^2}
\]

---

### Mean Absolute Percentage Error (MAPE)

Measures forecasting accuracy in percentage terms.

\[
MAPE=\frac{100}{n}\sum\left|\frac{y_i-\hat{y_i}}{y_i}\right|
\]

---

## Project Workflow

```text
Raw Dataset
     │
     ▼
Data Cleaning
     │
     ▼
Exploratory Data Analysis
     │
     ▼
ADF & KPSS Testing
     │
     ▼
Differencing
     │
     ▼
ACF / PACF Analysis
     │
     ▼
ARIMAX Model Selection
     │
     ▼
Training
     │
     ▼
Forecasting
     │
     ▼
Performance Evaluation
```

---

## Results

The ARIMAX framework successfully captured both temporal patterns and environmental influences on crop yields.

### Key Findings

- Climatic variables significantly improved forecasting performance.
- Several crop-state combinations achieved low forecasting errors.
- Stable crop series required only simple ARIMAX structures.
- Highly volatile crop series required higher-order differencing.
- Environmental predictors played a significant role in yield estimation.

### Best Performing Models

#### Gram Yield – Uttarakhand

- Model: ARIMAX(0,1,0)
- MAE: 0.0404
- RMSE: 0.0607

#### Mustard Yield – Tamil Nadu

- Model: ARIMAX(0,1,0)
- MAE: 0.0175
- RMSE: 0.0249

#### Wheat Yield – West Bengal

- Model: ARIMAX(0,4,0)
- MAE: 0.0647
- RMSE: 0.0693

These results demonstrate the effectiveness of ARIMAX models for agricultural forecasting when combined with relevant environmental variables.

---

## Visualizations

The project includes:

- Time series plots
- Yield trend analysis
- Actual vs Predicted comparisons
- ACF plots
- PACF plots
- State-wise forecasting dashboards
- Environmental variable impact analysis

Interactive dashboards were developed using Power BI to facilitate exploration of crop yield patterns.

---

## Technology Stack

### Programming Language

- Python

### Libraries

- Pandas
- NumPy
- Statsmodels
- Scikit-Learn
- Matplotlib
- Seaborn

### Visualization

- Power BI

---

## Applications

This forecasting framework can be applied to:

- Agricultural Planning
- Food Security Management
- Crop Production Forecasting
- Climate Impact Assessment
- Government Policy Formulation
- Resource Allocation
- Precision Agriculture

---

## Future Improvements

Potential enhancements include:

- Seasonal ARIMAX (SARIMAX)
- Deep Learning Models (LSTM, GRU)
- Ensemble Forecasting Methods
- Satellite Data Integration
- Soil Quality Indicators
- Real-Time Yield Prediction Systems
- Weather Forecast Integration

---

## Learning Outcomes

This project provided practical experience in:

- Time Series Analysis
- ARIMA and ARIMAX Modeling
- Forecasting Techniques
- Statistical Testing
- Feature Engineering
- Agricultural Analytics
- Data Visualization
- Model Evaluation

---



## Conclusion

This project demonstrates how ARIMAX models can be effectively used to forecast crop yields by incorporating environmental and climatic variables. The proposed framework provides an interpretable, scalable, and data-driven approach for agricultural forecasting and decision support.

The results highlight the importance of combining time series techniques with domain-specific exogenous variables to improve forecasting performance across diverse agricultural regions.
