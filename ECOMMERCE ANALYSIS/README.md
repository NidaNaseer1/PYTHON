# E-Commerce Sales Analysis using Python

An exploratory data analysis (EDA) project on 5,000 e-commerce orders, built with Python. It covers revenue, categories, regions, payment methods, customers, ratings and delivery performance, and turns them into clear business insights.

## Project Objective

- Clean and prepare raw e-commerce order data
- Measure overall business performance (revenue, orders, customers, quantity)
- Find the top categories, regions, payment methods and customers
- Study monthly sales trends and seasonality
- Understand customer satisfaction and delivery performance

## Dataset

- **File:** `Ecommerce_Cleaned_Data.xls`
- **Records:** 5,000 orders
- **Main fields used:** Order Date, Customer ID, Product Category, Region, Payment Method, Quantity, Revenue, Customer Rating, Delivery Days

## Tools and Libraries

- Python 3
- pandas and NumPy for data cleaning and analysis
- Matplotlib and Seaborn for visualisation
- Jupyter Notebook

## Analysis Workflow

1. **Data loading:** read the Excel file into a pandas DataFrame
2. **Data cleaning:** check missing values, duplicates and data types; convert `Order Date` to datetime
3. **Feature engineering:** extract month and month name; calculate Average Order Value
4. **KPI calculation:** total revenue, orders, customers, quantity sold
5. **Group-by analysis:** revenue by category, region, payment method and month
6. **Customer analysis:** top 10 customers by revenue
7. **Operations analysis:** average rating by category, average delivery days by region
8. **Visualisation and insights**

## Key Results

| Metric | Value |
|---|---|
| Total Revenue | ₹51,09,776 |
| Total Orders | 5,000 |
| Total Customers | 989 |
| Total Quantity Sold | 20,224 |
| Average Order Value | ~₹1,022 |

## Key Insights

- **Electronics** is the top category with about 36% of revenue (₹18.30L), followed by Clothing (~30%), Home (~19%) and Beauty (~15%).
- **West** is the top region (₹13.46L); all four regions are close (₹12.36L to ₹13.46L).
- **Payment mix:** Card is the largest share (~46%), then COD (35%) and Wallet (~19%).
- **Seasonality:** revenue peaks in May (₹4.80L) and is lowest in April (₹3.99L).
- **Ratings** are almost the same across categories (2.94 to 3.01 out of 5), so customer satisfaction has room to improve.
- **Delivery time** averages about 6.1 days, with very little difference between regions.
- **Customer 1663** is the top customer, with about ₹17,681 in revenue.

## Visualisations

- Bar chart: Revenue by Category
- Pie/Donut chart: Revenue by Payment Method
- Bar chart: Revenue by Region
- Line chart: Monthly Revenue Trend
- Horizontal bar chart: Top 10 Customers
- Bar charts: Average Rating by Category, Average Delivery Days by Region

## Project Structure

```
├── Ecommerce_Cleaned_Data.xls        # Dataset
├── Ecommerce_Analysis.ipynb          # Python analysis notebook
├── images/                           # Saved charts
└── README.md
```

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/ecommerce-analysis-python.git
cd ecommerce-analysis-python

# 2. Install the required libraries
pip install pandas numpy matplotlib seaborn xlrd jupyter

# 3. Open the notebook
jupyter notebook Ecommerce_Analysis.ipynb
```

## Sample Code

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_excel("Ecommerce_Cleaned_Data.xls")
df["Order Date"] = pd.to_datetime(df["Order Date"])

# Revenue by category
cat_rev = df.groupby("Product Category")["Revenue"].sum().sort_values(ascending=False)
cat_rev.plot(kind="bar", title="Revenue by Category")
plt.ylabel("Revenue (₹)")
plt.show()

# Monthly revenue trend
monthly = df.groupby(df["Order Date"].dt.month)["Revenue"].sum()
monthly.plot(marker="o", title="Monthly Revenue Trend")
plt.show()
```

## Future Improvements

- Repeat-customer rate and customer segmentation (RFM analysis)
- Late-delivery percentage and its effect on ratings
- Sales forecasting with a time-series model


[LinkedIn](https://linkedin.com/in/your-profile) | [GitHub](https://github.com/your-username)
