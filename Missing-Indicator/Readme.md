# Advanced Missing Value Imputation & Automation

This repository covers advanced strategies for handling missing data, including creating indicators for missingness, utilizing random sampling for imputation, and automating the selection of imputation parameters using Scikit-Learn pipelines.

## 📌 Projects Overview

### 1. Missing Indicator
This technique involves creating a new binary feature that indicates whether a value was missing in the original column.
- **Objective**: To capture the "missingness" as a potential predictive signal, often used alongside other imputation methods like Mean or Median.
- **Implementation**: Uses `MissingIndicator` or the `add_indicator=True` parameter in Scikit-Learn's `SimpleImputer`.
- **Benefit**: Particularly effective when data is not missing at random (MNAR).

### 2. Random Sample Imputation
This method replaces missing values with random observations taken from the available data in the same column.
- **Objective**: To preserve the original variance and distribution of the dataset, which is often distorted by mean/median imputation.
- **Logic**: It maintains the shape of the histogram and is robust to outliers compared to mean imputation.
- **Constraint**: This is generally an "offline" technique, as the randomness can make it difficult to reproduce exactly in a production environment without fixed seeds.

### 3. Automatically Selecting Imputer Parameters
This project focuses on using **GridSearchCV** and **Pipelines** to find the optimal imputation strategy for a specific machine learning model.
- **Automation**: Instead of manually choosing between Mean, Median, or Mode, the pipeline tests different strategies and selects the one that results in the best model performance (e.g., highest R2 score or lowest MSE).
- **Techniques**: Demonstrates `ColumnTransformer` to apply different imputers to numerical vs. categorical columns simultaneously.

## 🛠️ Workflow
1. **Feature Engineering**: Implementing custom transformers and Scikit-Learn built-ins to modify the feature space.
2. **Pipeline Integration**: Wrapping imputation and model training into a single executable pipeline to prevent data leakage.
3. **Hyperparameter Tuning**: Using cross-validation to compare different imputation "constants" and "strategies".
4. **Validation**: Analyzing the impact of these advanced methods on model accuracy and error metrics.

## 🚀 Libraries Used
- **Scikit-Learn**: For `MissingIndicator`, `SimpleImputer`, `Pipeline`, and `GridSearchCV`.
- **Pandas**: For data cleaning and feature construction.
- **Matplotlib/Seaborn**: For comparing data distributions before and after random sampling.

---

### How to Use
1. Install dependencies:
   ```bash
   pip install pandas scikit-learn matplotlib seaborn
   ```

### Video Link:https://youtu.be/Ratcir3p03w