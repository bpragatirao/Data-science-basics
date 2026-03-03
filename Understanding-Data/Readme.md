# Dataset Exploratory Data Analysis (EDA)

This project performs an initial exploratory data analysis on the classic Titanic dataset (`train.csv`) to understand its structure, identify missing values, and observe preliminary correlations between passenger features and survival rates.

## Dataset Overview

The dataset contains information about **891 passengers** with **12 unique columns**. The primary goal of this analysis is to understand the factors that influenced the survival of individuals on board.

### Data Dimensions
* **Total Rows**: 891
* **Total Columns**: 12

## Analysis Summary

### 1. Data Composition
The dataset consists of various data types including integers, floats, and objects (strings):
* **Numerical (7 columns)**: PassengerId, Survived, Pclass, Age, SibSp, Parch, Fare.
* **Categorical/Object (5 columns)**: Name, Sex, Ticket, Cabin, Embarked.

### 2. Missing Values
Significant gaps were identified in specific columns that would require cleaning for further modeling:
* **Cabin**: 687 missing values.
* **Age**: 177 missing values.
* **Embarked**: 2 missing values.

### 3. Mathematical Insights
Descriptive statistics reveal the following about the passengers:
* **Survival Rate**: The mean survival rate is approximately **38.38%**.
* **Age Range**: Passengers ranged from infants (**0.42 years**) to seniors (**80 years**), with an average age of ~**29.7 years**.
* **Fare**: Ticket prices varied significantly, from **0.00** to a maximum of **512.33**.

### 4. Correlation with Survival
Preliminary correlation analysis shows how various features relate to the 'Survived' column:
* **Fare**: Shows a positive correlation (**0.257**), suggesting higher-paying passengers had better survival odds.
* **Pclass**: Shows a negative correlation (**-0.338**), indicating that passengers in lower classes (higher class number) were less likely to survive.
* **Age**: Shows a weak negative correlation (**-0.077**).

## Requirements
To run this notebook, you will need the following Python libraries:
* `pandas`
* `numpy` (optional, for additional math)

## Usage
1. Ensure `train.csv` is in the same directory as the notebook.
2. Open `understanding-data.ipynb` in a Jupyter environment.
3. Run all cells to generate the summary statistics and correlation reports.

## Video Link: https://www.youtube.com/watch?v=mJlRTUuVr04