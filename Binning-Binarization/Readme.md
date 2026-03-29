# Data Discretization: Binning and Binarization

This repository contains two Jupyter Notebooks exploring different techniques for transforming continuous numerical variables into discrete features. These methods are essential for simplifying complex data distributions and making non-linear relationships easier for models to capture.

## 📂 Featured Notebooks

### 1. Binning (Discretization)
The `binning.ipynb` notebook demonstrates how to divide continuous data into intervals or "bins."
* **Technique:** Uses Scikit-Learn's `KBinsDiscretizer`.
* **Strategies Explored:**
    * **Uniform:** Bins have identical widths.
    * **Quantile:** Each bin contains the same number of data points.
    * **K-Means:** Bins are defined based on 1D k-means clustering.
* **Use Case:** Transforming `Age` and `Fare` from the Titanic dataset into categorical buckets to help Decision Trees identify non-linear patterns.
* **Encoding Options:** Compares `ordinal` encoding (integer bins) with `onehot` encoding (binary columns for each bin).

### 2. Binarization
The `binarization.ipynb` notebook focuses on the special case of discretization where data is split into exactly two categories based on a threshold.
* **Technique:** Uses Scikit-Learn's `Binarizer` and custom logic within a `ColumnTransformer`.
* **Use Case:** Creating a "Family" indicator. For example, transforming the number of siblings/parents (`SibSp` + `Parch`) into a binary feature: `0` (traveling alone) or `1` (traveling with family).
* **Thresholding:** Demonstrates how to set specific cutoff points to convert continuous variables into binary flags.

---

## 🛠️ Requirements
* **NumPy**
* **Pandas**
* **Matplotlib**
* **Scikit-Learn**

## 📊 Dataset: Titanic
Both notebooks utilize the Titanic dataset, specifically focusing on:
* `Age` and `Fare`: Continuous variables used for binning.
* `SibSp` and `Parch`: Discrete variables used to demonstrate binarization.
* `Survived`: The target variable used to evaluate model accuracy improvements.

---

## 🚀 Key Takeaways
1. **Model Performance:** Discretization can significantly impact the accuracy of models like Decision Trees by reducing the noise in continuous features.
2. **Handling Outliers:** Binning helps mitigate the influence of outliers by grouping them into a single high-value bin.
3. **Feature Engineering:** Binarization is a powerful way to encode domain knowledge (like the "alone vs. family" concept) directly into the feature set.

### Video Link: https://youtu.be/kKWsJGKcMvo