# Diabetes Prediction Project

## Overview
This project aims to predict diabetes using various machine learning models. The dataset consists of medical variables that contribute to the likelihood of diabetes. The models compared include:

- **Logistic Regression**
- **K-Nearest Neighbors (KNN)**
- **Support Vector Machine (SVM)**
- **Random Forest**

Feature engineering techniques were applied to improve model performance.

## Dataset
The dataset used is `https://www.kaggle.com/datasets/mathchi/diabetes-data-set`, containing the following features:
- **Pregnancies**: Number of times pregnant
- **Glucose**: Plasma glucose concentration
- **BloodPressure**: Diastolic blood pressure (mm Hg)
- **SkinThickness**: Triceps skin fold thickness (mm)
- **Insulin**: 2-Hour serum insulin (mu U/ml)
- **BMI**: Body mass index (weight in kg/(height in m)^2)
- **DiabetesPedigreeFunction**: Diabetes likelihood based on family history
- **Age**: Age of the patient
- **Outcome**: Target variable (1 = Diabetic, 0 = Non-Diabetic)

## Feature Engineering
To improve model performance, the following feature engineering steps were applied:
1. **Handling Missing Values**: Replaced `0` values in `BloodPressure`, `SkinThickness`, `Insulin`, and `BMI` with the median.
2. **Feature Scaling**: Applied MinMaxScaler to standardize `Glucose`, `BMI`, `Age`, and the new feature `BMI_Age`.
3. **Feature Interaction**: Created a new feature `BMI_Age` (BMI * Age) to capture interaction effects.
4. **Binning**: Categorized `Age` into bins (`Young`, `Middle-aged`, `Senior`) and applied one-hot encoding.

## Model Training & Evaluation
Each model was trained on the dataset split into **75% training** and **25% testing**. Model performance was evaluated using:
- **Accuracy**: Measures overall correctness.
- **Precision**: Measures how many predicted diabetic cases were correct.
- **Recall**: Measures how many actual diabetic cases were correctly identified.

### Model Performance Summary
| Model                         | Accuracy | Precision | Recall  |
|--------------------------------|----------|----------|---------|
| Logistic Regression           | 72.9%    | 65.3%    | 47.8%   |
| K-Nearest Neighbors (KNN)      | 69.3%    | 60.0%    | 35.8%   |
| Support Vector Machine (SVM)   | 71.3%    | 61.1%    | 49.3%   |
| Random Forest                 | 75.0%    | 67.3%    | 55.2%   |
| **Random Forest (Feature Eng.)** | **74.5%** | **65.5%** | **56.7%** |

### Best Model: **Random Forest with Feature Engineering**
- Achieved the **best balance between accuracy, precision, and recall**.
- Improved recall, detecting more diabetic cases correctly.
- Suitable for medical prediction as it reduces false negatives.


