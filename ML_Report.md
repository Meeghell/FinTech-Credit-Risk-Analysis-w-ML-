## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

- **Explain the purpose of the analysis:**  
    The purpose of this analysis is to build and evaluate machine learning models to predict credit risk. This involves identifying whether a loan is healthy (low risk) or high risk based on historical lending data.
- **Explain what financial information the data was on, and what you needed to predict.**  
    The data consists of historical lending activity from a peer-to-peer lending services company. The dataset includes financial information such as loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, and total debt. The target variable to predict is the loan status, where `0` indicates a healthy loan and `1` indicates a high-risk loan.
- **Provide basic information about the variables you were trying to predict (e.g., `value_counts`):**  
    The target variable `loan_status` is highly imbalanced:
    
    - `0` (healthy loan): 75,036 instances
    - `1` (high-risk loan): 2,500 instances
    
- **Describe the stages of the machine learning process you went through as part of this analysis:**
    
    1. **Data Preparation:** Read the data from a CSV file and split it into features (`X`) and labels (`y`).
    2. **Data Splitting:** Split the data into training and testing sets using `train_test_split`.
    3. **Model Training with Original Data:** Train a logistic regression model using the original training data.
    4. **Model Evaluation with Original Data:** Evaluate the model's performance using accuracy score, confusion matrix, and classification report.
    5. **Resampling:** Use `RandomOverSampler` to balance the training data.
    6. **Model Training with Resampled Data:** Train a logistic regression model using the resampled training data.
    7. **Model Evaluation with Resampled Data:** Evaluate the model's performance using accuracy score, confusion matrix, and classification report.
    
- **Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method):**
    
    - **Logistic Regression:** Used to build the classification model.
    - **RandomOverSampler:** Used to balance the training data by oversampling the minority class (high-risk loans).
    

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

- **Machine Learning Model 1 (Original Data):**
    
    - **Balanced Accuracy Score:** 0.952
    - **Precision (Healthy Loan):** 1.00
    - **Recall (Healthy Loan):** 0.99
    - **Precision (High-Risk Loan):** 0.85
    - **Recall (High-Risk Loan):** 0.91
    
- **Machine Learning Model 2 (Resampled Data):**
    
    - **Balanced Accuracy Score:** 0.994
    - **Precision (Healthy Loan):** 1.00
    - **Recall (Healthy Loan):** 0.99
    - **Precision (High-Risk Loan):** 0.84
    - **Recall (High-Risk Loan):** 0.99
    

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

- **Which one seems to perform best? How do you know it performs best?**  
    The logistic regression model trained with resampled data (Model 2) performs best. This is evident from its higher balanced accuracy score (0.994) and improved recall for high-risk loans (0.99) compared to the model trained with original data.
- **Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s?)**  
    Yes, performance depends on the problem. In this case, accurately predicting high-risk loans (`1`s) is crucial to minimize financial risk. Model 2's higher recall for high-risk loans makes it more suitable for this purpose.
- **If you do not recommend any of the models, please justify your reasoning.**  
    I recommend using the logistic regression model trained with resampled data (Model 2) because it provides a better balance between precision and recall for both healthy and high-risk loans, making it more reliable for predicting credit risk.