## FunctionDef get_baidu_poi(roi_key, city_str, baidu_ak, output)
**get_baidu_poi**: The function of get_baidu_poi is to retrieve point of interest (POI) data from the Baidu Map API based on the specified POI name and city, and save the results to a text file.

**parameters**:
- roi_key: The name of the point of interest.
- city_str: The name of the city where the POI search will be conducted.
- baidu_ak: The Baidu Web API Access Key.
- output: The file save path where the POI data will be stored.

**Code Description**:
The get_baidu_poi function starts by initializing necessary variables and opening log and output files to store the results. It then enters a loop to make API requests to Baidu Map API, retrieve POI data, and write the relevant information to the output file. The function handles exceptions, logs errors, and continues the process until all relevant data is retrieved.

The function run in the main.py file of the Baidu_POI_crawl project calls get_baidu_poi with the required parameters (roi_key, city_str, baidu_web_ak, output) obtained from the user input. It ensures that the output directory exists, then invokes get_baidu_poi to fetch and save the POI data. Once the process is completed, a completion message is printed.

**Note**:
- Ensure that the Baidu Web API Access Key (baidu_ak) is valid and has the necessary permissions to access the Baidu Map API.
- The function will continuously make API requests until all relevant POI data is retrieved, handling exceptions and logging errors along the way.
- Make sure to provide valid inputs for roi_key, city_str, baidu_ak, and output to fetch accurate POI data and save it to the specified file path.
