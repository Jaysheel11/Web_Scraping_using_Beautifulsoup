# Web_Scraping_using_Beautifulsoup
This code scrapes company data from AmbitionBox and creates a DataFrame for analysis.

Import the necessary libraries:

Import the pandas library for working with data frames.
Import BeautifulSoup from the bs4 module for parsing HTML content.
Import the requests library for making HTTP requests.
Create an empty data frame: Create a pandas DataFrame called final to store the scraped company data.

Define an empty list: Initialize an empty list called webpage to store the HTML content of each page.

Loop over the range of page numbers:

Iterate over the range from 0 to 333, representing the page numbers.
Set the headers variable to contain the User-Agent header for the HTTP requests.
Send an HTTP GET request to the AmbitionBox website with the corresponding page number using the requests.get() function.
Retrieve the HTML content of the page using the .text attribute of the response object.
Append the HTML content to the webpage list.
Loop over each page's content:

Iterate over each page_content in the webpage list.
Use BeautifulSoup to parse the HTML content by creating a BeautifulSoup object with the HTML content and the specified parser (html.parser).
Use soup.find_all() to find all the <div> elements with the class name 'company-content-wrapper'.
Initialize empty lists for each attribute of interest: name, rating, reviews, ctype, hq, old, and employees.
Extract information for each company:

Iterate over each i (company element) in the company list.
Use .find() or .find_all() on the i element to extract specific information (company name, rating, reviews, etc.) and append them to their respective lists (name, rating, reviews, etc.).
Handle cases where the number of infoEntity elements is insufficient by appending empty strings to the lists.
Create a dictionary and a DataFrame:

Create a dictionary d with keys corresponding to the attribute names (name, rating, reviews, etc.) and values corresponding to the respective lists.
Create a DataFrame df using the dictionary d.
Append the DataFrame df to the final DataFrame.
Print or further process the final DataFrame: At this point, the final DataFrame contains the scraped company data. You can print it or perform additional data processing or analysis as needed.

By following these steps, the code scrapes company data from multiple pages on the AmbitionBox website and stores it in a pandas DataFrame for further use or analysis.
