## FunctionDef get_url(path, url)
**get_url**: The function of get_url is to open a Chrome browser, navigate to a specified URL, retrieve the HTML content of the page, and return it.

**parameters**:
- path: A string representing the file path to the Chrome WebDriver executable.
- url: A string representing the URL of the webpage to be accessed.

**Code Description**:
The get_url function initializes a Chrome WebDriver using the provided path, opens the specified URL in the browser, waits for the page to load completely, executes a script to retrieve the HTML content of the page, and then returns the HTML content as a string.

**Note**:
- Make sure to have the Chrome WebDriver executable available at the specified path.
- Ensure that the URL provided is accessible and valid.

**Output Example**:
"<html><head>...</head><body>...</body></html>"
## FunctionDef get_img_links(res)
**get_img_links**: The function of get_img_links is to extract all image links from the provided HTML content.

**parameters**:
- res: The HTML content to be parsed and searched for image links.

**Code Description**:
The get_img_links function takes the HTML content as input and uses the BeautifulSoup library to parse the content. It then searches for all img tags with a src attribute, which represents image links, and returns a list of these image links.

**Note**:
Make sure to pass valid HTML content as the input parameter to ensure accurate extraction of image links.

**Output Example**:
[https://example.com/image1.jpg, https://example.com/image2.jpg, ...]
## FunctionDef download_img(img_link, index)
**download_img**: The function of download_img is to download an image from a given URL and save it to a specified output directory with a proper file extension.

**parameters**:
- img_link: A string representing the URL of the image to be downloaded.
- index: An integer indicating the index of the image being downloaded.

**Code Description**:
The function first defines a list of image file extensions including ".jpeg", ".jpg", ".png", and ".gif". It then sets the default extension to ".jpg". Next, it iterates through the list of extensions to find the correct extension for the image by checking if the URL contains any of the specified extensions. Once the extension is determined, it uses the requests library (rq) to get the image data from the provided URL. The function then opens a file in binary write mode at the specified output directory with the index and extension in the filename, and writes the image data to the file.

**Note**:
- Ensure that the 'output' variable is defined and points to the desired output directory before calling this function.
- Handle exceptions appropriately when using this function to download images.
