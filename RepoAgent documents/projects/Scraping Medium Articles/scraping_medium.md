## FunctionDef get_page
**get_page**: The function of get_page is to retrieve and parse the HTML content of a Medium article from a user-provided URL.

**parameters**:
- No explicit parameters are passed to the function.

**Code Description**:
The get_page function first prompts the user to enter the URL of a Medium article. It then validates the URL to ensure it belongs to medium.com. If the URL is valid, it sends a GET request to the URL, raises an exception if the response status is not successful, and parses the HTML content using BeautifulSoup. Finally, it returns the parsed HTML content.

**Note**:
- Ensure the URL provided is a valid Medium article link.
- This function relies on the requests and BeautifulSoup libraries, so make sure they are installed before using the function.

**Output Example**:
A BeautifulSoup object containing the parsed HTML content of the Medium article.
## FunctionDef purify(text)
**purify**: The function of purify is to clean up HTML text by replacing specific tags with newlines and removing all HTML tags.

**parameters**:
- text: A string containing HTML text that needs to be purified.

**Code Description**:
The purify function takes a string of HTML text as input. It replaces specific HTML tags like "<br>", "<br/>", and "<li>" with newline characters. Then, it removes all HTML tags from the text using regular expressions. The cleaned text is returned as the output.

In the project, the purify function is utilized within the collect_text function in the scraping_medium.py file. In the collect_text function, after extracting certain elements from the HTML content, the purify function is called to clean up the text before further processing. This ensures that the extracted text is free from unwanted HTML tags and formatted correctly for display or analysis.

**Note**: It is essential to pass a string containing HTML text to the purify function for proper cleaning. The function is specifically designed to handle HTML tags and may not work as expected with plain text.

**Output Example**:
If the input text is "<p>Hello<br/>World</p>", the purify function will return "Hello\nWorld".
## FunctionDef collect_text(soup)
**collect_text**: The function of collect_text is to extract and format text content from HTML using Beautiful Soup, organizing it into a structured output.

**parameters**:
- soup: A Beautiful Soup object representing the parsed HTML content.

**Code Description**:
The collect_text function first initializes a string variable 'fin' with the URL. It then extracts the title from the HTML head section, formats it, and appends it to 'fin'. Next, it locates the main header of the article and extracts the introduction section by traversing through the previous siblings. The function then appends the introduction and the main header content to 'fin'. Finally, it iterates through the subsequent siblings of the main header, organizing the content into sections separated by headers. The cleaned and structured text is returned as the output.

Within the function, the 'purify' function is called to clean up the extracted HTML text before appending it to the final output. This ensures that the text is free from unwanted HTML tags and formatted correctly for display or further processing.

**Note**: It is crucial to provide a Beautiful Soup object representing the HTML content to the collect_text function for proper extraction and formatting. The function is specifically designed to work with HTML content and may not function correctly with other types of data.

**Output Example**:
If the extracted text includes the title, introduction, and main content sections, the collect_text function will return a structured text output containing these sections in the correct order.
## FunctionDef save_file(fin)
**save_file**: The function of save_file is to save the content passed as an argument into a text file in a specified directory.

**parameters**:
- fin: The content to be saved in the text file.

**Code Description**:
The save_file function first checks if a directory named 'scraped_articles' exists. If the directory does not exist, it creates one. Then, it constructs a file name using the title of the content passed (assuming the title variable is defined in the calling code) and saves the content in a text file with the constructed file name in the 'scraped_articles' directory. The function uses UTF-8 encoding to write the content into the file. Finally, it prints a message indicating the successful saving of the file along with the directory where the file is saved.

**Note**:
- Ensure that the title variable is defined in the calling code to construct the file name correctly.
- The saved file will be in the 'scraped_articles' directory relative to the current working directory.
