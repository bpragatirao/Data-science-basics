# Titanic Dataset: Univariate Analysis

This project focuses on **Univariate Analysis** of the Titanic dataset. By examining each variable individually, we aim to understand the distribution, central tendency, and frequency of specific features before moving into multivariate modeling.

## 1. Categorical Data Analysis

The analysis explores the frequency distribution of categorical features using counts and percentages.

### Survived (Target Variable)
* **Distribution**: A majority of the passengers did not survive.
* **Visualization**: Bar charts and pie charts were used to visualize the "death vs. survival" ratio.

### Pclass (Passenger Class)
* **Insights**: Most passengers belonged to the **3rd Class**.
* **Hierarchy**: The data shows a clear count descending from 3rd class to 1st class.

### Sex & Embarked
* **Gender**: The dataset contains a higher count of male passengers compared to female passengers.
* **Port of Embarkation**: The majority of passengers embarked from **Southampton (S)**.

---

## 2. Numerical Data Analysis

For continuous variables, the analysis focuses on the shape of the data and identifying potential outliers.

### Age
* **Distribution**: The age distribution is roughly **Normal** (Gaussian), with a slight right skew.
* **Key Stats**: Most passengers were in the 20–40 age range.

### Fare
* **Distribution**: Highly **skewed to the right**.
* **Outliers**: Boxplots indicate several high-value outliers, representing luxury tickets that cost significantly more than the median fare.

---

## 3. Data Quality & Distribution Shapes
* **Skewness**: The `skew()` function was applied to measure the asymmetry of numerical distributions.
* **Outliers**: Identified primarily in the `Fare`, `SibSp` (siblings/spouses), and `Parch` (parents/children) columns using Boxplots.

## Tools Used
* **Pandas**: For data manipulation and frequency tables.
* **Seaborn/Matplotlib**: For generating Histograms, Distplots, Boxplots, and Pie charts.

## Video Link : https://www.youtube.com/watch?v=4HyTlbHUKSw