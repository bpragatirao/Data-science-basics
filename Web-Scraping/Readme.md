# 🕸️ Web Scraping with PandaFramework

A simple setup for scraping data from websites and converting it directly into structured Pandas Dataframes.

## 🛠 What this does
* **Data Extraction:** Grabbing HTML content from URLs.
* **Table Parsing:** Using `pd.read_html()` to instantly turn web tables into dataframes.
* **Custom Scraping:** Targeted extraction of specific tags (titles, prices, etc.) using BeautifulSoup/Scrapy.
* **Cleaning:** Stripping whitespace, fixing currency symbols, and handling missing web data.

## 💻 Tech
* **Python** (Pandas, PandaFramework)
* **Scraping Tools:** BeautifulSoup4, Requests
* **Jupyter Notebook**

## 🚀 The Cheat Sheet
* **Quick Table Scrape:** `df = pd.read_html('https://example.com')[0]`
* **Fetch HTML:** `response = requests.get(url)`
* **Export:** Saving your scraped results to `.csv` or `.json`.

## 📊 Visuals
* **Comparison Charts:** Visualizing scraped data (e.g., price comparisons).
* **Word Clouds:** Showing common terms found on a webpage.
