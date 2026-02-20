# 🚂 Train Data: JSON to SQL

A simple project to take messy, nested train data from JSON files and organize it into a clean SQL database.

## 🛠 What this does
* **JSON Flattening:** Takes nested lists (like stops inside a route) and turns them into flat tables.
* **SQL Migration:** Moves everything into a local SQLite database for easier querying.
* **Analysis:** Using SQL inside Jupyter to find the most delayed trains and busiest stations.

## 💻 Tech
* **Python** (Pandas)
* **SQL** (SQLite)
* **Jupyter Notebook** (ipython-sql magic)

### Referrences:
* **Video link** : https://www.youtube.com/watch?v=fFwRC-fapIU
* **Xampp download link** : https://www.apachefriends.org/index.html 
* **World dataset** : https://www.kaggle.com/busielmorley/worldcities-pop-lang-rank-sql-create-tbls?select=world.sql 
* **Pandas read_json documentation** : https://pandas.pydata.org/docs/reference/api/pandas.read_json.html 
* **Pandas read_sql_query documentation**: https://pandas.pydata.org/docs/reference/api/pandas.read_sql_query.html#pandas.read_sql_query