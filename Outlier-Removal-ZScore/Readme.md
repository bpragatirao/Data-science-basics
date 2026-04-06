# Outlier Removal using Z-Score

This repository demonstrates the implementation of **Z-Score** based outlier detection and removal. This statistical technique is best suited for datasets that follow a **Normal Distribution** (Bell Curve).

## Project Overview
The project uses a placement dataset to identify and handle extreme values in the `cgpa` feature. By calculating how many standard deviations a data point is from the mean, we can identify "noise" that might negatively impact machine learning model performance.

## Technical Stack
* **Language**: Python 3
* **Libraries**: `numpy`, `pandas`, `matplotlib`, `seaborn`

## Methodology
1. **Distribution Check**: Using `sns.distplot` to confirm the feature is normally distributed.
2. **Z-Score Calculation**: Finding the number of standard deviations ($\sigma$) a point is from the mean ($\mu$).
3. **Boundary Setting**: 
    * **Upper Limit**: $\mu + 3\sigma$
    * **Lower Limit**: $\mu - 3\sigma$
4. **Handling Techniques**:
    * **Trimming**: Removing rows entirely if they fall outside the limits.
    * **Capping (Winsorization)**: Replacing outliers with the nearest boundary value to maintain dataset size.

## Results
* **Detection**: Identified students with extreme CGPAs (e.g., 9.12 or 3.3).
* **Outcome**: Created a cleaned dataset with a normalized range, improving the reliability of statistical analysis.

## Usage
1. Ensure `placement.csv` is available in the root directory.
2. Run `Outlier-removal-zscore.ipynb` to visualize the distribution and execute the removal/capping logic.

### Video Link:https://youtu.be/OnPE-Z8jtqM