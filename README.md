# Heart Disease Prediction Model

This repository contains a LazyFCA machine-learning model for predicting heart disease using various medical features, including age, blood pressure, cholesterol levels, and others. The model is trained on the UCI Heart Disease dataset, and features are binarized to improve the model's ability to learn patterns related to heart disease risk factors.

## Table of Contents
- [Project Overview](#project-overview)
- [Data Description](#data-description)
- [Binarization of Features](#binarization-of-features)

## Project Overview

This project aims to predict whether a patient has heart disease based on several medical attributes. The dataset used for training the model includes categorical and continuous variables, which have been binarized to improve model interpretability and performance.

## Data Description

The dataset used in this project is the UCI Heart Disease dataset, which includes the following features:
- **cp**: Chest pain type (categorical)
- **age**: Age of the patient (continuous)
- **trestbps**: Resting blood pressure (continuous)
- **chol**: Serum cholesterol (continuous)
- **fbs**: Fasting blood sugar (binary: 1 if greater than 120 mg/dl)
- **restecg**: Resting ECG results (categorical)
- **thalach**: Maximum heart rate achieved (continuous)
- **exang**: Exercise induced angina (binary: 1 if present)
- **oldpeak**: ST depression induced by exercise (continuous)
- **ca**: Number of major vessels colored by fluoroscopy (categorical)
- **thal**: Thalassemia (categorical)
- **num**: Presence or absence of heart disease (target variable, binary: 1 if present)

## Binarization of Features

The following categorical and continuous features were binarized to improve model performance and interpretability:

1. **cp** (Chest Pain Type):
   - `cp_typical_angina`, `cp_atypical_angina`, `cp_non_anginal`, `cp_asymptomatic`
   
2. **age**:
   - `age_le_{threshold}`, `age_ge_{threshold}` (based on age thresholds)

3. **trestbps** (Resting Blood Pressure):
   - `trestbps_le_{threshold}`, `trestbps_ge_{threshold}` (based on blood pressure thresholds)

4. **chol** (Cholesterol):
   - `chol_le_{threshold}`, `chol_ge_{threshold}` (based on cholesterol thresholds)

5. **fbs** (Fasting Blood Sugar):
   - `fbs` (1 if greater than 120 mg/dl)

6. **restecg** (Resting ECG results):
   - `restecg_normal`, `restecg_stt_abnormality`, `restecg_lv_hypertrophy`

7. **thalach** (Maximum Heart Rate Achieved):
   - `thalch_le_{threshold}`, `thalch_ge_{threshold}` (based on heart rate thresholds)

8. **exang** (Exercise Induced Angina):
   - `exang` (1 if present)

9. **oldpeak** (ST Depression Induced by Exercise):
   - `oldpeak_le_{threshold}`, `oldpeak_ge_{threshold}` (based on oldpeak thresholds)

10. **ca** (Number of Major Vessels):
    - `ca_{i}` (i ∈ [0, 1, 2, 3])

11. **thal** (Thalassemia):
    - `thal` (1 if normal)
