## FunctionDef sql(sqlstr)
**sql**: The function of sql is to execute SQL queries and return the results.

**parameters**:
- sqlstr: A string representing the SQL query to be executed.

**Code Description**:
The `sql` function establishes a connection to a MySQL database using the provided credentials from the configuration file. It then creates a cursor to execute the SQL query passed as a parameter. The function fetches all the records resulting from the query, closes the cursor and connection, and finally returns the fetched results.

In the project, the `read_mysql_to_csv` function in the `export_mysql_data_to_csv.py` file calls the `sql` function to retrieve data from the database based on the SQL query specified in the configuration file. The retrieved data is then written to a CSV file.

**Note**:
It is essential to ensure that the SQL query passed to the `sql` function is valid and follows the syntax rules of the MySQL database to avoid errors.

**Output Example**:
Assuming the SQL query retrieves two records with three columns each:
[(value1, value2, value3), (value4, value5, value6)]
## FunctionDef read_mysql_to_csv(filename)
**read_mysql_to_csv**: The function of read_mysql_to_csv is to retrieve data from a MySQL database based on a specified SQL query and write the results to a CSV file.

**parameters**:
- filename: A string representing the name of the CSV file to write the data into.

**Code Description**:
The `read_mysql_to_csv` function opens a CSV file in write mode with UTF-8 encoding using the provided filename. It then calls the `sql` function to execute the SQL query specified in the configuration file. The results obtained from the query are iterated over, and each result is written as a row in the CSV file.

The `sql` function establishes a connection to a MySQL database, executes the SQL query, fetches all the records, and returns the results. This function is crucial for retrieving data from the database.

**Note**:
Ensure that the SQL query passed to the `sql` function is valid and adheres to the MySQL syntax rules to prevent any errors in data retrieval and CSV file writing.
## FunctionDef upload_file_robots(filename)
**upload_file_robots**: The function of upload_file_robots is to upload a file to a specified URL and return the media ID of the uploaded file.

**parameters**:
- filename: A string representing the path to the file to be uploaded.

**Code Description**:
The upload_file_robots function first constructs a URL using the wecom_key to upload the file. It then prepares the file data to be posted as JSON. The function sends a POST request to the constructed URL with the file data. Upon receiving a response, it converts the response to JSON format and extracts the media ID from the response. Finally, the function returns the media ID.

**Note**:
- Ensure that the wecom_key variable is defined and accessible in the scope where the function is called.
- Make sure the file specified by the filename parameter exists and is accessible for reading.

**Output Example**:
"media_id": "1234567890"
## FunctionDef send_file_robots(media_id)
**send_file_robots**: The function of send_file_robots is to send a file to a specified destination using a webhook.

**parameters**:
- media_id: The media ID of the file to be sent.

**Code Description**:
The send_file_robots function constructs a URL for WeCom API using the provided key, prepares the file data in JSON format with the given media ID, and then sends a POST request to the constructed URL with the JSON data. The function returns the response object from the POST request.

**Note**:
Ensure that the media_id parameter is a valid media ID for the file to be sent.

**Output Example**:
{
    'status_code': 200,
    'message': 'File sent successfully'
}
