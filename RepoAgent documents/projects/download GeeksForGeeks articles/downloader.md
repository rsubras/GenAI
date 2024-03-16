## FunctionDef get_driver
**get_driver**: The function of get_driver is to set up Chrome options for printing and launch a Chrome browser with predefined settings.

**parameters**: 
- None

**Code Description**: 
The get_driver function initializes Chrome options for printing a webpage as a PDF. It sets up preferences for printing, including recent destinations and selected destination ID. Additionally, it configures the browser to enable kiosk printing mode. Finally, it launches a Chrome browser with the specified settings using the ChromeDriverManager.

This function is called by the download_article function in the downloader.py module. In the download_article function, get_driver is used to obtain a browser instance, navigate to a specified URL, execute a print command on the webpage, and then close the browser.

**Note**: 
Developers can utilize this function to automate printing tasks in Chrome browsers with specific settings for PDF generation.

**Output Example**: 
A Chrome browser instance with predefined printing settings is returned.
## FunctionDef download_article(URL)
The function of download_article is to download a webpage as a PDF by printing it using a Chrome browser with predefined settings.

**parameters**: 
- URL: The URL of the webpage to be downloaded as a PDF.

**Code Description**: 
The download_article function initiates a Chrome browser instance by calling the get_driver function. It then navigates to the specified URL, triggers a print command on the webpage to generate a PDF, and finally closes the browser.

The get_driver function is responsible for setting up Chrome options for printing and launching the browser with the required settings. It configures preferences for printing, including recent destinations and selected destination ID, and enables kiosk printing mode. The function returns a Chrome browser instance with the specified settings.

The download_article function utilizes the get_driver function to automate the process of downloading a webpage as a PDF. By executing a print command on the webpage, developers can generate PDFs with specific settings in Chrome browsers.

**Note**: 
Developers can use the download_article function to automate the task of downloading webpages as PDFs with predefined printing settings in Chrome browsers.
