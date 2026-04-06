# Outlier Removal using Interquartile Range (IQR)

This repository demonstrates the **IQR Method** (Tukey's Fences) for outlier detection. This technique is robust for **skewed datasets** as it does not assume a normal distribution.

## Project Overview
Focusing on the `placement_exam_marks` feature, this project addresses data points that fall far outside the central tendency. Since exam marks are often non-normally distributed, the IQR method provides a more accurate boundary than the Z-score.

## Technical Stack
* **Language**: Python 3
* **Libraries**: `numpy`, `pandas`, `matplotlib`, `seaborn`

## Methodology
1. **Skewness Analysis**: Using `df.skew()` and box plots to confirm the data is non-normal.
2. **Mathematical Approach**:
    * **IQR**: $Q3 (75th Percentile) - Q1 (25th Percentile)$.
    * **Upper Fence**: $Q3 + 1.5 \times IQR$.
    * **Lower Fence**: $Q1 - 1.5 \times IQR$.
3. **Processing**:
    * **Trimming**: Deleting the outlier rows.
    * **Capping**: Replacing values above the Upper Fence or below the Lower Fence with the fence values themselves.

## Results
* **Visualization**: Compared the "before" and "after" distributions using box plots.
* **Outcome**: Successfully minimized the impact of extreme exam scores while retaining the overall data structure.