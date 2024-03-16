## ClassDef PwdDisplay
**PwdDisplay**: The function of PwdDisplay is to display the list of Wi-Fi networks along with their passwords stored on the device.

**attributes**:
- No specific attributes are defined within this Class.

**Code Description**:
The `PwdDisplay` class is designed to manage the display of Wi-Fi network information stored on the device. Upon initialization, the class changes the current directory to the root directory, creates a 'passwords' folder if it does not exist, exports Wi-Fi profiles to XML files in the 'passwords' folder, and then displays the list of Wi-Fi networks along with their passwords. 

The class contains the following methods:
1. `export_xml(self, command=None)`: This method takes a command as input, executes it to export Wi-Fi profiles to XML files, and then removes the temporary file created during the process.
   
2. `file_path(self) -> list[str]`: This method retrieves the file paths of the XML files containing Wi-Fi profile information stored in the 'passwords' folder and returns them as a list of strings.
   
3. `get_ssid_pwd(self) -> list`: This method parses the XML files, extracts the SSID and password information for each Wi-Fi network, and returns a dictionary with SSID as keys and passwords as values.
   
4. `display_password(self)`: This method displays the list of Wi-Fi networks along with their corresponding passwords, prompts the user to choose a network, and then displays the selected network's SSID and password.

The `__del__` method is a destructor that thanks the user for using the tool and deletes the XML files containing Wi-Fi profile information.

**Note**:
- Ensure that the 'netsh' utility is available on the system to execute the Wi-Fi profile export command successfully.
- The user interaction in the `display_password` method requires manual input for selecting a Wi-Fi network.

**Output Example**:
Here is the list of Wi-Fi networks registered on this device:
[1] Network1
[2] Network2
...
Please choose a number: 2
SSID: Network2
Password: Password123
### FunctionDef __init__(self)
**__init__**: The function of __init__ is to initialize the PwdDisplay class by setting the current directory, creating a "passwords" folder if it does not exist, and calling the export_xml and display_password functions.

**parameters**: This function does not take any parameters.

**Code Description**: The __init__ function first changes the current directory to "./" using the os.chdir() method. It then checks if the "passwords" folder exists, and if not, it creates the folder using the os.system() method with the command "mkdir passwords". After setting up the directory structure, the function calls the export_xml method with a specific command to export Wi-Fi profiles with clear text passwords to the "passwords" folder. Finally, it calls the display_password method to interactively display the list of Wi-Fi networks and their passwords to the user.

The __init__ function is an essential part of the PwdDisplay class initialization process. It ensures that the necessary directory structure is in place for storing password information and triggers the export and display of Wi-Fi passwords. By calling the export_xml and display_password functions, it sets up the environment for managing and presenting Wi-Fi password data on a Windows system.

**Note**: It is crucial to ensure that the "passwords" folder is created successfully to store the exported Wi-Fi password information. Additionally, the commands executed within the export_xml method should be valid and safe for execution on the system. The __init__ function plays a key role in initializing the PwdDisplay class and preparing it for handling Wi-Fi password operations effectively.
***
### FunctionDef export_xml(self, command)
**export_xml**: The function of export_xml is to export a specified command output to an XML file.

**parameters**: 
- command: A string representing the command to be executed for exporting the data.

**Code Description**: 
The `export_xml` function takes an optional `command` parameter, which is a string containing the command to be executed. Within the function, the command is split into individual elements, and then the `subprocess.run` function is used to execute the command and write the output to a temporary file named "tmp.txt". Finally, the temporary file is removed after the command execution is completed.

In the context of the project, the `export_xml` function is called within the `__init__` method of the `PwdDisplay` class. When the `PwdDisplay` class is initialized, the current directory is set, a "passwords" folder is created if it does not exist, and then the `export_xml` function is called with a specific command to export Wi-Fi profiles with clear text passwords to the "passwords" folder. This function is part of a process that involves exporting and displaying Wi-Fi passwords on a Windows system.

