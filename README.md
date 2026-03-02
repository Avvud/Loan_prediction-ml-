🏦 Loan Status Prediction using Machine Learning
📌 Project Overview

This project builds a machine learning classification system to predict whether a loan application will be approved based on applicant financial and demographic information.

The implementation focuses on constructing a reproducible ML pipeline, including preprocessing, scaling, model comparison, and hyperparameter optimization.

🎯 Objective

Financial institutions must evaluate loan applications while minimizing default risk.

This project attempts to learn approval patterns from historical loan data and automate decision prediction.

Prediction Target

Loan_Status
0 → Rejected
1 → Approved
⚙️ Machine Learning Pipeline
Raw Dataset
     ↓
Missing Value Removal
     ↓
Categorical Encoding
     ↓
Train-Test Split
     ↓
Feature Scaling
     ↓
Model Training
     ↓
Model Evaluation
     ↓
Hyperparameter Optimization
📂 Dataset Processing
✅ Data Cleaning

Missing values removed using:

data.dropna(inplace=True)

Constraint:

Row deletion reduces dataset size.

May introduce sampling bias.

✅ Feature Encoding

Categorical features converted using:

LabelEncoder

Engineering Trade-off:

Fast implementation

Introduces artificial ordinal relationships

Failure Case:
Models may interpret encoded categories numerically even when unordered.

✅ Feature Scaling

Standardization performed using:

StandardScaler

Required because:

Distance-based models (KNN) are scale-sensitive.

Prevents feature dominance.

🤖 Models Implemented
1️⃣ Logistic Regression

Baseline linear classifier.

Why used

Interpretable

Stable convergence

Suitable for tabular financial data

Strength:
✔ Low variance
✔ Fast inference

Limitation:
✖ Cannot capture nonlinear approval boundaries

2️⃣ K-Nearest Neighbors (KNN)

Instance-based learning model.

Strength:
✔ Learns nonlinear decision regions

Constraints:

High inference latency

Sensitive to noise

Performance degrades with dimensionality

3️⃣ Gaussian Naive Bayes

Probabilistic classifier assuming feature independence.

Strength:
✔ Extremely fast training

Failure Case:
Financial attributes are often correlated → assumption violated.

🔍 Hyperparameter Optimization

Logistic Regression tuned using:

GridSearchCV (5-fold Cross Validation)

Parameters explored:

Regularization type (l1, l2)

Regularization strength (C)

Purpose:

Reduce overfitting

Improve generalization

📊 Evaluation Metrics

Model performance evaluated using:

Confusion Matrix

Precision

Recall

F1 Score

Classification Report

Focus:

False Loan Approval Risk

False Rejection Cost
