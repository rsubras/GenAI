## FunctionDef download(url, file_name)
**download**: The function of download is to download a file from a specified URL and save it with a given file name.
**parameters**:
- url: The URL from which the file will be downloaded.
- file_name: The name under which the downloaded file will be saved.
**Code Description**:
The download function uses the requests library to get the content from the provided URL. It then opens a file with the specified file name in binary write mode and writes the content of the response into the file.
**Note**:
Make sure to handle exceptions and errors that may occur during the download process, such as network issues or invalid URLs.
## FunctionDef setup(pathtofile)
**setup**: The function of setup is to set the wallpaper image on a Linux system using the nitrogen command.

**parameters**:
- pathtofile: A string representing the path to the image file to be set as the wallpaper.

**Code Description**:
The setup function takes the path to an image file as a parameter. It then constructs a command using the system function to execute the nitrogen command with the --set-auto flag and the path to the image file. The path to the image file is obtained by joining the current working directory (getcwd()) with the provided pathtofile using the path.join method.

**Note**:
Make sure the path to the image file is correct and accessible by the nitrogen command.
Ensure that the nitrogen command is installed on the Linux system for the function to work properly.
