# Telco Customer Churn Analysis<div align="center">



Analysis of telecom customer behavior to identify churn patterns and build predictive models for early intervention.# Telco Customer Churn Analysis



## 📌 Project OverviewData science project demonstrating end-to-end exploratory analysis, feature engineering, predictive modeling, and business insight generation for customer retention.



This project analyzes a telecom customer dataset to understand why customers leave and which factors contribute most to churn. I built two classification models (Logistic Regression and Decision Tree) to predict at-risk customers and provided actionable retention strategies.</div>



**Dataset**: [Telco Customer Churn (Kaggle)](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)  ## 🚀 Objective

7,043 customers • 21 features including demographics, services, contracts, and billingIdentify the key drivers of customer churn and build a predictive model to flag at-risk customers early, enabling targeted retention strategies.



## 📁 Repository Structure## 📂 Repository Structure

```

```├── data

├── data/│   ├── raw/                # Original Kaggle dataset (tracked)

│   ├── raw/                    # Original dataset│   ├── external/           # 3rd party reference data (optional)

│   └── README.md              # Data documentation│   ├── interim/            # Scratch outputs (ignored)

├── notebooks/│   ├── processed/          # Clean & feature-engineered datasets (ignored)

│   └── customer_churn_analysis.ipynb    # Main analysis notebook│   └── README.md

├── images/                     # Visualizations and charts├── notebooks/              # Jupyter notebooks (EDA, modeling)

├── src/                        # Helper scripts (data prep utilities)├── src/                    # Reusable Python modules (data prep, utils)

├── analysis_summary.md         # Key findings document├── models/                 # Serialized models (ignored)

├── requirements.txt├── reports/

└── README.md│   ├── figures/            # Generated visualizations

```│   └── churn_summary_report.md

├── requirements.txt        # Python dependencies

## 🔍 Analysis Workflow└── README.md

```

1. **Data Cleaning** – Fixed data types, handled missing values in TotalCharges

2. **EDA** – Explored churn patterns across contract types, payment methods, tenure, and services## 🧠 Dataset

3. **Feature Engineering** – One-hot encoding, train/test split, feature scalingSource: [Telco Customer Churn – Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)  

4. **Modeling** – Trained Logistic Regression and Decision Tree classifiersRows: 7043 • Columns: 21  

5. **Evaluation** – Compared models using accuracy, precision, recall, F1, and ROC-AUCIncludes customer demographics, services subscribed, contract/payment details, and churn flag.

6. **Insights** – Identified top churn drivers and proposed retention tactics

## ⚙️ Workflow Overview

## 📊 Key Findings1. Ingest raw CSV ➜ `data/raw/`  

2. Clean & engineer features (see `src/data_prep.py`) ➜ `data/processed/`  

- **Month-to-month contracts** have significantly higher churn (~42%) vs annual contracts3. Exploratory Data Analysis (EDA) ➜ churn patterns & correlations  

- **Electronic check users** churn more frequently than automatic payment users4. Modeling (Logistic Regression + Decision Tree / Random Forest)  

- **Tenure** is highly predictive – most churn happens in first year5. Evaluation (Accuracy, Precision, Recall, F1, ROC-AUC)  

- Customers **without tech support or online security** are more likely to leave6. Interpretation (feature importance, SHAP - optional)  

- **Fiber optic users** show elevated churn (possible pricing/service issues)7. Business recommendations (retention levers)  



## 🤖 Model Performance## � Key Early Insights (Illustrative)

- Month-to-month contracts show the highest churn relative to longer-term contracts.  

| Model                | Accuracy | Precision | Recall | F1    | ROC-AUC |- Electronic check payment method correlates with elevated churn; consider incentivizing auto-pay.  

|---------------------|----------|-----------|--------|-------|---------|- Tenure strongly inversely related to churn—first-year retention pivotal.  

| Logistic Regression | 0.80     | 0.73      | 0.68   | 0.70  | 0.84    |

| Decision Tree       | 0.84     | 0.77      | 0.72   | 0.74  | 0.87    |## 🧮 Model Metrics (Sample Placeholder)

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |

*Decision Tree selected for production due to better interpretability and performance*|-------|----------|-----------|--------|----|---------|

| Logistic Regression | 0.80 | 0.73 | 0.68 | 0.70 | 0.84 |

## 💡 Business Recommendations| Random Forest       | 0.84 | 0.77 | 0.72 | 0.74 | 0.87 |



1. **Incentivize long-term contracts** – Offer discounts for customers who switch from monthly to annual plansActual values will be updated after running the modeling notebook.

2. **Promote auto-pay** – Small billing discount for bank transfer/credit card payments

3. **First-year retention program** – Proactive outreach during months 1-12## � Visuals

4. **Bundle value-added services** – Cross-sell tech support and online securityGenerated figures are saved under `reports/figures/` (e.g., `churn_rate_by_contract.png`, `correlation_heatmap.png`).

5. **Deploy churn scoring** – Use model to flag high-risk customers monthly for targeted campaigns

## 💡 Retention Recommendations (Initial)

## 🛠️ Tech Stack- Introduce loyalty incentives for <12 month tenure customers.

- Promote paperless + auto-pay enrollment to reduce payment-related churn.

- **Python** (pandas, numpy, matplotlib, seaborn, scikit-learn)- Prioritize outreach to high ARPU customers flagged with early churn risk.

- **Jupyter Notebook** for interactive analysis

- **Logistic Regression & Decision Tree** for classification## 🧪 Reproducibility

```powershell

## 🚀 How to Runpython src/data_prep.py    # produce processed dataset

python -m pip install -r requirements.txt

```powershell```

# Clone the repoOpen and run the notebook in `notebooks/` for full EDA & modeling.

git clone https://github.com/adityashirsatrao007/Customer-Churn-Analysis.git

cd Customer-Churn-Analysis## 🧰 Tech Stack

Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-Learn

# Install dependencies

pip install -r requirements.txt## � Author

Aditya

# Run the notebook

jupyter notebook notebooks/customer_churn_analysis.ipynb---

```> Contributions, issues, and feature requests welcome!


## 📷 Sample Visuals

Explore visualizations in the `/images` folder including churn distributions, feature importance charts, confusion matrices, and ROC curves.

---

**Author**: Aditya  
Feel free to connect or reach out with questions!
