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

- Used oversampling (resample) on the training data to balance the classes and improve minority class representation.

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

# Key Results On OverSampled Data

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

- **Train Performance:** Extremely high metrics across the board (precision, recall, f1-score = 0.99), indicating very strong performance and near-perfect predictions.

- **Test Performance:** Slight drop in recall for class 0 (0.94), but overall, the performance is still very high with accuracy and f1-score = 0.97. This suggests the model generalizes well with only slight overfitting.

- **Conclusion:** Random Forest shows robust and consistent performance for both training and test datasets, making it the strongest candidate for the problem.

# Key Results On Orignal Imbalaced Data

- Classification Report Of Orignal Imbalanced Dataset
  
| Class          | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| 0              | 1.00      | 0.97   | 0.99     | 54844   |
| 1              | 0.71      | 1.00   | 0.83     | 3748    |
| **Accuracy**   |           |        | 0.97     | 58592   |
| **Macro Avg**  | 0.86      | 0.99   | 0.91     | 58592   |
| **Weighted Avg** | 0.98    | 0.97   | 0.98     | 58592   |

**Overall Metrics:**

- Accuracy: 0.97
  The model correctly predicts 97% of all cases in the dataset.
- Macro Average:
  Precision: 0.86
  Average precision across both classes. Lowered due to Class 1's precision.
- Recall: 0.99
  High recall as both classes have strong recall values.
- F1-Score: 0.91
  Balanced performance across both classes.
- Weighted Average:
  Weighted by class support, these averages reflect the dominance of Class 0 in the dataset
**Precision: 0.99**
**Recall: 0.97**
**F1-Score: 0.98**

# Key Insights

- The model performs exceptionally well for the majority class (Class 0), with near-perfect precision and recall.
- For the minority class (Class 1), recall is excellent (1.00), but precision is lower (0.71), meaning there are false positives for claims.
- The overall accuracy of 97% reflects strong model performance, though this is influenced by the class imbalance.


# Challenges

Precision for the minority class is lower (0.71), indicating false positives.

High accuracy is driven by the majority class, which may mask issues with minority class predictions.

# Conclusion

The Random Forest model successfully predicted insurance claims with 97% accuracy on imbalanced data, achieving excellent recall (1.00) for claims.
Despite the strong performance, precision for claims (class 1) was lower (0.71), indicating some false positives. 
By applying oversampling to balance the data, the model showed near-perfect results on the training data, proving its potential for future improvements. 


