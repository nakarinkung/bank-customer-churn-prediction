# Bank-Customer-Churn-Prediction

## Overview
This project explores how machine learning can help banks predict which customers are likely to leave (churn).  
By analysing customer demographics, account activity, and engagement patterns, the goal is to identify early warning signs of churn and provide actionable insights for customer retention.

---

## Research Questions
1. **Can machine learning help banks predict which customers are likely to leave, and how accurate can these predictions be?**  
2. **Which machine learning algorithm works best for predicting customer churn in banking data?**  
3. **What customer characteristics and behaviours are the most important warning signs that a customer might leave the bank?**

---

## Project Goals
- Perform **data exploration and cleaning**
- Build and compare multiple **machine learning models**  
- Improve model performance using **oversampling** for class imbalance  
- Interpret model predictions with **SHAP analysis**  
- Identify key features driving customer churn  

---

## Dataset Description
Each row represents a bank customer with demographic and financial information.

| Feature | Description |
|----------|-------------|
| **CustomerId** | Unique customer identifier |
| **Surname** | Customer’s last name |
| **CreditScore** | Creditworthiness score |
| **Geography** | Country of residence (France, Spain, Germany) |
| **Gender** | Male or Female |
| **Age** | Age of the customer |
| **Tenure** | Years the customer has been with the bank |
| **Balance** | Current account balance |
| **NumOfProducts** | Number of products held (e.g., accounts, credit cards) |
| **HasCrCard** | Credit card ownership (1 = Yes, 0 = No) |
| **IsActiveMember** | Active membership status (1 = Yes, 0 = No) |
| **EstimatedSalary** | Estimated annual salary |
| **Exited** | Target variable (1 = Churned, 0 = Retained) |

---

## Data Preprocessing
- Removed missing and duplicate entries  
- Handled **outliers** in numerical features  
- Applied **label encoding** / **one-hot encoding** to categorical variables  
- **Scaled** numerical variables for consistent model performance  
- **Oversampling** (e.g., SMOTE) applied to balance churn vs. non-churn classes  

---

## Machine Learning Models
Three models were trained and compared:

| Model | Type | Key Strengths |
|--------|------|---------------|
| **Logistic Regression** | Linear baseline | Interpretable, identifies significant predictors |
| **Random Forest** | Ensemble of decision trees | Handles nonlinearity, robust to noise |
| **XGBoost** | Gradient boosting | High accuracy, feature importance analysis |

---

## Model Evaluation
Each model was evaluated using:
- **Accuracy**
- **Precision / Recall / F1-score**
- **ROC–AUC**
- **Confusion Matrix**
- **Cross-validation scores**

Oversampling improved model balance and recall for the minority (churn) class.

---

## Model Insights with SHAP
**SHAP (SHapley Additive exPlanations)** was used to interpret the best-performing model (XGBoost).  
It explains how each feature contributes to the prediction of churn probability.

### Key Churn Indicators
- **Age** — Older customers show higher churn risk  
- **IsActiveMember** — Inactive customers are more likely to leave  
- **Balance** — Customers with moderate balances show varying loyalty patterns  
- **Geography** — Regional trends influence churn rates  
- **CreditScore** — Lower scores slightly correlate with churn  

Visuals include:
- SHAP summary plots  
- Feature importance bar charts  
---

## Results Summary

| Model | Accuracy | ROC–AUC | Key Notes |
|--------|-----------|----------|------------|
| Logistic Regression | Moderate | Moderate | Good interpretability |
| Random Forest | Higher | High | Balanced performance |
| XGBoost | Highest | Excellent | Best model overall |

➡️ **XGBoost achieved the best predictive performance**, providing strong accuracy and explainability with SHAP.

---

## Technologies Used
- **Python**
- **pandas**, **numpy**
- **matplotlib**, **seaborn**
- **scikit-learn**
- **XGBoost**
- **imbalanced-learn (SMOTE)**
- **SHAP**

---

## Key Takeaways
- Machine learning can effectively **predict churn** with reasonable accuracy.  
- **XGBoost** provides the best balance between accuracy and interpretability.  
- **Customer activity, age, and geography** are critical signals for churn.  
- **SHAP** enables transparent insights into model decisions, supporting business action.  

---

