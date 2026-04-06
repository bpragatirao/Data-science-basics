# Outlier Removal using Z-Score

This repository demonstrates the practical implementation of **Z-Score** based outlier detection and removal. The project focuses on identifying data points that significantly deviate from the mean in a normally distributed dataset.

## Project Overview
Outliers can skew statistical analyses and degrade the performance of machine learning models. This project uses a placement dataset to identify students with unusually high or low CGPAs based on the standard deviation from the average.

## Technical Stack
* **Language**: Python 3
* **Libraries**: 
    * `numpy` and `pandas` for data manipulation
    * `matplotlib` and `seaborn` for data visualization

## Methodology

### 1. Statistical Foundation (Z-Score)
The Z-score represents how many standard deviations a data point is from the mean. It is calculated as:
$$Z = \frac{x - \mu}{\sigma}$$
Where:
* $x$ is the value
* $\mu$ is the mean
* $\sigma$ is the standard deviation

### 2. Implementation Steps
* **Distribution Check**: Visualizing data using Distplots to ensure the feature follows a Normal Distribution.
* **Boundary Calculation**: 
    * **Upper Limit**: $mean + 3 \times std$
    * **Lower Limit**: $mean - 3 \times std$
* **Trimming**: Removing rows that fall outside the calculated boundaries.
* **Capping (Winsorization)**: Replacing outliers with the upper or lower limit values instead of deleting them.

## Key Results
The project showcases the "before" and "after" effects of outlier removal:
* **Before**: The CGPA column contained extreme values (e.g., 9.12 or 3.30) that were outside the $3\sigma$ range.
* **After**: The dataset is cleaned, resulting in a more robust distribution for subsequent modeling or analysis.

## Usage
1. Ensure `placement.csv` is available in the root directory.
2. Run `Outlier-removal-zscore.ipynb` to visualize the distribution and execute the removal/capping logic.

### Video Link:https://youtu.be/OnPE-Z8jtqM