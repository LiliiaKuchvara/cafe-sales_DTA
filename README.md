# ☕ Cafe Sales Analysis

An end-to-end data analytics project focused on data cleaning, exploratory data analysis (EDA), and interactive dashboard development using Python and Tableau.

---

## 📌 Project Overview

The goal of this project is to analyze cafe sales data, evaluate product performance, explore customer purchasing patterns, and derive actionable business insights.

The project follows a complete data analytics workflow, starting with a raw dataset containing missing values and inconsistent entries, followed by data cleaning, exploratory data analysis, and interactive Tableau dashboard development.

## 🎯 Project Objectives

- Inspect and assess the quality of raw sales data.
- Clean and prepare the dataset for analysis.
- Analyze revenue and quantity sold by product.
- Explore sales by payment method and location.
- Identify monthly, daily, and weekday sales patterns.
- Analyze transaction outliers using the IQR method.
- Investigate correlations between numerical variables.
- Build interactive Tableau dashboards to communicate business insights.

## 🛠 Tools & Technologies

| Category | Tools |
|---|---|
| Programming Language | Python |
| Data Analysis | Pandas, NumPy |
| Data Visualization | Matplotlib |
| Environment | Jupyter Notebook, Google Colab |
| Dashboarding | Tableau Public |
| Version Control | GitHub |

## 📂 Dataset

The original dataset, **Cafe Sales — Dirty Data for Cleaning Training**, is sourced from Kaggle.

[View Dataset on Kaggle](https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training)

The raw dataset contains **10,000 transactions and 8 columns**:

- Transaction ID
- Item
- Quantity
- Price Per Unit
- Total Spent
- Payment Method
- Location
- Transaction Date

The dataset intentionally contains missing values and inconsistent entries, including `ERROR` and `UNKNOWN` placeholders.

## 🧹 Data Cleaning & Preparation

The data preparation process included:

- Inspecting data types, invalid entries, and missing values.
- Checking for duplicate rows and repeated transaction IDs.
- Replacing `ERROR` and `UNKNOWN` placeholders with missing values during cleaning.
- Converting numerical columns and transaction dates to appropriate data types.
- Reconstructing missing numerical values using available transaction information.
- Recovering some missing product names using price patterns and observed product distributions.
- Retaining unidentified payment methods and locations as `Unknown`.
- Removing records with missing critical values.
- Creating additional time-based features, including month, weekday, and weekend indicators.
- Creating an `item_guessed` flag to identify reconstructed product names.

### Cleaning Results

| Metric | Result |
|---|---:|
| Original Records | 10,000 |
| Final Records | 9,514 |
| Removed Records | 486 (4.86%) |
| Original Columns | 8 |
| Final Columns | 14 |
| Missing Values After Cleaning | 0 |
| Reconstructed Product Names | 450 |

## 📊 Exploratory Data Analysis & Key Findings

### 1. Business KPIs

| KPI | Result |
|---|---:|
| Total Revenue | $84,868.50 |
| Total Transactions | 9,514 |
| Average Check | $8.92 |
| Total Units Sold | 28,744 |
| Top Product by Revenue | Salad |
| Salad Revenue | $18,220 |

### 2. Product Performance

- Salad generated the highest revenue, with **$18,220**, accounting for approximately **21.47%** of total revenue.
- Sandwich and Smoothie were the next highest revenue-generating products.
- Coffee had the highest quantity sold, with **3,766 units**.

### 3. Payment Method & Location Analysis

- Among identified payment methods, Digital Wallet generated the highest revenue, although the difference from Cash was very small.
- Unknown payment methods account for approximately **31.02%** of total revenue.
- Among identified locations, In-store accounted for approximately **50.46%** of revenue, while Takeaway accounted for **49.54%**.
- Unknown locations account for approximately **39.63%** of total revenue.

### 4. Sales Trends

- June recorded the highest monthly revenue (**$7,353**).
- February recorded the lowest monthly revenue (**$6,644**).
- Tuesday had the highest average check (**$9.20**).
- Wednesday had the lowest average check (**$8.72**).
- Average check was almost identical on weekdays (**$8.93**) and weekends (**$8.89**).

### 5. Outlier Analysis

The Interquartile Range (IQR) method was used to identify unusual transaction values.

- **259 outlier transactions** were identified, representing approximately **2.72%** of all transactions.
- All identified outliers were Salad purchases with a transaction value of **$25**.
- These transactions were reviewed in context and retained, as they represent valid purchases rather than confirmed data errors.

### 6. Correlation Analysis

The correlation matrix was used to investigate relationships between quantity, unit price, and total spending.

| Variables | Correlation |
|---|---:|
| Quantity & Price Per Unit | 0.01 |
| Quantity & Total Spent | 0.70 |
| Price Per Unit & Total Spent | 0.65 |

The results indicate:

- A negligible relationship between quantity and unit price.
- A strong positive relationship between quantity and total transaction value.
- A moderately strong positive relationship between unit price and total spending.

---

## 📈 Tableau Dashboards

Two interactive dashboards were developed in Tableau to present the results of the analysis from different business perspectives.

### 1. Sales Overview

Provides a high-level view of cafe performance, including:

- Total Revenue
- Total Transactions
- Average Check
- Revenue by Product
- Revenue by Location
- Revenue by Month
- Revenue by Payment Method


### 2. Sales Patterns & Insights

Focuses on sales dynamics, transaction behavior, and statistical relationships.

Includes:

- Daily Revenue & 7-Day Moving Average
- Average Check by Weekday
- Boxplot: Quantity & Total Spent
- Outlier Transactions by Product
- Correlation Heatmap


**[View Interactive Dashboards on Tableau Public](https://public.tableau.com:9443/views/Cafe_Sales_EDA_Dashboard/SalesOverview?:language=de-DE&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---

## ⚠️ Data Limitations

- Some product names were reconstructed and are identified using the `item_guessed` flag.
- Missing payment methods and locations are retained as `Unknown`.
- Reconstructed values are based on available information and assumptions, so they should not be treated as fully verified original values.
- Statistical outliers were reviewed in context rather than automatically removed.
- The findings should be interpreted with these data quality limitations in mind.

## ## 📁 Repository Structure

```text
cafe_sales/
│
├── data/
│   ├── cafe_sales_clean(O).csv
│   └── dirty_cafe_sales.csv
│
├── notebooks/
│   ├── eda_cafe_sales.ipynb
│   └── requirements.txt
│
├── tableau/
│   └── dashboard.twbx
│
└── README.md
```

## 💡 Conclusion

This project demonstrates an end-to-end data analytics workflow, from raw data inspection and cleaning to exploratory data analysis and interactive Tableau dashboard development.

The analysis highlights product performance, payment and location patterns, sales trends, transaction outliers, and relationships between numerical variables.

It also demonstrates the importance of data quality, transparent assumptions, and careful interpretation when transforming raw data into meaningful business insights.
