# Loan Default Prediction Model

## Project Overview

This project aims to develop a classification model to predict whether a client is likely to default on their loan. By leveraging machine learning techniques, the project addresses the challenges faced by banks in making accurate, unbiased loan approval decisions. The ultimate goal is to improve decision-making efficiency and reduce the likelihood of bad loans (non-performing assets) while adhering to interpretability requirements for regulatory compliance.

## Problem Statement

Banks rely heavily on loan interest for profitability, but bad loans can significantly impact their bottom line. Traditionally, loan approvals have been based on manual assessments, which are time-intensive and prone to human bias. This project aims to simplify the process by creating a predictive model based on past applicant data. The model will help identify potential defaulters while maintaining interpretability to explain rejection decisions.

## Objective

1. Develop a machine learning model to classify loan applicants as likely to default or repay.

2. Provide key insights and recommendations on the most important features influencing loan approval decisions.

## Dataset

The dataset used for this project is the Home Equity Dataset (HMEQ), which includes baseline and loan performance data for recent home equity loans. Key attributes include:

* **BAD**: Target variable (1 = Defaulted, 0 = Repaid)

* **LOAN**: Loan amount approved

* **MORTDUE**: Amount due on the existing mortgage

* **VALUE**: Current value of the property

* **REASON**: Reason for the loan (Home improvement or debt consolidation)

* **JOB**: Job type of the applicant

* **YOJ**: Years at the current job

* **DEROG**: Number of major derogatory reports

* **DELINQ**: Number of delinquent credit lines

* **CLAGE**: Age of the oldest credit line in months

* **NINQ**: Number of recent credit inquiries

* **CLNO**: Number of existing credit lines

* **DEBTINC**: Debt-to-income ratio

## Methodology

1. **Data Exploration:** Analyzed the dataset for missing values, outliers, and feature distributions.

2. **Feature Engineering:** Addressed missing data, encoded categorical variables, and scaled numerical features.

3. **Modeling:** Built and evaluated multiple classification models, including:

    * Logistic Regression

    * Decision Trees

    * Random Forest

    * Gradient Boosting (e.g., XGBoost)

4. **Model Evaluation:** Used metrics such as precision, recall, F1-score, and ROC-AUC to evaluate performance.

5. **Threshold Adjustment:** Fine-tuned the decision threshold to 0.23 to maximize recall for class 1 while maintaining acceptable precision.

6. **Interpretability:** Leveraged techniques like SHAP values to identify key features influencing predictions.

## Results and Insights

### Executive Summary

* The primary objective was to maximize recall to minimize the number of false negatives.

* The XGBoost model achieved the best performance with a recall of 0.94 (adjusted threshold: 0.23).

* The dataset was imbalanced, with class 0 (negative class) overrepresented. While recall for class 0 was high, recall for class 1 was 0.80, showing a need for further optimization.

### Problem and Solution Summary

* Key Insights:

    * Accurately predicts both classes while balancing precision and recall.

    * Focused on reducing false negatives to avoid missing high-risk defaulters.

    * Adjusted the threshold to optimize recall for class 1, ensuring better identification of defaulters.

* Final Model: XGBoost, chosen for its robustness in handling imbalanced datasets and complex data structures.

### Recommendations for Implementation

1. **Data Improvements:** Use techniques like SMOTE or undersampling to improve recall for class 1 without significantly reducing precision.

2. **Integration:**

    * Deploy the trained model into the production system for real-time predictions or batch processing.

    * Regularly evaluate the model’s performance and adjust the threshold as needed.

3. **Monitoring and Scalability:**

    * Set up robust systems to monitor performance metrics in production.

    * Trigger retraining when performance degrades or new data becomes available.

    * Ensure scalability for increasing volumes of data while maintaining response times.

## Technologies Used

* **Programming Language:** Python

* **Libraries:** pandas, NumPy, scikit-learn, XGBoost, matplotlib, seaborn

* **Tools:** Jupyter Notebook, Google Colab
