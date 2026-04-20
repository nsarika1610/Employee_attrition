# Employee Attrition Prediction using Machine Learning

## Project Overview
This project develops a machine learning-based employee attrition prediction system using structured organisational data. The objective is to identify employees at risk of leaving by comparing multiple machine learning models under a consistent experimental framework.

The project evaluates both baseline and tuned versions of the following models:
- XGBoost
- LightGBM
- CatBoost
- TabNet

The final selected model is **XGBoost Tuned**, based on its strong balance between **F1 Score** and **Recall**, which are critical for identifying employees at risk of attrition.

---

## Dataset
The dataset used in this project was obtained from Kaggle:

**Employee Attrition Dataset – Stealth Technologies**  
https://www.kaggle.com/datasets/stealthtechnologies/employee-attrition-dataset

### Dataset Summary
- Training records: 59,598
- Testing records: 14,900
- Original columns: 24
- Final features used: 22
- Numerical features: 7
- Categorical features: 15
- Target variable: `Attrition`

---

## Project Aim
To build and compare machine learning models for predicting employee attrition using structured organisational data and to identify the most effective model based on evaluation metrics such as **F1 Score**, **Recall**, and **ROC-AUC**.

---

## Research Questions
- **RQ1:** How effectively can machine learning models predict employee attrition using structured organisational data?
- **RQ2:** Which model among XGBoost, LightGBM, CatBoost, and TabNet provides the best performance in predicting employee attrition based on evaluation metrics such as F1 Score, Recall, and ROC-AUC?

---

## Workflow
The project follows this pipeline:

1. Data loading
2. Data inspection
3. Exploratory Data Analysis (EDA)
4. Feature selection
5. Feature separation
6. Data splitting
7. Preprocessing
8. Model training
9. Hyperparameter tuning
10. Evaluation and comparison

---

## Exploratory Data Analysis
EDA was performed to understand the structure and quality of the dataset before modelling.

The analysis included:
- dataset shape inspection
- missing values analysis
- duplicate check
- feature type classification
- target validation
- overall dataset consistency check

---

## Preprocessing
The following preprocessing steps were implemented:
- Removed non-predictive identifier column: `Employee ID`
- Selected `Attrition` as the target variable
- Encoded target variable:
  - Left = 0
  - Stayed = 1
- Applied stratified 80:20 split to create validation data
- Used `StandardScaler` for numerical features
- Used `OrdinalEncoder(handle_unknown="use_encoded_value", unknown_value=-1)` for categorical features
- Used model-specific preprocessing for CatBoost and TabNet

---

## Models Implemented

### Baseline Models
- XGBoost Baseline
- LightGBM Baseline
- CatBoost Baseline
- TabNet Baseline

### Tuned Models
- XGBoost Tuned
- LightGBM Tuned
- CatBoost Tuned
- TabNet Tuned

---

## Evaluation Metrics
The models were evaluated using:
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- PR-AUC

### Best Model Selection Logic
The final model was selected using the following priority order:

**F1 Score > Recall > PR-AUC > ROC-AUC > Accuracy > Precision**

---

## Final Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC AUC | PR AUC |
|------|----------|----------|--------|----------|---------|--------|
| XGBoost Baseline | 0.753859 | 0.763083 | 0.769674 | 0.766364 | 0.844100 | 0.864211 |
| XGBoost Tuned | 0.760990 | 0.767826 | 0.780230 | 0.773979 | 0.848642 | 0.868299 |
| LightGBM Baseline | 0.757970 | 0.766503 | 0.774472 | 0.770467 | 0.845867 | 0.865693 |
| LightGBM Tuned | 0.760487 | 0.768793 | 0.777031 | 0.772890 | 0.847929 | 0.867487 |
| CatBoost Baseline | 0.759899 | 0.770767 | 0.771753 | 0.771260 | 0.849819 | 0.870202 |
| CatBoost Tuned | 0.761997 | 0.771852 | 0.775432 | 0.773638 | 0.850434 | 0.870749 |
| TabNet Baseline | 0.750252 | 0.771874 | 0.743602 | 0.757475 | 0.836844 | 0.853836 |
| TabNet Tuned | 0.752349 | 0.761159 | 0.769194 | 0.765155 | 0.840060 | 0.858905 |

---

## Best Model
The final selected model is:

### **XGBoost Tuned**
- Accuracy: 0.760990
- Precision: 0.767826
- Recall: 0.780230
- F1 Score: 0.773979
- ROC-AUC: 0.848642
- PR-AUC: 0.868299

This model was selected because it achieved the **best balance between F1 Score and Recall**, which is important for correctly identifying employees at risk of attrition.

---

## Feature Importance
The most important factors influencing employee attrition include:
- Job Satisfaction
- Monthly Income
- Work-Life Balance
- Performance Rating

---


## Technologies Used
- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- LightGBM
- CatBoost
- PyTorch TabNet
- Matplotlib
- Seaborn
---

## Conclusion
This project shows that machine learning can effectively predict employee attrition using structured organisational data. Among all evaluated models, XGBoost Tuned achieved the strongest overall performance.

