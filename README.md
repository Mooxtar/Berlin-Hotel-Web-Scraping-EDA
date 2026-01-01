# Berlin Hotel Web Scraping & EDA (Agoda • Booking • Kayak)

A notebook-based project that **scrapes hotel/apartment listings in Berlin** (prices + ratings + metadata), **cleans and merges the data**, and then runs **exploratory analysis** and a simple **interactive accommodation finder**.

> **Note on responsible scraping:** This repository is for educational/data-analysis purposes. Please respect each website’s Terms of Service, robots.txt, and avoid high request rates.

---

## What this project does

- **Scrape listings** (dynamic pages) using **Selenium (Chrome)**  
- **Collect hotel details** such as:
  - name, address / location
  - stars, rating, number of ratings
  - total price and price per night
  - distance to city centre
  - description + image URLs (when available)
  - `source` (Agoda / Booking / Kayak)
- **Clean + preprocess** the scraped results
- **Save datasets to CSV**
- **EDA + visualization** (price/rating/stars relationships, distributions, etc.)
- **Interactive finder** (filter accommodations by user preferences)

---

## Data sources

The notebook contains scraping flows for:
- **Agoda** search results + detail pages
- **Booking.com** data loading/structuring (CSV workflow)
- **Kayak** search results + detail pages

Because these sites change often, selectors or page structure may require small updates over time.

---

## Outputs

During a typical run, the notebook generates CSV files such as:

- `output_agora_berlin.csv` — Agoda scrape (after preprocessing)  
- `kayak_hotels_berlin_final.csv` — Kayak scrape  
- `Combined.csv` — merged dataset across sources (common column order)

**Example run (from this notebook):**
- Agoda scrape collected **98** accommodations; **90** remained after preprocessing/cleaning.

---

## Requirements

### Recommended: Google Colab
The notebook includes cells to set up **headless Chrome + chromedriver** (via apt + downloads) and run Selenium safely in Colab using `pyvirtualdisplay`.

### Local environment (Mac/Linux/Windows)
You need:
- Python **3.9+**
- Google Chrome (or Chromium)
- A compatible **chromedriver** (matching your Chrome version)

Python packages used:
- `selenium`, `selenium-stealth`, `beautifulsoup4`, `requests`
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `pyvirtualdisplay` (mainly for Colab/Linux headless)

---

## How to run

1. Open the notebook:
   - `Berlin_hotel_webscraping_ipynb_.ipynb`

2. Run the setup cells (browser + driver).
   - In Colab, run the provided installation cells (Chrome/driver + packages).

3. Set/adjust the target search URL(s) if needed:
   - City (Berlin), dates, number of adults, currency, etc.

4. Run the scraping pipeline:
   - Scroll handling (for dynamic loading)
   - Pagination (if enabled)
   - Link extraction
   - Detail scraping per accommodation

5. Run preprocessing + EDA:
   - cleaning, type conversions, missing values handling
   - plots and comparisons
   - optional merge across sources into `Combined.csv`

6. Use the interactive finder section to filter results.

---




