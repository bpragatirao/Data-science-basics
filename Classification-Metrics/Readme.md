# Comprehensive Evaluation Metrics for Binary and Multi-Class Classification

This repository features three sequential Jupyter Notebooks focused on the implementation, evaluation, and breakdown of classification metrics in Machine Learning. It serves as a practical guide to interpreting model performance, moving systematically from **Binary Classification Diagnostics** to **Multi-Class Evaluation Strategies** across varying dataset sizes and dimensions.

---

## 📂 Repository Structure

The project is structured across three target notebooks, each examining evaluation metrics under different data dynamics:

1. **`classification-metrics-binary.ipynb`** — Focuses on binary classification metrics, exploring parameters such as Precision, Recall, F1-Score, and the trade-offs involved in tuning decision thresholds for two-class problems.
2. **`classification-metrics-multi-iris1.ipynb`** — Explores multi-class evaluation using the classic, low-dimensional Iris flower dataset, highlighting how per-class metrics are computed and aggregated.
3. **`classification-metrics-multi-mnist1.ipynb`** — Scales multi-class validation to a high-dimensional handwritten digit classification problem (MNIST subset), demonstrating micro vs. macro averaging over larger cluster spaces.

---

## 📊 Dataset Configurations & Targets

### 1. Binary Classification System
* **Data Context:** Evaluates two-class distributions to diagnose performance bottlenecks using diagnostic matrices.
* **Objective:** Establish baseline definitions for Type I (False Positive) and Type II (False Negative) errors to balance classification behavior.

### 2. Multi-Class Iris Botanical Dataset
* **Data Context:** The classic Iris dataset containing 3 distinct targets (*Iris-setosa*, *Iris-versicolor*, and *Iris-virginica*) evaluated across 4 physical characteristics.
* **Objective:** Evaluate baseline multi-class performance when data is balanced and perfectly separated into distinct clusters.

### 3. High-Dimensional MNIST Handwritten Digits
* **Data Context:** High-dimensional image arrays representing handwritten digits (`0` through `9`).
* **Objective:** Analyze multi-class evaluation at scale, tracking model confusion across complex structural features and higher class volumes.

---

## 🧠 Diagnostic Breakdowns & Key Metrics

Each notebook leverages Scikit-Learn's `sklearn.metrics` module to calculate, compare, and extract performance criteria:

### 📐 Core Calculations Documented
* **Accuracy:** The ratio of correct predictions to total observations. (Handled with caution regarding class imbalance).
* **Precision (Positive Predictive Value):** Measures the accuracy of positive predictions.
  $$\text{Precision} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Positives (FP)}}$$
* **Recall (Sensitivity / True Positive Rate):** Measures the model's ability to find all positive instances.
  $$\text{Recall} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Negatives (FN)}}$$
* **F1-Score:** The harmonic mean of Precision and Recall, providing a balanced metric for uneven class distributions:
  $$\text{F1-Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$$

### 🔄 Multi-Class Averaging Strategies
When moving beyond binary classification (as seen in the Iris and MNIST notebooks), metrics are computed on a per-class basis and aggregated using distinct strategies:
* **`average=None`:** Outputs a raw array containing independent scores calculated specifically for each distinct label.
* **`average='macro'`:** Calculates metrics independently for each class and then takes their unweighted average. Treats all classes equally, regardless of their support count.
* **`average='micro'`:** Aggregates the total true positives, false negatives, and false positives globally across all classes to calculate a single overall metric.

---

## 💻 Code Snippets & Reporting Formats

The notebooks utilize comprehensive execution frameworks to print structured performance tables. A primary highlight across the multi-class workflows is the generation of Scikit-Learn’s `classification_report`:

```python
from sklearn.metrics import classification_report

# Generating detailed per-class and macro/micro aggregated reports
print(classification_report(y_test, y_pred1))```