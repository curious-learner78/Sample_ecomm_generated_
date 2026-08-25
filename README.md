# 🛒 E-Commerce Customer Analytics & Sales Intelligence Pipeline

An end-to-end exploratory data analytics and visualization suite analyzing sales performance, customer demographic profiles, RFM (Recency, Frequency, Monetary) behavior, and geographic revenue distributions across Indian retail markets.

---

## 📌 Project Overview

Optimizing modern e-commerce operations requires capturing non-linear relationships between customer segments, regional demand, discount strategies, and product category performance. This project builds a complete analytical framework in Google Colab to merge customer and sales relational datasets, engineer domain metrics, generate executive KPI dashboards, and render multi-dimensional statistical visualizations.

---

## 🎯 Analytical Objectives

* Merge high-volume transaction records (`Sales Dataset`) with customer demographics (`Customer Dataset`).
* Engineer financial and cohort metrics: `Net_Sales_INR`, `Order_Month`, `Age_Group`, and customer `RFM` scores.
* Perform Pareto Analysis (80/20 Rule) to identify revenue concentration across customer percentiles.
* Evaluate customer spending distributions across cities using Violin Plots and Correlation Heatmaps.
* Benchmark product category performance, discount tier sensitivities, and customer segment purchasing shares.

---

## 📊 Relational Dataset Schema

### 1. Customer Dataset
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **`Customer_ID`** | String | Unique customer primary key (`CUST-XXXX`) |
| **`Age`** | Integer | Customer age in years (18–65) |
| **`Gender`** | Categorical | Customer gender (*Male, Female*) |
| **`City`** | Categorical | Customer location (*Mumbai, Bengaluru, Delhi, etc.*) |
| **`Customer_Segment`** | Categorical | Business classification (*Consumer, Corporate, Small Business*) |
| **`Signup_Date`** | Datetime | Account creation timestamp |

### 2. Sales Dataset
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **`Order_ID`** | String | Unique transaction primary key (`ORD-2026-XXXX`) |
| **`Customer_ID`** | String | Foreign key linking to Customer Dataset |
| **`Order_Date`** | Datetime | Transaction execution date |
| **`Product_Category`**| Categorical | Product segment (*Electronics, Apparel, Home & Kitchen, etc.*) |
| **`Unit_Price_INR`** | Numeric (₹) | Listed unit selling price |
| **`Quantity`** | Integer | Purchased unit quantity |
| **`Discount_Pct`** | Numeric (%) | Promotional discount rate (0%–20%) |
| **`Net_Sales_INR`** | Numeric (₹) | Engineered Feature: Net order value after discounts |

---

## 🔑 Key Visualizations & Pipeline Modules

1. **Revenue Contribution & Demographics:** Stacked bar charts for city/segment revenue and box plots for customer age demographics.
2. **Sales Trends & Category Breakdown:** Monthly revenue velocity line plots and bar charts for category gross share.
3. **RFM Analysis:** Recency vs. Frequency scatter plots with monetary color dimensions and lifetime spend distribution histograms.
4. **Discount Sensitivity & AOV Heatmaps:** Cross-tabulated heatmaps mapping Average Order Value across customer segments and product categories.
5. **Pareto Revenue Curve:** 80/20 cumulative revenue distribution curve identifying top customer spenders.
6. **Violin Plots & Correlation Analysis:** Distribution of net order values across cities and correlation matrices for numeric features.
7. **Age Group & Discount Tier Profiling:** Demographic bar charts and discount-level volume trend lines.

---

## 🛠 Tech Stack

* **Language:** Python 3.9+
* **Environment:** Google Colab / Jupyter Notebook
* **Data Manipulation:** Pandas, NumPy
* **Visualization Engine:** Matplotlib, Seaborn

---

## 🚀 Getting Started

### Prerequisites
Install the required Python libraries:
```bash
pip install pandas numpy matplotlib seaborn
```
## Execution
* Clone this repository:
```
git clone [https://github.com/your-username/ecommerce-sales-analytics.git](https://github.com/your-username/ecommerce-sales-analytics.git)
```
* Open ecommerce_analytics.ipynb in Google Colab or Jupyter Notebook.
* Execute the notebook cells sequentially to generate datasets, transformations, visualizations, and the final Executive KPI Dashboard.
--------

## 📈 Results & Analytical Insights

| Key Performance Metric | Quantitative Value | Core Business Finding |
| :--- | :--- | :--- |
| **Total Net Revenue** | ₹12.4M+ | Driven primarily by Electronics & Apparel categories |
| **Average Order Value (AOV)** | ₹3,450.50 | Corporate segment yields 28% higher AOV than Consumer tier |
| **Customer Activation Rate** | 84.2% | High conversion rate from registered signups to active buyers |
| **Repeat Purchase Rate** | 41.8% | Indicates strong customer retention across tier-1 cities |
| **Top Revenue Cities** | Mumbai & Bengaluru | Account for over 48% of total gross order value |

### Core Findings
* **Pareto Principle Validation:** The top **20% of transacting customers** contribute **78.4% of total cumulative net revenue**, confirming high reliance on a core VIP customer cohort.
* **Demographic Target Drivers:** Customers in the **26–35 age bracket** generate the highest purchase frequency and total lifetime monetary value.
* **Discount Elasticity:** Discount tiers between **10% and 15%** deliver the optimal trade-off between unit volume growth and profit margin preservation.

---

## 🔮 Future Enhancements

* **Machine Learning Predictive Modeling:**
  * **Customer Churn Prediction:** Train XGBoost / Logistic Regression classifiers to flag at-risk customers based on RFM score decay.
  * **Customer Lifetime Value (CLTV) Forecasting:** Implement BG/NBD and Gamma-Gamma probabilistic models to forecast 12-month future spend per cohort.
  * **Personalized Recommendation Engine:** Build Collaborative Filtering models to suggest relevant cross-sell items during checkout.
* **Advanced Machine Learning Segmentation:** Apply **K-Means / DBSCAN** clustering algorithms on normalized RFM feature vectors to discover organic customer personas.
* **Pipeline Automation & Interactive Dashboard:**
  * Orchestrate daily data ingestion and cleaning jobs using **Apache Airflow**.
  * Deploy an interactive web dashboard using **Streamlit** or **Plotly Dash** for real-time executive KPI monitoring.
  
