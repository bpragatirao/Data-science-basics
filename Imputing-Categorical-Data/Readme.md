# Categorical Data Imputation: Handling Missing Values

This repository demonstrates two effective strategies for handling missing categorical data in machine learning pipelines: **Frequent Value (Mode) Imputation** and **Missing Category Imputation**. These methods ensure that models can process datasets with incomplete categorical features without introducing significant bias.

## 📌 Projects Overview

### 1. Frequent Value (Mode) Imputation
This technique replaces missing categorical values with the most frequent value (mode) of that variable.
- **Use Case**: Best suited when data is "Missing Completely at Random" (MCAR) and the missingness is less than 5%.
- **Implementation**: Utilizes `SimpleImputer(strategy='most_frequent')` from Scikit-Learn.
- **Validation**: Includes code to check the distribution of categories before and after imputation to ensure the mode remains dominant without distorting the feature's nature.

### 2. Missing Category Imputation
This approach treats "Missing" as a separate category itself.
- **Use Case**: Ideal when the fact that data is missing is actually a signal (Missing Not at Random - MNAR).
- **Strategy**: Replaces `NaN` values with a new label, such as "Missing" or "Unknown".
- **Benefit**: Prevents the loss of information and allows the model to learn patterns associated with missing data points.

## 📊 Dataset Analysis
The projects utilize common datasets (e.g., `train.csv` for housing prices) to demonstrate these techniques on features like:
- **GarageQual**: Quality of the garage.
- **FireplaceQu**: Quality of the fireplace.
- **Education Level**: Candidate demographics.

## 🛠️ Workflow
1. **Missing Value Profiling**: Identifying the percentage of null values in each categorical column.
2. **Train-Test Split**: Ensuring imputation parameters are learned only from the training set to avoid data leakage.
3. **Statistical Comparison**: Evaluating changes in category frequencies using frequency tables and bar plots.

## 🚀 Libraries Used
- **Pandas**: For data manipulation and frequency counts.
- **NumPy**: For handling array operations.
- **Scikit-Learn**: For the `SimpleImputer` class.
- **Matplotlib**: For visualizing categorical distributions.

---

### How to Use
1. Ensure your dataset (e.g., `train.csv` or `data_science_job.csv`) is in the local directory.
2. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib
   ```