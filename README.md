# Credit Risk Analysis & Delinquency Prediction

## Project Overview
This project focuses on predicting loan delinquency using historical borrower data. The primary objective was to build an interpretable classification model to identify high-risk individuals, helping financial institutions mitigate potential losses.

## Key Challenges
* **Class Imbalance:** The dataset is highly imbalanced, with only 14% of cases representing delinquent accounts.
* **Model Interpretability:** In the credit industry, "Black Box" models are often avoided. I prioritized Logistic Regression to maintain transparency in decision-making.

## Tech Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Seaborn, Matplotlib, Scikit-learn
* **Models:** Logistic Regression, Random Forest Classifier

## Model Performance & Comparison

| Model | Accuracy | Recall (Class 1) | Observations |
| :--- | :--- | :--- | :--- |
| **Logistic Regression** | 45% | **0.36** | Best at identifying risk. Used `class_weight='balanced'` to catch 36% of delinquencies. |
| **Random Forest** | 86% | **0.00** | Suffered from the "Accuracy Trap." It predicted "Safe" for everyone, failing to find any risk. |

### The "Accuracy Trap" Insight
While the **Random Forest** showed a higher nominal accuracy (86%), it failed to identify a single delinquent account. The **Logistic Regression** (45% accuracy) was actually the more "useful" model for the business because it prioritized **Recall**, successfully flagging high-risk borrowers that the complex model missed.

## Key Visualizations
* **Correlation Heatmap:** Identified multi-collinearity between `credit_score` and `missed_payments`.
* **Age Group Analysis:** Visualized total missed payments across demographics to identify high-risk segments.
* **Confusion Matrix:** Used to diagnose the trade-off between False Positives and False Negatives.

## Future Improvements
1.  **SMOTE (Oversampling):** Implement Synthetic Minority Over-sampling Technique to better train models on delinquent cases.
2.  **Gradient Boosting:** Explore XGBoost or LightGBM to capture non-linear relationships that Logistic Regression missed.
3.  **Feature Engineering:** Create debt-to-income ratios and credit utilization tiers to improve linear separation.

---
*Developed as part of a Credit Risk Portfolio Project.*
