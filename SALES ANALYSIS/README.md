# Amazon Product Sales Analysis

An exploratory data analysis (EDA) of Amazon order data using Python. The notebook cleans the data, calculates key business metrics, and uses charts to show which products, locations and time periods drive sales and profit.

## Dataset

| Item | Details |
|---|---|
| File | `Amazon_sales.xlsx` |
| Size | 3,203 rows (order lines), 13 columns |
| Orders / Customers | 1,611 orders, 686 customers |
| Period | January 2011 to December 2014 |
| Geography | United States (West-coast and nearby states, mostly California) |

**Columns:** `Order ID`, `Order Date`, `Ship Date`, `Status`, `Customer Name`, `Country`, `City`, `Region`, `Category`, `Product Name`, `Sales`, `Quantity`, `Profit`

> **Note:** `Region` contains US states (e.g. California, Washington) and `Category` contains product sub-categories (e.g. Binders, Phones). Keep this in mind when reading the charts.

Data quality: no missing values and no duplicate rows.

## Tools Used

- Python 3
- pandas, NumPy: data handling and calculations
- Matplotlib, Seaborn: charts
- openpyxl: reading the Excel file
- Jupyter Notebook

## Project Structure

```
.
├── sales_analysis.ipynb    # Main analysis notebook
├── Amazon_sales.xlsx       # Dataset
└── README.md
```

## How to Run

1. Install the requirements:
   ```bash
   pip install pandas numpy matplotlib seaborn openpyxl jupyter
   ```
2. Put `sales_analysis.ipynb` and `Amazon_sales.xlsx` in the same folder.
3. In the notebook, update the data-loading line to point to the file, for example:
   ```python
   df = pd.read_excel("Amazon_sales.xlsx")
   ```
4. Start Jupyter and run all cells from top to bottom:
   ```bash
   jupyter notebook sales_analysis.ipynb
   ```

## What the Notebook Does

1. **Load and inspect:** shape, columns, data types, summary statistics.
2. **Data quality checks:** missing values and duplicates.
3. **Feature engineering:**
   - `Year`, `Month`, `Month Name`, `Year-Month` from the order date
   - `Shipping Days` (ship date minus order date)
   - `Profit Margin` (profit divided by sales, in percent)
   - `Profit Status` (Profit / Loss / No Profit)
4. **KPIs:** total sales, total profit, profit margin, orders, customers, quantity, average sales.
5. **Group analysis:** by category, region (state), city, product, month, order status, and top loss-making products.
6. **Visualisations:** bar charts, monthly sales trend, pie chart of order status, sales histogram, correlation heatmap.

## Key Findings

- **Overall:** about $725K in sales and $108K in profit, a margin of roughly 14.9%.
- **Growth:** sales dipped in 2012, then grew in 2013 and 2014. Profit nearly doubled in 2014 ($43.9K vs $24.0K in 2013), with margin rising to about 17.5%.
- **Location:** California accounts for about 63% of sales and Washington about 19%. Los Angeles, Seattle and San Francisco are the top three cities.
- **Loss-making categories:** Bookcases and Machines lose money overall. Tables generate about $85K in sales but only about $1.5K in profit.
- **Delivery:** about 40% of order lines are delayed (shipped in 5 to 7 days).
- **Skewed sales:** the typical (median) sale is about $61 while the average is about $226, because a few very large sales pull the average up. A single copier sale contributes about 6% of total profit.
- **Losses:** about 10% of order lines are loss-making.

## Possible Next Steps

- Deeper profit analysis for Tables, Bookcases and Machines.
- Measure how delayed orders relate to state and product category.
- Customer segmentation (repeat vs one-time buyers).
- Forecast monthly sales.
