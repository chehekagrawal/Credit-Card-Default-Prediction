# Credit Card Default Prediction

## Project Overview

This project focuses on developing a robust machine learning model to predict the probability of credit card default for the subsequent month. The primary objective is to provide a proactive risk management tool for financial institutions, enabling them to identify customers at high risk of default and implement timely interventions. This data-driven approach moves beyond simple prediction to create an interpretable and actionable solution.

---

## The Business Problem

In the financial landscape, accurately forecasting credit card default is crucial for mitigating financial losses and managing risk effectively. This project was undertaken for "Bank A" to address this challenge by building a model that can identify potential defaulters in advance. This allows the bank to optimize its credit risk strategies and take proactive measures.

---

## Our Approach: A Structured, Iterative Journey

The development of the predictive model followed a systematic and iterative process, encompassing the following key phases:

1.  **Data Loading & Initial Inspection:** The project began with loading and examining the customer datasets to understand their structure and the available data.

2.  **Exploratory Data Analysis (EDA):** This phase involved a deep dive into the data to visualize distributions, uncover patterns, and analyze trends in financial behavior over the preceding six months. A key focus was understanding the correlations between customer attributes and the likelihood of default.

3.  **Feature Engineering:** To enhance the predictive power of the models, new features were engineered to capture more nuanced financial habits. These included metrics like average payment delays, total delinquency counts, and credit utilization ratios.

4.  **Data Preprocessing & Cleaning:** The data was meticulously cleaned and prepared for modeling. This included standardizing payment history codes and handling missing values to ensure high-quality input for the models.

5.  **Model Training, Comparison & Selection:** A diverse suite of classification models was trained, including:
    *   Logistic Regression
    *   Random Forest
    *   XGBoost
    *   LightGBM

    A significant challenge was the class imbalance between defaulting and non-defaulting customers, which was addressed using techniques like class weighting and SMOTE. Models were rigorously evaluated with a special emphasis on the F2-score, which prioritizes the identification of actual defaulters.

6.  **Model Optimization:** The best-performing model, LightGBM, underwent further optimization through:
    *   **Hyperparameter Tuning:** RandomizedSearchCV was employed to find the optimal settings for the LightGBM algorithm.
    *   **Decision Threshold Tuning:** The probability cutoff for classifying a customer as a defaulter was fine-tuned to maximize the F2-score.

7.  **Final Prediction Generation:** The fully optimized model and its ideal threshold were used to generate predictions on an unlabeled validation dataset.

---

## Key Findings and Results

The final LightGBM model, after optimization, demonstrated a strong ability to predict credit card defaults.

*   **Champion Model:** The final model achieved a **test set F2-score of 0.6149** and a **Recall of 0.7994** for the default class.
*   **Critical Predictors:** The analysis consistently highlighted the paramount importance of recent financial behaviors, specifically:
    *   `pay_amt1` (most recent payment amount)
    *   `Bill_amt1` (most recent bill amount)
    *   `PAY_X` payment statuses
*   **Core Attributes:** Core customer attributes like `LIMIT_BAL` (credit limit) and `age` also proved to be significant predictors.

---

## Business Implications

The final model, with an optimal decision threshold of 0.3776, is projected to achieve a **Recall of approximately 79.9%** and a **Precision of approximately 31.98%** on unseen data.

*   **Impact of False Negatives:** The model is expected to correctly identify nearly 4 out of every 5 customers who would genuinely default, which is a substantial capture rate for minimizing credit losses.
*   **Impact of False Positives:** The precision rate indicates that for every 100 customers flagged as high-risk, about 68 are likely to be false alarms. This necessitates a well-designed intervention strategy that is low-cost and customer-centric to avoid negatively impacting good customers.
*   **Strategic Trade-off:** The model intentionally prioritizes high Recall over Precision, aligning with the common banking principle that the cost of a missed default is significantly greater than the cost of a false positive.

---

## Repository Structure

*   `Credit Card Default Prediction.ipynb`: The Jupyter Notebook containing the complete code for data analysis, feature engineering, model training, and evaluation.
*   `Credit Card Default Prediction Report.pdf`: A detailed report summarizing the project's objectives, methodology, findings, and business implications.
*   `README.md`: This file, providing an overview of the project.

---

## How to Use This Project

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/credit-card-default-prediction.git
    ```
2.  **Explore the Jupyter Notebook:** Open `Credit Card Default Prediction.ipynb` to review the code and the step-by-step process.
3.  **Read the Report:** For a comprehensive understanding of the project, refer to the `Credit Card Default Prediction Report.pdf`.
