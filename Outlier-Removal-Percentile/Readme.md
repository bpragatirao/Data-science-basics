# Outlier Removal using Percentiles (Capping)

This repository demonstrates the implementation of **Percentile-based Outlier Removal**, also known as **Winsorization**. This method is highly effective for datasets where you want to define custom thresholds for "extreme" values regardless of the data distribution.

## Project Overview
The project utilizes a dataset containing student attributes like **CGPA** and **Placement Exam Marks**. Instead of using standard deviations or fixed fences, this approach identifies outliers based on specific data quantiles (e.g., the top 1% and bottom 1% of the population).

## Technical Stack
* **Language**: Python 3
* **Libraries**: `numpy`, `pandas`, `matplotlib`, `seaborn`

## Methodology

### 1. Identifying Boundaries
Boundaries are set by calculating specific percentiles of the feature:
* **Upper Limit**: Often set at the **99th percentile** (value below which 99% of data falls).
* **Lower Limit**: Often set at the **1st percentile** (value below which only 1% of data falls).

### 2. Implementation Steps
* **Statistical Analysis**: Using `df['column'].describe()` to understand the min, max, and mean before processing.
* **Quantile Calculation**: Using `df['column'].quantile(0.99)` and `df['column'].quantile(0.01)` to find the cutoff points.
* **Trimming**: Creating a subset of data that exists strictly between the 1st and 99th percentiles.
* **Capping (Winsorization)**: Using `np.where()` to replace any value above the 99th percentile with the 99th percentile value, and any value below the 1st percentile with the 1st percentile value.


## Key Results
* **Data Integrity**: Unlike trimming, the capping method preserves the total number of observations (rows) in the dataset, which is crucial for maintaining sample size.
* **Outcome**: Extreme "fluke" scores or entries are pulled back to the boundary of the majority, reducing the variance and preventing model over-fitting to rare extreme cases.

## Usage
1. Ensure the `weight-height.csv` or placement dataset is available.
2. Run `Outlier-removal-percentile.ipynb` to execute the percentile calculations and view the distribution plots.