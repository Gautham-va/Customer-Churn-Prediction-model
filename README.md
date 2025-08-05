# 📉 Customer Churn Prediction

This project performs churn prediction using customer demographic, transaction, service usage, and online activity data. It includes data merging from multiple Excel sheets, cleaning, EDA, feature engineering, and preprocessing via Scikit-learn pipelines.

---

## 📂 Data Overview

- Multiple sheets from Excel:
  - `Customer_Demographics`
  - `Transaction_History`
  - `Customer_Service`
  - `Online_Activity`
  - `Churn_Status`
- Merged using `CustomerID`

---

## 🔧 Preprocessing Highlights

- Filled missing values (e.g., `AmountSpent`, `LoginFrequency`)
- Converted date columns to `datetime` objects
- Removed duplicates
- Created new features:
  - `TotalInteractions`
  - `DaysSinceLastLogin`

---

## 📊 EDA

- Churn distribution countplot
- Histogram: `AmountSpent`
- Boxplot: `LoginFrequency` vs `ChurnStatus`
- Correlation heatmap for numeric columns

---

## 🏗️ Feature Engineering

- Created `interaction_count` from service logs
- Days since last login calculated from `LastLoginDate`
- Features selected:
  - **Numeric**: `AmountSpent`, `LoginFrequency`, `DaysSinceLastLogin`, `TotalInteractions`
  - **Categorical**: `ProductCategory`, `ServiceUsage`

---

## ⚙️ Preprocessing Pipeline

- **Numeric Pipeline**: Median imputation + Standard Scaler
- **Categorical Pipeline**: Most frequent imputation + OneHotEncoder
- Combined using `ColumnTransformer`
- Output: `X_processed` — ready for model training

---

## 📦 Requirements

```text
pandas
numpy
seaborn
matplotlib
scikit-learn
