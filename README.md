# ☕ Cafe Sales Analysis

An end-to-end data analytics project focused on cleaning, exploring, and visualizing cafe sales data using Python and Tableau.

## 📌 Project Overview

The goal of this project is to analyze cafe sales, evaluate product performance, explore customer purchasing patterns, and derive actionable business insights.

The project follows a complete data analytics workflow, starting with a raw dataset containing missing values and inconsistent entries, followed by data cleaning, exploratory data analysis (EDA), and interactive Tableau dashboard development.

## 🎯 Objectives

- Inspect and assess the quality of raw sales data.
- Clean and prepare the dataset for analysis.
- Analyze revenue and quantity sold by product.
- Explore sales by payment method and location.
- Identify monthly, daily, and weekday sales patterns.
- Analyze transaction outliers using the IQR method.
- Investigate correlations between numerical variables.
- Build interactive Tableau dashboards to communicate business insights.

## 🛠 Tools & Technologies

- **Python:** Pandas, NumPy
- **Visualization:** Matplotlib
- **Environment:** Jupyter Notebook / Google Colab
- **Dashboarding:** Tableau Public
- **Version Control:** GitHub

## 📂 Dataset

The original dataset, **Cafe Sales — Dirty Data for Cleaning Training**, is sourced from Kaggle.

[Dataset on Kaggle](https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training)

The raw dataset contains 10,000 transactions and 8 columns:

- Transaction ID
- Item
- Quantity
- Price Per Unit
- Total Spent
- Payment Method
- Location
- Transaction Date

The dataset intentionally contains missing values and inconsistent entries, including `ERROR` and `UNKNOWN` placeholders.

## 🧹 Data Cleaning

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
| Original records | 10,000 |
| Final records | 9,514 |
| Removed records | 486 (4.86%) |
| Original columns | 8 |
| Final columns | 14 |
| Missing values after cleaning | 0 |
| Reconstructed product names | 450 |

## 📊 Key Findings

### Business KPIs

| KPI | Result |
|---|---:|
| Total Revenue | $84,868.50 |
| Total Transactions | 9,514 |
| Average Check | $8.92 |
| Total Units Sold | 28,744 |
| Top Product by Revenue | Salad |
| Salad Revenue | $18,220 |

### Product Performance

- Salad generated the highest revenue, with **$18,220**, accounting for approximately **21.47%** of total revenue.
- Sandwich and Smoothie were the next highest revenue-generating products.
- Coffee had the highest quantity sold, with 3,766 units.

### Payment Method & Location

- Among identified payment methods, Digital Wallet generated the highest revenue, although the difference from Cash was very small.
- Unknown payment methods account for approximately 31.02% of total revenue.
- Among identified locations, In-store accounted for approximately 50.46% of revenue, while Takeaway accounted for 49.54%.
- Unknown locations account for approximately 39.63% of total revenue.

### Sales Trends

- June recorded the highest monthly revenue (**$7,353**).
- February recorded the lowest monthly revenue (**$6,644**).
- Tuesday had the highest average check (**$9.20**).
- Wednesday had the lowest average check (**$8.72**).
- Average check was almost identical on weekdays (**$8.93**) and weekends (**$8.89**).

### Outlier Analysis

- The IQR method identified **259 outlier transactions**, representing approximately **2.72%** of all transactions.
- All identified outliers were Salad purchases with a transaction value of **$25**.
- These transactions were reviewed in context and retained, as they represent valid purchases rather than confirmed data errors.

### Correlation Analysis

The correlation matrix revealed:

| Variables | Correlation |
|---|---:|
| Quantity & Price Per Unit | 0.01 |
| Quantity & Total Spent | 0.70 |
| Price Per Unit & Total Spent | 0.65 |

The results indicate a strong positive relationship between quantity and total transaction value, as well as a moderately strong positive relationship between unit price and total spent.

## 📈 Tableau Dashboards

Interactive Tableau visualizations were developed to explore business performance and sales patterns.

## 📊 Tableau Dashboards

The project includes two interactive Tableau dashboards developed to explore cafe sales performance and uncover business insights.

### 1. Sales Overview

Provides a high-level view of business performance, including total revenue, number of transactions, average check, product revenue, revenue by location, monthly revenue, and payment method distribution.

![Sales Overview](screenshots/sales-overview.png)

### 2. Sales Patterns & Insights

Explores daily revenue trends, the 7-day moving average, average check by weekday, transaction outliers, and correlations between quantity, unit price, and total spending.

![Sales Patterns & Insights](screenshots/sales-patterns.png)

### 1. Sales Overview

- Key business KPIs
- Revenue by product
- Revenue by location
- Revenue by payment method
- Monthly revenue
- Product quantity analysis

### 2. Sales Patterns & Insights

- Daily Revenue & 7-Day Moving Average
- Average Check by Weekday
- Boxplot: Quantity & Total Spent
- Outlier Transactions by Product
- Correlation Heatmap

[View Tableau Dashboard on Tableau Public](https://public.tableau.com:9443/views/Cafe_Sales_EDA_Dashboard/SalesOverview?:language=de-DE&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## ⚠️ Data Limitations

- Some product names were reconstructed and are identified using the `item_guessed` flag.
- Missing payment methods and locations are retained as `Unknown`.
- Reconstructed values are based on available information and assumptions, so they should not be treated as fully verified original values.
- Statistical outliers were reviewed in context rather than automatically removed.
- The findings should be interpreted with these data quality limitations in mind.

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

This project demonstrates an end-to-end data analytics workflow, from raw data inspection and cleaning to exploratory data analysis and interactive Tableau dashboard development.

The analysis highlights product performance, payment and location patterns, sales trends, transaction outliers, and relationships between numerical variables.

It also demonstrates the importance of data quality, transparent assumptions, and careful interpretation when transforming raw data into meaningful business insights.
