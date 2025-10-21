# 🍽️ Restaurant Sales Forecasting: A Time Series Modeling Approach Using ARIMA and Prophet
***By Samuel Oyedele***

## 🎯 Objective
The goal of this project is to analyze daily restaurant sales data and build predictive models capable of forecasting future sales trends.  
We compare **ARIMA** and **Prophet** models, evaluate their performance, and refine the most accurate model for **30-day future sales forecasting**.

---

## 📚 Overview
Restaurants depend on accurate sales forecasts for effective staffing, inventory, and marketing decisions.  
This project demonstrates a complete **end-to-end time series forecasting workflow** that includes:
- Data cleaning and preprocessing
- Exploratory Data Analysis
- Model building using ARIMA and Prophet  
- Outlier detection and removal  
- Model tuning and evaluation  
- Future sales prediction  

---

## ⚙️ Tools and Libraries Used
- **Python**
- **Pandas**, **NumPy** → Data cleaning and manipulation  
- **Matplotlib**, **Seaborn** → Data visualization  
- **Statsmodels** → ARIMA model  
- **Prophet (by Meta)** → Time series forecasting  
- **scikit-learn** → Evaluation metrics  

---

## 🧩 Dataset Description
The dataset includes daily restaurant order records with the following key columns:
- `Order Date` → Date of the transaction  
- `Order Total` → Total sales amount per day  

The data was aggregated to daily totals for time series modeling.

---

## 🚀 Project Workflow

### **Step 1: Data Preparation**
- Loaded and inspected dataset using `pandas`
- Converted order dates to datetime format
- Aggregated daily total sales and sorted chronologically

### **Step 2: Exploratory Data Analysis**
- Visualize the sales trend
- Decompose the series into trend, seasonality and residuals using `statsmodels`

### **Step 3: ARIMA Model**
- Applied ARIMA (AutoRegressive Integrated Moving Average) model using `statsmodels`
- Split into train/test
- Tuned parameters `(p, d, q)` through iterative testing
- Evaluated using **MAE**, **RMSE**, and **MAPE**
- **Result:** MAPE = **31.67%** → struggled to model strong seasonal components

### **Step 4: Prophet Model**
- Built a baseline **Prophet** model to capture trend and seasonality
- Evaluated model on the same data split
- **Result:** MAPE = **30.36%** → Slight improvement, better trend adaptability

### **Step 5: Model Refinement**
- Removed outliers using **IQR (Interquartile Range)** method
- Tuned Prophet hyperparameters:
  - `changepoint_prior_scale` (trend flexibility)
  - `seasonality_prior_scale` (seasonal strength)
- **Improved Result:** MAPE = **28.33%** → more reliable and accurate forecasts

### **Step 6: Future Forecasting**
- Visualized both actual and predicted values with confidence intervals
- Generated **30-day future forecast** using the refined Prophet model  

---

## 📊 Model Evaluation Summary

| Model | MAE | RMSE | MAPE | Comment |
|--------|------|------|--------|----------|
| **ARIMA** | — | — | 31.67% | Basic model, limited in seasonal capture |
| **Prophet (Base)** | — | — | 30.36% | Captured weekly trend & seasonality |
| **Prophet (Refined)** | — | — | **28.33%** | Improved accuracy after outlier removal & tuning |

---

## 📈 Visualizations
- **Trend Analysis:** Prophet decomposition showing sales growth & seasonality
- **Actual vs Predicted:** Side-by-side comparison for validation  
- **Forecast Plot:** 30-day future forecast with uncertainty intervals  

---

## 🧠 Key Takeaways
- **ARIMA** provided a good baseline but lacked flexibility with non-linear seasonality.  
- **Prophet** effectively modeled complex patterns in sales data.  
- Removing outliers and tuning model parameters led to significant performance gains.  
- The refined Prophet model achieved **MAPE = 28.33%**, suitable for practical business forecasting.  
- The model’s 30-day forecast provides actionable insights for **staff planning, marketing, and inventory management.**

---

## 🔮 Next Steps
- Include external factors such as holidays, promotions, or events to enhance prediction accuracy.  
- Deploy the model using **Streamlit** or **Power BI** for interactive business dashboards.  
- Automate model retraining with new data.

## Samuel Oyedele
📍 Data Analyst
🔗 [LinkedIn Profile](https://www.linkedin.com/in/oyedele-samuel-53579b19b)
