# Heart Disease Prediction: AIML Capstone Project

**Professional Certificate in AI/ML — Capstone Project**

---

## Problem Statement

In 2021, heart disease was the leading cause of death in the U.S., responsible for approximately 695,000 deaths (about 209.6 deaths per 100,000 people). This makes accurate heart disease prediction critically important; improved predictability could help mitigate thousands of deaths. Unlike cancer, there is less unpredictability if risk factors are well understood.

---

## Data

**Source:** [Kaggle - Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)

### Column Descriptions

| Column            | Description                                                                                             |
|-------------------|--------------------------------------------------------------------------------------------------------|
| Age               | Patient's age in years. Older age is associated with higher cardiovascular risk.                       |
| Sex               | Biological sex (Male/Female). Males have higher risk at younger ages; gap narrows after menopause.     |
| ChestPainType     | Chest pain type: typical angina, atypical angina, non-anginal pain, or asymptomatic.                   |
| RestingBP         | Resting blood pressure (mmHg). High values indicate hypertension and increased risk.                   |
| Cholesterol       | Serum cholesterol (mg/dL). High levels contribute to atherosclerosis.                                  |
| FastingBS         | Fasting blood sugar (1 if >120 mg/dL, else 0). Indicates diabetes/prediabetes risks.                   |
| RestingECG        | Resting ECG results. Can detect arrhythmias and heart damage.                                          |
| MaxHR             | Maximum heart rate during exercise. Lower values may indicate poor fitness or heart problems.          |
| ExerciseAngina    | Chest pain during exercise (Yes/No). Suggests coronary artery disease.                                 |
| Oldpeak           | ST depression on ECG during exercise (in mm). Indicates inadequate blood flow.                         |
| ST_Slope          | Slope of peak exercise ST segment (upsloping, flat, downsloping). Downsloping/flat are more concerning.|

---

## Methodology: CRISP-DM Framework

1. **Data Collection & Loading**
   - Dataset loaded into a pandas DataFrame.

2. **Data Cleaning & Preprocessing**
   - Invalid zero values in RestingBP and Cholesterol imputed with the median.
   - Features separated into numerical and categorical.
   - Used `ColumnTransformer` pipeline:
     - One-hot encoding for categorical features.
     - Standard scaling for numerical features.

3. **Exploratory Data Analysis (EDA)**
   - Visualizations for feature distributions and relationship with the HeartDisease target.
   - Correlation heatmap for numerical features.

4. **Model Training**
   - Trained and compared four models:
     - Logistic Regression
     - Random Forest Classifier
     - Bagging Classifier
     - XGBoost Classifier
   - Hyperparameter tuning with `GridSearchCV` (5-fold cross-validation), optimizing for recall.

5. **Model Evaluation**
   - Evaluated on a held-out test set using Accuracy, Precision, Recall, F1-Score, and ROC-AUC.
   - Comparison table and combined ROC curve plotted for model selection.

---

## Model Performance Comparison

| Model                | Accuracy  | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) |
|----------------------|-----------|---------------------|------------------|--------------------|
| Logistic Regression  | 0.876812  | 0.922078            | 0.865854         | 0.893082           |
| **Random Forest**    | 0.873188  | 0.881657            | **0.908537**     | 0.894895           |
| Bagging              | 0.829710  | 0.897959            | 0.804878         | 0.848875           |
| XGBoost              | 0.855072  | 0.907895            | 0.841463         | 0.873418           |

---

## Top Predictors

- **ST_Slope**: Slope of the ST segment during exercise.
- **Oldpeak**: ST depression induced by exercise.
- **ChestPainType_ASY**: Asymptomatic chest pain.
- **Age**: Patient’s age.
- **ExerciseAngina**: Whether angina was induced by exercise.

---

## Conclusion

Given the dataset and the models used, the **Random Forest Classifier** is best suited for this use case, primarily due to its high recall, which is crucial for correctly identifying patients with heart disease.

Project Report : https://github.com/karanmohan-git/AIML-Capstone-Project-Heart-Disease-Prediction/blob/main/Capstone%20Project_Final%20Report_KaranKauchur.pdf

---

