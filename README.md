# 💳 Credit Card Default Prediction

### A Data-Driven Approach to Proactive Risk Management

---

## 🎯 Project Overview

This project delivers a robust machine learning model designed to predict the likelihood of credit card default in the subsequent month. The core objective is to equip financial institutions with an interpretable and actionable tool for proactive risk management, enabling them to identify at-risk customers and implement timely, data-informed interventions.

---

## 💼 The Business Problem

In today's dynamic financial landscape, the ability to accurately forecast credit card default is paramount for mitigating financial losses. This project was undertaken for "Bank A" to replace reactive measures with a forward-looking predictive strategy, aiming to optimize credit risk policies and safeguard financial health.

---

## 🚀 Our Approach: A Structured, Iterative Journey

The development of the predictive model followed a systematic, multi-phase process to ensure robustness and reliability:

1.  **📊 Exploratory Data Analysis (EDA):** Dived deep into the dataset to visualize distributions, uncover hidden patterns in financial behavior, and identify key correlations with default likelihood.

2.  **🛠️ Feature Engineering:** Moved beyond raw data by constructing new, insightful features—such as average payment delays, total delinquency counts, and credit utilization ratios—to capture nuanced customer behaviors.

3.  **🧼 Data Preprocessing & Cleaning:** Ensured the highest data quality by standardizing payment history codes, meticulously handling missing values, and scaling numerical features to prepare a clean, high-quality dataset for modeling.

4.  **🧠 Model Training & Selection:** Trained and evaluated a diverse suite of classification models, including Logistic Regression, Random Forest, XGBoost, and LightGBM. Special techniques (e.g., `scale_pos_weight`) were used to address the inherent class imbalance of the dataset.

5.  **⚙️ Model Optimization:** The top-performing model, **LightGBM**, was selected and underwent two critical stages of optimization:
    *   **Hyperparameter Tuning:** Used `RandomizedSearchCV` to find the optimal model configuration.
    *   **Decision Threshold Tuning:** Fine-tuned the classification cutoff to maximize the F2-score, aligning the model's performance with the business priority of catching as many defaulters as possible.

6.  **✅ Final Prediction Generation:** Deployed the fully optimized model to generate predictions on the final, unlabeled validation dataset.

---

## 🏆 Key Findings & Results

The final, optimized LightGBM model demonstrated a strong predictive capability, balancing the need to identify defaulters with practical business constraints.

> **Final Model Performance (Test Set):**
> *   **F2-Score:** `0.6149`
> *   **Recall:** `0.7994` (Correctly identifies ~80% of actual defaulters)
> *   **Precision:** `0.3198`

**🔑 Critical Predictors:**
Analysis consistently revealed that the most significant predictors of default were rooted in recent financial activity:
*   **`pay_amt1`** (Most Recent Payment Amount)
*   **`Bill_amt1`** (Most Recent Bill Amount)
*   **`PAY_X` Statuses** (Payment History)
*   Core attributes like **`LIMIT_BAL`** (Credit Limit) and **`age`** also proved highly influential.

---

## 📈 Business Implications

The final model is tuned for a specific strategic trade-off, prioritizing the capture of defaulters.

*   **Impact of False Negatives (Missing Defaulters):** With a **Recall of ~80%**, the model provides a strong safety net, significantly reducing the number of defaults that would otherwise go unnoticed and lead to financial loss.

*   **Impact of False Positives (Incorrectly Flagging Good Customers):** A **Precision of ~32%** means that intervention strategies must be carefully designed. Low-cost, customer-centric actions like gentle payment reminders are recommended to avoid alienating customers who are incorrectly flagged.

*   **⚖️ The Strategic Trade-off:** The model is intentionally optimized for high Recall at the expense of Precision. This reflects a common banking stance where the financial damage from a missed default far outweighs the operational cost of a false positive. The included threshold tuning plot allows the bank to adjust this balance based on its specific risk appetite.

---

## 📂 Repository Structure
