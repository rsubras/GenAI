## FunctionDef extract(zip_file)
**extract**: The function of extract is to unzip a given .zip file and save the contents in the current working directory.

**parameters**:
- zip_file: A string representing the path to the .zip file that needs to be extracted.

**Code Description**:
The extract function takes a .zip file as input, extracts its contents, and saves them in a new directory created in the current working directory. It first checks if the provided file is a .zip file by verifying if the file name ends with ".zip". If it is a .zip file, the function proceeds to unzip the file using the zipfile module. The extracted contents are saved in a new directory with the same name as the original .zip file in the current working directory.

**Note**:
- Make sure to provide the correct path to the .zip file when calling the extract function.
- The extracted contents will be saved in a new directory created in the current working directory.
