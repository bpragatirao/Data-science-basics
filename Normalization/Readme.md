# Data Normalization Project

This project demonstrates the implementation of **Normalization (Min-Max Scaling)** as a feature scaling technique in machine learning. It explores how to transform numerical data into a standard range while maintaining the original data distribution.

## Table of Contents
* [Overview](#overview)
* [Libraries Used](#libraries-used)
* [Dataset](#dataset)
* [Implementation Steps](#implementation-steps)
* [Visualizations](#visualizations)

## Overview
Normalization is a preprocessing step used to scale numerical features to a fixed range, typically between 0 and 1. This is crucial for algorithms that are sensitive to the magnitude of data, such as K-Nearest Neighbors (KNN) or Neural Networks.

## Libraries Used
* **NumPy & Pandas**: For data manipulation and processing.
* **Matplotlib & Seaborn**: For data visualization and distribution analysis.
* **Scikit-Learn**: Specifically `train_test_split` for data partitioning and `MinMaxScaler` for scaling.

## Dataset
The notebook uses the **Wine dataset** (`wine_data.csv`). It specifically focuses on three columns:
1. Class label
2. Alcohol
3. Malic acid

## Implementation Steps
1. **Data Loading**: Reading the CSV file and assigning relevant column names.
2. **Train-Test Split**: Dividing the data to ensure scaling is learned only from the training set to prevent data leakage.
3. **Scaling**: Applying `MinMaxScaler` from `sklearn.preprocessing`.
4. **Verification**: Comparing the descriptive statistics (min, max) before and after scaling to ensure the range is correctly set to [0, 1].

## Visualizations
The notebook includes several plots to compare the data states:
* **Scatter Plots**: To observe how the relative positions of data points remain unchanged while axes are rescaled.
* **KDE Plots**: To verify that the probability distribution (shape) of the features remains the same after normalization.

### Video Link: https://youtu.be/eBrGyuA2MIg