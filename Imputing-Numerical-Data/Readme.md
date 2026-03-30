# Feature Engineering: Missing Value Imputation Techniques

This repository contains practical implementations of various univariate imputation techniques used to handle missing data in machine learning workflows. The focus is on preserving data integrity while making the dataset suitable for modeling.

## 📌 Projects Overview

### 1. Mean and Median Imputation
This project demonstrates how to replace missing numerical values using the mean or median of the available observations. 
- **Median Imputation**: Preferred when the data distribution is skewed, as it is robust to outliers.
- **Mean Imputation**: Suitable for normally distributed data.
- **Key Analysis**: The notebook evaluates the impact of imputation on the original variable's variance and its covariance with other features.

### 2. Arbitrary Value Imputation
This technique involves replacing missing values with an arbitrary value, often outside the normal range of the data (e.g., -1, 999, or "Missing").
- **Goal**: To capture the "missingness" as a potential signal for the model.
- **Usage**: Typically used when data is not missing at random and the fact that a value is missing is informative.

## 🛠️ Workflow & Methodology
Both notebooks follow a standardized data science approach:
1. **Exploratory Data Analysis (EDA)**: Identifying the percentage of missing values and analyzing the distribution of numerical features.
2. **Train-Test Split**: Imputation parameters (mean, median, or arbitrary values) are calculated only on the training set to prevent data leakage.
3. **Visualization**: Using Histograms and KDE (Kernel Density Estimate) plots to compare the "Before" and "After" distributions.
4. **Correlation Analysis**: Checking if the imputation significantly alters the relationship between features.

## 🚀 Libraries Used
- **Pandas**: For data structures and handling null values.
- **NumPy**: For mathematical operations.
- **Matplotlib / Seaborn**: For visualizing distribution shifts and density plots.
- **Scikit-Learn**: For implementing `SimpleImputer` and managing data splits.

## 📈 Summary of Results
- **Mean/Median**: Effective for small amounts of missing data but can shrink the variance of the variable if the missingness is high.
- **Arbitrary Value**: Useful for tree-based models (like Random Forest or XGBoost) but may negatively impact linear models if the arbitrary value is too far from the data range.

---

### How to Use
1. Clone this repository.
2. Ensure you have the required datasets in the project directory.
3. Install dependencies:
   ```bash
   pip install pandas numpy seaborn matplotlib scikit-learn
   ```

### Video Link : https://youtu.be/mCL2xLBDw8M