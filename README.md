# Loan Application Prediction

This project predicts the approval status of two-wheeler loan applications based on data from various applicants and third-party sources. It uses machine learning techniques, primarily focusing on Random Forest classification, to predict whether an application will be **APPROVED** or **DECLINED**.

## Table of Contents
- [Introduction](#introduction)
- [Dataset Information](#dataset-information)
- [Approach](#approach)
  - [Data Cleaning](#data-cleaning)
  - [Feature Engineering](#feature-engineering)
  - [Model Building](#model-building)
  - [Model Evaluation](#model-evaluation)
  - [Handling Mismatched Columns](#handling-mismatched-columns)
- [Requirements](#requirements)


## Introduction

This project tackles the problem of determining whether a two-wheeler loan application will be accepted or rejected. The input data consists of loan application details and associated features from multiple sources. The project follows a structured machine learning pipeline that includes data cleaning, feature engineering, model training, and predictions.

## Dataset Information

The project utilizes three main files:
1. **Assignment_Train.csv**: The training dataset containing loan application details and their approval status.
2. **Assignment_Test.csv**: The test dataset for which predictions need to be made.
3. **Assignment_FeatureDictionary.xlsx**: A feature dictionary providing information about the columns present in the dataset.

## Approach

### Data Cleaning

- Checked for missing values and imputed missing numerical values using mean imputation.
- Cleaned and standardized the `APPLICATION LOGIN DATE` column by converting it into a uniform `DD-MM-YYYY` format.
- Handled any missing or inconsistent data to ensure a clean dataset for model building.

### Feature Engineering

- Extracted features such as `Day`, `Month`, and `Year` from the `APPLICATION LOGIN DATE` for both train and test datasets.
- Dropped unnecessary columns, including the original date column after feature extraction.

### Model Building

- Used a **RandomForestClassifier** with 100 estimators as the primary model for predicting the application status.
- The target variable was the `Application Status`, which was encoded as either **APPROVED** (1) or **DECLINED** (0).

### Model Evaluation

- The model was evaluated using metrics such as **Accuracy**, **F1 Score**, and a **Classification Report** on a validation set split from the training data.
  
### Handling Mismatched Columns

- Added any missing columns in the test dataset with default values.
  - For categorical columns, the default value was an empty string.
  - For numerical columns, the default value was 0.
- Removed any extra columns in the test dataset not present in the training dataset.

## Requirements

- Python 3.x
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn


