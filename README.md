# Yes Bank Stock Price Prediction using Regression Models

## Project Overview
This project focuses on predicting monthly closing prices of **Yes Bank** using historical stock price data. It leverages machine learning regression models including **Linear Regression**, **Random Forest Regressor**, and **XGBoost Regressor**, along with feature engineering, hyperparameter tuning, and model evaluation techniques to provide accurate and interpretable stock price forecasts.

Accurate predictions can assist investors and financial institutions in strategic planning, risk management, and informed decision-making.

---

## Project Type
- **Type:** Regression Machine Learning Project  
- **Contribution:** Individual - Jevin Chokshi  

---

## Dataset
The dataset contains monthly stock price data for Yes Bank including the following columns:
- `Date` – Date of record (month-year format)
- `Open` – Opening price for the month
- `High` – Highest price in the month
- `Low` – Lowest price in the month
- `Close` – Closing price for the month

**Dataset size:** 185 records  

---

## Key Steps

### 1. Data Preprocessing
- Converted `Date` column to datetime.
- Extracted additional features: Month, Year, Quarter.
- Added derived features:
  - `Price_change` = High - Low
  - `Gains` = Close - Open
- Handled transformations for regression:
  - **Power Transformation (Yeo-Johnson)** for features
  - **Log Transformation** for target variable (Close price)
- Standardized features using **StandardScaler**

### 2. Exploratory Data Analysis (EDA)
- Statistical summary and visualizations to understand trends and relationships
- Identified most volatile months, quarters, and yearly gains/losses
- Generated correlation heatmaps and pair plots for insights

### 3. Model Development
Implemented three regression models:

1. **Linear Regression**
   - Baseline model
   - Cross-validated using 5-Fold KFold
   - Achieved high R² and low RMSE
2. **Random Forest Regressor**
   - Ensemble method capturing non-linear patterns
   - Hyperparameter tuning with GridSearchCV
   - Strong performance, minor overfitting observed
3. **XGBoost Regressor**
   - Gradient boosting method
   - Hyperparameter tuning using GridSearchCV
   - Highest predictive accuracy among models

### 4. Model Evaluation
Models were evaluated using:
- **R² Score:** Measures variance explained by the model
- **Root Mean Squared Error (RMSE):** Measures average prediction error
- **Mean Absolute Error (MAE):** Measures average absolute deviation

**Business Impact:**  
Reliable stock price predictions support financial planning, risk assessment, and strategic investment decisions.

### 5. Model Explainability
- Feature importance analysis (from XGBoost) to identify key predictors
- Interpretability ensures insights are actionable for investment decisions

---

## Performance Summary

| Model                  | R² Score (Test) | RMSE (Test) | MAE (Test) |
|------------------------|----------------|-------------|------------|
| Linear Regression      | 0.989          | 9.35        | 6.81       |
| Random Forest Regressor| 0.983          | 11.79       | 7.07       |
| XGBoost Regressor      | 0.994          | 6.33        | 4.15       |

**Observation:** XGBoost delivered the highest predictive accuracy and stability across cross-validation folds.

---

## How to Run
1. Clone the repository:
```bash
git clone https://github.com/<your-username>/yesbank-stock-prediction.git
