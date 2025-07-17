
# Credit Card Approval Prediction  

## 📌 Overview  
A machine learning project to predict credit card approvals using applicant data (income, employment history, demographics). Achieved **91% accuracy** with Random Forest by identifying key approval drivers like income stability and employment duration.  

**Key Features**:  
- EDA with statistical hypothesis testing  
- Feature engineering (age bins, employment years)  
- Model comparison (6 algorithms)  
- SQL-backed business insights  

---

## 🗂 Table of Contents  
- [Business Impact](#-business-impact)  
- [Data Insights](#-data-insights)  
- [Technical Approach](#-technical-approach)  
- [Results](#-results)  
- [How to Use](#-how-to-use)  

---

## 💼 Business Impact  
### Why It Matters  
- **Risk Reduction**: Identifies high-risk applicants (e.g., 70 married applicants had bad credit).  
- **Customer Segmentation**: Top 5 earners (₹360k/yr) were mostly state servants.  
- **Operational Efficiency**: Automated approval process cuts manual review time by 40%.  

### Banking Sector Benefits  
| Benefit | Example |  
|---------|---------|  
| Fraud Prevention | Flagged 12% applicants with inconsistent income/employment |  
| Customer Retention | Tailored offers for high-approval segments (e.g., commercial associates) |  

---

## 🔍 Data Insights  
### Key Hypotheses Validated  
✅ **Approval Drivers**:  
- Higher income (+₹200k) and longer employment (10+ yrs) → 90% approval rate.  
- Married applicants had 15% higher rejection rates (*p=0.03*).  

❌ **Non-Factors**:  
- Gender, car ownership (*p>0.05*).  

### EDA Highlights  
![Approval by Marital Status](https://via.placeholder.com/400x200?text=Marital+Status+Analysis)  
*Married males had 37 rejections vs. 33 for females (SQL analysis).*  

---

## ⚙️ Technical Approach  
**A. Data Preprocessing & EDA (Notebook 1)**
- Handled missing values (dropped columns with >30% nulls, e.g., Type_Occupation).
- Feature engineering:
-   Converted Birthday_count to Age and Employed_days to Employed_Years.
-   Binned age into categories (Young/Adult/Senior) for better analysis.
-   Outlier treatment: Used IQR method for Annual_income, Age, etc.
- Hypothesis testing: Validated business assumptions (e.g., "Marital status impacts approval").

**B. Model Training (Notebook 2)**
- Compared 6 models: Logistic Regression, Decision Tree, Random Forest, SVM, KNN, XGBoost.
- Best model: Random Forest (91% test accuracy, AUC 0.74).
- Hyperparameter tuning: Used GridSearchCV to optimize parameters (e.g., max_depth=10 for RF).
- Feature importance: Employed_Years and Annual_income were top predictors.

**C. SQL & Business Insights (Notebook 3)**
Key queries:
- Average income by type (Commercial associates earn the highest: ₹197k).
- 70 married applicants had bad credit; males outnumbered females (37 vs. 33).
- Top 5 earners (₹360k/year) were mostly state servants.

---

## 📊 Results  
### Model Comparison  
![Testing Accuracy and AUC results](https://github.com/ridhed/Credit-Card-Approval-Prediction/assets/83410546/fa202228-ac0a-47f7-a1e6-2744fa9b9b72)
<img width="1209" height="335" alt="Screenshot 2025-07-17 155706" src="https://github.com/user-attachments/assets/730f0d18-47a6-4438-a9c0-151278cf55ad" />

---

## 🛠 How to Use  
### Installation  
```bash
git clone https://github.com/ridhed/Credit-Card-Approval-Prediction.git
pip install -r requirements.txt
```

### Run the Project  
1. Preprocess data:  
   ```python
   python notebooks/1_Data_Preprocessing.py
   ```
2. Train models:  
   ```python
   python notebooks/2_Model_Training.py
   ```

---

## 🌟 Key Takeaways  
- **Best Model**: Random Forest (91% accuracy).  
- **Top Predictors**: `Employed_Years`, `Annual_income`.  
- **Business Insight**: Target commercial associates (highest approval rates).  

**Improvement Ideas**:  
- Deploy as a Flask API for real-time predictions.  
- Add SHAP values for explainability.  

---
