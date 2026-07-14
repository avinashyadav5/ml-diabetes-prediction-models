# 🩺 Multi-Class Diabetes Prediction using Machine Learning

A comprehensive machine learning project for predicting diabetes status using health and lifestyle indicators from the **CDC Behavioral Risk Factor Surveillance System (BRFSS) 2021 dataset**.

The project compares multiple machine learning algorithms for classifying individuals into three categories:

- **0 — No Diabetes**
- **1 — Prediabetes**
- **2 — Diabetes**

The complete pipeline includes data exploration, preprocessing, feature analysis, model training, hyperparameter tuning, multiclass evaluation, model comparison, SHAP explainability, model serialization, and deployment-ready inference.

---

## 📌 Project Overview

Diabetes is a chronic health condition that affects how the body converts food into energy. Early identification of individuals at risk of diabetes or prediabetes can help support timely screening and preventive interventions.

This project uses 21 health and lifestyle indicators from the BRFSS 2021 survey to build a multiclass machine learning system capable of predicting diabetes status.

The primary objective is to:

- Explore relationships between health indicators and diabetes status.
- Train and compare multiple machine learning algorithms.
- Evaluate performance using metrics suitable for an imbalanced multiclass problem.
- Explain model predictions using SHAP.
- Export the selected model for future API and web application deployment.

> **Important:** This project is intended for educational and screening-oriented machine learning research. It is not a medical diagnostic tool and should not replace professional medical advice, clinical evaluation, or laboratory testing.

---

## 📊 Dataset

The project uses the cleaned **BRFSS 2021 Diabetes Health Indicators Dataset**.

### Dataset characteristics

- **236,378 survey responses before project-level preprocessing**
- **21 input features**
- **1 target variable**
- **3 target classes**

### Target variable

| Class | Meaning |
|---|---|
| `0` | No Diabetes |
| `1` | Prediabetes |
| `2` | Diabetes |

The dataset is highly imbalanced, with the No Diabetes class representing the majority of observations and Prediabetes being the smallest class.

This imbalance is an important consideration when interpreting accuracy and weighted metrics.

---

## 🧬 Input Features

The model uses the following 21 health and lifestyle indicators:

| Feature | Description |
|---|---|
| HighBP | High blood pressure |
| HighChol | High cholesterol |
| CholCheck | Cholesterol checked within the relevant survey period |
| BMI | Body Mass Index |
| Smoker | Smoking history |
| Stroke | History of stroke |
| HeartDiseaseorAttack | Coronary heart disease or myocardial infarction history |
| PhysActivity | Physical activity |
| Fruits | Fruit consumption |
| Veggies | Vegetable consumption |
| HvyAlcoholConsump | Heavy alcohol consumption |
| AnyHealthcare | Access to healthcare coverage |
| NoDocbcCost | Unable to see a doctor because of cost |
| GenHlth | Self-reported general health |
| MentHlth | Number of poor mental-health days |
| PhysHlth | Number of poor physical-health days |
| DiffWalk | Serious difficulty walking or climbing stairs |
| Sex | Sex indicator |
| Age | Age category |
| Education | Education category |
| Income | Income category |

---

## 🔄 Complete Machine Learning Workflow

The project follows this end-to-end workflow:

```text
BRFSS 2021 Dataset
        │
        ▼
Data Loading and Inspection
        │
        ▼
Missing Value Analysis
        │
        ▼
Duplicate Detection and Removal
        │
        ▼
Exploratory Data Analysis (EDA)
        │
        ├── Class Distribution
        ├── Feature Distributions
        ├── Correlation Analysis
        └── Health Indicator Analysis
        │
        ▼
Feature Analysis
        │
        ├── Mutual Information
        └── Random Forest Feature Importance
        │
        ▼
Stratified Train-Test Split
        │
        ├── 80% Training Data
        └── 20% Testing Data
        │
        ▼
Standard Scaling
        │
        └── Applied to distance/margin-based models
        │
        ▼
Stratified K-Fold Cross-Validation
        │
        ▼
Model Training and Evaluation
        │
        ├── Logistic Regression
        ├── Decision Tree
        ├── Random Forest
        ├── K-Nearest Neighbors
        ├── Linear SVM
        ├── XGBoost
        └── CatBoost
        │
        ▼
Hyperparameter Tuning
        │
        ├── Logistic Regression
        ├── Decision Tree
        ├── Random Forest
        ├── KNN
        └── Linear SVM
        │
        ▼
Comprehensive Model Comparison
        │
        ├── Accuracy
        ├── Balanced Accuracy
        ├── Macro Precision
        ├── Macro Recall
        ├── Macro F1
        ├── Weighted Precision
        ├── Weighted Recall
        ├── Weighted F1
        └── One-vs-Rest ROC-AUC
        │
        ▼
Final Model Selection
        │
        ▼
XGBoost Selected for Deployment
        │
        ▼
SHAP Explainability
        │
        ├── Prediabetes Beeswarm Plot
        ├── Diabetes Beeswarm Plot
        └── Global SHAP Feature Importance
        │
        ▼
Final Validation Checks
        │
        ▼
Model Serialization
        │
        ├── xgboost_diabetes_model.json
        └── model_metadata.json
        │
        ▼
Prediction Function
        │
        ▼
Deployment-Ready Inference Pipeline