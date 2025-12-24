# 📡 Customer Churn Prediction for "TeleDom"

## 📄 Project Description

This project aims to predict customer churn for the telecommunications operator "TeleDom." In a highly competitive market, the marketing department seeks to identify customers who are likely to terminate their contracts. The goal is to proactively offer them special conditions and promo codes to retain them.

**Business Objective:** Develop a machine learning model to predict whether a subscriber will terminate their contract.  
**Target Metric:** ROC-AUC.

## 💾 Data Overview

The data is valid as of **February 1, 2020**. The dataset consists of four files joined by `customerID`:

1.  **`contract_new.csv`**: Contract details (payment method, duration, monthly/total charges).
    * *Target Variable*: Derived from `EndDate` (if a termination date exists, the customer has churned).
2.  **`personal_new.csv`**: Client demographics (gender, partner status, dependents, senior citizen status).
3.  **`internet_new.csv`**: Internet service details (connection type, security, backup, etc.).
4.  **`phone_new.csv`**: Telephony service details.

## 🔧 Tools Used

The project is implemented in **Python** using the following libraries:

* **Data Manipulation:** `pandas`, `numpy`
* **Visualization:** `matplotlib`, `seaborn`
* **Machine Learning:** `scikit-learn`, `xgboost`
* **Statistical Analysis:** `statsmodels`, `phik`
* **Imbalanced Data:** `imbalanced-learn`
* **Model Interpretation:** `shap`

## 🧠 Main Techniques

The project employs specific advanced techniques for data processing and modeling:

* **Correlation Analysis**: Using **$\phi_k$ (Phik)** correlation matrix to capture non-linear relationships between categorical and numerical variables.
* **Class Imbalance Handling**: Utilizing **ADASYN** (Adaptive Synthetic Sampling) to generate synthetic data for the minority class (churned customers).
* **Feature Engineering**:
    * Creating new features like `agr_duration` (contract duration in days).
    * Imputing missing values based on service logic (e.g., missing internet services treated as 'No').
* **Data Transformation Pipelines**:
    * **One-Hot Encoding (OHE)** for nominal categorical features.
    * **Ordinal Encoding** for ordinal features.
    * **Scaling** using `StandardScaler` and `RobustScaler`.
* **Model Selection & Tuning**:
    * Comparing **Logistic Regression**, **Random Forest**, and **XGBoost**.
    * Hyperparameter optimization using **GridSearchCV**.
* **Model Explainability**: Using **SHAP** (SHapley Additive exPlanations) values to interpret model predictions and understand feature importance.

## ⚙️ Project Workflow

1.  **Data Loading & Inspection**: Merging multiple datasets and correcting data types.
2.  **Preprocessing**: Handling missing values, removing duplicates, and feature engineering.
3.  **Exploratory Data Analysis (EDA)**: Visualizing churn distributions and analyzing feature correlations.
4.  **Preparation for Training**: Splitting data, encoding features, and applying ADASYN.
5.  **Modeling**: Training multiple classifiers and tuning hyperparameters via cross-validation.
6.  **Evaluation**: Testing the best model on a hold-out set using the **ROC-AUC** metric.

## 🚀 How to Run

1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/project-name.git](https://github.com/your-username/project-name.git)
    ```
2.  Install the dependencies:
    ```bash
    pip install pandas numpy seaborn matplotlib scikit-learn xgboost phik shap imbalanced-learn statsmodels
    ```
3.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook "notebook (24).ipynb"
    ```

## 📊 Results

* A comprehensive analysis of churn factors was conducted.
* A robust predictive model was built using Gradient Boosting (XGBoost) / Random Forest.
* The model achieved a **ROC-AUC score suitable for production**, meeting the business requirements.

---
*Author: Ekaterina Babina*
