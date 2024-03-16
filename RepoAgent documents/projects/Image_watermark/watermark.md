## FunctionDef watermark_photo(input_image_path, watermark_image_path, output_image_path)
**watermark_photo**: The function of watermark_photo is to add a watermark image to a base image and save the result as a new image.

**parameters**:
- input_image_path: The file path of the base image.
- watermark_image_path: The file path of the watermark image.
- output_image_path: The file path where the output image will be saved.

**Code Description**:
The function first opens the base image and the watermark image using the provided file paths. It then resizes the watermark image to a specific size based on the base image dimensions. A new transparent image is created with the same size as the base image. The original image is pasted onto the transparent image, followed by pasting the resized watermark image at a calculated position. The function checks the mode of the base image and converts the transparent image accordingly. Finally, the resulting image is saved at the specified output path with optimization and quality settings.

**Note**:
- Ensure that the input_image_path and watermark_image_path point to valid image files.
- The output_image_path should specify the location and filename for the saved image.

**Output Example**:
Saving output_image_path...
