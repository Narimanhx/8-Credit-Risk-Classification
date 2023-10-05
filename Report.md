# Module 12 Report: Credit Risk Analysis

## Overview of the Analysis

The purpose of this analysis is to develop machine learning models to assess the credit risk of borrowers using financial information from a peer-to-peer lending service company's historical data. Specifically, we aim to predict whether a loan is healthy (0) or has a high risk of default (1) based on various features related to the borrower's financial situation.

### Data Summary

- The dataset contains information about loans, including loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, and total debt.
- The target variable is "loan_status," with 0 indicating healthy loans and 1 indicating high-risk loans.
- The data is imbalanced, with a significantly higher number of healthy loans (0) compared to high-risk loans (1).

### Machine Learning Process

The analysis can be broken down into the following stages:

1. **Data Preprocessing:**
   - Clean and Prepare the Data
   - Handle Missing Values
   - Encode Categorical Variables
   - Split the Data into Training and Testing Sets

2. **Model Training (Original Data):**
   - Fit a Logistic Regression Model Using the Training Data

3. **Model Evaluation (Original Data):**
   - Make Predictions on the Testing Data
   - Generate a Classification Report
   - Calculate Metrics such as Precision, Recall, and F1-Score

4. **Data Resampling:**
   - Use RandomOverSampler from imbalanced-learn to Balance the Target Variable in the Training Data

5. **Model Training with Resampled Data:**
   - Fit Another Logistic Regression Model Using the Resampled Training Data

6. **Model Evaluation with Resampled Data:**
   - Make Predictions on the Testing Data (Resampled)
   - Generate a Classification Report for the Resampled Model
   - Calculate Metrics such as Precision, Recall, and F1-Score for the Resampled Model


## Results

### Machine Learning Model 1: Logistic Regression with Original Data

http://localhost:8888/lab/tree/Documents/Documents/ASSIGNMENT9--07-08/Images/Report%201.png

- Balanced Accuracy: 0.952
- Precision (Label 0 - Healthy Loan): 1.00
- Precision (Label 1 - High-Risk Loan): 0.85
- Recall (Label 0 - Healthy Loan): 0.99
- Recall (Label 1 - High-Risk Loan): 0.91
- F1-Score (Label 0 - Healthy Loan): 1.00
- F1-Score (Label 1 - High-Risk Loan): 0.88
- Accuracy: 0.99

### Machine Learning Model 2: Logistic Regression with Resampled Data

http://localhost:8888/lab/tree/Documents/Documents/ASSIGNMENT9--07-08/Images/Report%202.png

- Balanced Accuracy: 0.994
- Precision (Label 0 - Healthy Loan): 1.00
- Precision (Label 1 - High-Risk Loan): 0.84
- Recall (Label 0 - Healthy Loan): 0.99
- Recall (Label 1 - High-Risk Loan): 0.99
- F1-Score (Label 0 - Healthy Loan): 1.00
- F1-Score (Label 1 - High-Risk Loan): 0.91
- Accuracy: 0.99

## Summary

Both machine learning models, whether using the original data or resampled data, performed exceptionally well in predicting the creditworthiness of borrowers.

- Model 2, which utilized the resampled data, demonstrated slightly higher balanced accuracy, precision, and recall for both label 0 (healthy loan) and label 1 (high-risk loan) compared to Model 1.
- The F1-Scores for both models indicate a good balance between precision and recall for both classes, though there is a slight drop for label 1.
- In terms of accuracy, both models achieved a very high accuracy score of 0.99, indicating their effectiveness in predicting loan status.

Given the performance of both models, it is recommended to use Model 2 with the resampled data as it achieved slightly better results. However, it is important to note that the choice of the model may depend on the specific problem being addressed. In situations where it is crucial to predict high-risk loans accurately, Model 2 may be preferred due to its higher recall for label 1. However, for a more balanced focus on both healthy and high-risk loans, either model can be considered as they exhibit high precision and recall for both classes.

Ultimately, the decision should be made based on the specific goals and requirements of the credit risk assessment task.