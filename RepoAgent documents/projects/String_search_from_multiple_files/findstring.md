## FunctionDef getfiles(path)
**getfiles**: The function of getfiles is to search for a specific text in files within a given directory and its subdirectories.

**parameters**:
- path: The directory path where the search for the text will be performed.

**Code Description**:
The getfiles function starts by changing the current working directory to the specified path. It then lists all the files in that directory. For each file, it checks if it is a directory or a file. If it is a directory, the function recursively calls itself to search for the text in the subdirectory. If it is a file, it opens the file in read mode and checks if the specified text is present in the file. If the text is found, it prints a message indicating the text was found in the file, prints the absolute path of the file, and returns True. If the text is not found in any of the files, it prints a message indicating the text was not found and returns False.

**Note**:
- Ensure that the 'os' module is imported before using this function.
- The function will only search for the exact text match within the files.

**Output Example**:
If the text "example" is found in a file:
example found in 
C:\path\to\file\example.txt

If the text "example" is not found in any file:
example not found!
