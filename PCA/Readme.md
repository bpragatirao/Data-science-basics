# Principal Component Analysis (PCA): From Theory to Practice

This repository provides a comprehensive exploration of **Principal Component Analysis (PCA)**, covering both its mathematical foundations and its practical application in machine learning pipelines.

## Project Overview
PCA is a powerful dimensionality reduction technique used to simplify complex datasets while retaining as much variance as possible. This project is split into two parts:
1.  **Mathematical Foundations**: A step-by-step manual implementation using Linear Algebra.
2.  **Practical Application**: Using PCA to optimize a high-dimensional image classification task (MNIST).

## Technical Stack
* **Language**: Python 3
* **Libraries**: `numpy`, `pandas`, `scikit-learn`, `matplotlib`, `plotly`

---

## 1. Step-by-Step Mathematical Implementation
This section demonstrates the "inner workings" of PCA by reducing a 3D synthetic dataset into a 2D plane without using high-level library shortcuts.

### Mathematical Workflow
1.  **Mean Centering**: Shifting the data so the mean of each feature is zero.
2.  **Covariance Matrix**: Computing the $3 \times 3$ matrix to find relationships between features.
3.  **Eigen-Decomposition**: 
    * **Eigenvectors**: Determining the directions of the new principal axes.
    * **Eigenvalues**: Determining the magnitude of variance captured by each axis.
4.  **Projection**: Transforming the original data points onto the new principal components.



---

## 2. Practical Demo: MNIST Digit Classification
This section applies PCA to the **MNIST dataset** (784 features) to demonstrate how dimensionality reduction affects model training and accuracy.

### Key Features
* **Explained Variance Analysis**: Using a **Scree Plot** to visualize the cumulative variance and determine how many components are needed to retain 90% or 95% of the information.
* **Dimensionality Compression**: Reducing 784 pixels down to a fraction of the original size.
* **Performance Benchmarking**: Comparing a Logistic Regression model's training speed and accuracy on the raw data versus the PCA-transformed data.



---

## Key Results
* **Efficiency**: PCA significantly reduces the computational cost and training time for high-dimensional models.
* **Visualization**: Interactive 3D plots (via Plotly) show how data clusters are preserved even after being projected onto lower-dimensional spaces.

## Usage
1.  **For Theory**: Run `pca_step_by_step.ipynb` to see the manual matrix calculations.
2.  **For Application**: Run `pca-demo.ipynb` to see the impact on MNIST classification performance.

### PCA code Kaggle notebook : https://www.kaggle.com/nitsin/pca-demo-1 
### Video Link:https://youtu.be/tXXnxjj2wM4