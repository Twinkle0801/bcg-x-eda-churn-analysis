# BCG X Data Science Simulation — Task 3: EDA & Data Cleaning

Exploratory data analysis and data cleaning performed on PowerCo client and pricing
data as part of the BCG X (Forage) Data Science Virtual Experience.

## Objective
PowerCo, a major energy utility, is losing customers to churn. This notebook explores
customer profile data and historical pricing data to surface early patterns —
particularly around price sensitivity — ahead of feature engineering and predictive
modeling in later stages of the simulation.

## What's in this notebook
- Data type review and summary statistics for both datasets
- Missing value and duplicate checks
- Churn baseline and churn broken down by: sales channel, contract type (`has_gas`),
  number of active products, customer tenure, and origin/contract offer
- Distribution and outlier (boxplot) analysis of consumption, forecast, margin, and
  subscribed power columns
- Correlation heatmap across numeric client features
- Price data exploration and datetime cleaning
- Aggregation and merge of price history onto the client table

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
✅ EDA & Data Cleaning complete — proceeding to Feature Engineering (Task 4) next.