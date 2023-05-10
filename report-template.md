# Module 12 Report Template

## Overview of the Analysis

When deciding if a person can receive a requested loan, lenders must understand the level of credit risk associated with them. This is probability of the borrower’s failure to repay the full amount of the loan plus interest resulting in cash flow loss. 

In this project I focused on creating a Logistics Regression Model to determine the accuracy of loan status in the studied data set.

The financial information provided by a lending company included data regarding loan size, interest rates, borrower debt and income, number of open accounts, derogatory marks, and finally a loan status stating if the borrower was considered healthy or high-risk. 

The function value_counts() confirmed the data was heavily imbalanced with 75,036 labeled healthy and 2,500 labeled high-risk. 

![balanace](https://github.com/mhanson16/credit-risk-classification/assets/119544491/e98f352e-a681-4c5d-ae6d-48bce48ad038)

Utilizing the SKLearn library, I was able to split the data into x and y, training and testing values. The data was then ready to be applied and fitted to the Logistic Regression model. Predictions were formed to compare to the actual data points to create an accuracy score, confusion matrix and a final classification report. 

## Results

* Machine Learning Model 1 - Logistic Regression Model with the Original Data using the training data (X_train and y_train):
  * Accuracy: 95.2%
  * Precision: Nearly 100% for Healthy loans and 86% for Non-healthy loans
  * Recall Scores: Nearly 100% for Healthy loans and 90% for Non-healthy loans, telling us that <1% of Healthy loans were incorrectly labeled  while about 10% of high-risk loans were incorrectly labeled. 
  * The confusion matrix states that 56 out of the 18,719 predicted healthy loans were actually high-risk, while 102 of the 665 high-risk loans were actually healthy.



* Machine Learning Model 2 - Predicting Logistic Regression Model with Resampled Training Data using the training data (X_train and y_train):
  * Accuracy: 99.37%
  * Precision: Nearly 100% for Healthy loans and 84% for Non-healthy loans
  * Recall Scores: 99% for Healthy loans and Non-healthy loans, telling us that 1% of loans were incorrectly labeled.
  * The confusion matrix states that 4 out of the 18,653 predicted healthy loans are actually high-risk, while 116 of the 731 high-risk loans are actually healthy.

## Summary

Both models show incorrect predictions for both labels. It is important to understand that though they are both incorrectly marked those would result in very different outcomes for the lender. It is much more dangerous to accidentally lend to a high-risk borrower than to not lend to a healthy borrower. 

Though Model 2 had 14 more false negatives(healthy predicted as high-risk) than Model 1, Model 2 had 52 fewer false positives(high-risk predicted as healthy) than Model 1. Model 2’s accuracy score was 99.37% compared to Model 1’s 95.2%. There for I recommend the use of Model 2 for this scenario.
