## FunctionDef setup(url)
**setup**: The function of setup is to extract pagination links from a given URL page and call the scrap function for each link to scrape news data.

**parameters**:
- url: The URL of the webpage containing pagination links.

**Code Description**:
The setup function starts by sending a GET request to the provided URL and retrieves the HTML content. It then uses BeautifulSoup to parse the content with the 'lxml' parser. The function locates the 'div' element with the class "pagenation" and finds all 'a' tags that do not have "void" in their href attribute.

After extracting the pagination links, the function iterates over each link, appends the base URL, and calls the scrap function with the constructed URL and index to scrape news data from each page.

The setup function relies on the scrap function to extract news titles, dates, and image sources from the provided URLs. By calling the scrap function for each pagination link, the setup function ensures comprehensive data extraction from multiple pages.

**Note**:
- Ensure the 'div' element with the class "pagenation" exists on the webpage to extract pagination links accurately.
## FunctionDef scrap(url, idx)
**scrap**: The function of scrap is to extract news titles, dates, and image sources from a given URL page and store them in a structured format.

**parameters**:
- url: The URL of the webpage to scrape.
- idx: The index number to identify the page in the submission dictionary.

**Code Description**:
The scrap function starts by sending a GET request to the provided URL and then parses the HTML content using BeautifulSoup with the 'lxml' parser. It then locates the 'ul' element with the id "category" and finds all 'span' and 'img' tags within it. The function extracts the image sources and alt text (news headings) from the 'img' tags, and the text content from the 'span' tags.

After extracting the necessary information, the function appends dictionaries containing the titles, dates, and image sources to the submission dictionary based on the provided index.

The setup function in the moneycontrol_scrapper.py file calls the scrap function for each link extracted from the pagination section of the webpage. It iterates over the links, calls the scrap function with the constructed URL, and passes the index to organize the scraped data.

**Note**:
- Ensure the 'ul' element with the id "category" exists on the webpage to avoid any errors during scraping.
- The submission dictionary should be initialized and accessible within the scope of the scrap function to store the extracted data correctly.
## FunctionDef json_dump(data)
**json_dump**: The function of json_dump is to dump the provided data into a JSON file with a filename based on the current date.

**parameters**:
- data: The data to be dumped into the JSON file.

**Code Description**:
The json_dump function first retrieves the current date in the format "Month Day, Year" using the datetime module. It then creates a new JSON file with a filename that includes the current date and 'moneycontrol_' prefix. Finally, it dumps the provided data into the newly created JSON file using the json module.

**Note**:
Ensure that the data provided to the json_dump function is in a format that can be serialized into JSON.
