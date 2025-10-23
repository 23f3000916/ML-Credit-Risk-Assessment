# Data-Driven Credit Risk Assessment: Predicting Customer Default

**Project Type:** BDM Capstone Project

## 1. Project Overview

This capstone project develops a data-driven predictive model to help a financial services firm identify high-risk credit card applicants *before* a card is issued. The goal is to leverage machine learning to flag customers likely to default, thereby reducing financial losses and strengthening the company's risk management strategy.

## 2. Problem Statement

The objective is to build a reliable classification model that predicts customer default. This model helps to:
* Flag high-risk accounts to reduce loan loss exposure.
* Understand the key factors driving default risk.
* Refine lending strategies with data-driven insights.

## 3. Dataset

The analysis was performed on the **"Default of Credit Card Clients"** dataset, a publicly available resource from the UCI Machine Learning Repository.

* **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients)
* **Scope:** 30,000 customer records with 24 features (demographics, credit limit, payment history, bill amounts, etc.).

## 4. Methodology & Analysis

The project followed a structured data science workflow:

1.  **Data Preprocessing:** Cleaned the dataset by renaming columns and mapping undocumented category values (for `EDUCATION` and `MARRIAGE`) to an 'Others' category for consistency.

2.  **Exploratory Data Analysis (EDA):** Uncovered a **22.1%** default rate, indicating a significant class imbalance. This finding emphasized the need to use metrics like **Recall** for model evaluation, as accuracy alone would be misleading.

3.  **Model Building & Evaluation:** Three classification models were trained and compared:
    * Logistic Regression (Baseline)
    * Decision Tree
    * Random Forest (Final Model)

**Model Performance Comparison:**

| Model | Accuracy | Precision (Default) | Recall (Default) | F1-Score (Default) |
| :--- | :---: | :---: | :---: | :---: |
| Logistic Regression | 81.15% | 0.67 | 0.23 | 0.34 |
| Decision Tree | 81.72% | 0.65 | 0.36 | 0.46 |
| **Random Forest** | **81.90%** | **0.66** | **0.36** | **0.47** |

The **Random Forest** was selected as the final model because it provided the best balance of performance, especially in **Recall (36%)**. For this business problem, maximizing Recall (correctly identifying actual defaulters) is critical to minimizing financial losses.

## 5. Key Findings

* **Insight 1: Recent Behavior is the Key Predictor:** The feature importance analysis showed that **`PAY_1` (the most recent month's payment status)** is overwhelmingly the most significant predictor of default, far more than static demographic data.

* **Insight 2: Credit Risk is Dynamic:** The key takeaway is that a customer's risk profile is not fixed; it changes based on their *current actions*. The most recent data is the most valuable data for assessing risk.

## 6. Actionable Recommendations

Based on the analysis, three data-driven recommendations were proposed:

1.  **Adopt the Random Forest Model** for automated risk scoring in the underwriting process.
2.  **Prioritize Recent Payment Behavior** (e.g., `PAY_1`, `PAY_2`) in all credit policies and risk assessments.
3.  **Develop a Proactive, Tiered Alert System** based on payment delays to intervene early and prevent serious delinquency.

## 7. Tools & Technologies

* **Language:** Python
* **Libraries:** Pandas, Matplotlib, Seaborn, Scikit-learn
* **Environment:** Jupyter Notebook

## 8. Repository Contents

* `BDM Capstone Report Proposal.pdf`: The initial project proposal.
* `BDM Capstone Report Final.pdf`: The comprehensive final report.
* `BDM Capstone Presentation.pdf`: A summary slide deck of the project.
* `Credit_Risk_Analysis.ipynb`: The Jupyter Notebook containing all analysis code.
* `data.xls`: The dataset used.
