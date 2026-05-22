# 📈 Simple Linear Regression Project

## 📌 Project Overview
This project demonstrates the implementation of **Simple Linear Regression**, one of the fundamental supervised machine learning algorithms used for predicting continuous numerical values.

The model learns the relationship between:
- **Independent Variable (X)** → Input feature
- **Dependent Variable (Y)** → Target/output value

The objective is to fit the **best straight line** through the data points to make predictions.

---

## 🧠 What is Simple Linear Regression?

Simple Linear Regression models the relationship between two variables using the equation:

```math
y = mx + c
```

Where:
- `y` → Predicted value
- `x` → Input feature
- `m` → Slope of the line
- `c` → Intercept

The algorithm tries to minimize the prediction error between actual and predicted values.

---

## ⚙️ Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

## 📂 Project Structure

```bash
Simple-Linear-Regression/
│
├── data/
│   └── dataset.csv
│
├── notebooks/
│   └── linear_regression.ipynb
│
├── src/
│   ├── data_preprocessing.py
│   ├── train_model.py
│   └── evaluate_model.py
│
├── requirements.txt
└── README.md
```

---

## 🚀 Steps Performed

1. Imported the dataset
2. Performed data preprocessing
3. Split data into training and testing sets
4. Trained the Linear Regression model
5. Made predictions
6. Evaluated model performance using regression metrics
7. Visualized regression line and predictions

---

# 📊 Evaluation Metrics Explained

Regression metrics help measure how well the model predicts values.

---

## 1️⃣ R² Score (Coefficient of Determination)

The **R² Score** measures how well the regression line explains the variability of the data.

### Formula

```math
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
```

Where:
- `SSres` → Sum of squared residual errors
- `SStot` → Total sum of squares

### Interpretation

| R² Score | Meaning |
|---|---|
| 1.0 | Perfect prediction |
| 0.9+ | Excellent model |
| 0.7–0.9 | Good model |
| 0.5–0.7 | Moderate fit |
| < 0.5 | Poor fit |

### Example
- `R² = 0.92`
  - The model explains **92%** of the variance in the data.

---

## 2️⃣ Mean Absolute Error (MAE)

MAE calculates the average absolute difference between actual and predicted values.

### Formula

```math
MAE = \frac{1}{n}\sum |y_i - \hat{y}_i|
```

### Interpretation
- Lower MAE → Better model
- Easy to understand because errors are in original units

---

## 3️⃣ Mean Squared Error (MSE)

MSE measures the average squared difference between predictions and actual values.

### Formula

```math
MSE = \frac{1}{n}\sum (y_i - \hat{y}_i)^2
```

### Interpretation
- Penalizes larger errors more heavily
- Lower MSE indicates better performance

---

## 4️⃣ Root Mean Squared Error (RMSE)

RMSE is the square root of MSE.

### Formula

```math
RMSE = \sqrt{\frac{1}{n}\sum (y_i - \hat{y}_i)^2}
```

### Interpretation
- Gives error in the same unit as target variable
- More sensitive to large prediction errors

---

# 📈 Visualization

The project includes:
- Scatter plot of actual data points
- Best fit regression line
- Prediction comparison graphs

These visualizations help understand:
- Correlation between variables
- Accuracy of the fitted regression line
- Prediction behavior

---

# 🧪 Sample Code

```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score

model = LinearRegression()
model.fit(X_train, y_train)

predictions = model.predict(X_test)

score = r2_score(y_test, predictions)

print("R2 Score:", score)
```

---

# ✅ Advantages of Linear Regression

- Simple and easy to implement
- Fast training
- Interpretable results
- Works well for linear relationships

---

# ❌ Limitations

- Assumes linear relationship
- Sensitive to outliers
- Cannot model complex nonlinear patterns

---

# 📌 Conclusion

This project demonstrates how Simple Linear Regression can be used to predict continuous values and evaluate model performance using important regression metrics such as:
- R² Score
- MAE
- MSE
- RMSE

Understanding these metrics is essential for interpreting the quality and reliability of machine learning regression models.
