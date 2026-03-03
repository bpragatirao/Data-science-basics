# Titanic Dataset: Automated EDA with Pandas Profiling

This project uses the `ydata-profiling` (formerly `pandas-profiling`) library to generate a high-level, interactive summary of the Titanic dataset.

## Automated Report Features

* **Overview**: Provides a summary of dataset statistics, including total observations, missing cells, and duplicate rows.
* **Variable Insights**: Generates individual profiles for every column, highlighting distinct values, zeros, and skewness.
* **Interactions & Correlations**: Automatically generates Pearson, Spearman, and Kendall correlation matrices.
* **Missing Value Analysis**: Visualizes the sparsity of the data (e.g., the high number of missing values in the `Cabin` column).
* **Sample Data**: Displays the first and last rows of the dataset for quick verification.

## Benefits
* **Speed**: Replaces hundreds of lines of manual plotting and grouping code with a single command.
* **Completeness**: Ensures no hidden patterns or data quality issues are overlooked during the initial phase.

## Video Link:https://www.youtube.com/watch?v=E69Lg2ZgOxg