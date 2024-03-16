## FunctionDef Resize_image(size, image)
**Resize_image**: The function of Resize_image is to resize an image to a specified size and save the resized image.

**parameters**:
- size: The dimensions to which the image will be resized.
- image: The path of the image file to be resized.

**Code Description**:
The Resize_image function first checks if the provided image file exists. If the file exists, it opens the image using the Image module, resizes it to the specified dimensions using the thumbnail method with ANTIALIAS quality, and then saves the resized image in a "resize" folder with the original image name appended with ".jpg".

In case of any exceptions during the image processing, the function catches the exception, prints an error message indicating the type of exception that occurred, and the file that caused the error.

**Note**:
- Make sure to provide valid paths for both the image file and the "resize" folder where the resized image will be saved.
- Ensure that the necessary libraries such as os and Image from PIL are imported before calling the Resize_image function.
