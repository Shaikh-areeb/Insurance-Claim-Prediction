# Claim Status Prediction Project

## Overview

This project aims to predict whether an insurance claim will be made (claim_status) using various customer and vehicle-related features. 
The primary challenge is to handle the class imbalance between claims (minority class) and non-claims (majority class) while achieving high accuracy and balanced metrics.

## Dataset Description

**Features Used**

- subscription_length: Length of the customer's subscription.

- customer_age: Age of the customer.

- vehicle_age: Age of the insured vehicle.

- region_density: Population density of the customer's region.

- region_code: Code representing the customer's region.

**Target Variable:**

- claim_status: Binary classification:

- 0: No claim.

- 1: Claim.

Key Challenges:

Class Imbalance:

Majority class (claim_status = 0): 54844 samples.

Minority class (claim_status = 1): 3748 samples.

Approach

Data Preprocessing:

Extracted relevant features and the target variable from the dataset.

Applied label encoding to transform categorical variables into numeric format for compatibility with machine learning algorithms.

Handling Imbalance:

Used oversampling (e.g., SMOTE or similar techniques) on the training data to balance the classes and improve minority class representation.

Model Training:

Built and trained several models, including:

Random Forest

Decision Tree

XGBoost (XGB)

Selected Random Forest as the best model based on its consistent performance across training and test datasets.

Evaluation Metrics:

Used classification reports to evaluate model performance, focusing on:

Precision

Recall

F1-Score

Overall Accuracy

Key Results

Random Forest Performance

Training Data:

Accuracy: 99%

Balanced metrics for both classes (f1-score: ~0.99).

Test Data:

Accuracy: 97%

High recall for claims (1.00), but slightly lower precision (0.71).

Weighted average metrics remain strong (precision: 0.98, f1-score: 0.98).

Improvements from Oversampling:

Minority class (claim_status = 1) recall improved to 1.00, ensuring no claims are missed.

Challenges and Improvements

Challenges:

Precision for the minority class is lower (0.71), indicating false positives.

High accuracy is driven by the majority class, which may mask issues with minority class predictions.

Potential Improvements:

Threshold Tuning:

Adjust prediction thresholds to balance precision and recall for claims.

Cost-Sensitive Learning:

Assign higher misclassification costs to the minority class to reduce false positives.

Feature Engineering:

Add new features or refine existing ones to improve model differentiation between classes.
