# Loan Default Prediction using Machine Learning

## Overview

This project builds a machine learning model to predict whether a borrower will default on a loan using financial and borrower-related features.

## Approach

* Data cleaning and preprocessing
* Feature engineering
* Removal of data leakage variables
* Model training and comparison

## Models Used

* Logistic Regression
* Random Forest
* XGBoost

## Final Model

XGBoost achieved the best performance and was selected as the final model.

## Performance

* Accuracy: 0.8995
* Precision: 0.9257
* Recall: 0.6441
* F1 Score: 0.7596
* ROC-AUC: 0.89

## Key Insights

* Loan and borrower characteristics significantly influence default risk
* Feature importance highlights key drivers such as credit type

## Known Issues

### Critical Analysis: Feature Importance
In the current version of the model, `Credit Type` shows a dominant feature importance score of **0.79**. 

### Why is this so high?

* Real-World Logic: In credit risk, whether a loan is "Equity-backed" versus "Unsecured" is often the single most significant predictor of default. The model is correctly identifying this high-level risk divider.
* Potential Data Leakage: There is a possibility that `Credit Type` is a "proxy" variable, meaning it contains information that is only decided *after* the bank already determines a borrower's risk level.

### Planned Investigation

To ensure the model isn't "cheating" by over-relying on this one feature, future updates will include:
* Training a version of the model without this feature to see how the model performs

## Conclusion

This model provides a meaningful analysis of borrower risk and demonstrates strong predictive potential. While the current findings are encouraging, the project remains an iterative work in progress. Future updates will focus on refining feature importance and validating the model against broader datasets to enhance its robustness.

