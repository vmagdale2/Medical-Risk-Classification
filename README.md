# Medical-Risk-Classification
Supervised Machine Learning Classification and Interpretability 
# 🩺 Predicting High-Risk Patients: A Classification Analysis

## 🎯 Objective

The objective of this analysis is to **predict which patients are at high risk for cardiovascular complications** using a classification model. This allows healthcare professionals to identify at-risk individuals earlier and provide proactive interventions. The model prioritizes both **accuracy** and **interpretability**, enabling medical stakeholders to trust and act on the model's recommendations.

## 📊 Dataset Overview

The dataset contains information on **1,000 synthetic patients**, each with demographic, lifestyle, and medical history data. The binary target variable `HighRisk` indicates whether a patient is considered high-risk based on a combination of their attributes.

### Dataset Summary:
- Target variable: `HighRisk` (Yes/No)
- Slight class imbalance (≈21% high risk), handled with SMOTE
- 12 input features including `BMI`, `Smoking`, `CholesterolLevel`, `FamilyHistory`, and more

## 🔧 Data Exploration & Preparation

### Key Cleaning & Feature Engineering Steps:
- Converted categorical features into dummy variables
- Applied binary encoding to Yes/No fields
- Used **SMOTE** to oversample the minority class and balance the dataset
- Performed **train/test split** after resampling to avoid data leakage

Class distribution was verified before and after SMOTE to ensure correct balancing for model training.

## 🤖 Model Comparison

Three classification models were trained and evaluated:

| Model               | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|--------------------|----------|-----------|--------|----------|---------|
| Logistic Regression | ~0.99    | ~0.99     | ~0.99  | ~0.99    | ~0.99   |
| Decision Tree       | ~0.99    | ~0.99     | ~0.99  | ~0.99    | ~0.99   |
| Random Forest       | ~1.00    | ~1.00     | ~1.00  | ~1.00    | ~1.00   |

### Selected Final Model: **Decision Tree**

While all models performed exceptionally well due to the synthetic data’s strong feature-to-target correlation, the **Decision Tree Classifier** was chosen for its **interpretability**. It enables clear, rule-based explanations that are especially valuable in medical settings.

## 🔍 Key Insights

- **Smoker status**, **high cholesterol**, and **low physical activity** were among the strongest predictors of high risk.
- The decision tree showed clear, interpretable thresholds such as:
  - If `Smoker = Yes` and `CholesterolLevel > 220`, the patient is very likely to be high-risk.
  - Patients aged 60+ with both `Hypertension` and a `FamilyHistory` had a high likelihood of being high risk.

### Visual Tools Used:
- Decision tree plot to illustrate branching logic
- Permutation importance analysis to validate key features

## ⚠️ Limitations & Future Improvements

- The dataset is synthetic and reflects highly separable feature relationships, which may not represent real-world clinical complexity.
- Future analysis could benefit from:
  - Adding more nuanced medical data (medications, lab results)
  - Incorporating time-series behavior or patient monitoring data
  - Validating the model on real-world patient datasets

## ✅ Final Thoughts

This project demonstrates the use of supervised machine learning for a real-world-style healthcare application. The chosen **Decision Tree model** balances performance with interpretability, offering actionable insights for medical decision-makers while maintaining strong predictive power.
