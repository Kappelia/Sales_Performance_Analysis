# Sales Performance Analysis for Global Electronics Retailer

## Executive Summary
This project performs **Exploratory Data Analysis (EDA)** on the *Global Electronics Retailer* dataset to identify key trends in sales performance, customer behavior, and profitability across countries and product categories.  

Using **Python (Pandas, NumPy, Matplotlib)** for data cleaning, transformation, and analysis — and **Tableau** for visualization — the project prepares a clean analytical dataset and extracts business insights to support strategic decisions.

---

## Business Problem
Retail sales data often contains missing or inconsistent values, and decision-makers struggle to identify which products, stores, or months drive the most revenue.  

The main business questions are:
1. Which product categories and brands generate the highest revenue and margin?
2. How does sales performance change over time?
3. What delivery time patterns can be observed, and how do they impact revenue?

---

## Methodology (EDA Steps)
This notebook follows the 7 core steps of Exploratory Data Analysis:

| Step | Description |
|------|--------------|
| **1. Import data** | Load multiple CSV files (Sales, Products, Stores, Customers, Exchange Rates) from Google Drive. |
| **2. Analyze structure** | Check dimensions, column names, and data types. |
| **3. Handle missing values** | Identify NaNs, duplicates, and outliers. |
| **4. Data cleaning & typing** | Convert dates, numeric fields, and remove currency symbols. |
| **5. Feature engineering** | Generate delivery time metrics and impute missing delivery dates. |
| **6. Build star-schema table** | Join fact and dimension tables (`Sales`, `Products`, `Customers`, `Stores`). |
| **7. Perform EDA** | Visualize revenue and margin trends, top products, and categories. |

---

## Data Pipeline Overview
**1. Data Sources:**
- `Customers.csv` — customer demographics and locations  
- `Products.csv` — product metadata (name, brand, cost, price, subcategory)  
- `Sales.csv` — sales transactions with order and delivery dates  
- `Stores.csv` — store locations and sizes  
- `Exchange_Rates.csv` — optional currency metadata  
- `Data_Dictionary.csv` — field descriptions  

**2. Processing Steps:**
- Loaded safely via `read_csv_safely()` with encoding fallback  
- Cleaned and trimmed text fields  
- Converted `Order Date`, `Delivery Date`, and `Open Date` to datetime  
- Converted prices and quantities to numeric  
- Handled missing values in delivery dates using logical imputation  
- Removed duplicates  

**3. Output:**
- A **clean analytical dataset** ready for Tableau visualization:  
  `Prep_Tableau/analysis_table_with_delivery.csv`

---

## Key Analysis Results
### 1. Sales Over Time
![Sales over time](images/sales_over_time.png)

- Clear seasonality with sales peaks around late Q4 (holiday season)
- Gross margin follows a similar trend but with slightly lower amplitude

### 2. Top Products & Subcategories
![Top products](images/top_products.png)

- “Adventure Works Desktop PCs” and “WWII Desktop PCs” dominate total revenue  
- Subcategories *MP4&MP3*, *Audio*, and *Cameras & Accessories* drive most profit

### 3. Delivery Analysis
- 79% of delivery dates were missing and were logically imputed (+3 days after order date)
- Average delivery time (including imputations): **3.3 days**

---

## Tools & Technologies
| Category | Tools |
|-----------|-------|
| Data Preparation | Python, Pandas, NumPy, Pathlib |
| Data Cleaning | Regex, Type Conversion, Datetime handling |
| Visualization | Matplotlib, Tableau |
| Project Environment | Google Colab + Google Drive integration |

---

## Results & Business Insights
- Clean dataset prepared for Tableau dashboards  
- Identified revenue concentration among a few key product lines  
- Found delivery delay pattern (avg 3 days) influencing order frequency  
- Seasonal peaks confirm strong Q4 sales performance  

---

## Next Steps
1. Build a Tableau dashboard showing revenue and margin by category, country, and month  
2. Create an interactive filter for “Delivery Time” and “Currency”  
3. Automate monthly updates of the CSV export using Python  

---

> *Author:* [Kappelia](https://github.com/Kappelia)  
> *Project:* Sales Performance Analysis for Global Electronics Retailer  
> *Environment:* Google Colab + Tableau
> *Requirements:* Pandas, Numpy, Matplotlib, Pathlib

