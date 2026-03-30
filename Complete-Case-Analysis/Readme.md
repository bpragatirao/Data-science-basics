# Data Science Job Training - Complete Case Analysis (CCA)

This project explores the application of **Complete Case Analysis (CCA)**, also known as listwise deletion, to handle missing data in a dataset of candidates looking for jobs in data science. The analysis focuses on ensuring that the distribution of data remains consistent after removing missing values.

## 📌 Project Overview
The notebook demonstrates how to identify, analyze, and mitigate missing data using CCA. It specifically targets variables where the missingness is less than 5%, a common threshold for safely removing rows without significantly biasing the dataset.

## 📊 Dataset Highlights
The dataset used is `data_science_job.csv`, which includes:
* **Demographics**: City development index, education level, and enrolled university type.
* **Professional Experience**: Relevant experience years and total training hours.
* **Target Variable**: Indicates if a candidate is looking for a job change.

## 🛠️ Workflow

### 1. Missing Data Profiling
- Calculated the percentage of missing values per feature.
- Identified "Complete Case" candidates (columns with < 5% missing data) such as `education_level`, `city_development_index`, and `experience`.

### 2. Implementation of CCA
- Filtered the dataframe to retain only rows where the specified features were non-null.
- Reduced the dataset size while maintaining a representative sample.

### 3. Data Integrity Validation
- **Numerical Features**: Compared histograms and Density Plots (PDFs) of `training_hours` and `city_development_index` before and after CCA to ensure the data distribution did not shift.
- **Categorical Features**: Analyzed the ratio of categories in `education_level` and `enrolled_university` to confirm that the proportion of each class (e.g., Graduate, Masters, PhD) remained stable.

## 🚀 Libraries Used
* **Pandas**: Data manipulation and missing value analysis.
* **NumPy**: Numerical operations and data handling.
* **Matplotlib**: Visualization of data distributions and comparative analysis.

## 📈 Key Findings
The analysis confirms that when missing data is "Missing Completely at Random" (MCAR) and represents a small fraction of the total dataset, Complete Case Analysis is an effective method to create a clean dataset for machine learning models without distorting the underlying statistical properties.

---

### Usage
To reproduce the analysis:
1. Ensure `data_science_job.csv` is in the project root.
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib
   ```

### Video Link : https://youtu.be/aUnNWZorGmk