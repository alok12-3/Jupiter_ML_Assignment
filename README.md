# 🔮 Predicting Change in Credit Score – ML Internship Assignment (Jupiter)

## 📌 Objective
Simulate a realistic dataset and build a machine learning model to predict whether a customer’s credit score will **increase**, **decrease**, or remain **stable** over the next 3 months.

---

## 🚀 Approach

### 1. 🧪 Synthetic Dataset Generation
- **Dataset Size:** 25,000+ rows (unique customer-month instances)
- **Features:**
  - **Demographics:** Age, gender, location
  - **Financials:** Income, EMI, outstanding amount, utilization, credit limit
  - **Behavioral:** DPD (days past due), inquiries, recent usage
  - **Summary Stats:** Repayment score, months since last default
- **Target Variable:** `target_credit_score_movement` (increase / decrease / stable)
- **Heuristics Used:**
  - 🔻 Likely Decrease: High DPD, high utilization, new inquiries
  - 🔺 Likely Increase: Low EMI/income ratio, strong repayment score
  - ➖ Stable: All other cases
- **Note:** Data distribution mimics real-world credit behavior, with injected randomness for diversity.

### 2. 📊 Exploratory Data Analysis (EDA)
- Visualized key distributions (income, utilization, repayment score)
- Analyzed class distribution & feature correlations
- Discovered strong indicators for score movement

### 3. 🤖 Model Training & Evaluation
- **Model:** XGBoost multi-class classifier
- **Pipeline:** Preprocessing (scaling, encoding, imputation)
- **Class Imbalance Handling:** SMOTE + class weights
- **Evaluation Metrics:**
  - Accuracy
  - Weighted F1-score
  - Class-wise recall
- **Model Explainability:** Analyzed feature importances and correlations

### 4. ⚙️ Advanced Modeling
- Hyperparameter tuning using **Optuna**
- Ensemble learning (XGBoost + LightGBM + Logistic Regression)
- Calibration for reliable probability outputs

---

## ✅ Results

### 🏆 Best Model
- **Stacked Ensemble:** XGBoost + LightGBM + Logistic Regression

### 📈 Performance Metrics
- **Accuracy:** ~67%
- **Weighted F1-score:** ~0.67
- **Class-wise Recall:** Balanced across all three classes

### 🔑 Key Feature Drivers
- Repayment history score
- Credit utilization ratio
- Recent DPD
- EMI-to-income ratio

---

## 💼 Business Takeaways

- **High-Risk Segments:** Customers with high DPD, high utilization, and recent inquiries are at risk of score reduction.
- **Growth Opportunities:** Customers with strong repayment history and low EMI/income ratios may see improvements.
- **Actionable Interventions:**
  - Early warnings for high-risk customers
  - Dynamic credit limit adjustments
  - Personalized financial guidance

---

## 📁 Files Included

| File                          | Description                                |
|------------------------------|--------------------------------------------|
| `synthetic_credit_score_dataset.csv` | Generated synthetic dataset              |
| `JUPITER27.ipynb`            | Full EDA, model training, evaluation, tuning |
| `README.md`                  | Project overview and documentation         |

---

## 📌 Assumptions
- All feature logic is derived from domain knowledge and public credit datasets.
- No real credit bureau data is used.
- All code is self-contained and reproducible within the notebook.

---

> **Prepared for**: *Jupiter ML Internship Assignment*  
> **Team**: President’s Office – Strategic Projects
