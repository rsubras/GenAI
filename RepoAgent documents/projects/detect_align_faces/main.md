## FunctionDef main(files)
**main**: The function of main is to process a list of image files, detect faces in each image, align the detected faces, and save the aligned faces as new image files.

**parameters**:
- files: A list of file paths to the images to be processed.

**Code Description**: 
The `main` function initializes a face detector and a shape predictor. It then iterates through each image file in the input list. For each image, it reads the file, converts the color space, detects faces using the `detect_align_faces` function, aligns the detected faces, and saves the aligned faces as new image files with indexed filenames.

During the face detection and alignment process, the function utilizes the `detect_align_faces` function to accurately align the detected faces based on the facial landmarks extracted from the images.

**Note**: 
- Ensure that the input image files exist and are accessible.
- The face detector and shape predictor objects should be properly initialized before calling the function.
- Handle any exceptions that may occur during the image processing and face alignment steps.
## FunctionDef detect_align_faces(detector, sp, img)
**detect_align_faces**: The function of detect_align_faces is to detect faces in an image, extract facial landmarks, calculate the alignment parameters, and transform the detected faces accordingly.
**parameters**:
- detector: The face detector object used to detect faces in the image.
- sp: The shape predictor object used to predict facial landmarks.
- img: The input image containing faces to be aligned.

**Code Description**: 
The `detect_align_faces` function first detects faces in the input image using the provided face detector. It then extracts facial landmarks using the shape predictor. By utilizing the extracted landmarks, the function calculates the angle, distance, and scale required to align and transform the detected faces. The aligned faces are stored in a list and returned as the output.

Within the function, the `shape_to_pos` function is called to extract the positions of the left and right eyes from the facial landmarks. These eye positions play a crucial role in determining the alignment parameters for transforming the faces accurately.

**Note**: 
- Ensure that the input image contains detectable faces.
- The face detector and shape predictor objects should be appropriately initialized before calling the function.
- Handle any exceptions that may arise during the face detection and landmark prediction processes.

**Output Example**: 
[array([aligned_face_1]), array([aligned_face_2]), ...]
## FunctionDef shape_to_pos(shape)
**shape_to_pos**: The function of shape_to_pos is to extract the coordinates of specific facial parts from a given shape object.

**parameters**:
- shape: The shape object containing facial landmarks.

**Code Description**: 
The function `shape_to_pos` takes a shape object as input and iterates through its parts to extract the x and y coordinates of each part. It then separates the coordinates of the left and right eye regions based on predefined ranges. Finally, it returns these coordinates as NumPy arrays representing the left and right eye positions.

In the calling function `detect_align_faces`, the `shape_to_pos` function is used to extract the positions of the left and right eyes from the facial landmarks obtained using the `sp` function. These eye positions are further utilized to calculate the angle, distance, and scale for aligning and transforming the detected faces in the image.

**Note**: 
- Ensure that the input shape object contains the necessary facial landmarks.
- The LEFT_EYE_RANGE and RIGHT_EYE_RANGE should be defined before calling the `shape_to_pos` function.
- Make sure to handle any exceptions that may occur during the extraction of coordinates.

**Output Example**: 
(array([[x1_left, y1_left],
       [x2_left, y2_left],
       ...
       [xn_left, yn_left]]), 
 array([[x1_right, y1_right],
       [x2_right, y2_right],
       ...
       [xm_right, ym_right]]))
