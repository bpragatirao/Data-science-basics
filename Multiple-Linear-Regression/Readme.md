# 📊 Multiple Linear Regression from Scratch

## 📌 Project Overview

This project demonstrates the implementation of **Multiple Linear Regression** using both:

1. **Scikit-Learn's LinearRegression**
2. **A custom-built Linear Regression model from scratch using NumPy**

The objective is to understand the mathematical foundations of linear regression while comparing a manual implementation with Scikit-Learn's optimized implementation.

The project uses:
- The **Diabetes Dataset** from Scikit-Learn
- Synthetic regression data generated using `make_regression()`
- Performance evaluation using regression metrics
- 3D visualization of regression planes

---

## 🎯 Objectives

- Understand how Multiple Linear Regression works.
- Learn how regression coefficients and intercepts are calculated.
- Implement Linear Regression from scratch using the Normal Equation.
- Compare custom implementation with Scikit-Learn.
- Evaluate model performance using regression metrics.
- Visualize regression surfaces in 3D.

---

## 🧠 What is Multiple Linear Regression?

Multiple Linear Regression models the relationship between multiple independent variables and a dependent variable.

### Mathematical Equation

```math
y = b_0 + b_1x_1 + b_2x_2 + \cdots + b_nx_n
```

Where:

- `y` = Predicted value
- `b₀` = Intercept
- `b₁, b₂, ..., bₙ` = Feature coefficients
- `x₁, x₂, ..., xₙ` = Input features

The model learns the best coefficients that minimize prediction error.

---

## 📂 Project Structure

```bash
Multiple-Linear-Regression/
│
├── notebooks/
│   ├── code-from-scratch.ipynb
│   └── multiple_linear_regression.ipynb
│
├── src/
│   ├── custom_linear_regression.py
│   ├── train.py
│   └── evaluate.py
│
├── requirements.txt
└── README.md
```

---

## 🛠 Technologies Used

- Python
- NumPy
- Pandas
- Scikit-Learn
- Plotly
- Matplotlib

---

## 📚 Dataset Used

### Diabetes Dataset

The notebook uses Scikit-Learn's built-in Diabetes dataset:

```python
from sklearn.datasets import load_diabetes

X, y = load_diabetes(return_X_y=True)
```

Dataset Characteristics:

- 442 samples
- 10 numerical features
- Continuous target variable

---

## 🚀 Workflow

### 1. Data Loading

Load the Diabetes dataset and inspect its dimensions.

### 2. Train-Test Split

Split the dataset into:

- Training Set (80%)
- Testing Set (20%)

```python
train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=2
)
```

### 3. Model Training

Train a Multiple Linear Regression model using:

```python
LinearRegression()
```

### 4. Prediction

Generate predictions on unseen test data.

### 5. Evaluation

Evaluate model performance using regression metrics.

### 6. Visualization

Create a 3D regression plane using Plotly.

---

# 🔨 Linear Regression From Scratch

A custom class is implemented to understand the internal working of Multiple Linear Regression.

### Features

- Manual coefficient calculation
- Manual intercept calculation
- Custom prediction method
- NumPy-based implementation

The custom model follows the same workflow:

```python
model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

---

# 📊 Evaluation Metrics

## 1️⃣ R² Score

Measures how well the model explains variability in the target variable.

### Formula

```math
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
```

### Interpretation

| R² Score | Performance |
|-----------|------------|
| 1.0 | Perfect Fit |
| 0.9+ | Excellent |
| 0.7 – 0.9 | Good |
| 0.5 – 0.7 | Moderate |
| < 0.5 | Poor |

---

## 2️⃣ Mean Absolute Error (MAE)

Average absolute difference between actual and predicted values.

### Formula

```math
MAE = \frac{1}{n}\sum |y_i - \hat{y}_i|
```

### Interpretation

- Lower MAE indicates better performance.
- Errors are measured in original target units.

---

## 3️⃣ Mean Squared Error (MSE)

Average squared difference between predictions and actual values.

### Formula

```math
MSE = \frac{1}{n}\sum (y_i - \hat{y}_i)^2
```

### Interpretation

- Penalizes large errors heavily.
- Lower values indicate better performance.

---

## 4️⃣ Root Mean Squared Error (RMSE)

Square root of MSE.

### Formula

```math
RMSE = \sqrt{\frac{1}{n}\sum (y_i - \hat{y}_i)^2}
```

### Interpretation

- Provides error in the same unit as the target variable.
- Easier to interpret than MSE.

---

# 📈 3D Regression Visualization

The project generates synthetic data with two independent variables and visualizes:

- Data points
- Regression plane
- Relationship between features and target

Visualization is created using:

```python
plotly.express.scatter_3d()
plotly.graph_objects.Surface()
```

This helps understand how the regression plane fits multidimensional data.

---

# 🧪 Sample Code

```python
from sklearn.linear_model import LinearRegression

lr = LinearRegression()

lr.fit(X_train, y_train)

y_pred = lr.predict(X_test)
```

### Evaluation

```python
from sklearn.metrics import (
    mean_absolute_error,
    mean_squared_error,
    r2_score
)

print("MAE:", mean_absolute_error(y_test, y_pred))
print("MSE:", mean_squared_error(y_test, y_pred))
print("R2:", r2_score(y_test, y_pred))
```

---

# ✅ Key Learnings

- Understanding regression mathematically.
- Difference between single and multiple linear regression.
- Building ML algorithms from scratch.
- Model evaluation techniques.
- Visualizing multidimensional regression problems.
- Comparing custom implementations with Scikit-Learn.

---

# 📌 Results

The custom implementation produces predictions similar to Scikit-Learn's Linear Regression model, demonstrating the correctness of the mathematical approach.

Performance is evaluated using:

- R² Score
- MAE
- MSE
- RMSE

---

# 🚀 Future Improvements

- Gradient Descent implementation
- Regularization (Ridge & Lasso)
- Polynomial Regression
- Feature Engineering
- Cross Validation

---

# 👨‍💻 Author

This project was developed as a hands-on learning exercise to understand the mathematics and implementation details behind Multiple Linear Regression and build machine learning algorithms from scratch using NumPy.

### Video Link : https://youtu.be/ashGekqstl8