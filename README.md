# Fraud Detection with Transaction Data

This project aims to build a model to detect fraudulent transactions using machine learning techniques. The dataset consists of various features related to transactions, such as distance from the home and previous transaction history, and a target variable indicating whether the transaction is fraudulent or not.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data](#data)
3. [Preprocessing](#preprocessing)
4. [Modeling](#modeling)
5. [Evaluation](#evaluation)
6. [Results](#results)

## Project Overview

The goal of this project is to identify fraudulent transactions using a dataset of credit card transaction data. The dataset contains features such as:
- Distance from the home
- Distance from the last transaction
- Ratio to the median purchase price
- Whether the retailer is a repeat one
- Usage of chip or PIN number during the transaction
- Whether the order was made online
- Fraud flag (target variable)

The project follows the typical data science workflow:
1. **Data Loading and Exploration**
2. **Preprocessing and Cleaning**
3. **Model Training and Evaluation**
4. **Model Performance Metrics**

## Data

The dataset `card_transdata.csv` includes multiple features related to credit card transactions:
- `distance_from_home`: Distance to the cardholder's home.
- `distance_from_last_transaction`: Time gap between current and last transaction.
- `ratio_to_median_purchase_price`: Purchase price in relation to the median price.
- `repeat_retailer`: Flag for repeat retailers (1 for true, 0 for false).
- `used_chip`: Flag indicating if the transaction used a chip (1 for true, 0 for false).
- `used_pin_number`: Flag indicating if the transaction used a pin (1 for true, 0 for false).
- `online_order`: Flag indicating if the transaction was made online (1 for true, 0 for false).
- `fraud`: Target variable indicating if the transaction is fraudulent (1 for true, 0 for false).

## Preprocessing

### 1. **Data Exploration**
- We load the data and check the first few rows to understand the structure.
- We check for null values and duplicates to ensure data quality.

### 2. **Feature Scaling**
- Some features are standardized using `StandardScaler` to bring them to a common scale, which helps with many machine learning algorithms.

### 3. **Splitting Data**
- The data is split into training and test sets using a 70-30 split.

## Modeling

Several models are tested in this project:
1. **Logistic Regression**: Used to predict fraudulent transactions based on the transformed features.
2. **PCA (Principal Component Analysis)**: Used to reduce dimensionality and extract the most important features from the data.

### PCA:
- We perform PCA on the training data to reduce the number of features and retain as much variance as possible.
- The explained variance ratio indicates how much information each component holds.

## Evaluation

The model's performance is evaluated using the following metrics:
- **Accuracy**: Measures the overall correctness of the model.
- **Precision**: The fraction of relevant instances among the retrieved instances.
- **Recall**: The fraction of relevant instances that have been retrieved.
- **F1 Score**: The weighted average of Precision and Recall.
- **Confusion Matrix**: Provides a summary of the model's predictions versus the actual values.

### Results:
The final evaluation shows:
- **Accuracy**: ~57.29%
- **Precision**: ~1.76%
- **Recall**: ~7.13%
- **F1 Score**: ~2.83%
