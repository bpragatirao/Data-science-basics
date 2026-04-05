# Titanic Survival Prediction: KNN vs. Simple Imputation

This repository contains a machine learning analysis evaluating the impact of different data imputation strategies on predictive model accuracy. The project uses the Titanic dataset to compare **K-Nearest Neighbors (KNN) Imputation** against **Simple (Mean) Imputation**.

## Project Overview
Missing values in the `Age` feature (approximately 19.87% of the dataset) present a challenge for survival prediction. This project demonstrates how capturing local data patterns through KNN can lead to better model performance than using global statistical averages.

## Technical Stack
* **Language**: Python 3.8.3
* **Libraries**: 
    * `numpy` and `pandas` for data handling
    * `scikit-learn` for preprocessing and Logistic Regression

## Dataset Features
The model is trained on the following subset of the Titanic dataset:
* **Age**: The primary target for imputation.
* **Pclass**: Passenger ticket class.
* **Fare**: Fare paid for the journey.
* **Survived**: Target variable (0 = No, 1 = Yes).

## Imputation Methodologies

### 1. K-Nearest Neighbors (KNN) Imputation
* **Configuration**: `n_neighbors=3`, `weights='distance'`.
* **Logic**: Fills missing values by identifying the three most similar passengers and weighting their ages by their proximity in the feature space.

### 2. Simple Imputation
* **Configuration**: Default `SimpleImputer` (Mean).
* **Logic**: Fills all missing values with the average age of the available training data.

## Performance Results
A **Logistic Regression** model was trained on both versions of the data to evaluate the impact of the imputation method on accuracy:

| Imputation Method | Accuracy Score |
| :--- | :--- |
| **KNN Imputer (k=3)** | **0.7151** |
| **Simple Imputer (Mean)** | **0.6927** |

**Conclusion**: The KNN approach outperformed simple mean imputation by approximately 2.2%, suggesting that the "distance-based" relationship between passenger features provides more reliable estimates for missing data.

## Usage
1. Ensure `train.csv` is in the project directory.
2. Run the `KNN-imputer.ipynb` notebook to reproduce the preprocessing pipeline and results.