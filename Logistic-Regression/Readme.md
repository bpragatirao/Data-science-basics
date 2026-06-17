# Logistic Regression: From the Perceptron Trick to Gradient Descent

This repository features three sequential Jupyter Notebooks that map out the educational journey and progression of foundational binary classification algorithms in machine learning. It starts with the geometric intuitions of the classic **Perceptron Trick**, transitions through the **Sigmoid Activation Function**, and culminates in an optimal **Logistic Regression Model via Gradient Descent**.

---

## 📂 Repository Structure

The single-file project is divided across three distinct notebooks, each focusing on a fundamental phase of evolutionary neuron design:

1. **`perceptron-trick.ipynb`** — Implements the basic step-function Perceptron using random classification points to showcase how a decision boundary moves strictly based on misclassified coordinates.
2. **`perceptron-trick-sigmoid.ipynb`** — Integrates the Sigmoid Activation function to smooth the prediction thresholds, transforming discrete step adjustments into continuous probability updates.
3. **`gradient-descent.ipynb`** — Formulates Logistic Regression systematically from scratch by combining Sigmoid activations with Binary Cross-Entropy Loss optimization via Vectorized Gradient Descent.

---

## 📊 Dataset Configuration

All three notebooks utilize synthetic binary classification datasets generated dynamically with `sklearn.datasets.make_classification`. The pipeline evaluates $100$ samples featuring $2$ distinct numeric attributes across $2$ balanced structural classes:

* **Sample Size ($n$):** 100
* **Dimensionality:** 2 Features ($X_1, X_2$)
* **Separation Multiplier (`class_sep`):** Scaled incrementally across files (ranging from 10 to 30) to test decision boundary resilience against varying clustering densities.

---

## 🧠 Notebook Breakdowns

### 1. Perceptron Trick (`perceptron-trick.ipynb`)
This notebook demonstrates how a single-layer neuron learns an optimal separating hyperplane using standard iterative sample testing.

* **Mechanism:** Picks a random point dynamically from the dataset. If a point is misclassified (e.g., a positive class falls into the negative classification zone or vice versa), the decision boundary vector coordinates subtract or add the scalar features of that point scaled by a Learning Rate ($\eta$).
* **Boundary Formula:** $$A x_1 + B x_2 + C = 0$$
* **Key Coding Feature:** Implements a localized loop function to visually plot individual epoch adjustment lines against the matplotlib coordinate space.

### 2. Sigmoid Perceptron (`perceptron-trick-sigmoid.ipynb`)
Building on the classic trick, this file handles structural instability when handling boundary-fringe data points by swapping the harsh step threshold for a continuous function.

* **Mechanism:** Maps input values onto a mathematical probability framework between `0` and `1` using the **Sigmoid function**:
    $$\sigma(z) = \frac{1}{1 + e^{-z}}$$
* **Key Advantage:** Weights are no longer updated solely based on right vs. wrong; they are updated based on *how confident* the model was in its prediction, preventing radical decision line swings.

### 3. Gradient Descent Optimization (`gradient-descent.ipynb`)
The final phase generalizes the network into a standard Logistical Classifier optimized continuously via Gradient Descent calculus.

* **Vectorization:** Pre-processes the design matrix by prepending a column of ones ($1$) to account cleanly for intercepts and biases simultaneously in single-step matrix math:
    ```python
    np.insert(X, 0, 1, axis=1)
    ```
* **Mathematical Engine:** Combines the Sigmoid activation with the Log-Loss function (Binary Cross-Entropy) to take deliberate, partial-derivative-guided steps down the error surface.
* **Update Step:**
    $$W_{new} = W_{old} - \eta \cdot \frac{\partial L}{\partial W}$$

---

## 🛠️ Environment Setup & Requirements

To interact with and run the notebooks, ensure your Python working environment has the following primary data stack packages configured:

```bash
pip install numpy matplotlib scikit-learn jupyter