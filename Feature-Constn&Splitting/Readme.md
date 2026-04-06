# Feature Engineering: Construction and Splitting

This repository focuses on **Feature Engineering** techniques, specifically **Feature Construction** and **Feature Splitting**. These methods are used to create more meaningful input variables from existing raw data to improve the predictive power of machine learning models.

## Project Overview
Raw data often contains information in a format that is not directly "digestible" by algorithms. This project demonstrates how to manually derive new features (Construction) and break down complex strings (Splitting) using the Titanic and House Price datasets.

## Technical Stack
* **Language**: Python 3
* **Libraries**: `numpy`, `pandas`, `scikit-learn`

## Methodology

### 1. Feature Construction
Feature construction involves combining two or more existing features to create a new one that captures a specific relationship.
* **Example (Titanic)**: Combining `SibSp` (siblings/spouses) and `Parch` (parents/children) to create a `Family_Size` feature.
* **Logic**: `df['Family_Size'] = df['SibSp'] + df['Parch'] + 1`.
* **Outcome**: This identifies whether a passenger was traveling alone or with a large group, which is a strong predictor for survival.

### 2. Feature Splitting
Feature splitting involves extracting specific, useful information from a single complex column.
* **Example (Titanic Names)**: Splitting the `Name` column to extract titles like "Mr.", "Mrs.", or "Master".
* **Example (House Prices)**: Splitting a "Property_Address" string to extract "City" or "Zip Code" as individual categorical features.

## Key Results
* **Improved Correlation**: The newly constructed `Family_Size` feature often shows a stronger correlation with the `Survived` target than the individual `SibSp` or `Parch` columns.
* **Categorical Insights**: Extracting titles from names allows the model to capture social status and age groups (e.g., "Master" for young boys), which significantly impacts survival probability.

## Usage
1. Ensure the Titanic `train.csv` or relevant dataset is available in the directory.
2. Run `Feature-construction-splitting.ipynb` to see the step-by-step transformation of raw columns into model-ready features.

### Video Link https://youtu.be/ma-h30PoFms