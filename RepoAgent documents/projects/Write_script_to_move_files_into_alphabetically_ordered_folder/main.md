## FunctionDef getfoldername(filename)
**getfoldername**: The function of getfoldername is to determine the folder name based on the first character of the filename.

**parameters**:
- filename: A string representing the name of the file.

**Code Description**:
The getfoldername function takes a filename as input and returns a folder name based on the first character of the filename. If the first character is an alphabet, it returns the lowercase of that character. Otherwise, it returns 'misc' as the folder name.

This function is utilized in the project's main.py file in the createfolder function to check if a folder with the determined name already exists before creating a new folder. It is also used in the movetofolder function to move files into folders based on the first character of their filenames.

**Note**:
Ensure that the filenames passed to this function are valid strings.
Make sure to handle exceptions if needed when using this function.

**Output Example**:
- getfoldername('Test.txt') -> 't'
- getfoldername('010.txt') -> 'misc'
## FunctionDef readdirectory
**readdirectory**: The function of readdirectory is to read the filenames in the current directory, append them to a list, and remove the 'main.py' file from the list.

**parameters**: 
- No parameters are passed to this function.

**Code Description**: 
The readdirectory function utilizes the os module to interact with the operating system. It first initializes a global variable called filenames. It then iterates through the files in the current directory using os.listdir() and checks if each item is a file using os.path.isfile(). If the item is a file, it appends the filename to the filenames list. Finally, it removes the 'main.py' file from the filenames list.

**Note**: 
- Ensure that the 'os' module is imported before calling this function.
- This function assumes that the 'main.py' file exists in the current directory and removes it from the list of filenames.
## FunctionDef createfolder
**createfolder**: The function of createfolder is to create folders based on a list of filenames provided.

**parameters**:
- No parameters are directly passed to this function. It utilizes the global variable filenames.

**Code Description**:
The createfolder function iterates through the list of filenames. For each filename, it checks if a folder with the determined name already exists using the getfoldername function. If the folder does not exist, a new folder is created with the determined name. This function is essential for organizing files into alphabetically ordered folders based on the first character of their filenames.

The createfolder function is dependent on the getfoldername function, which determines the folder name based on the first character of the filename. By utilizing this function, createfolder ensures that folders are created and named correctly according to the specified criteria.

**Note**:
- Ensure that the global variable filenames is properly defined and contains valid filenames.
- Handle any exceptions that may arise during the folder creation process.
## FunctionDef movetofolder
**movetofolder**: The function of movetofolder is to move files into alphabetically ordered folders based on the first character of their filenames.

**parameters**:
- None

**Code Description**:
The movetofolder function iterates through a list of filenames and moves each file to a folder determined by the getfoldername function. It constructs the source and destination paths using the current working directory and the folder name obtained from getfoldername. Finally, it uses the shutil.move method to move the files to their respective folders.

This function relies on the global variable 'filenames' to access the list of files to be moved. It also calls the getfoldername function to determine the folder name for each file based on the first character of the filename.

**Note**:
- Ensure that the 'filenames' global variable is properly populated with valid filenames before calling this function.
- Handle exceptions that may arise during the file moving process, such as permission errors or invalid file paths.
