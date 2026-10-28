# Customer Churn, Cohort & Retention Analysis

## Project Overview

This project explores customer churn patterns using subscription, transaction, and demographic data from the KKBOX dataset. Using Python, Pandas, NumPy, Matplotlib, and Seaborn, the analysis investigates customer segments and transaction behaviours associated with churn.

The goal is to derive actionable insights that can help inform customer retention strategies.

## Business Objectives

- Measure the overall customer churn rate.
- Identify customer segments with higher observed churn.
- Explore churn patterns across demographic and customer attributes.
- Investigate payment and auto-renewal behaviour.
- Compare monthly transaction activity across customer cohorts.
- Develop data-driven recommendations for further retention analysis.

## Tools & Technologies

- **Language:** Python
- **Data Analysis:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook

## Dataset

The project uses three datasets:

| Dataset | Description |
|---|---|
| `train_v2.csv` | Customer churn labels |
| `members_v3.csv` | Customer demographic and registration information |
| `transactions_v2.csv` | Subscription and payment history |

The raw CSV files are not included in this repository due to their size. They can be obtained from the [KKBOX Churn Prediction dataset on Kaggle](https://www.kaggle.com/competitions/kkbox-churn-prediction-challenge/data). Download the required files and place them in `Data/Raw/` before running the notebook.

The analysis uses the labelled customer population as its base and enriches it with available demographic and transaction information.

## Analysis Performed

- Data loading, structure inspection, and data quality checks
- Duplicate and customer ID consistency checks
- Missing and invalid value handling
- Customer-level transaction feature engineering
- Overall churn rate calculation
- Churn comparisons by transaction history, gender, age group, auto-renewal behaviour, registration method, and city
- Payment behaviour comparison between churned and retained customers
- Cohort-based analysis of monthly transaction activity

## Key Findings

- **Overall churn:** The observed churn rate was 8.99% across 970,960 labelled customers.
- **Transaction history:** Customers without matching transaction records had a churn rate of 78.74%, compared with 6.20% among customers with recorded transaction history.
- **Age:** Younger age groups showed higher observed churn rates than older groups.
- **Auto-renewal:** Customers whose recorded transactions consistently had auto-renew enabled had a churn rate of 3.79%, compared with 30.73% among customers whose transactions did not always have auto-renew enabled.
- **Payment behaviour:** Churned customers had a higher mean average payment, although the median was the same for both groups.
- **Customer segments:** Churn rates varied across recorded city and registration-method codes.

These findings describe associations in the available data and should not be interpreted as evidence of causation.

## Limitations

- Missing transaction records do not necessarily mean a customer never transacted.
- Transaction-derived features summarize the available historical data and may not represent behaviour immediately before churn.
- City and registration-method values are categorical codes whose meanings have not been verified.
- Cohort analysis measures observed monthly transaction activity, not confirmed subscription retention.
- The findings are based on historical data and may not represent current customer behaviour.

## Project Structure

```text
Customer Churn & Retention Analysis/
├── Data/
│   └── Raw/
│       ├── members_v3.csv
│       ├── train_v2.csv
│       └── transactions_v2.csv
├── Notebook/
│   └── customer_churn_retention_analysis.ipynb
└── README.md
```

## How to Run

1. Clone or download the repository.
2. Install Python and Jupyter Notebook.
3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

4. Download the required CSV files from the dataset source above and place them in `Data/Raw/`.
5. Open `Notebook/customer_churn_retention_analysis.ipynb` in Jupyter Notebook.
6. Run the cells in order.

The notebook uses relative file paths, making it easier to reproduce the analysis when the project folder structure is preserved.

## Conclusion

This project demonstrates an end-to-end exploratory data analysis workflow, from data quality checks and feature engineering to churn comparisons, cohort-based transaction analysis, and business recommendations. It highlights how customer-level data can be used to investigate churn patterns while accounting for data limitations.
