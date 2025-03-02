# Yelp Business Scraper

## Overview
This Python script is designed to scrape business listings from Yelp. Using Selenium for browsing and BeautifulSoup for parsing, the script extracts business details such as name, website, phone number, location, rating, and review count for a specific business type and location provided by the user. The scraped data is saved into a CSV file for later use.

## Features
- Scrapes business details like name, website, phone number, location, rating, and review count.
- Can scrape multiple pages dynamically from the Yelp website.
- Stores the scraped data in a structured CSV file.
- Includes robust logging to track the scraping process.

## Setup
### Prerequisites
- Python 3.x
- Selenium
- BeautifulSoup
- pandas
- Webdriver Manager
- Google Chrome installed

### Python Libraries Used
- selenium
- beautifulsoup4
- webdriver_manager
- pandas
- re
- time
- random

## Functionality
### User Inputs:
- The script prompts the user to input the following:
- Business type: The type of business you're looking for (e.g., "restaurants", "salons", etc.).
- Location: The location where you want to find businesses (e.g., "New York", "Los Angeles").
- Number of Pages: The number of pages of business listings to scrape from Yelp.

## Web Scraping:
- Selenium is used to simulate web browsing in a headless Chrome browser. It automatically opens the Yelp search results and loads the content dynamically.
- BeautifulSoup is used to parse the page's HTML content and extract relevant business details like:
     - Business Name
     - Website
     - Phone Number
     - Location
     - Rating
     - Review Count

## Pagination:
The script navigates through multiple result pages based on the user's input. For each page, it dynamically loads the content, extracts data, and then moves on to the next page.

## Logging:
- A logger is integrated to keep track of the scraping progress, log any errors, and ensure smooth execution.
- Logs are stored in a file named logs/yelp.log.

## Data Storage:
- All the scraped data is stored in a list and eventually saved as a CSV file.
- The file is named based on the business type and location (e.g., restaurants_New_York.csv).

## Code Breakdown
### Setup and Initialization:
- Selenium WebDriver is used to automate a Chrome browser, which simulates browsing the Yelp website.
- A custom logger is set up to log all the scraping activities in a log file located at logs/yelp.log.

### get_inside_data(item_url, title) Function:
- This function takes a business URL and title as arguments and fetches the business details.
- It extracts the business name, website, phone number, location, rating, and review count for each listing on the page and stores this information in a list (main_list).

### scrape_pages(base_url, num_pages) Function:
- This function iterates through the specified number of pages (provided by the user).
- For each page, it constructs the URL, extracts business links, calls get_inside_data(), and introduces a random delay to avoid detection.

## Main Execution:
- The user provides the business type, location, and number of pages to scrape.
- The script constructs the Yelp search URL, starts scraping data, and saves the collected information into a CSV file.

## Output Format
The output CSV file will contain the following columns:
- Title: The business name.
- Website: The business website URL.
- Phone Number: The contact phone number.
- Location: The business address.
- Rating: The business rating.
- Review Count: The total number of reviews.

## Usage
### Run the Script:
python yelp_scraper.py

### Provide User Inputs:
- Business type (e.g., "restaurants", "salons").
- Location (e.g., "New York", "Chicago").
- Number of pages to scrape.

### Scraping Process:
The script will automatically navigate the Yelp site, scrape the business listings, and save them in a CSV file.

### CSV Output:
The extracted data will be saved in a file named business_type_location.csv, for example, restaurants_New_York.csv.


