# Diabetes-Forecasting
The aim is to build a Support Vector Machine (SVM) model to classify whether an individual has diabetes based on diagnostic measurements.
# Predicting Diabetes Onset using Support Vector Machines (SVM)

## Project Overview

Diabetes is a global health challenge affecting **537 million adults worldwide** (International Diabetes Federation, 2023). It is a leading cause of blindness, kidney failure, heart disease, and amputations. This project applies **Support Vector Machines (SVM)** to classify patients as **diabetic or non-diabetic** using the **Pima Indians Diabetes Database**. The objective is to evaluate the feasibility of SVM models in **clinical decision support systems (CDSS)** for hospitals.

## Objectives

- **Develop an SVM-based classification model** for predicting diabetes onset.
- **Analyze key patient health metrics** through Exploratory Data Analysis (EDA).
- **Improve model performance** using feature selection and hyperparameter tuning.
- **Assess real-world applicability** in healthcare settings.

## Dataset Overview

- **Dataset Name:** Pima Indians Diabetes Database
- **Source:** National Institute of Diabetes and Digestive and Kidney Diseases (NIDDK)
- **Patient Group:** Pima Indian women (high-risk diabetes group)
- **Total Instances:** 768 patients
- **Features (8):** Glucose levels, blood pressure, insulin levels, BMI, age, etc.
- **Target Variable:** Diabetes status (`1 = Diabetic`, `0 = Non-Diabetic`)

## Exploratory Data Analysis (EDA)

- **Outliers detected** in insulin and skin thickness measurements.
- **Class imbalance:** More non-diabetic than diabetic cases, requiring resampling techniques.
- **Missing values replaced** with column means to avoid data loss.

### **Dataset Summary Statistics**

| Feature           | Count | Mean  | Std Dev | Min  | 25%  | 50%  | 75%  | Max |
| ----------------- | ----- | ----- | ------- | ---- | ---- | ---- | ---- | --- |
| Pregnancies       | 768   | 0.226 | 0.198   | 0.0  | 0.05 | 0.18 | 0.35 | 1.0 |
| Glucose           | 768   | 0.611 | 0.153   | 0.22 | 0.50 | 0.59 | 0.70 | 1.0 |
| Blood Pressure    | 768   | 0.592 | 0.099   | 0.19 | 0.52 | 0.59 | 0.65 | 1.0 |
| Skin Thickness    | 768   | 0.269 | 0.097   | 0.07 | 0.20 | 0.23 | 0.32 | 1.0 |
| Insulin           | 768   | 0.140 | 0.110   | 0.02 | 0.09 | 0.09 | 0.15 | 1.0 |
| BMI               | 768   | 0.484 | 0.102   | 0.27 | 0.41 | 0.48 | 0.55 | 1.0 |
| Diabetes Pedigree | 768   | 0.195 | 0.137   | 0.03 | 0.10 | 0.15 | 0.26 | 1.0 |
| Age               | 768   | 0.410 | 0.145   | 0.26 | 0.30 | 0.36 | 0.51 | 1.0 |

## Data Preprocessing

- **Handling Missing Values:** Replaced zeros in medical features (`plas, pres, skin, insu, mass`) with mean values.
- **Feature Scaling:** Used **StandardScaler** to normalize numerical values.
- **Data Splitting:** **70% Training, 30% Testing**.
- **Encoding:** Converted categorical labels to numerical format.

##  Model Selection & Training

**SVM Kernel Comparisons:**

| Kernel         | Decision Function Shape | Accuracy (Test)            |
| -------------- | ----------------------- | -------------------------- |
| **Linear**     | ovo                     | 74%                        |
| **RBF**        | ovo                     | 74%                        |
| **Polynomial** | ovo                     | **75% (Best Performance)** |

### **Why Did the Polynomial Kernel Perform Best?**

- Captures **non-linear relationships** in medical data.
- Provides a balance between **accuracy and generalizability**.

## Model Evaluation

- **Overall Accuracy:** 74%
- **Precision (Diabetic Cases):** 0.64
- **Recall (Diabetic Cases):** 0.59 *(indicates missed diabetic cases)*
- **F1-Score (Diabetic Cases):** 0.61

### Key Takeaways

- The model **performs better for non-diabetic cases** than diabetic cases.
- **False negatives (missed diabetes cases) are a concern in medical settings**.
- Class imbalance **reduces recall for diabetic cases**, indicating a need for **resampling techniques**.

## Medical Impact & Real-World Applications

### **A. How Can This Be Used in Healthcare?**

- Hospitals such as **Mayo Clinic and Johns Hopkins** use predictive models for **early diabetes screening**.
- The model can be **integrated into hospital EHRs (Electronic Health Records)** for **automated risk assessment**.
- **Remote Patient Monitoring Programs:** Clinics such as **Cleveland Clinic** could use this model to track high-risk patients.

### **B. Ethical Considerations in AI for Healthcare**

- **Bias & Fairness:** The model performs poorly for diabetic cases, requiring fairness improvements.
- **Regulatory Compliance:** Any real-world deployment would need to meet **FDA and HIPAA standards**.
- **Interpretability:** Clinicians need explainable AI models; SVM could be paired with **SHAP or LIME** to improve transparency.

## Limitations & Future Work

### **Current Limitations:**

- **Class imbalance** negatively impacts recall (diabetic cases are underrepresented).
- **Minimal feature engineering**; adding new medical predictors (HbA1c levels) could improve accuracy.

### **Future Improvements:**

Apply **Oversampling/Undersampling** to improve recall. 

Explore **Hybrid Models (SVM + Random Forest or Neural Networks)**.&#x20;

Incorporate **real-world data from EHRs** for clinical validation.

##  How to Run This Project

1. **Clone this repository:**
   ```sh
   git clone https://github.com/DanielleBopda/Diabetes-Forecasting.git
   ```
2. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```
3. **Run the Python script:**
   ```sh
   python diabetes_forecastingdaniellebopda.py
   ```
4. **Explore results in Jupyter Notebook (if applicable).**

## Project Report

 D**ownload Full Report** → [Diabetes Forecasting Report](https://github.com/DanielleBopda/Diabetes-Forecasting/raw/main/Diabetes_Forecasting.docx)

## Portfolio Website

🔗 **View this project on my portfolio:** [Danielle's Portfolio](https://daniellebopda.github.io/Danielle-portfolio/)

