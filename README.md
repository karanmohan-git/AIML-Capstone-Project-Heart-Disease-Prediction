**DATA:**
DATA SOURCE - https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction

Explanation of what each column represents in a heart disease dataset:
Age - Patient's age in years. Older age is generally associated with higher cardiovascular risk due to arterial aging and accumulated damage over time.
Sex - Biological sex (typically Male/Female). Males generally have higher risk of heart disease at younger ages, though this gap narrows after menopause in females.
ChestPainType - Classification of chest pain symptoms, usually categorized as typical angina, atypical angina, non-anginal pain, or asymptomatic. Typical angina (chest pain triggered by exertion and relieved by rest) is most strongly associated with coronary artery disease.
RestingBP - Resting blood pressure in mmHg. Higher values indicate hypertension, which damages arteries and increases heart disease risk. Normal is typically <120/80 mmHg.
Cholesterol - Serum cholesterol level in mg/dL. Higher levels contribute to atherosclerotic plaque formation in arteries. Total cholesterol >240 mg/dL is considered high risk.
FastingBS - Fasting blood sugar level, often as a binary indicator (1 if >120 mg/dL, 0 if ≤120 mg/dL). Elevated glucose levels indicate diabetes or prediabetes, major risk factors for cardiovascular disease.
RestingECG - Resting electrocardiogram results showing heart rhythm and electrical activity. Can detect arrhythmias, previous heart attacks, or left ventricular hypertrophy.
MaxHR - Maximum heart rate achieved during exercise testing. Lower maximum heart rates may indicate poor cardiovascular fitness or underlying heart problems.
ExerciseAngina - Whether chest pain occurs during exercise (Yes/No). Exercise-induced angina strongly suggests coronary artery disease as increased oxygen demand reveals inadequate blood supply.
Oldpeak - ST depression induced by exercise relative to rest on the ECG. Measured in millimeters, this indicates how much the ST segment drops during exercise, suggesting inadequate blood flow to heart muscle.
ST_Slope - The slope of the peak exercise ST segment on ECG, typically classified as upsloping, flat, or downsloping. Downsloping or flat ST segments during exercise are more concerning for coronary artery disease than upsloping patterns.

These variables collectively provide a comprehensive cardiovascular risk profile, combining demographic factors, symptoms, vital signs, lab values, and cardiac function tests commonly used in heart disease diagnosis and risk stratification.

**PROBLEM STATEMENT:**
Doing a simple google search will tell you : In 2021, heart disease was the leading cause of death in the U.S., responsible for approximately 695,000 deaths, which translates to about 209.6 deaths per 100,000 people. That is an alarming number. It is also know that people of south Asian descent also have high probability of heart disease.  
This is why its an important question to answer. If we can have abundance of caution and more accurate predictability of this diseases, 1000s of deaths could be mitigated. Unlike cancer, there is less mystery around this disease The obvious answers are eating habits and lifestyle. But there could be more insights that could be unlocked specially around hereditary passing on of the heart disease to the future generation. 

**CRISP-DM Methodology**
CRISP-DM (Cross-Industry Standard Process for Data Mining) is a widely-used methodology that provides a structured approach to data mining projects. Here's a step-by-step breakdown of its six phases:
1. Business Understanding
This initial phase focuses on understanding the project objectives and requirements from a business perspective. Key activities include defining business objectives, assessing the current situation, determining data mining goals, and producing a project plan. The goal is to translate business questions into data mining problem definitions.
2. Data Understanding
This phase involves initial data collection and familiarization with the data. Activities include gathering initial data, describing and exploring the data, and verifying data quality. You'll examine data attributes, identify data quality problems, and gain insights into the data that will inform later phases.
3. Data Preparation
Often the most time-consuming phase, data preparation involves all activities needed to construct the final dataset for modeling. This includes selecting relevant data, cleaning and transforming data, handling missing values, creating derived attributes, and formatting data appropriately for the chosen modeling techniques.
4. Modeling
In this phase, you select and apply various modeling techniques and calibrate their parameters to optimal values. Different algorithms may require different data formats, so you might need to step back to the data preparation phase. Activities include selecting modeling techniques, generating test designs, building models, and assessing model quality.
5. Evaluation
Before proceeding to deployment, you thoroughly evaluate the model and review the steps taken to construct it. The goal is to determine if the model properly achieves the business objectives and to decide if there are important business issues not sufficiently considered. This phase ensures the model meets business success criteria.
6. Deployment
The final phase involves planning and implementing the deployment of the model into the business environment. This might involve generating reports, implementing a repeatable data mining process, or creating a live system. The deployment phase also includes monitoring and maintenance plans to ensure the model continues to perform effectively over time.
The methodology is iterative, meaning you may need to cycle back to previous phases based on findings in later stages. This flexibility makes CRISP-DM particularly valuable for complex, real-world data mining projects.
