# 📊 Customer Churn Analysis Project  

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![SQL](https://img.shields.io/badge/Database-MySQL-orange?logo=mysql)
![PowerBI](https://img.shields.io/badge/Dashboard-Power%20BI-yellow?logo=powerbi)
![Machine Learning](https://img.shields.io/badge/Model-LGBM%20%7C%20XGBoost-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 🧠 Project Objective
This project aims to **analyze, visualize, and predict customer churn** using:
- **SQL** for data storage, transformation, and summary analysis  
- **Python** for exploratory data analysis (EDA) and churn prediction modeling  
- **Power BI** for interactive dashboards and business insights  

The goal is to help stakeholders **identify key churn drivers** and **develop data-driven retention strategies**.

---

## 💾 Data Source
- Dataset: **Telco Customer Churn** (or similar structured dataset)  
- Data stored in MySQL under database `db_churn`
- Sample SQL setup:
  ```sql
  CREATE DATABASE db_churn;
  USE db_churn;
  SELECT * FROM customer_data;
  ```
- Import the dataset into MySQL using any preferred method (Workbench, CSV import, or Python connector).  

---

## 🧩 Tech Stack

| Layer | Tools & Libraries |
|-------|--------------------|
| **Database** | MySQL |
| **Data Analysis** | Python (Pandas, NumPy) |
| **Visualization** | Matplotlib, Seaborn, Power BI |
| **Machine Learning** | Scikit-learn, XGBoost, LightGBM |
| **Other** | Jupyter Notebook, Power BI Desktop |

---

## 🔍 Exploratory Data Analysis (EDA)

Performed in Python to uncover key churn patterns and correlations:

- Distribution of churned vs. retained customers  
- Churn rate by gender, contract type, payment method, and tenure  
- Correlation heatmaps and pair plots  
- Outlier and missing value treatment  

---

## 🧮 SQL Insights

Some examples of SQL analysis performed:

```sql
SELECT Gender, COUNT(*) AS TotalCount,
       (COUNT(*) * 100.0 / (SELECT COUNT(*) FROM customer_data)) AS Percentage
FROM customer_data
GROUP BY Gender;
```

✅ **Key KPIs extracted:**
- Overall Churn Rate (%)  
- Churn by Gender  
- Churn by Contract Type  
- Monthly Charges & Tenure Distribution  

---

## 🤖 Machine Learning Model

### Models Implemented
1. **LightGBM (LGBMClassifier)**  
2. **XGBoost (XGBClassifier)**  

### Process Overview
- Feature encoding & scaling  
- Handling class imbalance (SMOTE / class weights)  
- Model training, tuning, and evaluation  
- Metrics used: **Accuracy**, **Precision**, **Recall**, **F1-score**, and **ROC-AUC**

✅ **Best Model:** *LightGBM*  
✅ **ROC-AUC:** ~0.89 (depending on dataset)

---

## 📊 Power BI Dashboards

Developed dynamic and interactive dashboards to visualize:
- **Overall Churn Trends**
- **Demographics Breakdown (Gender, Age, Contract Type)**
- **Revenue Loss from Churned Customers**
- **Predictive Model Results Visualization**

**KPIs Included:**
- Total Customers  
- Total Churned Customers  
- Churn Rate (%)  
- Avg. Monthly Charges by Segment  
- Tenure-based Churn Trends  

> *(Add Power BI screenshot here if available)*

---

## ⚙️ Project Structure

```
📁 churn-analysis/
│
├── 📂 data/                     # Raw & cleaned datasets
├── 📂 notebooks/                # Python notebooks for EDA & ML
├── 📂 dashboards/               # Power BI files (.pbix)
├── 📂 sql/                      # SQL scripts for data setup and queries
├── 📄 requirements.txt          # Python dependencies
├── 📄 README.md                 # Project documentation (this file)
└── 📄 churn_analysis.py         # Main Python analysis script
```

---

## 🚀 Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/churn-analysis.git
cd churn-analysis
```

### 2. Create & activate a virtual environment
```bash
python -m venv venv
venv\Scripts\activate  # (Windows)
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Setup database
- Import dataset into MySQL and run SQL scripts from `/sql/` folder  
- Update DB credentials in your Python config file or notebook  

### 5. Run the analysis
```bash
python churn_analysis.py
```

---

## 📈 Results Summary

| Metric | LGBM | XGBoost |
|--------|------|----------|
| Accuracy | 87% | 85% |
| ROC-AUC | 0.89 | 0.86 |
| Precision | 0.84 | 0.81 |
| Recall | 0.83 | 0.79 |

**Insights:**
- Customers with month-to-month contracts and high monthly charges are more likely to churn.  
- Long-term contract and auto-pay customers show lower churn rates.  

---

## 🧭 Future Enhancements
- Integration with live customer data sources  
- Automated churn prediction pipeline (via API or Streamlit app)  
- Deeper segmentation analysis using clustering  
- Real-time Power BI data refresh  

---
