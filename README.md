# 🩺 Healthcare Provider Fraud Detection

![Title](title_image.png)

This project aims to detect fraudulent healthcare providers using robust **feature engineering**, **ML pipelines**, and **model interpretation** tools — built entirely in Python.

---

## 🎯 Objective

Identify **potentially fraudulent providers** in Medicare claim data by:
- Engineering relevant provider-level features
- Handling missing data
- Using ML pipelines with hyperparameter tuning
- Interpreting predictions with SHAP

---

## 📁 Data Overview

- `InpatientData.csv` / `OutpatientData.csv` – Claim records
- `BeneficiaryData.csv` – Demographics & chronic conditions
- `Train-Labels.csv` – Fraud indicators (Yes/No)
- `Test.csv` – Unlabeled test data

---

## ⚙️ Workflow Summary

### 1. **Preprocessing & Feature Engineering**
- Converted dates, calculated durations
- Counted procedure & diagnosis codes
- Merged datasets on keys
- Aggregated claim-level data to **provider-level**

### 2. **Missing Value Imputation**
- Used `IterativeImputer` (sklearn) on numerical features
- Ensured consistent logic for train & test sets

### 3. **Scaling & Pipelines**
- `RobustScaler` used to reduce outlier impact
- All models trained using **`Pipeline`** for clean, reproducible workflows

### 4. **Modeling & Evaluation**
- Tuned 3 classifiers using `RandomizedSearchCV`:  
  - **Random Forest**
  - **Gradient Boosting** ✅ *Best performer*
  - Logistic Regression

### ✅ Best Model: Gradient Boosting
- Accuracy: `94.6%`
- F1-Score (Fraud): `0.69`
- Saved to: `saved_models/GradientBoosting_model.pkl`

---

## 🔍 Model Interpretability

Used **SHAP** to explain the best model's predictions:

| Plot | Description |
|------|-------------|
| ![Bar](./outputs/shap_summary_bar_plot.png) | Top features by mean impact |
| ![Beeswarm](./outputs/shap_beeswarm_plot.png) | Feature value vs impact distribution |

---

## 📤 Final Predictions

- Scaled and preprocessed `test_df`
- Predicted fraud labels using best model
- Output saved to: `csv_files/HealthCare_Fraud_Predictions.csv`

---

## 📌 Highlights

- 📦 End-to-end pipeline with **minimal data leakage**
- 📊 Emphasis on **feature engineering** over raw EDA
- 💡 Interpretability with **SHAP** for business trust

---

## 👨‍💻 Author

**Abdullah Hanjra**  
📧 Email: [abdullahshahzadhunjra@gmail.com](mailto:abdullahshahzadhunjra@gmail.com)  
🔗 GitHub: [github.com/abdullahhunjra](https://github.com/abdullahhunjra)  
🔗 LinkedIn: [linkedin.com/in/abdullahhunjra](https://linkedin.com/in/abdullahhunjra)

---

## 📃 License

MIT License. Free to use, modify, and distribute.
