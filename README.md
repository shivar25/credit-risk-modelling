# Credit Risk Modelling using Machine Learning

## Overview

This project develops an end-to-end machine learning pipeline for predicting loan default risk using the Home Credit Default Risk dataset. The objective is to identify applicants with a higher probability of default using application information and historical bureau records.

The project covers the complete machine learning workflow, including exploratory data analysis, feature engineering, statistical feature selection, model development, hyperparameter tuning, threshold optimization, and model interpretation.

---

## Problem Statement

Financial institutions need to assess the creditworthiness of loan applicants before approving loans. Incorrect lending decisions can increase financial losses due to loan defaults.

The objective of this project is to predict whether an applicant is likely to default on a loan using demographic, financial, and historical credit information.

---

## Dataset

Dataset: Home Credit Default Risk

Data Sources:

- Application Data
- Bureau Credit History

For computational efficiency, a sampled version of the dataset containing **50,000 applications** was used.

---

## Project Workflow

1. Data Understanding
2. Exploratory Data Analysis
3. Feature Engineering
4. Data Preprocessing
5. Statistical Feature Analysis
6. Baseline Model Training
7. XGBoost Hyperparameter Tuning
8. Threshold Optimization
9. Final Test Evaluation
10. Model Interpretation using SHAP

---

## Feature Engineering

Created several domain-inspired features including:

- Credit-to-Income Ratio
- Annuity-to-Income Ratio
- Credit-to-Annuity Ratio
- Income per Family Member
- Employment-to-Age Ratio

Historical bureau records were aggregated to create:

- Number of Previous Loans
- Active Loan Count
- Total Bureau Credit
- Total Bureau Debt
- Debt-to-Credit Ratio
- Average Credit History Length

---

## Statistical Feature Analysis

The project included statistical feature evaluation before model development.

Methods used:

- ANOVA (Numerical Features)
- Chi-Square Test (Categorical Features)
- Eta Squared Effect Size
- Cramér's V
- Correlation Filtering
- Variance Inflation Factor (VIF)

Separate feature sets were created for:

- Logistic Regression
- Tree-based Models

---

## Models Trained

- Logistic Regression
- Random Forest
- XGBoost

Class imbalance was handled using:

- `class_weight='balanced'`
- `scale_pos_weight` for XGBoost

---

## Hyperparameter Tuning

The XGBoost model was optimized using:

- RandomizedSearchCV
- 3-fold Cross Validation
- ROC-AUC as the optimization metric

The final classification threshold was selected using validation data to balance precision and recall.

---

## Final Results

| Model | Test ROC-AUC | Test PR-AUC |
|--------|-------------:|------------:|
| Logistic Regression | **0.745** | **0.224** |
| XGBoost | **0.753** | **0.242** |

Selected XGBoost operating point:

- Precision: **18.4%**
- Recall: **60.4%**
- F1-score: **0.282**
- Balanced Accuracy: **0.685**

---

## Model Interpretation

The project includes multiple model interpretation techniques:

- XGBoost Feature Importance
- Permutation Importance
- SHAP Global Explanations
- SHAP Local Explanations

The most influential predictors were:

- EXT_SOURCE_2
- EXT_SOURCE_3
- EXT_SOURCE_1
- CREDIT_ANNUITY_RATIO
- Bureau Credit History Features

---

## Repository Structure

```
credit-risk-modelling/

├── notebooks/
├── reports/
├── models/
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib
- Statsmodels

---

## Key Takeaways

- Developed a complete end-to-end credit risk modelling pipeline.
- Combined application and bureau credit history information.
- Performed statistical feature selection before modelling.
- Compared linear and tree-based machine learning models.
- Improved XGBoost using hyperparameter tuning and threshold optimization.
- Interpreted model behaviour using SHAP explanations.
