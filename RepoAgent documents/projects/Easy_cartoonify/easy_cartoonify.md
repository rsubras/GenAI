## FunctionDef find_the_image(file_name, directory_name)
**find_the_image**: The function of find_the_image is to search for a specific file in a given directory and return its path.

**parameters**:
- file_name: The name of the file to be searched for.
- directory_name: The directory in which the search will be conducted.

**Code Description**:
The function iterates through the directory and its subdirectories using os.walk(). It checks each file name in the directory against the provided file_name. If a match is found, the full path of the file is appended to the files_found list. Finally, the function prints and returns the path of the first file found.

**Note**:
- Ensure that the file_name and directory_name parameters are correctly provided.
- This function returns the path of the first file found matching the file_name.

**Output Example**:
C:\Users\Documents\example.jpg
