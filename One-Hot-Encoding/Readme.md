# One-Hot Encoding Implementation

This repository contains a Jupyter Notebook demonstrating various techniques to handle categorical data using **One-Hot Encoding (OHE)** in Python. The examples use a car sales dataset to transform categorical variables like brand, fuel type, and ownership into a machine-learning-ready format.

## 📋 Features

The notebook covers four primary approaches to categorical encoding:

### 1. One-Hot Encoding using Pandas
Demonstrates the use of `pd.get_dummies()` for a quick and easy transformation of the entire dataframe.
* **Method:** `pd.get_dummies(df, columns=['fuel', 'owner'])`
* **Output:** Creates binary columns for every unique value in the specified features.

### 2. K-1 One-Hot Encoding (Dummy Variable Trap)
Explains how to avoid multicollinearity by dropping the first encoded column.
* **Method:** `drop_first=True`
* **Logic:** If there are $n$ categories, only $n-1$ columns are needed to represent the data.

### 3. One-Hot Encoding using Scikit-Learn
Shows the production-grade method using `sklearn.preprocessing`. This is essential for machine learning pipelines to ensure the same transformation is applied to both training and testing sets.
* **Class:** `OneHotEncoder`
* **Key Parameters:** `drop='first'`, `sparse=False`, and `fit_transform()`.
* **Integration:** Demonstrates how to horizontal-stack (`np.hstack`) encoded features back with numerical features.

### 4. Handling High Cardinality (Top Categories)
A practical solution for features with many unique values (like `brand`).
* **Technique:** Identifying "Uncommon" categories based on a frequency threshold (e.g., counts < 100).
* **Benefit:** Reduces the dimensionality of the dataset by grouping rare categories into a single "uncommon" label before encoding.

---

## 🛠️ Requirements

To run this notebook, you will need the following Python libraries:
* **NumPy**
* **Pandas**
* **Scikit-Learn**

## 📊 Dataset Structure

The examples are performed on a `cars.csv` dataset with the following columns:
* `brand`: The manufacturer of the car (High cardinality).
* `km_driven`: Numerical feature representing distance.
* `fuel`: Categorical (Diesel, Petrol, CNG, LPG).
* `owner`: Categorical (First Owner, Second Owner, etc.).
* `selling_price`: The target variable for regression.

---

### Video Link : https://youtu.be/U5oCv3JKWKA