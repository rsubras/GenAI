## FunctionDef getPNG
**getPNG**: The function of getPNG is to get the location of a PNG image file and open it using the Pillow library.

**parameters**: 
- No parameters are passed to this function.

**Code Description**: 
The getPNG function first prompts the user to select a PNG file using a file dialog window. Once the user selects a file, the function uses the Image module from the Pillow library to open the selected PNG file. The opened image is stored in the global variable 'img' for further processing.

**Note**: 
It is important to ensure that the Pillow library is installed in the Python environment where this function is being used. Additionally, this function relies on the tkinter module for the file dialog window, so make sure tkinter is available in the Python environment as well.
## FunctionDef convertToICO
**convertToICO**: The function of convertToICO is to convert an image from PNG to ICO format using Pillow library and save it to a user-specified location.

**parameters**:
- No parameters are passed to this function.

**Code Description**:
The function first checks if the global variable `img` is not None. If `img` is None, an error message is displayed using `tk.messagebox.showerror()`. If `img` is not None, the user is prompted to select a location to save the converted file using `tk.filedialog.asksaveasfilename()` with a default extension of '.ico'. The image is then saved to the specified location using `img.save(export_file_path)`. Finally, a success message is displayed using `tk.messagebox.showinfo()`.

**Note**:
- Ensure that the global variable `img` is properly set before calling this function to avoid errors.
- Make sure to have the necessary libraries (Pillow, tkinter) imported before using this function.
