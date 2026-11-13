# ☕ Cafe Sales Analysis

An end-to-end data analytics project focused on cleaning, exploring, and visualizing cafe sales data using Python and Tableau.

## 📌 Project Overview

The goal of this project is to analyze cafe sales, identify product performance, explore sales patterns, and derive business insights.

The original dataset contains missing values, invalid entries, and inconsistent data that require cleaning before analysis.

## 🎯 Objectives

- Clean and prepare raw sales data.
- Analyze revenue and quantity sold by product.
- Explore sales by payment method and location.
- Identify monthly, weekly, and daily sales patterns.
- Investigate relationships between transaction variables.
- Build interactive Tableau dashboards.

## 🛠 Tools & Technologies

- **Python:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook
- **Dashboarding:** Tableau Public
- **Version Control:** GitHub

## 📂 Dataset


The original dataset contains 10,000 transactions and 8 columns, including transaction ID, item, quantity, price, total spent, payment method, location, and transaction date.
(https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training)

## 🧹 Data Cleaning

The data preparation process included:

- Identifying missing values, invalid entries, and duplicates.
- Replacing `ERROR` and `UNKNOWN` placeholders where appropriate.
- Converting numeric columns and dates to correct data types.
- Reconstructing some missing numerical values using available transaction information.
- Recovering some missing product names using price patterns and observed product distributions.
- Retaining unidentified payment methods and locations as `Unknown`.
- Removing records with missing critical values.
- Creating additional time-based features.

The `item_guessed` column identifies product names reconstructed during the cleaning process.

### Cleaning Results

| Metric | Result |
|---|---:|
| Original records | 10,000 |
| Final records | 9,514 |
| Removed records | 486 (4.9%) |
| Final columns | 14 |
| Missing values after cleaning | 0 |

## 📊 Key Findings

| KPI | Result |
|---|---:|
| Total Revenue | $84,868.50 |
| Total Transactions | 9,514 |
| Average Check | $8.92 |
| Total Units Sold | 28,744 |
| Top Product by Revenue | Salad |
| Salad Revenue | $18,220 |

Additional insights:

- Salad generated the highest revenue, accounting for approximately 21.47% of total revenue.
- Digital Wallet had the highest revenue among known payment methods.
- Among known locations, In-store accounted for 50.45% of revenue and Takeaway for 49.55%.
- June recorded the highest monthly revenue ($7,353), while February recorded the lowest ($6,644).
- Average check was almost identical on weekdays ($8.93) and weekends ($8.90).

## 📈 Tableau Dashboards

Three interactive dashboards were developed:

**1. Sales Overview**
- Key business KPIs
- Revenue by month and location
- Revenue by payment method
- Units sold by item

**2. Product Performance**
- Revenue and units sold by item
- Revenue share and quantity share
- Average revenue per unit by item

**3. Sales Patterns**
- Revenue by month and weekday
- Revenue by day of week
- Weekday vs. weekend revenue
- Relationship between transaction quantity and revenue

(https://public.tableau.com/views/Cafe_Sales_EDA_Dashboard/SalesOverview?:language=de-DE&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## ⚠️ Data Limitations

- Some product names were reconstructed and are identified by the `item_guessed` flag.
- Missing payment methods and locations are retained as `Unknown`.
- Reconstructed values involve assumptions and should not be treated as fully verified original data.
- Statistical outliers were reviewed in context rather than automatically removed.

These limitations should be considered when interpreting the results.

## 📁 Repository Structure

```text
cafe_sales/
│
├── README.md
│
├── data/
│   ├── dirty_cafe_sales.csv
│   └── cafe_sales_clean.csv
│
├── tableau/
│   └── dashboard.twbx
│
└── notebooks/
    ├── eda_cafe_sales.ipynb
    └── requirements.txt
```

## 💡 Conclusion

This project demonstrates an end-to-end data analytics workflow, from data cleaning and exploratory analysis to interactive dashboard development. It highlights the importance of data quality, transparent assumptions, and careful interpretation when turning raw data into business insights.
