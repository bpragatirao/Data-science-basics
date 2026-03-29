# Titanic Survival Prediction: Pipeline vs. Non-Pipeline Workflows

This project provides a comprehensive comparison between manual data preprocessing and automated Scikit-Learn Pipelines using the Titanic dataset. It demonstrates how to handle mixed data types, missing values, and feature scaling while comparing the complexity of prediction workflows with and without serialized pipeline objects.

## 📂 Project Structure

The analysis is divided into four main functional areas:

### 1. Training Without Pipelines
Demonstrates the traditional, step-by-step approach to data science workflows.
* **Manual Preprocessing:** Individual application of `SimpleImputer` for age, `OneHotEncoder` for gender and embarked status, and `MinMaxScaler` for numerical features.
* **Feature Engineering:** Manual concatenation of transformed arrays using `np.concatenate`.
* **Model Training:** Training a `DecisionTreeClassifier` on the manually assembled feature set.

### 2. Training With Pipelines
Shows the streamlined method using Scikit-Learn's `Pipeline` and `ColumnTransformer`.
* **Modular Transformers:** Defines specific `ColumnTransformer` steps for imputation, encoding, and scaling.
* **Feature Selection:** Integration of `SelectKBest` within the pipeline to automate feature importance.
* **Hyperparameter Tuning:** Demonstration of `GridSearchCV` applied directly to the pipeline object to find optimal tree depth.
* **Serialization:** Exporting the entire trained pipeline as `pipe.pkl` using `pickle`.

### 3. Prediction Workflows
Comparison of how new data is processed for inference:
* **Without Pipeline:** Requires loading multiple individual `.pkl` files (encoders, models) and replicating every preprocessing step (imputing, encoding, stacking) manually before calling `.predict()`.
* **With Pipeline:** Requires loading a single `pipe.pkl` file; raw data is passed directly to `pipe.predict()`, with all preprocessing steps handled internally.

---

## 🛠️ Requirements
* **NumPy**
* **Pandas**
* **Scikit-Learn**
* **Pickle**

## 📊 Dataset: Titanic (train.csv)
The models predict passenger survival based on:
* **Numerical Features:** Age, Fare, SibSp, Parch.
* **Categorical Features:** Sex, Embarked, Pclass.

---

## 🚀 Key Takeaways
1. **Consistency:** Pipelines prevent "data leakage" by ensuring the same statistics used in training are applied during testing.
2. **Simplicity:** Inference code is significantly reduced when using a serialized pipeline object.
3. **Automation:** Complex steps like feature selection and cross-validation become much easier to manage when wrapped in a single object.

### Video Link : https://youtu.be/xOccYkgRV4Q