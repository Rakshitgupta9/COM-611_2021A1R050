## Ques: Implement the web scrapping on Amazon website or any shopping site by importing the requests and the Beautiful Soup

# Amazon Product Scraper

This Python script allows you to scrape product information from Amazon product pages. You can extract details such as product title, price, rating, review count, and availability.

## Getting Started

### Prerequisites

Before running the script, make sure you have the following installed:

- Python 3.x
- BeautifulSoup (You can install it via pip: `pip install beautifulsoup4`)
- Requests (You can install it via pip: `pip install requests`)

### Usage

1. Clone this repository to your local machine:

```
git clone https://github.com/your_username/amazon-product-scraper.git
```

2. Navigate to the project directory:

```
cd amazon-product-scraper
```

3. Run the script:

```
python amazon_scraper.py
```

4. Enter the Amazon product URL when prompted.

## Functionality

- `get_title(soup)`: Extracts the product title from the provided BeautifulSoup object.
- `get_price(soup)`: Extracts the product price from the provided BeautifulSoup object.
- `get_rating(soup)`: Extracts the product rating from the provided BeautifulSoup object.
- `get_review_count(soup)`: Extracts the number of user reviews from the provided BeautifulSoup object.
- `get_availability(soup)`: Extracts the availability status of the product from the provided BeautifulSoup object.

## Example

```python
from bs4 import BeautifulSoup
import requests
from amazon_scraper import *

```
