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

claim_status: Binary classification:

- 0: No claim.

- 1: Claim.

# Key Challenges:

**Class Imbalance:**

- Majority class (claim_status = 0): 54844 samples.

- Minority class (claim_status = 1): 3748 samples.

# Approach

**Data Preprocessing:**

- Exploratory Data Analysis

- Extracted relevant features and the target variable from the dataset.

- Applied label encoding to transform categorical variables into numeric format for compatibility with machine learning algorithms.

**Handling Imbalance:**

Used oversampling (resample) on the training data to balance the classes and improve minority class representation.

**Model Training:**

Built and trained several models, including:

1) Random Forest
2) Decision Tree
3) XGBoost (XGB)

Selected Random Forest as the best model based on its consistent performance across training and test datasets.

**Evaluation Metrics:**

Used classification reports to evaluate model performance, focusing on:

- Precision
- Recall
- F1-Score
- Overall Accuracy

# Key Results

**Random Forest Performance**

- OverSampled Training Data :
  
| Class          | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| 0              | 1.00      | 0.98   | 0.99     | 38270   |
| 1              | 0.98      | 1.00   | 0.99     | 38511   |
| **Accuracy**   |           |        | 0.99     | 76781   |
| **Macro Avg**  | 0.99      | 0.99   | 0.99     | 76781   |
| **Weighted Avg** | 0.99    | 0.99   | 0.99     | 76781   |


- OverSampled Test Data:

  | Class          | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| 0              | 1.00      | 0.94   | 0.97     | 16574   |
| 1              | 0.95      | 1.00   | 0.97     | 16333   |
| **Accuracy**   |           |        | 0.97     | 32907   |
| **Macro Avg**  | 0.97      | 0.97   | 0.97     | 32907   |
| **Weighted Avg** | 0.97    | 0.97   | 0.97     | 32907   |

- Classification Report Of Orignal Imbalanced Dataset
  
| Class          | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| 0              | 1.00      | 0.97   | 0.99     | 54844   |
| 1              | 0.71      | 1.00   | 0.83     | 3748    |
| **Accuracy**   |           |        | 0.97     | 58592   |
| **Macro Avg**  | 0.86      | 0.99   | 0.91     | 58592   |
| **Weighted Avg** | 0.98    | 0.97   | 0.98     | 58592   |


# Challenges

Precision for the minority class is lower (0.71), indicating false positives.

High accuracy is driven by the majority class, which may mask issues with minority class predictions.


