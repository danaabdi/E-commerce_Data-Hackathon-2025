 
# 🛒 Modecraft Ecommerce Data Analysis Project

## Project Overview

As part of the **6th DubsTech Datathon**, this project focuses on analyzing transactional data from **Modecraft**, an e-commerce store offering a wide range of household items.

The goal was to identify high-performing products, uncover purchasing behavior trends, and support data-driven decision-making through a combination of analytics, visualization, and machine learning.

### Project Components

- 🧹 **Data Cleaning & Preparation** – using Python (Pandas) to clean and normalize raw data
- 🧮 **KPI Development** – creation of a custom **Product Health Score** to rank products based on revenue, quantity sold, and purchase frequency
- 📊 **Data Visualization** – interactive Tableau dashboard to explore metrics, trends, and rankings
- 🤖 **Machine Learning** – XGBoost model to validate key performance drivers and predict high-potential products

---

> This project showcases a full data pipeline: from data wrangling to insights to machine learning — all centered around real-world e-commerce operations.


---

##  Data Description

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

##  Data Cleaning Process

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
## New KPI: Product Health Score

The **Product Health Score** is a weighted composite metric created to evaluate product performance across three key dimensions:

Product Health Score =
(0.5 × Normalized Revenue) +
(0.3 × Normalized Quantity Sold) +
(0.2 × Normalized Invoice Count)

- **Revenue (50%)** — Profitability is the top priority.
- **Quantity Sold (30%)** — Popularity and demand matter.
- **Invoice Count (20%)** — Measures repeat purchases or transaction frequency.

> This metric allows Modecraft to prioritize products that not only generate high revenue but also show consistent customer purchase behavior.




##  Files in this Repository

- `Datathon_2025.ipynb`:  
  Jupyter notebook containing all the Python code used for data cleaning.  
  Outputs a cleaned `.csv` at the end.

## 🔗 View Dashboard

👉 [Click here to view the Tableau dashboard](https://public.tableau.com/views/Datathon2025_17456919773330/Dashboard1)

---

##  Additional Visuals

All visuals, insights, and summary slides are available in our  
 [Canva Presentation](#) *([Link](https://www.canva.com/design/DAGlwVlCVwo/qXdaVok-uXooKnCkfuT6hQ/edit))*

---

