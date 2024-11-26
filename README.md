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
## Features Description

- **id**: Unique identifier for each record (integer).
- **age**: Age of the patient (continuous).
- **sex**: Sex of the patient (binary: 'male' or 'female').
- **dataset**: Identifier for the dataset source (categorical).
- **cp**: Chest pain type (categorical):
  - 1: Typical angina.
  - 2: Atypical angina.
  - 3: Non-anginal pain.
  - 4: Asymptomatic.
- **trestbps**: Resting blood pressure (continuous, mmHg).
- **chol**: Serum cholesterol (continuous, mg/dL).
- **fbs**: Fasting blood sugar (binary: 1 if greater than 120 mg/dL, 0 otherwise).
- **restecg**: Resting ECG results (categorical):
  - 0: Normal.
  - 1: ST-T wave abnormality.
  - 2: Left ventricular hypertrophy.
- **thalach**: Maximum heart rate achieved (continuous, bpm).
- **exang**: Exercise-induced angina (binary: 1 if present, 0 otherwise).
- **oldpeak**: ST depression induced by exercise relative to rest (continuous).
- **slope**: Slope of the peak exercise ST segment (categorical):
  - 1: Upsloping.
  - 2: Flat.
  - 3: Downsloping.
- **ca**: Number of major vessels colored by fluoroscopy (categorical, range 0–3).
- **thal**: Thalassemia (categorical):
  - 3: Normal.
  - 6: Fixed defect.
  - 7: Reversible defect.
- **num**: Presence or absence of heart disease (target variable, binary: 1 if present, 0 otherwise).

## Features and Binarization

The dataset consists of 16 features, including demographic information, medical test results, and the target variable. Each feature has been carefully processed and, where applicable, binarized or categorized to enhance model performance and interpretability. Below are the details:

### 1. `age` (Age)
- **Binarization:**
  - `age_le_40`: Age ≤ 40.
  - `age_40_to_60`: Age in (40, 60].
  - `age_60_to_80`: Age in (60, 80].
  - `age_ge_80`: Age ≥ 80.
- **Reason:** Age ranges align with standard groupings used in medical studies.

### 2. `sex` (Sex)
- **Binarization:**
  - `male`: Sex = 1.
  - `female`: Sex = 0.
- **Reason:** Direct representation of male or female.

### 3. `dataset` (Dataset Identifier)
- **Binarization:**
  - Separate binary flags for each dataset (e.g., `dataset_1`, `dataset_2`, etc.).
- **Reason:** Enables the analysis of subsets from different data sources.

### 4. `cp` (Chest Pain Type)
- **Binarization:**
  - `cp_typical_angina`: Typical angina (1).
  - `cp_atypical_angina`: Atypical angina (2).
  - `cp_non_anginal`: Non-anginal pain (3).
  - `cp_asymptomatic`: Asymptomatic (4).
- **Reason:** Categorizes different types of chest pain for better interpretation.

### 5. `trestbps` (Resting Blood Pressure)
- **Binarization:**
  - `trestbps_le_120`: BP ≤ 120.
  - `trestbps_120_to_139`: BP in (120, 139].
  - `trestbps_140_to_159`: BP in (140, 159].
  - `trestbps_ge_160`: BP ≥ 160.
- **Reason:** Matches hypertension stages for clinical relevance.

### 6. `chol` (Cholesterol)
- **Binarization:**
  - `chol_le_200`: Cholesterol ≤ 200 (desirable).
  - `chol_200_to_239`: Cholesterol in (200, 239] (borderline high).
  - `chol_ge_240`: Cholesterol ≥ 240 (high).
- **Reason:** Reflects standard cholesterol level classifications.

### 7. `fbs` (Fasting Blood Sugar)
- **Binarization:**
  - `fbs_normal`: FBS ≤ 120.
  - `fbs_high`: FBS > 120.
- **Reason:** Clinical cutoff separates normal and abnormal levels.

### 8. `restecg` (Resting Electrocardiographic Results)
- **Binarization:**
  - `restecg_normal`: Normal ECG.
  - `restecg_st_t_wave`: ST-T wave abnormality.
  - `restecg_lv_hypertrophy`: Probable or definite left ventricular hypertrophy.
- **Reason:** Represents distinct ECG categories.

### 9. `thalch` (Maximum Heart Rate Achieved)
- **Binarization:**
  - `thalch_le_100`: Heart rate ≤ 100.
  - `thalch_100_to_140`: Heart rate in (100, 140].
  - `thalch_140_to_180`: Heart rate in (140, 180].
  - `thalch_ge_180`: Heart rate ≥ 180.
- **Reason:** Captures heart performance under stress.

### 10. `exang` (Exercise-Induced Angina)
- **Binarization:**
  - `exang_yes`: Angina during exercise (1).
  - `exang_no`: No angina during exercise (0).
- **Reason:** Binary feature for exercise-induced angina.

### 11. `oldpeak` (ST Depression Induced by Exercise)
- **Binarization:**
  - `oldpeak_le_1`: Depression ≤ 1.
  - `oldpeak_1_to_2`: Depression in (1, 2].
  - `oldpeak_ge_2`: Depression ≥ 2.
- **Reason:** Thresholds represent different risk levels.

### 12. `slope` (Slope of the Peak Exercise ST Segment)
- **Binarization:**
  - `slope_upsloping`: Upsloping (1).
  - `slope_flat`: Flat (2).
  - `slope_downsloping`: Downsloping (3).
- **Reason:** Categorical feature representing cardiac conditions.

### 13. `ca` (Number of Major Vessels Colored by Fluoroscopy)
- **Binarization:**
  - `ca_0`: No major vessels.
  - `ca_1`: 1 major vessel.
  - `ca_2`: 2 major vessels.
  - `ca_3`: 3 major vessels.
- **Reason:** Binary flags represent distinct vessel counts.

### 14. `thal` (Thalassemia Status)
- **Binarization:**
  - `thal_normal`: Normal.
  - `thal_fixed_defect`: Fixed defect.
  - `thal_reversible_defect`: Reversible defect.
- **Reason:** Encodes thalassemia conditions.

### 15. `num` (Target Variable: Presence of Heart Disease)
- **Binarization:**
  - `num_0`: No heart disease (0).
  - `num_1`: Heart disease present (1).
- **Reason:** Binary representation of the target variable.

---

These processed features improve the interpretability of the dataset and enhance model performance.
