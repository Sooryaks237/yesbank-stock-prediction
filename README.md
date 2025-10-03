# 📉 Yes Bank Stock Price Prediction (Machine Learning - Time Series)  

📊 **Tools Used**: Python (Pandas, NumPy, Matplotlib, Scikit-learn) | Google Colab  

---
## Table of Contents
- [Project Overview](#project-overview)
- [Data Structure](#data-structure)
- [Executive Summary](#executive-summary)
- [Recommendations](#Recommendations)
- [Methodology](#methodology)
- [Visualizations](#visualizations)

--- 

## 📌 Project Overview  
This project predicts the **closing stock price of Yes Bank** using **Machine Learning regression models**.  
This project focuses on forecasting the monthly closing price of Yes Bank stock using machine learning models.  
The goal is to build a **leakage-safe ML pipeline**, engineer time-series features, and evaluate models against a naive baseline.  

The analysis follows a **time-series-aware ML approach** with no data leakage, using **TimeSeriesSplit**.  

---

## 📂 Data Structure
- **Date**: Monthly timestamp  
- **Open, High, Low, Close**: Standard OHLC data  
- **Volume**: Trading volume  
- **Engineered Features**:  
  - Cyclical month encodings  
  - Price spreads & ratios  
  - Returns  
  - Rolling statistics  
  - Lagged values  

---

## 📊 Executive Summary
- Built and optimized a **Ridge regression pipeline** with time-aware CV.  
- Engineered **22+ leakage-safe features** for robust forecasting.  
- Achieved **MAE 44.6 vs 251.9 baseline (~82% improvement)**.  
- Implemented **recursive 6-month forecast** with feature re-computation.  
- Applied **permutation importance** for model interpretability.  

---

## ✅ Recommendations
- Extend features with **macroeconomic indicators, sector indices, or sentiment signals**.  
- Experiment with advanced models like **XGBoost, LightGBM, or LSTMs**.  
- Deploy forecasts through **interactive dashboards** for decision support.  

---

## 🔍 Methodology
1. **Feature Engineering**  
   - Cyclical month encoding (sin/cos)  
   - Price spreads & ratios (`hl_spread`, `oc_spread`, `range_ratio`)  
   - Returns (`ret_1`, `ret_3`, `ret_6`)  
   - Rolling stats (`roll_mean_3`, `roll_mean_6`, `roll_std_6`, `roll_min_6`, `roll_max_6`)  
   - Lag features (`lag_close_1`, `lag_close_2`, `lag_close_3`, `lag_close_6`, `lag_close_12`)  
   - Leakage prevented by shifting features  

2. **Splits**  
   - Train: 70%  
   - Validation: 15%  
   - Test: 15%  

3. **Modeling & Selection**  
   - Ridge regression (α ∈ {0.1, 1, 5, 10})  
   - Random Forest (n_estimators ∈ {200, 500}, depths, min_samples_leaf)  
   - GridSearchCV + TimeSeriesSplit  
   - Best: **Ridge**  

4. **Evaluation Metrics**  
   - MAE, RMSE, MAPE%  

---

## 📊 Results
| Model              | MAE   | RMSE  | MAPE%   |  
|--------------------|-------|-------|---------|  
| **Ridge (chosen)** | 44.6  | 60.4  | 66.5%   |  
| Naive Baseline     | 251.9 | 263.8 | 851.7%  |  

➡️ Ridge reduced MAE by **~82%** compared to baseline.  

---

## 📸 Sample Visualizations  

Closing stock price trend:  
![Closing Price Trend](closing_price.png)  

Predicted vs Actual prices:  
![Predicted vs Actual](predicted_vs_actual.png)  

Model forecast (next 6 months):  
![Forecast](forecast.png)  

---

## 📂 Project Files  
- `YesBank_MLproject.ipynb` → Jupyter Notebook with complete ML pipeline  
- 🔗 Dataset Source: [Yes Bank Stock Prices Dataset (Kaggle)](https://www.kaggle.com/datasets/simranjain17/yes-bank-stock-prices/data)  
- 📸 Screenshots of results (see below)  

---
## 🚀 How to Run the Project  
1. Open the notebook in **Google Colab** or Jupyter Notebook.  
2. Install required libraries if running locally:  
   ```bash
   pip install pandas numpy matplotlib scikit-learn

---

## 📫 Connect with Me  
- [LinkedIn](https://www.linkedin.com/in/soorya-k-s-/)  
- 📧 Email: **sooryaks552@gmail.com*
---

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

---
⭐️ From [Sooryaks237](https://github.com/Sooryaks237)
