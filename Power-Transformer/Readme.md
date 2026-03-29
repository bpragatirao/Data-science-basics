# Power Transformation: Box-Cox and Yeo-Johnson

This repository contains a Jupyter Notebook demonstrating how to use Scikit-Learn's **PowerTransformer** to stabilize variance and minimize skewness in numerical data. Using a concrete strength dataset, the notebook compares various power transformation techniques to improve the performance of linear regression models.

## 📋 Features

The notebook explores the "Normality" of data and how to achieve it through automated power transformations:

### 1. Diagnostic Visualization
Identifies non-normal distributions using a combination of plots for each feature in the dataset:
* **Histograms/Distplots:** To view the frequency distribution and skewness.
* **QQ-Plots (Probability Plots):** To check how closely the data follows a normal distribution line.


### 2. Box-Cox Transformation
* **Requirement:** Only works on strictly positive data ($x > 0$).
* **Mechanism:** Automatically finds the optimal exponent ($\lambda$) to transform the data into a Gaussian-like shape.
* **Analysis:** The notebook displays the specific $\lambda$ values calculated for each feature (e.g., Cement, Water, Age).

### 3. Yeo-Johnson Transformation
* **Requirement:** A more versatile version that works for both positive and negative data.
* **Implementation:** Demonstrated as a robust alternative to Box-Cox for datasets that might include zero or negative values.


### 4. Model Performance Benchmarking
Provides a side-by-side comparison of prediction accuracy:
* **Algorithm:** Linear Regression.
* **Metric:** $R^2$ Score.
* **Comparison:** Shows the improvement in $R^2$ scores when training on raw data versus power-transformed data.

---

## 🛠️ Requirements
* **NumPy & Pandas**
* **Matplotlib & Seaborn**
* **SciPy** (for `stats.probplot`)
* **Scikit-Learn**

## 📊 Dataset: `concrete_data.csv`
The notebook analyzes various factors affecting concrete compressive strength:
* **Input Features:** Cement, Blast Furnace Slag, Fly Ash, Water, Superplasticizer, Coarse Aggregate, Fine Aggregate, and Age.
* **Target:** Compressive Strength.

---

## 🚀 Key Takeaways
1. **Linear Model Assumptions:** Many parametric models (like Linear Regression) assume that errors and features are normally distributed; Power Transformers help satisfy this assumption.
2. **Lambda ($\lambda$) Optimization:** One of the greatest strengths of `PowerTransformer` is that it uses Maximum Likelihood Estimation (MLE) to decide the best transformation for each column automatically.
3. **Pipeline Integration:** Like other Scikit-Learn transformers, `PowerTransformer` can be seamlessly integrated into a `Pipeline` to prevent data leakage.

### Video Link : https://youtu.be/lV_Z4HbNAx0