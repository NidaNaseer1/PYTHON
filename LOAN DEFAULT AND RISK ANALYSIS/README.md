# Financial Risk and Loan Default Analysis (EDA)

Exploratory Data Analysis (EDA) on a loan dataset to find which borrower and loan characteristics are linked to **loan default**. Built with **Python** in a Jupyter Notebook.

## Objective

To clean the loan data and identify the factors that increase default risk, so that lenders can make better approval and pricing decisions. The analysis compares the **default rate** across loan grade, loan amount, income, purpose, term, credit utilisation and debt-to-income ratio.

## Tools and Libraries

- **Python 3**
- **Pandas, NumPy**: data cleaning and analysis
- **Matplotlib, Seaborn**: visualisation
- **Jupyter Notebook**

## Dataset

- **File:** `loan_train.csv` from kaggle
- **Size:** 27,003 loans and 47 columns
- **Target column:** `loan_status` (0 = Fully Paid, 1 = Charged Off / Default)
- **Class split:** 85.27% fully paid (23,026) and 14.73% charged off (3,977), so the data is **imbalanced**

## Project Workflow

**1. Data understanding**
- Checked shape, columns, data types and summary statistics

**2. Data cleaning**
- Checked missing values (count and percentage) and duplicates (none found)
- Dropped columns with very high missing values: `mths_since_last_delinq` (64.42%) and `mths_since_last_record` (92.82%)
- Filled missing text columns with the **mode** and `pub_rec_bankruptcies` with the **median**
- Detected **790 outliers** in `loan_amnt` using the IQR method (box plot)

**3. Default analysis**
- Loan status distribution
- Average interest rate by loan status
- Default rate by grade, loan amount group, income group, purpose, term, revolving credit utilisation and debt-to-income ratio (DTI)

## Key Findings

| Factor | Finding |
|---|---|
| Overall | **14.73%** of loans defaulted. |
| Interest rate | Defaulted loans have a higher average rate (**13.82%**) than fully paid loans (**11.59%**). |
| Loan grade | Default rate rises steadily from **6.11% (Grade A)** to **34.25% (Grade G)**. |
| Loan amount | Higher loan amounts default more: 13.41% (Low) up to **21.82%** (Very High). |
| Income | Lower income means higher default: **18.24%** (Low) vs. **11.24%** (Very High income). |
| Purpose | **Small business** loans are the riskiest (**27.03%**). Lowest are wedding (10.42%), car (10.13%) and major purchase (10.74%). |
| Loan term | **60-month** loans default at **25.48%**, more than double the 36-month loans (**11.24%**). |
| Credit utilisation | Default rises from **10.24%** (Low) to **19.41%** (Very High). |
| Debt-to-income | Default rises from **12.53%** to **16.78%** as DTI increases. |

## Business Recommendations

- Apply stricter checks or higher pricing for **lower grades (E, F, G)**, **60-month loans** and **small business loans**.
- Be careful with **very high loan amounts** and borrowers with **high credit utilisation** or **high DTI**.
- Use grade, term, income and credit utilisation together in a risk-scoring approach.

## How to Run

1. Clone this repository.
2. Install the requirements: `pip install numpy pandas matplotlib seaborn jupyter`
3. Update the file path in the notebook to point to your copy of `loan_train.csv`.
4. Open `Financial_Risk___Loan_Analysis.ipynb` and run all cells.

## Project Structure

```
├── Financial_Risk___Loan_Analysis.ipynb
├── loan_train.csv
└── README.md
```

## Future Improvements

- Correlation heatmap of numeric features
- Build a default prediction model (Logistic Regression, Random Forest) and handle class imbalance
- Analyse default rate by state and employment length

