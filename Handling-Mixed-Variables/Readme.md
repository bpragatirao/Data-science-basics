# Handling Mixed Variables in Feature Engineering

This repository contains a Jupyter Notebook dedicated to the identification and extraction of meaningful features from "mixed" variables—columns that contain both numbers and strings (labels) within the same observation. Using the Titanic and Titanic-related datasets, the notebook demonstrates how to clean and split these complex features for machine learning models.

## 📋 Features

The notebook focuses on transforming semi-structured data into pure numerical and categorical components:

### 1. Identifying Mixed Variables
Explores columns where data types are inconsistent or combined, such as:
* **Cabin:** Contains a letter (deck) and a number (room), e.g., `C123`.
* **Ticket:** Often contains a string prefix followed by a numerical sequence, e.g., `A/5 21171`.
* **Number_Survival:** A hypothetical or synthetic column containing mixed numeric and text-based survival indicators.

### 2. Feature Extraction: Numerical Parts
Demonstrates the use of regular expressions and string manipulation to isolate digits.
* **Method:** `df['column'].str.extract('(\d+)')`
* **Use Case:** Extracting the room number from `Cabin` or the sequence from `Ticket`.

### 3. Feature Extraction: Categorical Parts
Demonstrates how to capture the string component or prefix to identify logical groupings.
* **Method:** `df['column'].str[0]` or regex-based extraction.
* **Use Case:** Extracting the "Deck" letter (A, B, C, etc.) from a cabin number to use as a categorical feature.

### 4. Handling Missing Values in Mixed Data
Provides strategies for dealing with `NaN` values that often occur in mixed columns.
* **Logic:** Ensuring that extraction functions don't fail when encountering nulls and deciding whether to fill them before or after splitting the variable.

---

## 🛠️ Requirements
* **NumPy**
* **Pandas**
* **Matplotlib** (for visualizing the distribution of newly created features)

## 📊 Dataset: Titanic
The notebook specifically targets the challenging columns of the Titanic dataset:
* `Cabin`: Splitting into `cabin_num` and `cabin_cat`.
* `Ticket`: Separating the prefix from the numerical ID.
* `number_survival`: Extracting survival codes and labels.

---

## 🚀 Key Takeaways
1. **Unlocking Hidden Info:** Mixed variables often hide significant predictive power (e.g., the deck level in a cabin number might correlate strongly with survival rates).
2. **Data Cleaning Workflow:** Shows the importance of cleaning string data before applying standard Scikit-Learn transformers like `OneHotEncoder` or `SimpleImputer`.
3. **Regular Expressions (Regex):** Highlights regex as an essential tool for any data scientist dealing with messy, real-world datasets.

### Video Link : https://youtu.be/9xiX-I5_LQY