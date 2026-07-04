
# Climate Time-Series Forecasting using Statistical, Machine Learning and Deep Learning Models

This repository contains the programs and experiments completed as part of the **Computational Simulation Lab**. The project focuses on climate data analysis and forecasting using statistical time-series models, machine learning models, and deep learning models.

The experiments were mainly performed on climate datasets such as **ERA5 Sea Surface Temperature (SST)** data and **NOAA Niño 3.4 index data**. The objective was to understand temporal climate patterns, perform forecasting, compare model performance, and visualize the relationship between ENSO and sea surface temperature.

---

## Project Overview

Climate systems show strong temporal and seasonal patterns. In this project, different forecasting and regression-based models were implemented to analyze climate indices and sea surface temperature variations.

The project includes:

- Time-series forecasting of SST and Niño 3.4 index
- Stationarity testing using ADF test
- Train-test based forecasting
- ENSO and SST relationship analysis
- Spatial regression mapping
- Seasonal influence analysis
- Deep learning based sequence prediction
- Model evaluation using error metrics

---

## Datasets Used

The following datasets were used in this project:

### 1. ERA5 Sea Surface Temperature Dataset

ERA5 monthly sea surface temperature data was used for SST forecasting and spatial climate analysis.

The SST data was processed by calculating the spatial mean over latitude and longitude. Kelvin values were converted into Celsius where required.

### 2. NOAA Niño 3.4 Index Dataset

The Niño 3.4 index dataset was used for ENSO time-series forecasting. The dataset contains monthly Niño 3.4 values and was used for ANN, RNN, LSTM, CNN, SVM, Polynomial Regression, and Random Forest models.

### 3. NOAA DMI Dataset

The Dipole Mode Index, DMI, dataset was also considered as part of the climate index analysis.

---

## Models Implemented

The following models were implemented in this lab:

### Statistical Time-Series Models

1. **ARIMA**
   - Applied on ERA5 monthly SST data.
   - ADF test was used to check stationarity.
   - Differencing order was selected based on the p-value.
   - Forecasting was performed on the test period.

2. **SARIMA**
   - Applied on ERA5 monthly SST data.
   - Seasonal order was used to capture monthly seasonality.
   - A seasonal period of 12 was used for monthly climate data.

---

### Regression Models

3. **Linear Regression**
   - Used to study the relationship between Niño 3.4 index and SST.
   - Regression slope, intercept, and R² score were calculated.
   - Seasonal spatial regression maps were generated for DJF, MAM, JJA, and SON seasons.

4. **Polynomial Regression**
   - Used lag features from ENSO data.
   - Polynomial features were generated to capture nonlinear patterns.
   - Regression output was also converted into ENSO event classes:
     - La Niña
     - Neutral
     - El Niño

---

### Deep Learning Models

5. **Artificial Neural Network, ANN**
   - Used for Niño 3.4 time-series prediction.
   - Previous 12 months were used as input features.
   - Dense layers were used for regression-based forecasting.

6. **Long Short-Term Memory, LSTM**
   - Used for sequential prediction of Niño 3.4 index.
   - Input sequence length of 12 months was used.
   - LSTM was used to capture long-term temporal dependencies.

7. **Recurrent Neural Network, RNN**
   - Used for Niño 3.4 sequence prediction.
   - Simple RNN layers were used for time-series forecasting.

8. **Convolutional Neural Network, CNN**
   - A 1D CNN model was used for time-series prediction.
   - Conv1D layers were used to extract local temporal patterns from monthly climate sequences.

---

### Machine Learning Models

9. **Support Vector Machine, SVM**
   - Support Vector Regression, SVR, was used for Niño 3.4 forecasting.
   - RBF kernel was used to capture nonlinear relationships.

10. **Random Forest**
   - Random Forest Regressor was used for ENSO index forecasting.
   - Lag-based features were created from past Niño 3.4 values.

---

## Methodology

The general workflow followed in this project is:

1. Load climate dataset
2. Preprocess data
3. Convert data into time-series format
4. Normalize values where required
5. Create lag-based or sequence-based features
6. Split data into training and testing sets
7. Train the model
8. Generate predictions
9. Evaluate model performance
10. Visualize actual vs predicted values

For spatial regression analysis, the workflow included:

1. Load ERA5 SST data
2. Load Niño 3.4 ENSO index data
3. Match the time dimensions
4. Separate data season-wise into DJF, MAM, JJA, and SON
5. Perform grid-wise regression
6. Plot global seasonal influence maps
7. Apply 95% confidence/significance testing

---

## Evaluation Metrics

The following evaluation metrics were used across different models:

- Mean Squared Error, MSE
- Root Mean Squared Error, RMSE
- Mean Absolute Error, MAE
- R² Score
- Classification Accuracy, where ENSO values were converted into classes
- ADF statistic and p-value for stationarity checking

For ARIMA and SARIMA models, stationarity and forecasting performance were analyzed using ADF test and RMSE.

---

## Repository Structure

```text
climate-forecasting-computation-simulation-lab/
│
├── README.md
│
├── data/ 
│   ├── raw/ 
│
├── notebooks/
│   ├── time_series.ipynb
│   ├── arma.ipynb
│   ├── arma1.ipynb
│   ├── sarima.ipynb
│   ├── decision_tree.ipynb
│   ├── linear.ipynb
│   ├── multilinear.ipynb
│   ├── logistic.ipynb
│   ├── polynomialregression.ipynb
│   ├── ann,lstm,cnn,rnn,svr.ipynb
    └── randomforest.ipynb

---
```
## Technologies and Libraries Used
Python
NumPy
Pandas
Matplotlib
Xarray
Scikit-learn
Statsmodels
TensorFlow
Keras
NetCDF4

## Installation

Clone the repository:
git clone https://github.com/Chaitran06/climate-forecasting-computation-simulation-lab.git
cd climate-forecasting-computation-simulation-lab

## Install the required libraries:
pip install -r requirements.txt

## Run Jupyter Notebook:
jupyter notebook

Open the notebooks folder and run the model notebooks.

## Results Summary
The project compared multiple forecasting approaches for climate data.

ARIMA and SARIMA were useful for statistical forecasting of monthly SST data.
SARIMA was suitable for monthly SST because it considers seasonal patterns.
Linear Regression helped analyze the influence of ENSO on SST.
Spatial regression maps showed seasonal ENSO influence across different oceanic regions.
ANN, RNN, LSTM, and CNN were used for Niño 3.4 sequence prediction.
SVM and Random Forest were used as machine learning baselines for ENSO forecasting.
Deep learning models were able to capture temporal patterns from previous monthly values.

## Conclusion

This project demonstrates the application of statistical, machine learning, and deep learning models for climate time-series forecasting. Traditional models such as ARIMA and SARIMA provide interpretable forecasting methods, while machine learning and deep learning models can capture nonlinear and temporal dependencies in climate indices.

The experiments show how climate datasets such as ERA5 SST and NOAA Niño 3.4 can be used for forecasting, regression analysis, spatial visualization, and model comparison.

