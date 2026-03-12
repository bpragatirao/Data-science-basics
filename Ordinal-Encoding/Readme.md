# Ordinal and Label Encoding Project

This project explores **Categorical Encoding** techniques, specifically focusing on how to transform text-based categorical data into numerical values that machine learning models can process.

## Table of Contents
* [Overview](#overview)
* [Libraries Used](#libraries-used)
* [Techniques Demonstrated](#techniques-demonstrated)
* [Dataset Details](#dataset-details)

## Overview
In data science, we often encounter "Ordinal" data (categories with a specific order) and "Nominal" data (categories without order). This notebook demonstrates the practical implementation of `OrdinalEncoder` and `LabelEncoder` using Scikit-Learn.

## Libraries Used
* **Pandas**: For structured data handling.
* **NumPy**: For numerical computations.
* **Scikit-Learn**: Utilizing `preprocessing` modules for encoding.

## Techniques Demonstrated
1. **Ordinal Encoding**: Used for features where the order matters. For example:
   * **Education**: School < UG < PG
   * **Review**: Poor < Average < Good
2. **Label Encoding**: Used specifically for the **Target Variable** (the value we want to predict). In this case, it transforms categorical outputs like "Yes/No" into binary format (1/0).

## Dataset Details
The notebook uses a **Customer dataset** (`customer.csv`) containing:
* **Age**: Numerical feature.
* **Gender**: Nominal categorical feature.
* **Review**: Ordinal feature (Good, Average, Poor).
* **Education**: Ordinal feature (School, UG, PG).
* **Purchased**: Target label (Yes, No).

## Implementation Workflow
* Select the categorical columns for encoding.
* Define the order of categories for the `OrdinalEncoder`.
* Split the data into training and testing sets.
* Fit the encoder on the training data and transform both sets to ensure consistency.

### Video Link: https://youtu.be/w2GglmYHfmM