**Note**: 
It is important to ensure that the `command` parameter passed to the `export_xml` function is a valid command that can be executed using the `subprocess.run` function. Additionally, the temporary file "tmp.txt" is created during the execution of the command and is removed once the command execution is finished.
***
### FunctionDef file_path(self)
**file_path**: The function of file_path is to retrieve a list of file paths for XML files located in the "passwords" directory.

**parameters**: This Function does not take any parameters.

**Code Description**: The file_path Function uses the glob module to search for XML files in the "passwords" directory. It then returns a list of the file paths found. This function is essential for locating the XML files containing WiFi network SSID and password information.

In the project, the file_path Function is called by other methods such as get_ssid_pwd and __del__. In the get_ssid_pwd method, the file_path Function is used to retrieve the file paths of XML files, which are then parsed to extract SSID and password information. In the __del__ method, the file_path Function is utilized to delete the XML files after their use.

**Note**: It is important to ensure that the "passwords" directory exists and contains the necessary XML files for this function to work correctly.

**Output Example**: 
['passwords\wifi1.xml', 'passwords\wifi2.xml', 'passwords\wifi3.xml']
***
### FunctionDef get_ssid_pwd(self)
**get_ssid_pwd**: The function of get_ssid_pwd is to retrieve the SSID and password information from XML files located in the "passwords" directory and return them as a dictionary.

**parameters**: This Function does not take any parameters.

**Code Description**: The get_ssid_pwd function initializes an empty dictionary called ssid_pwd to store the SSID and password pairs. It then iterates over the file paths obtained from the file_path function. For each file path, it parses the XML file to extract the SSID and password information and adds them to the ssid_pwd dictionary. Finally, it returns the dictionary containing the SSID and password pairs.

The get_ssid_pwd function relies on the file_path function to retrieve the file paths of XML files containing WiFi network information. It is called in the display_password method to obtain the SSID and password information for display to the user.

**Note**: Ensure that the "passwords" directory exists and contains the necessary XML files for this function to work correctly.

**Output Example**: 
{'WiFi1': 'password1', 'WiFi2': 'password2', 'WiFi3': 'password3'}
***
### FunctionDef display_password(self)
**display_password**: The function of display_password is to retrieve the SSID and password information from XML files located in the "passwords" directory and display them to the user for selection.

**parameters**:
- This function does not take any parameters.

**Code Description**:
The display_password function initializes an index variable to 1 and calls the get_ssid_pwd function to retrieve the SSID and password information. It then iterates over the retrieved information, displaying the list of Wi-Fi networks registered on the device with their corresponding index numbers. The user is prompted to choose a number, and based on the selection, the function displays the selected SSID and its password.

The function relies on the get_ssid_pwd function to obtain the necessary SSID and password information from XML files. It interacts with the user by displaying the available Wi-Fi networks and prompting for user input to display the selected network's details.

**Note**:
Ensure that the "passwords" directory exists and contains the required XML files for the get_ssid_pwd function to retrieve the SSID and password information correctly. The user input for selecting a Wi-Fi network is expected to be a number corresponding to the displayed index.
***
### FunctionDef __del__(self)
**__del__**: The function of __del__ is to perform cleanup operations when the object is deleted.

**parameters**: This Function does not take any parameters.

**Code Description**: The __del__ function prints a message to thank the user for using the tool and then proceeds to delete the XML files by calling the file_path function to retrieve the file paths and using os.remove to delete each file. This function ensures that the files are removed after their use.

The file_path function is crucial for locating the XML files containing WiFi network SSID and password information. It searches for XML files in the "passwords" directory using the glob module and returns a list of the file paths found. In the get_ssid_pwd method, the file_path function is used to retrieve the file paths of XML files for parsing and extracting SSID and password information. In the __del__ method, the file_path function is utilized to delete the XML files after their use, ensuring proper cleanup.

**Note**: It is essential to have the "passwords" directory with the necessary XML files for the file_path function to work correctly. The __del__ function ensures that the XML files are deleted to maintain system cleanliness and security.
***
