# Bank Marketing Campaign: Classification Model Comparison

## Overview & Link
This project evaluates classification algorithms (Logistic Regression, K-Nearest Neighbors, Decision Trees, and Support Vector Machines) on the UCI Bank Marketing dataset to predict term deposit subscription.

- **Main Analysis Notebook:** [Jupyter Notebook](notebooks/bank_marketing_comparison.ipynb)

## Business Objective
Telephone marketing campaigns represent a major operational expense. The objective is to build a machine learning pipeline that identifies prospects with the highest likelihood of opening a term deposit, minimizing wasted representative time.

## Key Findings
- **Best Model:** Tuned Logistic Regression / Pruned Decision Tree achieved the best balance of ROC-AUC (~0.79 without duration leakage) and sub-second execution.
- **Top Predictors:** Previous campaign success (`poutcome = success`) and lower `euribor3m` rates.
- **Duration Handling:** `duration` was excluded from predictive modeling to prevent real-world data leakage.

## Actionable Recommendations
1. Deploy a priority calling queue based on model probability percentiles.
2. Filter out cold leads in unfavorable macro environments (high Euribor rates).
3. Automate CRM flagging for any client with a positive prior engagement outcome.
