# 📊 CSV Data Exploration

A quick and dirty guide to messing around with CSV data in Jupyter using Pandas. This covers everything from grabbing files online to cleaning up messy columns.

## 🛠 What's inside?
* **Remote Loading:** Pulling CSVs directly from a URL.
* **Data Cleanup:** Fixing separators, renaming columns, and handling weird formatting.
* **Quick Views:** Limiting rows and inspecting data types without crashing your notebook.

## 💻 Tech
* **Python** * **Pandas**
* **Jupyter Notebook**

## 🚀 The Cheat Sheet
* **Load via URL:** `pd.read_csv('https://link-to-your-file.csv')`
* **Custom Separators:** Using `sep=';'` or `sep='\t'` for those annoying non-comma files.
* **Modify:** Renaming columns or changing data types (e.g., strings to dates).
* **Sample:** Using `.head(10)` or `.sample(5)` to keep things readable.

## 📊 Visuals
* **Quick Plots:** Making histograms or bar charts of specific columns.
* **Correlations:** Checking how numbers relate to each other.

### Referrences:
* **Video link** : https://www.youtube.com/watch?v=a_XrmKlaGTs
* **Books dataset link** : http://www2.informatik.uni-freiburg.de/~cziegler/BX/