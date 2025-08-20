# -Loan-Approval-Prediction-Description
Loan Default Prediction 🏦
📌 Project Overview

This project focuses on building a machine learning model to predict loan default status (approved/rejected). It uses borrower and loan-related features to classify whether a person is likely to default or not.

📂 Dataset

The dataset contains the following features:

person_age – Age of the borrower

person_income – Annual income of the borrower

person_home_ownership – Home ownership status

person_emp_length – Employment length (in years)

loan_intent – Purpose of the loan (e.g., education, personal, medical)

loan_grade – Loan grade assigned by the lender

loan_amnt – Loan amount requested

loan_int_rate – Interest rate of the loan

loan_percent_income – Ratio of loan amount to borrower’s income

cb_person_default_on_file – Whether borrower has defaulted before (Yes/No)

cb_person_cred_hist_length – Length of credit history

Target Label:

loan_status → (0 = Loan Approved, 1 = Loan Defaulted)

⚙️ Preprocessing Steps

Handling Missing Values

Filled categorical NaNs with mode.

Filled numerical NaNs with median.

Encoding Categorical Features

Applied One-Hot Encoding for person_home_ownership, loan_intent, and cb_person_default_on_file.

Balancing the Dataset

Observed class imbalance (more approved loans than defaults).

Used two approaches:

class_weight="balanced" → Adjusts weights inversely proportional to class frequencies.

SMOTE (Synthetic Minority Oversampling Technique) → Generates synthetic samples for the minority class.

🤖 Models Used

Logistic Regression

Decision Tree Classifier

Both models were trained and evaluated with:

Baseline (imbalanced data)

Class Weight balancing

SMOTE oversampling

📊 Evaluation Metrics

Accuracy

Precision

Recall

F1 Score

Confusion Matrix

🔑 Since this is a loan default problem, Recall (True Positive Rate) is especially important.
Catching defaulters (1s) is more critical than just maximizing accuracy.

📈 Results

Logistic Regression and Decision Tree both achieved around 91% accuracy on baseline.

With class_weight="balanced", recall for defaulters improved but at the cost of precision.

With SMOTE, recall improved further, making the model better at detecting defaults.

Trade-off:

Balanced models reduce bias towards majority class.

Higher recall ensures fewer risky borrowers are misclassified as safe.

✅ Conclusion

Best approach: Use SMOTE + Logistic Regression (better recall, stable accuracy).

In real-world banking, catching potential defaulters is more important than overall accuracy.

This project demonstrates:

Understanding of imbalanced classification problems.

Use of resampling techniques (SMOTE) and class weights.

Clear evaluation with precision, recall, F1, and confusion matrix.

📌 Future Improvements

Hyperparameter tuning (GridSearchCV / RandomizedSearchCV).

Try ensemble methods (Random Forest, XGBoost).

Deploy as an API for real-time loan approval predictions.
