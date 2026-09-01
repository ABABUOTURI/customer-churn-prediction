readme_content = """# Telco Customer Churn Prediction

## Project Overview
This project builds a machine learning model to predict customer churn using the IBM Telco Customer Churn dataset. The goal is to identify which customers are likely to leave and understand the key drivers behind churn.

## Dataset
The dataset contains customer account information, services subscribed, billing details, and demographic data, along with a churn label indicating whether the customer left.

## Pipeline
1. **Data Loading** - Import raw CSV data
2. **Data Inspection** - Check structure, types, and missing values
3. **Data Cleaning** - Remove duplicates, handle missing values, fix TotalCharges data type
4. **Leakage Removal** - Drop columns that directly encode the outcome (Churn Value, Churn Score, Churn Reason, Churn indicator) and non-predictive identifiers (CustomerID, location fields)
5. **Feature Engineering** - One-hot encode categorical variables
6. **Train/Test Split** - 80/20 split with fixed random state
7. **Model Training** - RandomForestClassifier
8. **Evaluation** - Accuracy, classification report, ROC-AUC, confusion matrix, ROC/PR curves, calibration plot
9. **Feature Importance** - Identify top churn drivers
10. **Insights** - Translate model output into business recommendations

## Results
- **ROC-AUC Score:** 0.8709
- **Overall Accuracy:** 82%
- **Churn Recall:** 0.58 (catches 58% of actual churners)
- **Churn Precision:** 0.74 (74% of churn alerts are correct)

## Key Churn Drivers
| Feature | Importance |
|---|---|
| Tenure Months | 0.129 |
| Total Charges | 0.124 |
| Average Monthly Spend | 0.097 |
| Monthly Charges | 0.093 |
| CLTV | 0.087 |
| Tenure Group (49+ months) | 0.052 |
| Internet Service - Fiber Optic | 0.034 |
| Payment Method - Electronic Check | 0.033 |
| Dependents | 0.029 |
| Total Services Used | 0.029 |

## Key Insights
1. **Tenure is the strongest predictor** - Customers with shorter tenure are far more likely to churn. Onboarding and early-relationship engagement programs could reduce churn.
2. **Billing amount matters** - Higher total/monthly charges correlate with churn risk, especially when not matched by long tenure.
3. **Fiber optic and Electronic check are red flags** - These segments show elevated churn, suggesting service quality or billing friction worth investigating.
4. **Long tenure (49+ months) is protective** - Retention compounds over time; the highest-risk window is early in the customer relationship.

## Caveat
Total Charges, Average Monthly Spend, and CLTV are all correlated with tenure, so some of their predictive power likely reflects tenure's effect rather than fully independent signals.

## Model Artifact
The trained model is saved as `model.pkl` using joblib and can be reloaded for future predictions without retraining.

## Tech Stack
- Python, pandas, scikit-learn, matplotlib, seaborn, joblib
"""                                                                    # define the full README text as a multi-line string

with open('README.md', 'w') as f:                                     # open (or create) README.md in write mode
    f.write(readme_content)                                            # write the README content into the file

print("README.md created successfully.")                               # confirm the file was written
