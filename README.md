# Chicago Crime Hotspot Detection and Time Series Prediction

This repository contains a data analysis and machine learning project focused on **identifying crime hotspots** and **predicting future crime trends** using Chicago dataset. Using historical crime data, the project applies clustering, time series analysis, and predictive modeling to provide actionable insights into crime patterns.

The final output is a set of **JSON files** containing information on identified hotspots and their predicted future crime rates, designed for integration.

---

## 🚀 Project Goals
- **Data Analysis**: Understand historical crime patterns and distribution in Chicago.  
- **Hotspot Detection**: Use clustering to group crime incidents into geographical hotspots.  
- **Time Series Forecasting**: Predict the number of future crime incidents within each hotspot.  
- **Model Integration**: Prepare results in JSON format for front-end/mobile applications.  

---

## 📊 Dataset
The analysis is based on the comprehensive **"Crimes - 2001 to Present"** dataset provided by the City of Chicago. The Dataset Size is Approximately **82.73 lacs Rows** from 2001-2025.
This dataset includes detailed records of reported criminal incidents from **2001 to the present**, with information on **location, crime type, date, and time**.

📥 **Chicago Portal Link**: https://data.cityofchicago.org/
<br><br>
📥 **Dataset Link**: https://data.cityofchicago.org/Public-Safety/City-of-Chicago-Crime-Data/v9q9-3dm2#:~:text=This%20dataset%20reflects%20reported%20incidents%20of%20crime%20%28with,Uniform%20Crime%20Reporting%20%28IUCR%29%20codes%2C%20go%20to%20http%3A%2F%2Fdata.cityofchicago.org%2FPublic-Safety%2FChicago-Police-Department-Illinois-Uniform-Crime-R%2Fc7ck-438e
<br><br>

**Note** : Copy and then paste the link Otherwise it is giving 404 error on direct opening
---

## 🛠 Methodology

### 1. Data Preprocessing and Exploration
- **Loading and Cleaning**: Convert date/time, remove missing coordinates.  
- **Feature Engineering**: Create time-based features (year, month, day, weekday).  
- **Aggregation**: Monthly counts for time series; spatial grouping for clustering.  

### 2. Clustering for Hotspot Detection
Three clustering algorithms were explored:  
- **K-Means**: Iterated with different *k* values to find optimal clusters.  
- **DBSCAN**: Density-based clustering, good for irregular hotspot shapes.    

### 3. Time Series Forecasting
- For each hotspot, monthly crime counts were modeled.  
- Models used:  
  - **sktime** library (multiple forecasting algorithms).  
  - **Prophet** (by Facebook), ideal for seasonality and trend-based crime prediction.  

### 4. Hotspot Prediction with XGBoost
- A **supervised learning model (XGBoost)** was trained to unify predictions.  
- Final output includes **risk scores and future predictions per hotspot**.  

---

## 📌 Dataset Summary
- **Total Records**: 8.7 million (filtered for complete records).  
- **Time Range**: ~2001 to present.  

### 🔝 Top Crime Types
| Rank | Primary Type       | % of Total |
|------|-------------------|-------------|
| 1    | THEFT             | ~21%        |
| 2    | BATTERY           | ~18%        |
| 3    | CRIMINAL DAMAGE   | ~10%        |
| 4    | NARCOTICS         | ~8%         |
| 5    | OTHER OFFENSE     | ~7%         |

---

## 📍 Clustering and Hotspot Identification
- Crime hotspots were detected with clustering methods.  
- Each hotspot includes **central coordinates** and **dominant crime types**.  
- Visualizations highlight **high-density areas of crime activity**.  

---

## 📈 Predictive Model Results
Final outputs are exported as JSON files, including:  
- **Hotspot ID** and **coordinates**.  
- **Primary crime types** per hotspot.  
- **Predicted number of crimes for the next 30 days**.  

## 📦 Requirements
- Python 3.x
- pandas

- numpy

- matplotlib

- seaborn

- scikit-learn

- geopy

- xgboost

- sktime (with Prophet installed)
