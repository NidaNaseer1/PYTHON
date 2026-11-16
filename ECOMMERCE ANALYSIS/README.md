# E-Commerce Sales Analysis using Python

An exploratory data analysis (EDA) of 5,000 e-commerce orders using **Python (pandas and Matplotlib)**. The project measures overall sales performance, finds the top categories, regions, payment methods and customers, and studies monthly trends, customer ratings and delivery times.

> A Power BI dashboard was also built on the same cleaned data as part of this project.

## Objectives

- Check data quality (missing values, duplicates, data types)
- Calculate the key business KPIs
- Analyse revenue by category, region, payment method and month
- Identify the highest-value customers
- Understand customer satisfaction and delivery performance

## Dataset

**File:** `ecommerce_sales_analytics.csv` (5,000 rows, 12 columns)

| Column | Description |
|---|---|
| `order_id` | Unique order number |
| `order_date` | Date of the order |
| `customer_id` | Customer identifier |
| `product_category` | Electronics, Clothing, Home, Beauty |
| `region` | East, West, North, South |
| `quantity` | Units ordered (1 to 7) |
| `unit_price` | Price per unit |
| `discount` | Discount applied (0 to 0.35) |
| `payment_method` | Card, COD, Wallet |
| `delivery_days` | Days taken to deliver (1 to 11) |
| `customer_rating` | Rating given by the customer (1 to 5) |
| `revenue` | Order revenue |

## Tools and Libraries

- Python 3
- pandas
- Matplotlib
- Jupyter Notebook

## Analysis Steps

1. **Load data** with `pd.read_csv()` and inspect with `head()`, `shape`, `info()` and `describe()`
2. **Data quality check:** 0 missing values and 0 duplicate rows
3. **Data preparation:** convert `order_date` to datetime and extract `month`
4. **Revenue analysis** using `groupby()` by category, region, payment method and month
5. **Customer analysis:** top 10 customers by total revenue
6. **Satisfaction and delivery:** average rating by category, average delivery days by region
7. **KPI calculation:** total revenue, orders, customers, quantity and average order value
8. **Export** the cleaned dataset to `Ecommerce_Cleaned_Data.csv`

## Key KPIs

| KPI | Value |
|---|---|
| Total Revenue | 51,09,775.74 |
| Total Orders | 5,000 |
| Total Customers | 989 |
| Total Quantity Sold | 20,224 |
| Average Order Value | 1,021.96 |
| Average Customer Rating | 2.97 / 5 |
| Average Delivery Time | 6.12 days |

## Results

**Revenue by Product Category**

| Category | Revenue | Share |
|---|---|---|
| Electronics | 18,29,899 | 35.8% |
| Clothing | 15,31,932 | 30.0% |
| Home | 9,82,084 | 19.2% |
| Beauty | 7,65,861 | 15.0% |

**Revenue by Region:** West 13,45,582 | North 12,81,508 | South 12,46,641 | East 12,36,044

**Revenue by Payment Method:** Card 23,66,248 (46.3%) | COD 17,88,408 (35.0%) | Wallet 9,55,119 (18.7%)

**Top 5 Customers by Revenue:** 1663 (17,681), 1955 (16,265), 1675 (15,036), 1276 (15,024), 1647 (14,895)

## Key Insights

- **Electronics and Clothing** together bring in about 66% of total revenue.
- **West** is the top region, but the four regions are close (12.4L to 13.5L), so there is no weak region.
- **Card** is the most-used payment method, and **COD** still contributes 35% of revenue.
- **Monthly trend:** May has the highest revenue (4.80L) and April the lowest (3.99L). Months are grouped by calendar month across all years in the data.
- **Ratings** are almost identical across categories (2.94 to 3.01 out of 5), which suggests customer satisfaction is low-to-average everywhere and needs improvement.
- **Delivery** averages about 6.1 days with almost no difference between regions (6.08 to 6.17 days).
- Each customer places about 5 orders on average (5,000 orders / 989 customers).

## Visualisations

- Bar chart: Revenue by Product Category
- Bar chart: Revenue by Region
- Bar chart: Revenue by Payment Method
- Line chart: Monthly Revenue Trend
- Horizontal bar chart: Top 10 Customers by Revenue
- Bar chart: Average Customer Rating by Category
- Bar chart: Average Delivery Days by Region

## Repository Structure

```
├── ecommerce_sales_analytics.csv     # Raw dataset
├── Ecommerce_Analysis.ipynb          # Analysis notebook
├── Ecommerce_Cleaned_Data.csv        # Cleaned output
├── images/                           # Chart screenshots
└── README.md
```

## How to Run

```bash
git clone https://github.com/your-username/ecommerce-analysis-python.git
cd ecommerce-analysis-python
pip install pandas matplotlib jupyter
jupyter notebook Ecommerce_Analysis.ipynb
```

Before running, update the file path in the notebook to match your system:

```python
df = pd.read_csv("ecommerce_sales_analytics.csv")
```

## Future Improvements

- Repeat-customer rate and RFM customer segmentation
- Effect of discount on revenue and rating
- Late-delivery percentage and its impact on ratings
- Sales forecasting with a time-series model

s://github.com/your-username)
