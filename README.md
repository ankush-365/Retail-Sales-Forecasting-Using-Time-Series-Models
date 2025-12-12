# 📈 Monthly Store Sales Forecasting using SARIMA & Prophet

This project builds a monthly sales forecasting system using classical and modern time-series models.  
It uses the **Store Sales – Time Series Forecasting** dataset from Kaggle and predicts sales for the next **3 months** using:

- **SARIMA** (Seasonal ARIMA)
- **Prophet** (Meta/Facebook Prophet)

The workflow includes **EDA, feature engineering, model training, evaluation, and model comparison**.

---

## 🧹 Data Preparation

- Resampled daily data to **monthly sales**.
- Created additional features:
  - `month_num`, `year`
  - Holiday counts per month
  - Monthly promotions total
  - Lag features (`lag_1`, `lag_12`)
  - Difference features (`sales_diff_1`, `sales_diff_12`)
- Handled missing values with forward-fill or zeros depending on context.

---

## 📊 Exploratory Data Analysis (EDA)

The analysis included:

- Sales trend visualization  
- Seasonality detection  
- Rolling averages  
- ACF & PACF plots  
- Holiday impact study  

### Key Insights:
- Strong seasonal patterns exist.
- Sales spike around major holidays.
- Sales variability increases over years.

---

## 🔮 Models Used

### **1️⃣ SARIMA (Seasonal ARIMA)**

SARIMA was tuned and trained using the monthly aggregated sales.

**Performance:**
- Captured seasonality well.
- Reasonable forecasting accuracy.

| Metric | Value |
|--------|--------|
| MAPE | **0.0315 (3.15)%** |

---

### **2️⃣ Prophet**

Prophet was used with:
- Trend modeling  
- Yearly seasonality  
- Added holiday regressors  

**Performance:**
- Strong overall fit  
- Smooth seasonal component modeling  
- Excellent short-term forecast accuracy  

| Metric | Value |
|--------|--------|
| MAPE | **0.065 (6.5%)** |

Despite R² limitations, Prophet performed very well in terms of error.

---

## 🏁 Conclusion

- Both models worked well for monthly forecasting.
- **Prophet** performed slightly better for this dataset, especially due to holiday components.
- **SARIMA** provides a stable traditional baseline.
- The project demonstrates end-to-end forecasting:
  - Data cleaning  
  - Feature engineering  
  - Model training  
  - Error evaluation  
  - Future forecasting  

---
