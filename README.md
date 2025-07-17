---

# Credit Card Approval Prediction

## Overview

This project aims to predict credit card approval using a dataset that includes various features such as gender, car ownership, property ownership, income type, and more. The goal is to leverage data science techniques for credit scoring to assist in effective customer evaluation and minimize the risk of non-repayment of debts.

## Table of Contents

1. [Information](#information)
2. [Initial Hypotheses](#initial-hypotheses)
3. [Data Analysis Approach](#data-analysis-approach)
4. [EDA Findings](#eda-findings)
5. [Machine Learning Approach](#machine-learning-approach)
6. [Model Comparison](#model-comparison)

## Information

## Importance of the Proposal
- **Digital Financial Transactions:** In today's world, the rise in digital financial transactions has increased data complexity, necessitating efficient credit assessment.
- **Risk Mitigation:** Effective credit evaluation predicts whether a client is trustworthy, minimizing credit card fraud risks and ensuring a secure financial position for the institution.

## Impact on the Banking Sector
- **Customer Acquisition:** Focus on welcoming new credit card customers by leveraging data science tools such as Credit Scoring.
- **Risk Management:** Effective customer evaluation minimizes non-repayment risks, enhancing transaction security by detecting fraudulent activities.
- **Customer Satisfaction:** Understanding customer needs through data analysis allows the bank to tailor services, fostering satisfaction and loyalty.

## Future Relevance for Banks in India
- **Addressing Knowledge Gaps:** Future banking systems may benefit from insights into factors like Credit Score or CIBIL, Payment History, Number of Open Credit Accounts, Public Records, and Age.
  
## Key Technical Takeaways 
**A. Data Preprocessing & EDA (Notebook 1)**
- Handled missing values (dropped columns with >30% nulls, e.g., Type_Occupation).
- **Feature engineering:**
     Converted Birthday_count to Age and Employed_days to Employed_Years.
     Binned age into categories (Young/Adult/Senior) for better analysis.
     Outlier treatment: Used IQR method for Annual_income, Age, etc.
- **Hypothesis testing:** Validated business assumptions (e.g., "Marital status impacts approval").

**B. Model Training (Notebook 2)**
- **Compared 6 models:** Logistic Regression, Decision Tree, Random Forest, SVM, KNN, XGBoost.
- **Best model:** Random Forest (91% test accuracy, AUC 0.74).
- **Hyperparameter tuning:** Used GridSearchCV to optimize parameters (e.g., max_depth=10 for RF).
- **Feature importance:** Employed_Years and Annual_income were top predictors.

**C. SQL & Business Insights (Notebook 3)**
- **Key queries:**
- Average income by type (Commercial associates earn highest: ₹197k).
- 70 married applicants had bad credit; males outnumbered females (37 vs. 33).
- Top 5 earners (₹360k/year) were mostly state servants.
  
## Initial Hypotheses

### Categorical Feature Analysis

1. Gender, Car Ownership, Property Ownership, and Income Type do not significantly influence the target variable (Label).
2. Marital status significantly influences the target variable (Label).
3. Housing type does not significantly influence the target variable (Label).
4. Age Category does not significantly impact the target variable (Label).

### Numerical Feature Analysis

#### Annual Income Analysis

1. No significant correlation between annual income and the number of children.
2. Significant correlation between annual income and age.
3. Significant correlation between annual income and employed years.
4. No significant correlation between annual income and the number of family members.

#### Age Analysis

5. Significant correlation between the number of children and age.
6. Age and employed years are significantly correlated.
7. Significant correlation between age and the number of family members.

#### Employment Analysis

8. Employed years and the number of family members do not have a significant correlation.

---

## Data Analysis Approach

### Approach

1. Visualization
2. Pearson Correlation Coefficient with p_values
3. Association
4. Z-Tests

### Feature Engineering Techniques

1. Handling Outliers
2. Converting 'Birthday_count' to 'Birthdate' and 'Age'
3. Converting 'Employed_days' to 'Employment_startdate' and 'Employed_Years'
4. Using Binning and Discretization for 'Age'
5. Combining Categories in Categorical Features

### Data Analysis Justification

1. Data Cleaning and Preprocessing
2. EDA (Exploratory Data Analysis)
3. Handling Outliers
4. Feature Engineering
5. Feature Selection

### Important EDA Findings

- Gender Distribution
- Car Owner Distribution
- Label Distribution
- Marital Status Distribution
- Education Level Distribution
- Distribution of Age Category
- Children Distribution
- Annual Income Distribution
- Family Members Distribution
- Gender, Car Ownership, Property Ownership, and Income Type for the target variable (Label)
- Distribution of Marital status for the target variable (Label)
- Distribution of Housing type for the target variable (Label)
- Credit Card Approval by Age Category
- Annual Income by Age Category
- Box-plot for numerical features to handle outliers

---

## Machine Learning Approach

1. **Methods Used for Predictions**
   - Logistic Regression
   - Decision Tree
   - Random Forest
   - Support Vector Machine
   - K-Nearest Neighbour
   - Gradient Boosting

2. **Justification for Random Forest as the Most Appropriate Model**
   - Ability to handle non-linear relationships.
   - Robustness to overfitting.
   - Feature importance for interpretability.
   - Achieved high testing accuracy, mean cross-validation accuracy, and AUC.

3. **Steps to Improve Model Accuracy**
   - Fine-Tuning Hyperparameters
   - Cross-Validation Strategy
   - Results (Random Forest Model)

4. **Model Comparison**

![Testing Accuracy and AUC results](https://github.com/ridhed/Credit-Card-Approval-Prediction/assets/83410546/fa202228-ac0a-47f7-a1e6-2744fa9b9b72)


---
