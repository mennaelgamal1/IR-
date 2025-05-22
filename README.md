# 🌐 Website Crawlability Analyzer + Amazon Product Viewer

This project combines website crawlability analysis (based on `robots.txt`) with Amazon product data scraping and a rich Gradio interface to display key information and visuals.

---

## 🚀 Features

### ✅ Crawlability Analyzer
- Checks `robots.txt` for:
  - `Sitemap` links
  - `Crawl-delay` directives
- Verifies crawl permissions for common paths like `/gp/cart`, `/wishlist`, etc.
- Calculates a **Crawlability Score** (how many tested URLs are allowed)
- Provides practical scraping recommendations (e.g., use of `requests`, `Selenium`, or `Scrapy`)

### 🛒 Amazon Product Scraper
- Scrapes top product listings from **Amazon search results**
- Extracts product details like:
  - Title
  - Price
  - Rating
  - Reviews
  - Availability
  - Product image
- Saves data into an Excel file

### 📊 Product Viewer Interface (Gradio)
- Loads and displays scraped Amazon product data
- Shows:
  - First 20 product rows (Title, Price, Rating)
  - Top 10 product images with titles, price, and rating captions
- Clean and interactive UI using **Gradio**

---

## 🛠️ Setup Instructions

### 1. Clone this Repository
```bash
git clone https://github.com/yourusername/crawlability-analyzer.git
cd crawlability-analyzer
```

### 2. Install Required Libraries
Make sure you have **Python 3.8+** installed.

```bash
pip install -r requirements.txt
```

<details>
<summary>🔧 Click to see <code>requirements.txt</code></summary>

```
requests
beautifulsoup4
pandas
numpy
openpyxl
gradio
streamlit
selenium
```

</details>

### 3. WebDriver for Selenium
If using Selenium (e.g., for dynamic Amazon pages):

- Download ChromeDriver: https://sites.google.com/a/chromium.org/chromedriver/
- Make sure the version matches your Chrome browser.
- Add the executable to your PATH or specify in your script.

---

## 📂 How to Use

### 🌍 Crawlability Check
1. Launch the Gradio app:
```bash
python your_script_name.py
```

2. Enter the base URL (e.g., `https://www.amazon.com`) and click **Analyze Site Live**.
3. You'll see crawlability stats, score, and scraping recommendations.

---

### 📦 Scrape Amazon Product Data

1. Open your scraping script section (`__main__` block).
2. It fetches product search results (PlayStation 4) from:
```
https://www.amazon.com/s?k=playstation+4
```
3. Scrapes up to 100 product pages and saves them to an Excel file:
```
amazon_products_YYYYMMDD_HHMMSS.xlsx
```

> 📝 Note: This data is later used in the Gradio interface.

---

### 📊 View Products from Excel

1. Place the generated Excel file path inside the `load_excel_data()` function:
```python
file_path = r"C:\Users\YourUsername\Desktop\amazon_products_20250522_025027.xlsx"
```

2. Click **Load Products from Excel** to see:
   - Top 20 product details
   - Product image gallery with ratings and prices

---

## ⚠️ Legal & Ethical Disclaimer

- Scraping Amazon or similar sites may violate their [Terms of Service](https://www.amazon.com/gp/help/customer/display.html?nodeId=201909000).
- This project is for **educational purposes only**.
- Always respect `robots.txt`, rate-limiting, and avoid harming server performance.

---

## 🙋 Author

**Your Name**  
[GitHub](https://github.com/yourusername) • [LinkedIn](https://www.linkedin.com/in/yourprofile)

---

## 📌 To-Do (Optional Ideas)

- [ ] Add support for other e-commerce sites (e.g., eBay, BestBuy)
- [ ] Integrate headless Selenium with full rendering
- [ ] Export image gallery to HTML report
