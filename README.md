# BCG X Data Science Simulation — Task 3: EDA & Data Cleaning

Exploratory data analysis and data cleaning performed on PowerCo client and pricing
data as part of the BCG X (Forage) Data Science Virtual Experience.

## Objective
PowerCo, a major energy utility, is losing customers to churn. This notebook explores
customer profile data and historical pricing data to surface early patterns —
particularly around price sensitivity — ahead of feature engineering and predictive
modeling in later stages of the simulation.

## What's in this repo

### Task 3 — EDA & Data Cleaning (`Task 2 - eda_starter.ipynb`)
- Data type review and summary statistics for both datasets
- Missing value and duplicate checks
- Churn baseline and churn broken down by: sales channel, contract type (`has_gas`),
  number of active products, customer tenure, and origin/contract offer
- Distribution and outlier (boxplot) analysis of consumption, forecast, margin, and
  subscribed power columns
- Correlation heatmap across numeric client features
- Price data exploration and datetime cleaning
- Aggregation and merge of price history onto the client table

### Task 4 — Feature Engineering (`Task 3 - feature_engineering.ipynb`)
- Price-sensitivity features: Dec-vs-January off-peak diff, average and maximum
  price differences across pricing periods (off-peak/peak/mid-peak)
- Customer tenure and month-based date features (from a fixed reference date)
- Boolean and one-hot encoding of categorical columns, with rare categories filtered out
- Log-transformation of right-skewed consumption/forecast columns
- Correlation-driven removal of redundant columns
- Custom ratio features: consumption-vs-forecast gap, margin-per-consumption
- Final engineered dataset: 67 columns, 0 missing values, ready for modeling

### Task 5 — Modeling and Evaluation (`Task 4 - modeling_starter.ipynb`)
- Trained a Random Forest classifier (n_estimators=1000) on a 75/25 train-test split
- Evaluated using accuracy, precision, recall, F1, and a confusion matrix — not
  accuracy alone, since churn is imbalanced (~9.7%)
- **Key finding:** despite 90.4% accuracy, recall is only 4.6% — the model misses
  349 of 366 actual churners in the test set and is not yet production-ready
- Feature importance confirms consumption and margin (not price sensitivity) are
  the leading churn drivers, contradicting the client's original hypothesis
- Recommended next steps: address class imbalance (class weighting, SMOTE, or
  threshold tuning) before deployment

### Task 6 — Insights and Recommendations (`Executive_Summary.pdf`)
- One-slide SCQA executive summary for the steering committee
- Leads with the actionable recommendation: target retention on consumption and
  margin rather than price, and refine the model before relying on it operationally

## Datasets
`client_data.csv` and `price_data.csv` are provided by Forage for simulation use only
and are **not included in this repository**. See `Data Description.pdf` (also excluded)
for full column definitions, summarized below:

**client_data.csv** — customer profile: consumption history, forecasts, margins,
contract details, and churn label (26 columns, ~14.6k rows)

**price_data.csv** — monthly historical energy and power prices per client
(8 columns, ~193k rows)

## Tools
Python · pandas · numpy · matplotlib · seaborn · Jupyter

## Status
✅ EDA & Data Cleaning complete
✅ Feature Engineering complete
✅ Modeling and Evaluation complete
✅ Insights and Recommendations complete — project finished end to end.