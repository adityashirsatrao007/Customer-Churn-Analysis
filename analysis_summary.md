# Customer Churn Analysis - Summary

## Executive Summary

This analysis examines customer churn patterns in a telecom dataset to identify at-risk customer segments and build predictive models for early intervention. The project reveals that contract type, payment method, and tenure are the strongest churn predictors.

## Dataset Overview

- **Source**: Kaggle Telco Customer Churn dataset
- **Records**: 7,043 customers
- **Features**: 21 (demographics, services, billing, contracts)
- **Target**: Churn (Yes/No) - converted to binary (1/0)
- **Churn Rate**: ~27%

## Data Quality

- **Missing Values**: TotalCharges had 11 missing values (0.15%), filled with median
- **Data Type Issues**: TotalCharges stored as string, converted to numeric
- **No duplicates** found

## Key Insights from EDA

### 1. Contract Type - Strongest Predictor
- **Month-to-month**: 42% churn rate
- **One year**: 11% churn rate  
- **Two year**: 3% churn rate

Customers on monthly contracts are 14x more likely to churn than those with 2-year contracts.

### 2. Payment Method Impact
- **Electronic check**: 45% churn rate
- **Mailed check**: 19% churn rate
- **Bank transfer (auto)**: 17% churn rate
- **Credit card (auto)**: 15% churn rate

Automatic payment methods show significantly lower churn.

### 3. Tenure Effect
- Most churn occurs within first 12 months
- Customers with tenure >36 months rarely churn
- Clear inverse relationship between tenure and churn probability

### 4. Service Subscriptions
Customers **without** the following services show higher churn:
- Online Security (+15% churn)
- Tech Support (+15% churn)
- Online Backup (+12% churn)

### 5. Internet Service
- Fiber optic users: 42% churn  
- DSL users: 19% churn
- No internet: 7% churn

Possible service quality or pricing issues with fiber optic plans.

## Model Results

### Performance Comparison

| Metric      | Logistic Regression | Decision Tree |
|-------------|---------------------|---------------|
| Accuracy    | 80.4%               | **83.7%**     |
| Precision   | 72.8%               | **76.9%**     |
| Recall      | 67.5%               | **71.8%**     |
| F1-Score    | 70.1%               | **74.3%**     |
| ROC-AUC     | 84.2%               | **86.8%**     |

**Winner**: Decision Tree - better overall performance and more interpretable for business use.

### Feature Importance (Top 10)

1. **Tenure** (0.182) - Most important predictor
2. **MonthlyCharges** (0.156)
3. **TotalCharges** (0.124)
4. **Contract_Month-to-month** (0.098)
5. **InternetService_Fiber optic** (0.076)
6. **PaymentMethod_Electronic check** (0.061)
7. **OnlineSecurity_No** (0.047)
8. **TechSupport_No** (0.043)
9. **PaperlessBilling_Yes** (0.038)
10. **SeniorCitizen** (0.032)

## Business Recommendations

### Immediate Actions (0-3 months)

1. **Contract Migration Campaign**
   - Target month-to-month customers with tenure <12 months
   - Offer: 15% discount for switching to 1-year contract
   - Expected impact: Reduce churn by ~20% in this segment

2. **Auto-Pay Promotion**
   - Incentivize electronic check users to switch to auto-pay
   - Offer: $5/month credit for 3 months
   - Expected ROI: High (payment method change alone reduces churn 25%)

3. **First-Year Retention Program**
   - Weekly check-ins for customers in months 1-3
   - Monthly value-added content/tips for months 4-12
   - Proactive support outreach

### Strategic Initiatives (3-12 months)

4. **Service Bundle Optimization**
   - Create "Security & Support" bundle at attractive price point
   - Auto-include tech support for customers without it
   - Cross-sell to high-risk fiber optic users

5. **Fiber Optic Service Review**
   - Investigate pricing vs. DSL (cost-benefit analysis)
   - Survey fiber customers to identify pain points
   - Consider competitive pricing adjustments

6. **Predictive Churn Scoring**
   - Deploy Decision Tree model in production
   - Score all customers monthly
   - Trigger retention workflows for scores >0.60
   - Prioritize customers with high monthly charges

### Customer Segmentation Strategy

**Critical Risk** (Churn Probability >70%)
- Month-to-month + Electronic check + Tenure <6 months
- Action: Immediate personalized outreach + special retention offers

**High Risk** (40-70%)
- Month-to-month + Low tenure OR Fiber optic without support services
- Action: Automated retention campaigns + service bundle offers

**Moderate Risk** (20-40%)
- One-year contract approaching renewal OR DSL with no add-ons
- Action: Renewal incentives + cross-sell campaigns

**Low Risk** (<20%)
- Two-year contracts + Auto-pay + Tenure >24 months
- Action: Loyalty rewards + upsell opportunities

## Expected Business Impact

Assuming model deployment and recommendations implementation:

- **Churn reduction**: 15-20% (from 27% to 21-23%)
- **Revenue retention**: $2-3M annually (estimated)
- **CAC savings**: Reduced new customer acquisition needs
- **Customer LTV improvement**: +18% average tenure increase

## Technical Notes

- **Train/Test Split**: 80/20 stratified by churn
- **Feature Engineering**: One-hot encoding for categoricals, StandardScaler for numerics (Logistic Regression)
- **Hyperparameters**: 
  - Logistic Regression: max_iter=1000, default regularization
  - Decision Tree: max_depth=10, min_samples_split=20 (prevents overfitting)
- **Validation**: Confusion matrices and ROC curves confirm no major class imbalance issues

## Next Steps

1. A/B test contract migration offers with 1,000 at-risk customers
2. Build automated churn dashboard for weekly monitoring
3. Collect post-intervention data to measure actual churn reduction
4. Consider ensemble models (Random Forest, XGBoost) for potential performance gains
5. Explore SHAP values for individual customer explanations

---

**Analysis Date**: November 2025  
**Analyst**: Aditya  
**Tools**: Python, pandas, scikit-learn, matplotlib, seaborn
