# Liver-Cirrhosis-Model-Classification
machine learning project for Final Exam of Machine Learning subject, focused on predicting the **stage of liver cirrhosis** using patient health indicators.  
This project compares **Random Forest** and **XGBoost** classifiers to determine which model performs better in classifying disease stages.

## Dataset Information
- **Source:** Provided dataset (`1A.tsv`) containing 418 patient records and 18 columns.  
- **Target Variable:** `Stage` (1–4).  
- **Features include:**
  - Bilirubin, Albumin, Copper, Alkaline Phosphatase, Triglycerides, Platelets, Prothrombin, SGOT, etc.
  - Categorical attributes such as Drug, Gender, Ascites, Hepatomegaly, and Edema.

---

## Exploratory Data Analysis (EDA)
- Checked missing values and value distributions.
- Analyzed relationships between medical indicators and cirrhosis stages.
- Key findings:
  - **Platelets** and **Prothrombin time** strongly correlate with disease severity.
  - **Triglycerides** tend to increase in late stages (3–4), indicating worsening condition.

---

## Data Preprocessing
- Dropped redundant “*_Status” columns after EDA.
- Label-encoded categorical variables (`Gender`, `Drug`, etc.).
- Split dataset into **training (80%)** and **testing (20%)** sets.
- No scaling applied — tree-based models handle raw numeric ranges well.

---

## Model Training
Two algorithms were trained and tuned:

| Model | Accuracy | Weighted F1-Score | Remarks |
|--------|-----------|-------------------|----------|
| Random Forest | **0.58** | 0.54 | Best overall performance |
| XGBoost | 0.51 | 0.49 | Slightly weaker on minority classes |

### Class-wise Summary
- Both models struggled with minority classes (Stage 0–1).  
- Random Forest achieved higher precision and recall overall.

---

## Feature Importance
Using **SHAP** (SHapley Additive exPlanations):
- Most influential features:  
  **Prothrombin**, **Platelets**, **Bilirubin**, and **Triglycerides**.
- These align with medical expectations of liver function decline.

---

## Conclusion
- Random Forest slightly outperformed XGBoost with better macro and weighted averages.
- Future improvements could include:
  - Balancing data (e.g., SMOTE)
  - Trying gradient boosting variants (LightGBM, CatBoost)
  - Hyperparameter optimization with cross-validation
 

###### This project is for educational purposes only
###### by Calista.L
