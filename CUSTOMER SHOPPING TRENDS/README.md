# Customer Shopping Trends Analysis (EDA)

Exploratory Data Analysis (EDA) on customer shopping data to understand what customers buy, how much they spend, and how purchases vary by category, gender, season, age and payment method. Built with **Python** in a Jupyter Notebook.

## Objective

To find shopping patterns and turn them into simple business insights and decisions, such as:

- Which categories and items sell the most
- How much customers typically spend
- How shopping differs by gender, season, age and payment method
- How customer satisfaction (review rating) varies by category

## Tools and Libraries

- **Python 3**
- **Pandas, NumPy**: data loading and analysis
- **Matplotlib, Seaborn**: visualisation
- **Jupyter Notebook**

## Dataset

- **File:** `shopping_trends.csv` from kaggle
- **Size:** 3,900 records and 19 columns
- **Columns:** Customer ID, Age, Gender, Item Purchased, Category, Purchase Amount (USD), Location, Size, Color, Season, Review Rating, Subscription Status, Payment Method, Shipping Type, Discount Applied, Promo Code Used, Previous Purchases, Preferred Payment Method, Frequency of Purchases
- **Data quality:** no missing values and no duplicate rows

## Analysis Performed

- Dataset overview: shape, columns, data types, summary statistics
- Missing value and duplicate checks
- Category-wise purchase count
- Top 10 most purchased items
- Purchase amount distribution
- Gender-wise shopping
- Payment method analysis
- Season-wise shopping
- Age distribution, including age groups (18-25, 26-35, 36-45, 46-55, 56-70)
- Average purchase by category and by payment method
- Subscription status analysis
- Average review rating by category

## Key Findings

| Area | Finding |
|---|---|
| Category | **Clothing** is the most purchased category (1,737), followed by Accessories (1,240). Outerwear is the lowest (324). |
| Top items | Blouse, Jewelry and Pants lead with 171 purchases each. |
| Purchase amount | Average is about **$59.76**, ranging from $20 to $100. |
| Gender | **Male 68%** (2,652) and **Female 32%** (1,248) of records. |
| Payment method | Credit Card is highest (696) and Bank Transfer lowest (632), a small gap. |
| Season | Spread almost equally: Spring 25.6%, Fall 25.0%, Winter 24.9%, Summer 24.5%. |
| Age | Customers are aged 18 to 70 (average about 44). The 56-70 group is the largest (1,105), though it also covers a wider age range than the other groups. |
| Subscription | **73%** of customers are not subscribed (2,847 No vs. 1,053 Yes). |

## Business Recommendations

- Focus promotions and stock on **Clothing and Accessories**, and offer deals to lift **Outerwear** sales.
- Plan promotions **throughout the year**, as shopping stays steady across seasons.
- Create offers and bundles around the **~$60 average spend**.
- Keep **multiple payment options** available.
- Run targeted campaigns for male and female customers, and use age-group information for recommendations.
- Encourage the large non-subscribed group to subscribe.

## How to Run

1. Clone this repository.
2. Install the requirements: `pip install numpy pandas matplotlib seaborn jupyter`
3. Update the file path in the notebook to point to your copy of `shopping_trends.csv`.
4. Open `Customer_Shopping_Trends.ipynb` and run all cells.

## Project Structure

```
├── Customer_Shopping_Trends.ipynb
├── shopping_trends.csv
└── README.md
```

