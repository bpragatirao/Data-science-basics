# Titanic Dataset: Feature Scaling & Standardization

This project demonstrates the application of **Standardization** (Z-score normalization) to numerical features to prepare them for distance-based algorithms.

## Workflow

* **Train-Test Split**: The data was split into training and testing sets to prevent data leakage during the scaling process.
* **StandardScaler Application**: Used `sklearn.preprocessing.StandardScaler` to transform features such that they have a mean ($\mu$) of 0 and a standard deviation ($\sigma$) of 1.
* **Feature Impact**: Analysis focused on scaling `Age` and `Fare`, as these variables have vastly different ranges.

## Results
* **Before Scaling**: `Fare` had a much higher variance and magnitude compared to `Age`.
* **After Scaling**: Both features are on the same scale, ensuring that the model does not become biased toward the feature with larger numerical values.