# webscraping_ass
This is a publicly available website with data that could be useful for a future ML project, a Python script was written to scrape the data ethically, following the site’s rules and avoiding sensitive or restricted content. The data was then saved in a structured format (e.g., CSV or JSON) for potential future analysis or ML tasks.



# Book Data Web Scraper

This Python script scrapes book information from [Books to Scrape](https://books.toscrape.com/), a public website specifically designed for practicing web scraping.

## 📌 Features
- Collects:
  - Book Title
  - Price (£)
  - Availability Status
  - Rating (e.g., One, Two, Three)
- Saves data into a CSV file (`books_dataset.csv`)
- Scrapes multiple pages until no more data is found
- Includes a delay between requests to ensure ethical scraping

## 📂 Output Example

| Title | Price (£) | Availability | Rating |
|-------|-----------|--------------|--------|
| A Light in the Attic | 51.77 | In stock | Three |
| Tipping the Velvet | 53.74 | In stock | One |

## ⚙️ Requirements
- Python 3.x
- Install dependencies:
  ```bash
  pip install requests beautifulsoup4
