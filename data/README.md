# Data

This folder contains the Telco Customer Churn dataset.

## Source

**Dataset**: Telco Customer Churn from Kaggle  
**URL**: https://www.kaggle.com/datasets/blastchar/telco-customer-churn

## Files

- `raw/WA_Fn-UseC_-Telco-Customer-Churn.csv` - Original dataset (7,043 rows, 21 columns)

## Description

The dataset includes information about:
- Customer demographics (gender, age, dependents)
- Service subscriptions (phone, internet, streaming, etc.)
- Contract details (type, tenure)
- Billing information (monthly charges, payment method)
- Churn status (Yes/No)

## Usage

Load the dataset in the analysis notebook:
```python
import pandas as pd
df = pd.read_csv('data/raw/WA_Fn-UseC_-Telco-Customer-Churn.csv')
```
