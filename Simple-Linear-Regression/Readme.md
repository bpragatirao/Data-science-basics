# Simple Linear Regression: Custom Implementation vs. Scikit-Learn

This repository provides a comprehensive look at **Simple Linear Regression**, comparing a "from-scratch" mathematical implementation with the industry-standard `scikit-learn` library. It demonstrates how a single independent variable (CGPA) can be used to predict a continuous dependent variable (Package/LPA).

## Project Overview
The project is divided into two notebooks to showcase both the theory and the practical application of linear modeling:
1.  **MeraLR (Custom Class)**: A manual implementation of the Ordinary Least Squares (OLS) method.
2.  **Scikit-Learn Implementation**: A practical demo using standard data science libraries for rapid modeling.

## Technical Stack
* **Language**: Python 3
* **Libraries**: `numpy`, `pandas`, `matplotlib`, `scikit-learn`

---

## 1. Custom Implementation (`MeraLR`)
This notebook features a custom class named `MeraLR` that calculates the regression coefficients without high-level library assistance.

### Mathematical Logic (Ordinary Least Squares)
The class calculates the slope ($m$) and the intercept ($b$) using the following formulas:
* **Slope ($m$)**: 
  $$\frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sum (x_i - \bar{x})^2}$$
* **Intercept ($b$)**: 
  $$\bar{y} - m\bar{x}$$

### Class Features
* `fit(X_train, y_train)`: Iterates through the training data to compute the optimal $m$ and $b$ based on the mean of the features.
* `predict(X_test)`: Uses the derived linear equation ($y = mx + b$) to estimate values for new data points.



---

## 2. Scikit-Learn Demo
This notebook demonstrates the standard workflow for implementing linear regression in a production or research environment.

### Workflow
1.  **Data Visualization**: Using scatter plots to verify the linear relationship between student CGPA and the packages offered.
2.  **Train-Test Split**: Dividing the `placement.csv` data to evaluate the model's predictive accuracy on unseen data.
3.  **Model Fitting**: Utilizing `LinearRegression()` to quickly find the line of best fit.
4.  **Verification**: Visualizing the regression line over the scatter plot to see how well the model captures the data trend.


---

## Key Results
* **Consistency**: The custom `MeraLR` class yields identical coefficients (slope and intercept) to the `scikit-learn` model, proving the mathematical validity of the manual implementation.
* **Interpretation**: The model successfully quantifies the relationship between academic performance (CGPA) and job placement outcomes.

## Usage
1.  Ensure `placement.csv` is in the same directory.
2.  Run `MeralR-linear-regression.ipynb` to see the step-by-step logic.
3.  Run `Simple-linear-regression.ipynb` for the library-based implementation and visualization.

### Video Link : https://youtu.be/UZPfbG0jNec