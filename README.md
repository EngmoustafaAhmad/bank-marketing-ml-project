# Bank Marketing Classification (Machine Learning Project)

## Overview
This project focuses on building machine learning models to predict whether a client will subscribe to a bank term deposit (Yes/No) based on marketing campaign data.

The dataset used is the **Bank Marketing Dataset**, which contains customer information and campaign-related features.

---

## Objectives
- Perform data preprocessing and cleaning
- Handle missing values and categorical features
- Train and evaluate classification models
- Compare different techniques:
  - Random Forest
  - XGBoost
  - Feature Selection
  - PCA (Dimensionality Reduction)
- Improve performance on imbalanced data

---

## Dataset
- Source: UCI Bank Marketing Dataset
- Target Variable:
  - `y`: (yes → 1, no → 0)
- Class Distribution:
  - No (~88%)
  - Yes (~12%)

---

## Data Preprocessing
- Replaced `"unknown"` values with NaN
- Filled missing values:
  - Numerical → Median
  - Categorical → Mode
- Converted categorical variables using:
  - One-Hot Encoding
- Feature scaling using:
  - StandardScaler (for XGBoost)

---

## Models Used

### 1. Random Forest
- Ensemble learning method based on multiple decision trees
- Parameters:
  - n_estimators = 400
  - max_depth = 25
  - min_samples_split = 42
  - class_weight = balanced

### 2. XGBoost
- Gradient boosting algorithm
- Handles imbalance using `scale_pos_weight`
- Parameters:
  - n_estimators = 500
  - max_depth = 8
  - learning_rate = 0.05
  - subsample = 0.8

---

## Techniques Applied

### Feature Selection
- Used SelectFromModel based on feature importance

### Dimensionality Reduction
- PCA (Principal Component Analysis)
- Tested multiple component sizes

### Hyperparameter Tuning
- GridSearchCV used for:
  - n_estimators
  - max_depth

---

## Results

### Random Forest
- Accuracy: ~0.866
- Observations:
  - Good performance on majority class
  - Lower precision on minority class

### Random Forest + Feature Selection
- Accuracy: ~0.861
- Slight decrease due to loss of useful features

### Random Forest + PCA
- Accuracy: ~0.869
- Slight improvement

---

### XGBoost
- Accuracy: ~0.888
- F1 Score: ~0.896
- Better handling of imbalanced data

### XGBoost + PCA
- Accuracy: ~0.891 (Best)
- Improved generalization

---

## Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

---

## Key Insights
- XGBoost outperformed Random Forest due to boosting technique
- PCA helped reduce noise and improve performance
- Feature selection was not beneficial in this case
- Class imbalance significantly affects model performance
- Some features (e.g., duration) may introduce data leakage

---

## Visualizations
- Accuracy comparison (bar chart)
- F1-score comparison
- Heatmap for hyperparameter tuning

---

## Tools & Libraries
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Matplotlib, Seaborn


