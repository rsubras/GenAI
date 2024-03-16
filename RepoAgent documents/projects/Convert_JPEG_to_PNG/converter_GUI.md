## FunctionDef getJPG
**getJPG**: The function of getJPG is to get the location of an image file and open it using the Pillow library.

**parameters**: This Function does not take any parameters.

**Code Description**: The getJPG Function begins by using the filedialog module to prompt the user to select an image file. Once the user selects a file, the function uses the Image module from the Pillow library to open the selected image file and store it in the global variable im1.

**Note**: It is important to ensure that the Pillow library is installed in the Python environment where this code is being executed to avoid any import errors. Additionally, this function relies on user interaction to select an image file, so it may not be suitable for automated processes.
## FunctionDef convertToPNG
**convertToPNG**: The function of convertToPNG is to change the file extension to PNG and save it to the user's preferred location.

**parameters**: 
- No parameters are passed to this function.

**Code Description**: 
The `convertToPNG` function first checks if the global variable `im1` is None. If `im1` is None, it displays an error message using `tk.messagebox.showerror`. If `im1` is not None, the function prompts the user to select a location to save the PNG file using `filedialog.asksaveasfilename` with a default extension of '.png'. Finally, it saves the image `im1` to the selected export file path.

**Note**: 
- Ensure that `im1` is properly initialized before calling this function to avoid errors.
- The user will be prompted to select the location and provide a file name for the PNG file to be saved.
