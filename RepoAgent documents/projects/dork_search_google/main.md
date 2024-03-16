## FunctionDef Exploit(dork, total_page)
**Exploit**: The function of Exploit is to search for vulnerabilities in websites by performing a Google search with a specified search query (dork) and number of pages to search through.

**parameters**:
- dork: A string representing the search query to be used in Google search.
- total_page: An integer indicating the total number of pages to search through in Google search results.

**Code Description**:
The Exploit function first sets a user agent for the HTTP request headers. It then converts the total_page parameter to an integer. The function iterates through the Google search results based on the dork and total_page parameters. For each search result URL, it appends a single quote to the end to check for SQL injection vulnerabilities. It sends an HTTP GET request to the website using the requests library with the specified user agent. The function then searches for specific error messages in the website content and prints out any vulnerabilities found along with the vulnerability type.

**Note**:
- This function requires the Google search engine and the requests library to be installed.
- It is important to handle the errors and exceptions that may occur during the execution of this function.
- The function assumes the existence of the 'errors' dictionary and 'googlesearch' module, which are not defined in the provided code snippet.

**Output Example**:
VULN http://www.example.com
Vulnerability Type: SQL Injection
