# AdaBoost Ensemble Learning — Foundations & Hyperparameter Tuning

This repository contains a structured, hands-on curriculum detailing the algorithmic mechanics, boundary optimization, and hyperparameter tuning of the Adaptive Boosting (AdaBoost) ensemble architecture. The track transitions from fundamental sequential tree stump boosting to deep tuning pipelines executed on clinical diagnostic datasets.

---

## 📂 Repository Architecture

The workspace is organized into foundational modules and experimental pipelines targeting boosting optimization:

```text
└── 🚀 day66-adaboost
    ├── heart.csv                        # Tabular clinical dataset for heart disease classification
    ├── adaboost_demo.ipynb              # Sequential stump optimization and baseline training
    └── adaboost-hyperparameter.ipynb    # Multi-dimensional validation and hyperparameter tuning
 ```

## 🧠 Module Breakdown & Architectural Blueprints

### 1. Sequential Ensemble Mechanics (`adaboost_demo.ipynb`)
* **Core Concept:** Understanding the structural shift from parallel architectures (like Random Forests) to sequential greedy stagewise boosting models.
* **Algorithmic Engine:** Iteratively trains weak learners—specifically **Decision Stumps** (single-split decision trees with a max depth of 1).
* **Instance Weighting:** Calculates the total sample error of the active stump to assign its voting power (Amount of Say). Sample row weights are updated adaptively after each iteration: correctly classified instances have their weights decreased, while misclassified points see their weights magnified.
* **Boundary Evolution:** Focuses succeeding stumps exclusively on the hardest, previously misclassified feature regions, building a robust, high-performance master classifier from a collection of simple rules.

### 2. Advanced Hyperparameter Tuning & Validation (`adaboost-hyperparameter.ipynb`)
* **Objective:** Systematic optimization of boosting convergence boundaries to prevent overfitting and stabilize learning rates.
* **Key Tuning Hyperparameters:** Explores the performance trade-offs across complex diagnostic grids using Scikit-Learn:
  * `n_estimators`: Determining the total number of sequential boosting rounds to perform.
  * `learning_rate`: Controlling the shrinkage factor applied to each individual stump's "Amount of Say" (a lower rate slows down learning, requiring more estimators but smoothing out the loss surface).
  * `estimator` / `base_estimator`: Changing the base classifier from simple depth-1 stumps to slightly deeper tree structures to analyze variance-bias behaviors.
* **Validation Standards:** Integrates automated evaluation report grids tracking precision, recall bounds, and F1-scores to audit overall generalization.

---

## 📊 Dataset Profile (`heart.csv`)

The optimization routines are evaluated using a clinical heart disease data configuration. The classifiers map multi-dimensional patient physiological inputs into structured binary classification risk boundaries:

* **Target Variable:** Binary status tracking diagnostic risk factors.
* **Feature Signatures:** Includes patient metrics spanning numeric biomarkers, resting vital signs, and discrete categorical medical history values.

---

## 📈 Technical Execution Matrix

| Evaluation Capability | Optimization & Exploration Track | Diagnostic & Interpretation Track |
| :--- | :--- | :--- |
| **Primary Goal** | Minimize bias sequentially via weak learner boosting. | Tune learning boundaries and avoid overfitting loops. |
| **Key Metrics** | Adaptive Sample Weights, Class Error Margins. | Precision, Recall, Learning Curves, F1-Scores. |
| **Core Software Modules** | `sklearn.ensemble.AdaBoostClassifier` | `sklearn.metrics`, `matplotlib.pyplot` |

---

## 🛠️ Environment Configuration & Deployment

Verify your local execution environment contains the necessary software dependencies before starting data analysis:

### Installation
```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```