# Readme.me Write-up: Product Price Comparison Using Web Scraping

This is a simple Python script that demonstrates how to use web scraping to compare prices of products based on a list of keywords. The script utilizes the `requests` library to send HTTP requests and retrieve the HTML content of a webpage, and the `BeautifulSoup` library to parse and extract relevant information from the HTML.

## Requirements

To run this script, you need to have the following libraries installed:

- `requests`: You can install it using `pip install requests`.
- `beautifulsoup4`: You can install it using `pip install beautifulsoup4`.

## How to Use

1. Save the script in a Python file, for example, `product_price_comparison.py`.
2. Create a text file named `keywords.txt` and enter the keywords for the products you want to compare. Each keyword should be on a separate line.
3. Run the script using a Python interpreter or an IDE.

## Function: `search_products`

The `search_products` function searches for a product using a keyword and returns the search results. It takes a keyword as input and performs the following steps:

1. Replace spaces in the keyword with the `+` symbol to create a search query.
2. Send an HTTP GET request to the example.com website with the search query.
3. Parse the HTML content of the response using `BeautifulSoup`.
4. Find all the `<div>` elements with the class `product`, which represent the search results.
5. Return the search results as a list of BeautifulSoup objects.

## Function: `compare_prices`

The `compare_prices` function compares the prices of products based on a list of keywords and returns the lowest price. It takes a list of keywords as input and performs the following steps:

1. Iterate over each keyword in the list.
2. Call the `search_products` function to get the search results for the keyword.
3. Iterate over each search result and extract the price from the HTML using BeautifulSoup.
4. Convert the price to a floating-point number and append it to the `prices` list.
5. Find the lowest price from the `prices` list using the `min` function.
6. Return the lowest price.

## Example Usage

The script demonstrates an example usage by finding the lowest price among the products corresponding to the keywords in the `keywords.txt` file. Here's how it works:

1. Open the `keywords.txt` file and read its contents, splitting the lines to create a list of keywords.
2. Call the `compare_prices` function with the list of keywords.
3. Print the lowest price.

```python
# Read keywords from a text file
with open('keywords.txt', 'r') as file:
    keywords = file.read().splitlines()

# Example usage
lowest_price = compare_prices(keywords)
print(f"The lowest price is ${lowest_price}")
```

You can modify the script to suit your specific needs, such as changing the URL or the HTML elements to search for, based on the structure of the target website.

Please note that web scraping may be subject to legal restrictions and the terms of service of the website you are scraping. Make sure to review and comply with the relevant policies and regulations before using this script on any website.
