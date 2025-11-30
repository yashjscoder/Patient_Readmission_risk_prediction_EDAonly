# Diabetes 130-US Hospitals ML Pipeline (1999–2008)

This repository contains a comprehensive, end-to-end Machine Learning pipeline for the **Diabetes 130-US Hospitals dataset (1999–2008)**. The pipeline is designed to preprocess, encode, scale, and split clinical data, enabling reliable, interpretable AI/ML modeling for med-tech applications.

---

## Dataset Overview

* **Source:** Diabetes 130-US Hospitals dataset (1999–2008)
* **Features:** 130+ clinical and demographic attributes
* **Target:** Patient readmission within 30 days or >30 days

The dataset contains a mix of numeric, categorical, ordinal, and temporal variables, including lab results, medication usage, admission/discharge information, and patient demographics.

---

## Pipeline Overview

### 1. Raw Exploratory Data Analysis (EDA)

* Statistical profiling and distribution analysis of features
* Correlation matrix and multicollinearity detection
* Skewness and kurtosis evaluation
* Rare category detection and mapping
* Leakage checks and domain pattern identification

### 2. Data Cleaning

* Standardization of category labels and units
* Corrected biologically impossible values
* Removed duplicates and irrelevant features
* Enforced domain-specific constraints for medical validity

### 3. Missing Value Handling

* Numeric imputation: median, KNN-based (optional)
* Categorical imputation: mode or “Unknown”
* Missingness indicators and row-level missing counts
* Ensured clinical interpretability of imputed values

### 4. Outlier Treatment

* IQR and Z-score based filtering
* Winsorization and clipping for extreme values
* Domain-informed thresholds for physiologically impossible values
* Visual validation of outliers with boxplots

### 5. Categorical Encoding

* Label, One-Hot, Frequency, and Target encoding
* Handling high-cardinality variables without target leakage
* Optional advanced encodings: CatBoost, Leave-One-Out, Binary, Hashing

### 6. Feature Scaling

* StandardScaler, MinMaxScaler, and RobustScaler applied selectively
* Log-transform or power transform on skewed features
* Scaling applied only after train-test split to prevent data leakage

### 7. Train-Test Split & Cross-Validation

* Stratified and KFold splits depending on clinical grouping
* Leakage-proof pipeline for validation and test sets
* Ensured consistent column alignment after encoding

---

## Challenges Encountered

1. Preserving clinical interpretability while preprocessing high-dimensional data
2. Handling heterogeneous data types across 130+ features
3. Avoiding implicit target leakage in categorical encoding and feature engineering

---

## Importance in Medical & AIML Applications

* Ensures reproducible, high-quality preprocessing for predictive modeling
* Improves reliability of patient outcome predictions and readmission risk assessment
* Supports AI-assisted decision-making in clinical workflows
* Aligns with med-tech best practices: interpretability, robustness, and domain compliance

---

## Future Work

* Advanced feature engineering leveraging domain knowledge
* Baseline modeling: tree-based, linear, and ensemble algorithms
* Hyperparameter tuning, regularization, and overfitting mitigation
* Model interpretability: SHAP, feature importance, and partial dependence plots
* End-to-end pipeline automation for deployment in clinical ML environments

---

## Dependencies

* Python 3.9+
* pandas, numpy, scikit-learn, matplotlib, seaborn, joblib
* Optional: xgboost, catboost, lightgbm

---

## Usage

1. Clone the repository
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```
3. Preprocess the data using the pipeline scripts
4. Fit models and evaluate using cross-validation

---

## Author

Yash [LinkedIn/Portfolio link]
AI/ML Engineer | MedTech Data Specialist
