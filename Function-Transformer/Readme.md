# Custom Feature Engineering with FunctionTransformer

This repository contains a Jupyter Notebook exploring the use of Scikit-Learn's **FunctionTransformer** to apply custom mathematical transformations to data. Using the Titanic dataset, the notebook demonstrates how to handle skewed distributions and improve model performance through feature engineering.

## 📋 Features

The notebook focuses on transforming numerical features to achieve a more normal (Gaussian) distribution:

### 1. Diagnostic Tools
Before applying transformations, the notebook uses statistical plots to evaluate the data distribution:
* **Histograms:** To visualize the spread and skewness of variables like `Age` and `Fare`.
* **Probability Plots (QQ-Plots):** To compare the data distribution against a theoretical normal distribution.

### 2. Log Transformation
Demonstrates the application of the Log Transform to handle right-skewed data (specifically the `Fare` column).
* **Implementation:** `FunctionTransformer(np.log1p)` is used to handle zero values safely.
* **Impact:** Significant improvement in the "normality" of the distribution, which often leads to better performance in linear models.

### 3. Benchmarking Model Performance
The notebook provides a side-by-side comparison of model accuracy before and after transformations:
* **Algorithms used:** Logistic Regression and Decision Tree Classifier.
* **Evaluation:** Uses `cross_val_score` to ensure results are consistent across different data folds.

### 4. Integration with ColumnTransformer
Shows how to apply different custom functions to specific columns within a single preprocessing object.
* **Method:** Wrapping `FunctionTransformer` inside a `ColumnTransformer` to automate the workflow.

---

## 🛠️ Requirements

To run this notebook, you will need the following Python libraries:
* **NumPy & Pandas**
* **Matplotlib & Seaborn**
* **SciPy** (for `stats.probplot`)
* **Scikit-Learn**

## 📊 Dataset: Titanic
The notebook specifically uses the following columns from the Titanic training set:
* `Age`: Numerical feature for passenger age.
* `Fare`: Numerical feature for ticket price (highly skewed).
* `Survived`: The target variable.

---

## 🚀 Key Takeaways
1. **Mathematical Intuition:** Many machine learning algorithms perform better when numerical input variables have a Gaussian distribution.
2. **Custom Flexibility:** `FunctionTransformer` allows you to turn any Python function or NumPy mapping into a Scikit-Learn compatible transformer.
3. **Pipeline Ready:** These transformations can be easily integrated into a broader machine learning pipeline for automated deployment.

### Video Link : https://youtu.be/cTjj3LE8E90