## FunctionDef run(args)
**run**: The function of run is to execute the process of retrieving point of interest (POI) data from the Baidu Map API based on user-provided parameters and save the results to a specified file path.

**parameters**:
- args: A dictionary containing the necessary parameters for the function to run smoothly, including 'ak' (Baidu Web API Access Key), 'city' (city name), 'poi' (POI name), and 'save' (file save path).

**Code Description**:
The run function initializes variables by extracting values from the 'args' dictionary. It then checks if the specified output directory exists and creates it if not. Subsequently, the function calls the get_baidu_poi function from util.py with the provided parameters (roi_key, city_str, baidu_web_ak, output) to fetch and store the POI data. Upon completion, a message indicating the successful execution of the current area is printed.

The run function serves as the entry point for initiating the POI data retrieval process in the Baidu_POI_crawl project. By utilizing the get_baidu_poi function, it ensures the seamless extraction and storage of relevant POI information based on user-defined inputs.

**Note**:
- Ensure that valid and authorized Baidu Web API Access Key (baidu_ak) is provided in the 'args' dictionary.
- Input accurate values for 'roi_key', 'city_str', 'baidu_ak', and 'output' in the 'args' dictionary to fetch precise POI data and save it to the designated file path.
- The function handles the creation of the output directory and calls the get_baidu_poi function to carry out the data retrieval process efficiently.
