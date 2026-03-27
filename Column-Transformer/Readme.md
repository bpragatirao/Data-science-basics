# Scikit-Learn ColumnTransformer Implementation

This repository contains a Jupyter Notebook demonstrating the efficient use of the **ColumnTransformer** class from Scikit-Learn. The notebook compares the traditional "manual" approach to data preprocessing against the streamlined "transformer" approach using a COVID-19 clinical dataset.

## 📋 Features

The notebook illustrates two distinct workflows for handling mixed data types:

### 1. The "Manual" Approach (Aam Zindagi)
Demonstrates the labor-intensive method of transforming features individually and concatenating them.
* **Imputation:** Handling missing `fever` values using `SimpleImputer`.
* **Ordinal Encoding:** Converting `cough` severity ('Mild', 'Strong') using `OrdinalEncoder`.
* **One-Hot Encoding:** Transforming `gender` and `city` into binary vectors using `OneHotEncoder`.
* **Concatenation:** Manually merging the transformed arrays with the remaining `age` feature using `np.concatenate`.

### 2. The "ColumnTransformer" Approach (Mentos Zindagi)
Shows the production-standard method for applying different preprocessing steps to different columns simultaneously.
* **Class:** `ColumnTransformer`
* **Key Benefit:** Bundles all transformations into a single object, reducing code redundancy and preventing data leakage between training and testing sets.
* **Parameters:** * `transformers`: A list of tuples specifying (name, transformer, columns).
    * `remainder='passthrough'`: Ensures features not explicitly transformed (like `age`) are kept in the final output.

---

## 🛠️ Requirements

To run this notebook, you will need the following Python libraries:
* **NumPy**
* **Pandas**
* **Scikit-Learn**

## 📊 Dataset: `covid_toy.csv`
The notebook uses a sample dataset with the following schema:
* `age`: Numerical feature (Age of the patient).
* `gender`: Categorical (Male/Female).
* `fever`: Numerical with missing values (Body temperature).
* `cough`: Ordinal (Mild/Strong).
* `city`: Categorical (Delhi, Mumbai, Kolkata, Bangalore).
* `has_covid`: Target variable (Yes/No).

---

## 🚀 Why Use ColumnTransformer?
1. **Maintainability:** Changes to the preprocessing logic only need to be updated in one place.
2. **Pipeline Integration:** Can be directly plugged into a Scikit-Learn `Pipeline`.
3. **Simplicity:** Automatically handles the re-ordering and stacking of features that was previously done manually.

### Video Link : https://youtu.be/5TVj6iEBR4I