### Project Title: **Predicting Readmission Risk Using Machine Learning**

#### **Objective:**
The goal of this project is to build a machine learning model to predict hospital readmission for patients. The dataset used includes various medical features, such as lab procedures, medications, and hospital stay duration, among others. The target variable is whether a patient will be readmitted to the hospital (readmission: `Yes` or `No`). By identifying key features related to readmission risk, the model can help healthcare providers make informed decisions about patient care.

---

#### **Data Overview:**
The dataset contains a variety of medical and demographic features for each patient, such as:

- **Demographic Information:** Age, gender, race
- **Medical History:** Number of diagnoses, lab procedures, medications, and procedures
- **Hospital Data:** Admission type, discharge disposition, time spent in the hospital
- **Readmission Status (Target Variable):** Whether the patient was readmitted to the hospital within 30 days of discharge (`Yes` or `No`)

The data preprocessing involved cleaning the dataset by removing irrelevant or missing values, handling categorical variables, and feature selection.

---

#### **Data Preprocessing:**
1. **Handling Missing Values:** 
   - Some features in the dataset had missing values. These were either removed or imputed based on the nature of the data.
   - Features with a large number of missing values were excluded from the analysis.

2. **Feature Selection:**
   - A **Random Forest** model was used to evaluate the importance of each feature in predicting hospital readmission. 
   - The top 3 features were chosen based on their relevance to the target variable (readmission). These features were:
     - `num_lab_procedures`
     - `num_medications`
     - `time_in_hospital`

3. **Handling Categorical Data:**
   - The target variable (`readmitted`) was initially categorical with values `Yes` and `No`. These were mapped to numeric values (`1` for readmission and `0` for no readmission).
   - For the purpose of this analysis, age groups were also treated as a contributing factor for readmission prediction.

4. **Target Variable Transformation:**
   - The target variable was transformed to `0` (No) or `1` (Yes) based on both readmission status and age group (patients under 30 years or over 30 years old were considered as a group at risk of readmission, i.e., `1`).

---

#### **Exploratory Data Analysis (EDA):**
Before building the model, some initial exploration of the data was conducted:
- **Correlation Matrix:** The correlation between different features was analyzed to identify which features were most strongly related to readmission.
- **3D Scatter Plot:** A 3D scatter plot was created using the top 3 features (`num_lab_procedures`, `num_medications`, `time_in_hospital`) to visualize their relationship with the target variable (readmission). The plot displayed the distribution of patients based on these features, with color coding representing the readmission status.

---

#### **Model Development:**
A **Support Vector Machine (SVM)** model was trained on the cleaned and selected features to predict hospital readmission risk:
1. **Feature Selection:** The top 3 features identified earlier were used as the independent variables (inputs) for the SVM model.
2. **Target Variable:** The target variable was binary, representing whether a patient would be readmitted (1) or not (0).
3. **Model Training:** The SVM model was trained using the training dataset with the selected features and the transformed target variable.

---

#### **Visualization:**
A **3D scatter plot** was created to visualize the relationship between the top 3 features (`num_lab_procedures`, `num_medications`, `time_in_hospital`) and the readmission status. The plot helped in understanding how the different values of the features align with the target variable, providing insight into the factors that might influence readmission risk.

