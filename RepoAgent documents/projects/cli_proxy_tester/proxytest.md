## FunctionDef add_proxies_to_file(csv_path, proxies)
**add_proxies_to_file**: The function of add_proxies_to_file is to add one or multiple proxies to a CSV file.

**parameters**:
- csv_path: A string representing the file path of the CSV file.
- proxies: A list containing proxy information to be added to the CSV file.

**Code Description**:
The add_proxies_to_file function first checks if the CSV file specified by csv_path exists. If the file does not exist, a new DataFrame is created with columns for proxy_type, proxy_address, and proxy_status. If the file exists, the existing CSV file is loaded into a DataFrame.

Next, the function iterates over the proxies list. For each proxy, it checks if the proxy is already present in the DataFrame based on proxy_type and proxy_address. If the proxy is found, the function updates the proxy_status. If the proxy is not found, it appends the new proxy information to the DataFrame.

After processing all proxies, the function removes any duplicate entries from the DataFrame and writes the updated DataFrame back to the CSV file specified by csv_path.

In the project, this function is called by two other functions: test_single_proxy and test_csv_file. test_single_proxy calls add_proxies_to_file to add the result of testing a single proxy to the CSV file. test_csv_file, on the other hand, retests every proxy in a CSV file and then calls add_proxies_to_file to update the CSV file with the test results.

**Note**:
- Ensure that the csv_path parameter points to a valid CSV file path.
- The proxies list should contain dictionaries with keys 'proxy_type', 'proxy_address', and 'proxy_status' for each proxy entry.
## FunctionDef test_proxy(proxy_type, proxy_address, iptest)
**test_proxy**: The function of test_proxy is to test a given proxy against a specified IP address and determine its functionality.

**parameters**:
- proxy_type: A string representing the type of the proxy (e.g., 'http', 'https').
- proxy_address: A string indicating the address of the proxy.
- iptest: A string representing the IP address to test the proxy against.

**Code Description**:
The test_proxy function begins by logging the testing process for the provided proxy address. It then attempts to test the proxy by sending a request to the specified IP address using the proxy. Depending on the proxy type, either an HTTP or HTTPS request is made. The function handles different scenarios based on the response received:
- If the response is in JSON format, it checks if the IP address in the response matches the proxy address to determine the proxy's functionality.
- If an error occurs during the process, such as an invalid response or a proxy error, the function appropriately sets the proxy status.
Finally, the function logs the status of the proxy and returns a dictionary containing the proxy type, address, and status.

In the project, this function is called by two other functions:
1. test_single_proxy: This function tests an individual proxy by splitting the proxy address into type and address, then calling test_proxy with the extracted values.
2. test_csv_file: This function retests every proxy listed in a CSV file by iterating over the file's rows, calling test_proxy for each proxy, and then updating the CSV file with the results.

**Note**: Ensure that the proxy address is in the correct format (e.g., 'http://address:port' or 'https://address:port') before passing it to the test_proxy function.

**Output Example**:
{'proxy_type': 'https', 'proxy_address': 'example.com:8080', 'proxy_status': 'Proxy functional'}
## FunctionDef test_single_proxy(proxy, iptest, csv_path)
**test_single_proxy**: The function of test_single_proxy is to test an individual proxy and add it to a CSV file.

**parameters**:
- proxy: A string representing the proxy to be tested.
- iptest: A string indicating the IP address to test the proxy against.
- csv_path: A string representing the file path of the CSV file.

**Code Description**:
The test_single_proxy function takes the provided proxy and splits it into proxy_type and proxy_address. It then calls the test_proxy function to test the proxy against the specified IP address. The test result is added to the CSV file using the add_proxies_to_file function.

This function is part of the proxytest module and interacts with the test_proxy function to perform proxy testing. Additionally, it utilizes the add_proxies_to_file function to update the CSV file with the test results.

**Note**:
- Ensure that the csv_path parameter points to a valid CSV file path.
- The proxy parameter should be in the format 'type://address' (e.g., 'http://example.com:8080').
- The iptest parameter should be a valid IP address for testing the proxy.
## FunctionDef test_csv_file(iptest, csv_path)
**test_csv_file**: The function of test_csv_file is to (re)test every proxy in a given CSV file.

**parameters**:
- iptest: A string representing the IP address to test the proxies against.
- csv_path: A string representing the file path of the CSV file containing proxy information.

**Code Description**:
The test_csv_file function first checks if the specified CSV file exists. If the file exists, it reads the CSV file into a DataFrame. Next, it iterates over each proxy in the DataFrame, testing each proxy using the test_proxy function. After testing all proxies, the function calls add_proxies_to_file to update the CSV file with the test results.

This function is part of the proxy testing functionality in the project. It interacts with the add_proxies_to_file function to update the CSV file with the test results of each proxy. Additionally, it utilizes the test_proxy function to perform the actual testing of each proxy listed in the CSV file.

**Note**:
- Ensure that the csv_path parameter points to a valid CSV file path.
- The proxies list should contain dictionaries with keys 'proxy_type', 'proxy_address', and 'proxy_status' for each proxy entry.
## FunctionDef add_from_text_file(iptest, text_path, csv_path)
**add_from_text_file**: The function of add_from_text_file is to add a list of proxies from a text file (line by line).

**parameters**:
- iptest: A string representing the IP address for testing the proxies.
- text_path: A string indicating the file path of the text file containing the list of proxies.
- csv_path: A string representing the file path of the CSV file to which the test results will be added.

**Code Description**:
The add_from_text_file function reads the list of proxies from the specified text file line by line. It then iterates through each proxy, calling the test_single_proxy function to test and add the proxy to the CSV file. If the text file does not exist, a FileNotFoundError is raised.

Within the for loop, each proxy is treated individually, and the test_single_proxy function is utilized to test the proxy against the provided IP address and add the test result to the CSV file.

This function serves as a bridge between the text file containing proxies and the individual proxy testing mechanism provided by the test_single_proxy function.

**Note**:
- Ensure that the text_path and csv_path parameters point to valid file paths.
- The format of each proxy in the text file should be 'type://address' (e.g., 'http://example.com:8080').
- The iptest parameter should be a valid IP address for testing the proxies.
