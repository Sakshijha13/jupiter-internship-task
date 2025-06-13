# Credit Score Movement Prediction - Internship Task

## 🎯 Objective
Predict whether a customer's credit score will **increase**, **decrease**, or remain **stable** over the next 3 months using simulated financial behavior data.

---

## 📦 Dataset

- **Rows:** 25,000  
- **Each row**: Represents a customer-month entry  
- **Target column**: `target_credit_score_movement` (increase, decrease, stable)

### 🔍 Features:
- Demographic: age, gender, location
- Financial: monthly_income, monthly_emi_outflow, total_credit_limit
- Credit behavior: repayment_history_score, dpd_last_3_months, credit_utilization_ratio
- Loan & inquiry data: num_open_loans, num_hard_inquiries_last_6m, recent_loan_disbursed_amount

### 🧠 Label Generation Logic:
- **Decrease**: High DPD + high utilization + many hard inquiries  
- **Increase**: Low EMI/income ratio + high repayment score + no DPD  
- **Stable**: All other cases

---

## 🧪 Model Training

- Tried multiple models: `RandomForestClassifier`, `LogisticRegression`, `SVC`, and `XGBoost`
- Handled class imbalance using stratified sampling
- Evaluated using:
  - Accuracy
  - F1-score (macro)
  - Class-wise precision/recall
  - Confusion matrix

---

## 📊 Key Insights

- High DPD and credit utilization are strong indicators of score **decrease**
- Customers with good repayment history and low EMI/income ratio are likely to **improve** credit score
- Most customers fall under the **stable** category (as expected)

---

## 🛡 Recommendations

### For High-Risk (Likely Decrease):
- Trigger alerts for financial counseling
- Temporarily reduce credit limit
- Suggest auto-debit setup for EMIs

### For High-Opportunity (Likely Increase):
- Offer pre-approved loans or credit limit increases
- Reward good credit behavior with lower interest rates

---

## 📁 Files Submitted
- `credit_score_dataset.csv` — simulated dataset
- `sakshi.ipynb` — notebook with code, EDA, model training & evaluation
