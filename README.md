 
# 🛒 Modecraft Ecommerce Data Analysis Project

## 📊 TL;DR – Ecommerce Dashboard Summary
## 🔗 Data Visualization

 [Click here to view the Tableau dashboard](https://public.tableau.com/views/Datathon2025_17456919773330/Dashboard1)

This Tableau dashboard provides a high-level overview of Modecraft’s sales performance across key business dimensions.

### Top Sales Regions
- **United Kingdom** leads significantly in total sales.
- Followed by **Netherlands**, **EIRE**, and **Germany**.

### Customer Insights
- A few **high-value customers** contribute disproportionately to total revenue.
- Some customers made purchases exceeding **£1M**, indicating strong repeat behavior and brand loyalty.

### Top Products
- **Best-sellers** include:
  - *Paper Craft, Little Bird*
  - *Medium Ceramic Top Storage*
- These dominate sales volume and are ideal for bundling or promotions.

###  Sales Timing Patterns
- **Mid-day on Thursdays and Fridays** see the highest transaction volumes.
- Suggests optimal windows for **marketing campaigns** and **flash sales**.

###  Key Performance Indicators
- **Total Units Sold:** 5.66 million+
- **Total Products:** 4,061
- **Total Customers:** 4,340
- **Average Quantity per Transaction:** ~10.66 units

## Project Overview

As part of the **6th DubsTech Datathon**, this project focuses on analyzing transactional data from **Modecraft**, an e-commerce store offering a wide range of household items.

The goal was to identify high-performing products, uncover purchasing behavior trends, and support data-driven decision-making through a combination of analytics, visualization, and machine learning.

### Project Components

- **Data Cleaning & Preparation** – using Python (Pandas) to clean and normalize raw data
- **KPI Development** – creation of a custom **Product Health Score** to rank products based on revenue, quantity sold, and purchase frequency
- **Data Visualization** – interactive Tableau dashboard to explore metrics, trends, and rankings
- **Machine Learning** – XGBoost model to validate key performance drivers and predict high-potential products

---

##  Data Dictionary

The dataset included over **500,000 order records** with the following columns:

- `InvoiceNo`: Unique Invoice ID  
- `StockCode`: Unique Product ID  
- `Description`: Product Name  
- `Quantity`: Total units purchased  
- `InvoiceDate`: Date and time of the invoice  
- `UnitPrice`: Price per unit (GBP)  
- `CustomerID`: Unique Customer ID  
- `Country`: Country of origin for the order

---

##  Data Cleaning & Preparation

###  Initial Assessment
- Reviewed dataset dimensions and structure
- Identified null values across key columns
- Ran summary statistics to understand distributions

### Handling Negative Values
- Removed negative `Quantity` values (likely returns)
- Documented the percentage of data removed

### Handling Missing Values
- Replaced null `CustomerID`s with `"Unknown Customer"`
- Replaced missing product descriptions with `"Unknown Product"`

###  Feature Engineering
- Renamed `Description` to `Product Name` for clarity
- Extracted `Month` from `InvoiceDate`
- Added a `Season` column based on invoice month

### Final Verification
- Verified there were no remaining nulls
- Saved cleaned dataset for downstream analysis

---
## KPI Development

The **Product Health Score** is a weighted composite metric created to evaluate product performance across three key dimensions:

Product Health Score =
(0.5 × Normalized Revenue) +
(0.3 × Normalized Quantity Sold) +
(0.2 × Normalized Invoice Count)

- **Revenue (50%)** — Profitability is the top priority.
- **Quantity Sold (30%)** — Popularity and demand matter.
- **Invoice Count (20%)** — Measures repeat purchases or transaction frequency.

> This metric allows Modecraft to prioritize products that not only generate high revenue but also show consistent customer purchase behavior.


## Files in this Repository

| File Name                      | Description                                                           |
|-------------------------------|-----------------------------------------------------------------------|
| `E_commerce_Data_Cleaning.ipynb` | Jupyter notebook with Python code for data cleaning and preprocessing. |
| `ML_XGBOOST.ipynb`             | Jupyter notebook implementing the XGBoost machine learning model to validate KPI drivers and predict product success. |
| `Mode_Craft_Ecommerce_Data.xlsx` | Original raw dataset used for the analysis.                          |
| `Ecommerce_Dashboard.png`      | Screenshot of the Tableau dashboard visualizing key metrics and trends. |
| `Ecommerce_Tableau.pdf`        | Full visual                                               |
| `3rd Place - Data Analysis-2.jpg` | Award certificate for achieving 3rd place in the datathon.      |



## 🔗 Data Visualization

 [Click here to view the Tableau dashboard](https://public.tableau.com/views/Datathon2025_17456919773330/Dashboard1)

---

##  Presentation

All visuals, insights, and summary slides are available in 
 [Canva Presentation](#) *([Link](https://www.canva.com/design/DAGlwVlCVwo/qXdaVok-uXooKnCkfuT6hQ/edit))*

---
## Machine Learning Model: XGBoost

An **XGBoost** model was developed to identify features that best predict product success, helping validate the importance of each metric component.

### ML Highlights:

- **Model Type:** Gradient Boosted Decision Trees (XGBoost)
- **Target Variable:** Revenue Prediction
- **Key Features Used:**
  - Quantity sold
  - Invoice count
  - Price elasticity
  - Historical growth rate
- **Evaluation Metric:** AUC, Accuracy
- **Outcome:** Prediction quality is reliable for 
MAE <5 for Quantity
MAE <10 for Revenue (very good relative to average quantity ~4000+ units and revenue ~£8000+)

