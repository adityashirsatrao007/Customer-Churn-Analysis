# Customer Churn Analysis

Analyzing telecom customer data to figure out why people are leaving and what we can do about it.

## What's This About?

I wanted to understand customer churn better, so I grabbed a telecom dataset from Kaggle and dug into it. Built a couple models to predict which customers might leave, and found some interesting patterns along the way.

**Data**: Telco Customer Churn from Kaggle - about 7,000 customers with info on their contracts, services, billing, etc.

## What I Found

Some quick takeaways:

- Month-to-month customers churn WAY more than people on annual contracts (like 42% vs 3%)
- People paying with electronic checks leave more often - probably a hassle factor
- Most churn happens in the first year. After that people tend to stick around
- Customers without tech support or online security are more likely to bail
- Fiber optic users have higher churn - maybe pricing issue?

## The Models

Tried two approaches:

**Logistic Regression**: 81% accuracy, 0.84 AUC  
**Decision Tree**: 76% accuracy, 0.78 AUC

Logistic regression did better here. Not perfect but decent enough to be useful.

## Files

```
 data/
    raw/                 # dataset goes here
 notebooks/
    customer_churn_analysis.ipynb    # main analysis
 images/                  # all the charts
 analysis_summary.md      # detailed writeup
 requirements.txt
```

## Running It

If you want to run this yourself:

```bash
git clone https://github.com/adityashirsatrao007/Customer-Churn-Analysis.git
cd Customer-Churn-Analysis
pip install -r requirements.txt
```

Then open the notebook and run the cells. Should work fine.

## What Could Help Retention

Based on what I found:

1. Get people off month-to-month contracts - offer discounts for annual signup
2. Push automatic payments instead of electronic checks
3. Focus on the first year - that's when most people leave
4. Bundle in tech support and security features
5. Look at fiber optic pricing

## Tech Used

Python, pandas, matplotlib, seaborn, scikit-learn. Nothing fancy.

## Charts

Check out the /images folder for all the visualizations - distributions, correlations, model comparisons, etc.

---

Made this to practice data analysis and show I can turn messy data into something useful. Feel free to look around or reach out if you have questions.
