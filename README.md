**PROBLEM STATEMENT:**
Doing a simple google search will tell you : In 2021, heart disease was the leading cause of death in the U.S., responsible for approximately 695,000 deaths, which translates to about 209.6 deaths per 100,000 people. That is an alarming number. It is also know that people of south Asian descent also have high probability of heart disease.  
This is why its an important question to answer. If we can have abundance of caution and more accurate predictability of this diseases, 1000s of deaths could be mitigated. Unlike cancer, there is less mystery around this disease The obvious answers are eating habits and lifestyle. But there could be more insights that could be unlocked specially around hereditary passing on of the heart disease to the future generation. 

**DATA:**
**DATA SOURCE - https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction**

**Explanation of what each column represents in a heart disease dataset:**
1. **Age** - Patient's age in years. Older age is generally associated with higher cardiovascular risk due to arterial aging and accumulated damage over time.
2. **Sex** - Biological sex (typically Male/Female). Males generally have higher risk of heart disease at younger ages, though this gap narrows after menopause in females.
3. **ChestPainType** - Classification of chest pain symptoms, usually categorized as typical angina, atypical angina, non-anginal pain, or asymptomatic. Typical angina (chest pain triggered by exertion and relieved by rest) is most strongly associated with coronary artery disease.
4. **RestingBP** - Resting blood pressure in mmHg. Higher values indicate hypertension, which damages arteries and increases heart disease risk. Normal is typically <120/80 mmHg.
5. **Cholesterol** - Serum cholesterol level in mg/dL. Higher levels contribute to atherosclerotic plaque formation in arteries. Total cholesterol >240 mg/dL is considered high risk.
6. **FastingBS** - Fasting blood sugar level, often as a binary indicator (1 if >120 mg/dL, 0 if ≤120 mg/dL). Elevated glucose levels indicate diabetes or prediabetes, major risk factors for cardiovascular disease.
7. **RestingECG** - Resting electrocardiogram results showing heart rhythm and electrical activity. Can detect arrhythmias, previous heart attacks, or left ventricular hypertrophy.
8. **MaxHR** - Maximum heart rate achieved during exercise testing. Lower maximum heart rates may indicate poor cardiovascular fitness or underlying heart problems.
9. **ExerciseAngina** - Whether chest pain occurs during exercise (Yes/No). Exercise-induced angina strongly suggests coronary artery disease as increased oxygen demand reveals inadequate blood supply.
10 **Oldpeak** - ST depression induced by exercise relative to rest on the ECG. Measured in millimeters, this indicates how much the ST segment drops during exercise, suggesting inadequate blood flow to heart muscle.
11. **ST_Slope** - The slope of the peak exercise ST segment on ECG, typically classified as upsloping, flat, or downsloping. Downsloping or flat ST segments during exercise are more concerning for coronary artery disease than upsloping patterns.

These variables collectively provide a comprehensive cardiovascular risk profile, combining demographic factors, symptoms, vital signs, lab values, and cardiac function tests commonly used in heart disease diagnosis and risk stratification.

**CRISP-DM Methodology**
The project is structured around the CRISP-DM framework, covering the following key stages:

1. **Data Collection & Loading:** The dataset is loaded into a pandas DataFrame.
2. **Data Cleaning & Preprocessing:**
   a. Invalid zero values in RestingBP and Cholesterol were identified and imputed with the median.
   b. Features were separated into numerical and categorical types for appropriate processing.
   c. A ColumnTransformer pipeline was used for feature engineering:
        > One-Hot Encoding for categorical features.
        > Standard Scaling for numerical features.
3. **Exploratory Data Analysis (EDA):**
   a. Visualizations were created to understand the distribution of features and their relationship with the target variable (HeartDisease).
   b. A correlation heatmap was generated to analyze relationships between numerical features.
4. **Model Training:**
   a. Four different classification models were trained and compared:
        > Logistic Regression
        > Random Forest Classifier
        > Bagging Classifier
        > XGBoost Classifier
   b. GridSearchCV was used for hyperparameter tuning with 5-fold cross-validation, optimizing for recall to prioritize the correct identification of patients with heart disease.
5. **Model Evaluation:**
   a. Models were evaluated on a held-out test set using key metrics: Accuracy, Precision, Recall, F1-Score, and ROC-AUC.
   b. A comparison table and a combined ROC curve plot were generated to visualize and select the best-performing model.

**========== COMPARISON OF MODEL PERFORMANCE FOR HEART DISEASE PREDICTION ==========**

                     Accuracy	 Precision (Class 1)	Recall (Class 1)	F1-Score (Class 1)
Logistic Regression	 0.876812	 0.922078	          0.865854	         0.893082
**Random Forest**	       0.873188	 0.881657	          **0.908537**	         0.894895
Bagging	             0.829710	 0.897959	          0.804878	         0.848875
XGBoost	             0.855072	 0.907895	          0.841463	         0.873418

**The top predictors include:**
**ST_Slope:** The slope of the ST segment during exercise.
**Oldpeak:** ST depression induced by exercise.
**ChestPainType_ASY:** Asymptomatic chest pain.
**Age:** The patient's age.
**ExerciseAngina:** Whether angina was induced by exercise.

**Conclusion**
Given the dataset and the different models used for training it is safe to conclude that out of the four Models The Random Forest Classifier is the best-suited model for this particular use case, primarily because of its superior Recall. The Random Forest model achieved the highest recall (90.9%), meaning it was the most effective at correctly identifying patients with heart disease. Its high F1-score and overall accuracy make it a robust and reliable choice. The main reason is that in a medical diagnostic scenario like heart disease prediction, the last thing you want is high False Negatives. A False Negative occurs when the model predicts a patient does not have heart disease when they actually do. This can be dangerous, as it could prevent a patient from receiving timely and life-saving treatment.


** Used Google Gemini AI to repharase my thoughts for this readme document.
