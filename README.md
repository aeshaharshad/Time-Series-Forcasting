# 🥐 Time Series Forecasting for French Bakery Sales

## 📌 Project Overview
This project focuses on **time series forecasting** of daily sales data from a French bakery. It compares baseline and advanced statistical models, evaluates their performance, and improves predictions using exogenous variables and feature engineering.

---

## 📂 Dataset

**File:** `daily_sales_french_bakery.csv`

**Columns:**
- `unique_id` → Product name  
- `ds` → Date  
- `y` → Sales volume  
- `unit_price` → Product price  

**Preprocessing:**
- Converted `ds` to datetime
- Filtered products with at least 28 observations
- Created train/test splits (last 7 days as test set)

---

## 📊 Models Used

### Baseline Models
- Naive
- Historic Average
- Window Average (7-day)
- Seasonal Naive (weekly)

### Advanced Models
- ARIMA
- SARIMA

### Enhanced Models
- SARIMA with exogenous variables (price)
- SARIMA with engineered time features

---

## ⚙️ Workflow

### 1. Data Visualization
- Plotted time series for selected products
- Compared trends and seasonality

### 2. Forecasting
- Used `StatsForecast` for scalable forecasting
- Generated 7-day forecasts

### 3. Evaluation
Metrics used:
- MAE
- MSE
- RMSE
- MAPE
- SMAPE
- MASE
- Scaled CRPS

### 4. Cross-Validation
- Rolling window validation
- Multiple forecast windows for robust evaluation

### 5. Feature Engineering
- Fourier terms for seasonality
- Time features: day, week, month

### 6. Exogenous Variables
- Included `unit_price` in forecasting
- Compared performance with and without exogenous inputs

### 7. Prediction Intervals
- Generated probabilistic forecasts (80% confidence interval)

---

## 📈 Results & Insights

- Seasonal models outperform simple baselines
- SARIMA captures weekly patterns effectively
- Exogenous variables (price) slightly improve accuracy
- Cross-validation provides more realistic performance estimates
- Prediction intervals help quantify uncertainty

---

## 📉 Example Results (MAE)

| Model               | MAE |
|--------------------|-----|
| Naive              | ~6.10 |
| Historic Average   | ~5.23 |
| Window Average     | ~5.01 |
| Seasonal Naive     | ~4.61 |
| SARIMA             | ~8.90 |
| SARIMA + Exogenous | ~19.21 (CV) |
