# Predicting Customer Churn: A Data-Driven Analysis of Subscription Customer Behaviour

<p align="center">
  <b>Data Science & AI Capstone Project</b><br>
  Customer Churn Analysis and Classification
</p>

---

## 📌 Project Overview

Customer churn is an important problem for subscription-based service providers. Understanding which customer characteristics are associated with churn can help organizations analyze customer behaviour and develop data-driven retention strategies.

This project performs an end-to-end analysis of customer churn using the **Telco Customer Churn dataset**. The project covers data cleaning, preprocessing, exploratory data analysis (EDA), statistical analysis, feature engineering, machine learning model development, and model evaluation.

Two classification models were developed:

- Logistic Regression
- Decision Tree Classifier

The models were evaluated using accuracy, precision, recall, F1-score, and confusion matrices.

---

## 🎯 Objectives

The main objectives of this project are:

1. Prepare and clean the customer subscription dataset.
2. Identify patterns and relationships associated with customer churn.
3. Compare churned and non-churned customers using statistical analysis.
4. Perform feature engineering to improve the representation of customer behaviour.
5. Develop machine learning models for churn classification.
6. Evaluate model performance using multiple classification metrics.
7. Interpret the findings and provide data-driven recommendations.

---

## ❓ Research Questions

This project investigates the following questions:

- What are the major characteristics and data-quality issues in the dataset?
- Which customer characteristics are associated with churn?
- How do tenure, monthly charges, contract type, and internet service vary according to churn status?
- Are the observed differences and associations statistically significant?
- How accurately can machine learning models classify customer churn?

---

## 📊 Dataset

The project uses the **Telco Customer Churn dataset**.

### Dataset Information

| Property | Details |
|---|---|
| Original Records | 7,043 |
| Variables | 21 |
| Final Records | 7,032 |
| Target Variable | `Churn` |
| Identifier | `customerID` |
| Problem Type | Binary Classification |

The dataset contains customer demographic information, service subscriptions, contract details, payment information, tenure, and billing-related variables.

---

## 🧹 Data Cleaning

The following data-quality steps were performed:

- Checked for missing values
- Identified invalid/blank `TotalCharges` entries
- Converted `TotalCharges` from object to numeric format
- Checked for duplicate records
- Examined categorical-value consistency
- Investigated numerical outliers using the IQR method
- Removed 11 invalid records associated with blank `TotalCharges` values

After cleaning, the dataset contained **7,032 customer records**.

---

## ⚙️ Data Preprocessing

The following preprocessing techniques were applied:

- Removed `customerID` from modelling
- Separated features and target variable
- One-hot encoded categorical variables
- Standardized numerical variables using `StandardScaler`
- Used an 80:20 train-test split
- Applied stratified sampling
- Used `random_state=42` for reproducibility
- Implemented preprocessing using `ColumnTransformer`

The training set contained **5,625 records**, while the testing set contained **1,407 records**.

---

## 🔧 Feature Engineering

An additional feature named `AvgMonthlySpend` was created:

```text
AvgMonthlySpend = TotalCharges / tenure
