# 🏠 RentalBot – Zillow Clone Scraper & Google Form Filler

A Python automation bot that scrapes rental property data from a Zillow-style listings page and automatically submits each listing into a Google Form using Selenium.  
This project demonstrates end-to-end **web scraping + browser automation**, similar to a real-world data entry / RPA workflow.[web:39]

---

## 🚀 Features

- ✅ Scrapes **address**, **price**, and **listing URL** from a Zillow clone page  
- ✅ Uses **BeautifulSoup + requests** for HTML parsing and data extraction  
- ✅ Automates a **Google Form** using Selenium WebDriver  
- ✅ Loops through all scraped properties and submits a response for each  
- ✅ Simulates a real-world **data entry / RPA** use case  
- 🧪 Simple, readable structure using a `RentalBot` class  

---

## 🔧 Requirements

- Python 3.7+  
- Google Chrome installed  
- Matching ChromeDriver available on PATH (or configured in code)  

Install dependencies:

```bash
pip install -r requirements.txt
```


## 🛠 Setup
Clone the repo:

``` bash
git clone https://github.com/your-username/RentalBot-Zillow-GoogleForm-Automation.git
cd RentalBot-Zillow-GoogleForm-Automation
```
(Optional) Create and activate a virtual environment:

```bash
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # macOS / Linux
```
Install dependencies:

```bash
pip install -r requirements.txt
```
Run the bot:

```bash
python rental_bot.py
```

## 💡 How It Works

1. **Scrape rental listings**
   - Sends a GET request to the Zillow clone page:  
     https://appbrewery.github.io/Zillow-Clone/
   - Parses HTML using BeautifulSoup.
   - Extracts:
     - Property address
     - Monthly price
     - Listing URL

2. **Store data in memory**
   - Saves addresses, prices, and links in three Python lists:
     - `self.house_addresses`
     - `self.house_prices`
     - `self.house_links`

3. **Open Google Form**
   - Launches Chrome via `webdriver.Chrome()`.
   - Navigates to the Google Form URL:  
     https://forms.gle/7CmFc4o8JU1zECpW7

4. **Fill and submit the form**
   - For each property:
     - Finds the input fields (address, price, link) using XPATH.
     - Types the values using `send_keys()`.
     - Clicks the **Submit** button.
     - Clicks **Submit another response** and repeats for the next listing.


## 📦 File Structure
``` text
.
├── rental_bot.py         # Main bot logic (scraping + form filling)
├── requirements.txt      # Dependencies
└── README.md             # Documentation
```

## 📌 Notes

- This project is for **learning and portfolio** purposes.
- URLs used are demo/training pages (Zillow clone + Google Form), not real production systems.
- For a more robust version, you can:
  - Replace `time.sleep()` with `WebDriverWait`
  - Save data to CSV and load from CSV before form submission
  - Add logging to track which entries were submitted successfully

## 📬 Contact
Rohit Kumar  
Email: rohitkuarm5667@gmail.com  
LinkedIn: linkedin.com/in/rohitkumar81  
GitHub: github.com/RohitKumarChaudhari  
