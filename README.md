# Heart Disease Prediction

## Project Overview
This project focuses on predicting the likelihood of heart disease in individuals using machine learning models. The dataset includes both demographic and clinical features, such as age, cholesterol levels, chest pain type, and exercise-induced angina. The objective is to identify critical factors contributing to heart disease and build models to accurately classify patients at risk.

---

## Dataset Overview
The dataset comprises 14 attributes, including the target variable `target`, which indicates the presence of heart disease (1 = disease, 0 = no disease). Key features include:

- **Age**: Patient’s age in years.
- **Sex**: Gender of the patient (1 = male, 0 = female).
- **Cp (Chest Pain Type)**: Categorized into four types (e.g., typical angina, atypical angina).
- **Trestbps (Resting Blood Pressure)**: Blood pressure in mmHg at hospital admission.
- **Chol (Cholesterol)**: Serum cholesterol in mg/dL.
- **Thalach (Maximum Heart Rate Achieved)**: Measured during stress testing.
- **Oldpeak**: ST depression induced by exercise.
- **Exang (Exercise-Induced Angina)**: Presence of angina during exercise.

---

## Data Preprocessing
1. **Missing Values**: Verified that no missing values existed in the dataset.
2. **Feature Scaling**: Applied standardization to continuous variables for consistency.
3. **Feature Selection**: Recursive Feature Elimination (RFE) was employed with logistic regression to identify the most significant features.
4. **Hyperparameter Tuning**: Optimized the Decision Tree model using GridSearchCV for better performance.
5. **Data Splitting**: The dataset was divided into 80% training and 20% testing sets.

---

## Model Building
Three machine learning models were trained and evaluated:
1. **Logistic Regression**:
   - RFE was applied to optimize feature selection.
2. **Random Forest Classifier**:
   - Used as an ensemble model for comparison.
3. **Decision Tree Classifier**:
   - Hyperparameter tuning applied for enhanced performance.
   - Final model used for testing on a separate dataset.

---

## Model Evaluation
The models were evaluated based on accuracy. Below is the performance comparison:

| **Model**              | **Accuracy** |
|-------------------------|-------------|
| Logistic Regression     | 81%         |
| Random Forest           | 36%         |
| Decision Tree           | 81%         |
| Decision Tree (Test)    | 80%         |

---

## Insights
1. **Key Features Impacting Predictions**:
   - **Chest Pain Type (cp)**: Most significant feature associated with heart disease.
   - **Maximum Heart Rate (thalach)**: Lower values strongly correlated with higher risk.
   - **ST Depression (oldpeak)**: Higher values significantly increased the likelihood of heart disease.
   - **Exercise-Induced Angina (exang)**: Positive presence strongly correlated with heart disease.
2. **Age and Gender**:
   - Older patients and males exhibited higher risks of heart disease.
3. **Model Behavior**:
   - Logistic Regression and Decision Tree performed best in validation, achieving an accuracy of 0.81.

---

## Outcome of the Project
The final Decision Tree model was applied to a test dataset containing only patient IDs. Predictions were made on the likelihood of heart disease (1 = disease, 0 = no disease), achieving an accuracy of **0.80**. Below is an example of the prediction output:

| **Patient ID** | **Heart Disease Risk** |
|-----------------|------------------------|
| 001             | 1                      |
| 002             | 0                      |
| 003             | 1                      |
| 004             | 0                      |

![Heart Disease prediction Test Dataset](https://github.com/RihannatAdekunle/Heart-disease-prediction/blob/main/Heart%20disease%20prediction.csv)
These predictions allow targeted follow-ups for high-risk individuals, enabling timely medical interventions.

---

## Recommendations
1. **Focus on High-Risk Groups**:
   - Conduct regular screenings for older individuals and those with abnormal exercise responses or angina.
2. **Model Improvement**:
   - Explore boosting techniques (e.g., Gradient Boosting) to enhance model performance.
   - Investigate alternative feature engineering approaches.
3. **Feature Analysis**:
   - Evaluate new derived metrics, such as cholesterol ratios or blood pressure categories, for deeper insights.
4. **Implementation**:
   - Deploy the Decision Tree model in a clinical setting for real-time risk assessment.

---

## Conclusion
The project demonstrates that machine learning can effectively predict heart disease risk using clinical and demographic features. The Decision Tree model achieved an accuracy of 80% on unseen data, making it a viable tool for identifying high-risk patients and enabling proactive healthcare decisions.
