## ClassDef FrameCapture
**FrameCapture**: The function of FrameCapture is to capture frames from a video file using the OpenCV library.

**attributes**:
- directory: The directory where the captured frames will be stored.
- file_path: The path of the video file to capture frames from.

**Code Description**:
The FrameCapture class is designed to capture frames from a video file. Upon initialization, the class sets up the directory for storing the captured frames and removes any existing content in the directory. The capture_frames method reads the video file frame by frame using the cv2.VideoCapture function from the OpenCV library. Each frame is saved as an image file in the specified directory with a naming convention 'frameX.jpg', where X represents the frame number.

**Note**:
- Make sure to provide a valid file path when initializing the FrameCapture object.
- Ensure that the necessary libraries (OpenCV) are installed before using this class.
- The captured frames will be saved in the 'captured_frames' directory within the project.
### FunctionDef __init__(self, file_path)
**__init__**: The function of __init__ is to initialize the directory where the captured frames will be stored and truncate the directory if it already exists.

**parameters**:
- file_path: The path where the captured frames will be stored.

**Code Description**:
The __init__ function sets the directory to "captured_frames" and assigns the provided file_path to the object's file_path attribute. It then checks if the directory already exists. If it does, the function removes all its contents using shutil.rmtree(). Finally, it creates a new directory named "captured_frames" using os.mkdir().

**Note**:
- Ensure that the file_path parameter is provided with the path where the captured frames should be stored before initializing the object.
***
### FunctionDef capture_frames(self)
**capture_frames**: The function of capture_frames is to capture frames from a provided video file using the openCV library.

**parameters**:
- self: The instance of the class.
- file_path: The path to the video file from which frames are to be captured.
- directory: The directory where the captured frames will be saved.

**Code Description**:
This function starts by creating a cv2 object to capture frames from the video file specified by the file_path parameter. It then initializes variables for frame_number and frame_found. The function enters a while loop where it reads frames from the video using the cv2 object until no more frames are found. For each frame found, it saves the frame as an image in the specified directory with a filename in the format 'frame{frame_number}.jpg'. The frame_number is incremented after each frame is captured.

**Note**:
- Make sure to provide the correct file_path to the video file you want to capture frames from.
- Ensure that the directory where the frames will be saved exists and is accessible for writing.
***
