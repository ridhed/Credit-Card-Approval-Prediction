
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
- [Key Insights & Visualizations ](#-key-insights-&-visualizations )  
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

## 📊 Key Insights & Visualizations  

### 1. **Data Distribution**  
#### Demographics & Features  
- **Gender**: Balanced binary distribution (`F=0`, `M=1`).  
- **Education**: Mostly "Secondary Education" (727) vs. "Higher Education" (305).  
  ![Education Distribution]<img width="817" height="270" alt="Screenshot 2025-07-17 154913" src="https://github.com/user-attachments/assets/2bc97560-2c17-4f59-a745-cd4aeb234463" />
- **Marital Status**: 67.6% Married, 14.6% Single.  
  ![Marital Status](Screenshot_2025-07-17_154901.png)  
- **Income**: Right-skewed; most incomes ≤ ₹300K.  
  ![Income Distribution](Screenshot_2025-07-17_155007.png)  

#### Target Variable (`Label`)  
- **Approval Rate**: 87% approved vs. 13% rejected.  
  ![Approval Distribution](Screenshot_2025-07-17_154852.png)  

---

### 2. **Feature Importance & Model Performance**  
#### Top Predictors of Approval (Random Forest)  
1. **Employed_Years** (29%)  
2. **Age** (20%)  
3. **Annual_income** (19%)  
  ![Feature Importance](Screenshot_2025-07-17_155720.png)  

---

### 3. **Business Insights**  
#### Approval Trends by Demographics  
- **Age**: Seniors (60-69) have higher incomes but similar approval rates.  
  ![Income by Age](Screenshot_2025-07-17_155118.png)  
  ![Approval by Age](Screenshot_2025-07-17_155108.png)  
- **Marital Status**: Married applicants dominate (50% of data).  
  ![Approval by Marital Status](Screenshot_2025-07-17_155034.png)  
- **Property Ownership**: No significant impact on approval (`p=0.51`).  

#### SQL Findings  
- Highest earners: Commercial associates (₹197K avg).  
- Married males had 12% more rejections than females.  

---

### 4. **Data Preprocessing**  
#### Encoding & Feature Types  
- **Binary**: `Car_Owner` (`Y=1`, `N=0`), `Label` (`Approved=0`).  
- **Ordinal**: `Education` (Higher=1, Lower=2), `Age_Category` (Young=2).  
  *(Full mapping in Notebook 1)*  

#### Outliers Handled  
- Removed extreme values in `Annual_income`, `Age`, and `Employed_Years` using IQR.  

---

### 5. **How to Navigate This Project**  
1. **Notebook 1**: EDA, cleaning, feature engineering.  
2. **Notebook 2**: Model training/evaluation (91% accuracy).  
3. **Notebook 3**: SQL queries for business insights.  

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
