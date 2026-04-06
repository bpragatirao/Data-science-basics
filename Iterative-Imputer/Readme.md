# Startups Profit Prediction: Iterative Imputation Analysis

This repository features a data preprocessing project focused on **Iterative Imputation** (Multivariate Imputation by Chained Equations). The project demonstrates how to estimate missing values by modeling each feature with missing values as a function of other features in a round-robin fashion.

## Project Overview
In many real-world datasets, missing values are not random and dependencies exist between variables. This project uses a **Startups dataset** to demonstrate the manual logic and implementation of an iterative imputer to fill missing values in financial metrics.

## Dataset Features
The analysis focuses on the following columns from the Startups dataset:
* **R&D Spend**: Amount spent on Research and Development.
* **Administration**: Amount spent on administrative costs.
* **Marketing Spend**: Amount spent on marketing efforts.
* **Profit**: The target variable representing the startup's profit.

## Technical Implementation
The project implements the iterative process manually using **Linear Regression** to highlight the underlying mathematics:

1.  **Initialization**: Missing values are initially filled using the mean of their respective columns.
2.  **Iterative Modeling**: 
    * One variable with missing values is treated as the "target" while others act as "predictors".
    * A Linear Regression model is trained on rows where the target is known.
    * The model then predicts (imputes) the missing values for that specific column.
3.  **Refinement**: This process repeats across all columns with missing data, using the newly updated values from the previous step to improve subsequent predictions.
4.  **Convergence**: The process continues until the difference between the values in successive iterations becomes negligible (close to zero).

## Key Results
The notebook demonstrates the convergence of values by calculating the difference between iterations (e.g., `df3 - df2`), showing how the imputed values stabilize as the model "learns" the relationships between R&D, Administration, and Marketing spends.

## Dependencies
* `numpy`
* `pandas`
* `scikit-learn` (LinearRegression)

## Usage
1.  Ensure the startups dataset is available.
2.  Run `Iterative-imputer.ipynb` to view the step-by-step manual implementation and the convergence of the imputed data.

### Video Link : https://youtu.be/a38ehxv3kyk