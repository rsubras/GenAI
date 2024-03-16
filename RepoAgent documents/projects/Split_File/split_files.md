## ClassDef Split_Files
**Split_Files**: The function of Split_Files is to split a given CSV or TXT file into multiple files based on the specified index.

**attributes**: 
- file_name: Represents the name of the input file.
- directory: Indicates the output directory where the split files will be stored.
- split: Denotes the index at which the file should be split.
- file_extension: Stores the extension of the input file.
- file_number: Tracks the number of split files created.

**Code Description**: 
The Split_Files class is designed to split a CSV or TXT file into smaller files based on the provided index. Upon initialization, the class takes the input file name and split index. It then creates an output directory named "file_split" and determines the file extension based on the input file type.

The split_data method reads the input file, increments the index, and creates a DataFrame to store the split data. It iterates through the input data, appends rows to the split DataFrame, and writes the split files based on the specified index. The split files are saved in the "file_split" directory with a naming convention of "split_fileX.extension", where X represents the file number.

If the input file is a TXT file, the data is saved with space-separated values, while CSV files are saved with comma-separated values. The method ensures that any remaining data after splitting is saved in a separate file.

**Note**: 
- Ensure that the input file is either a CSV or TXT file.
- The split index determines the number of rows in each split file.
- The split files are stored in the "file_split" directory within the project.
### FunctionDef __init__(self, filename, split_number)
**__init__**: The function of __init__ is to initialize the object with the provided filename and split number, set up the output directory, determine the file extension, and set the initial file number.

**parameters**:
- filename: The name of the file to be split.
- split_number: The index at which the file should be split.

**Code Description**:
The __init__ function takes in the filename and split_number as parameters. It initializes the object by assigning the filename to self.file_name, setting the output directory to "file_split", converting the split_number to an integer and assigning it to self.split. 
The function then checks if the "file_split" directory exists. If it does, the directory is removed using shutil.rmtree() to ensure a clean slate. A new "file_split" directory is created using os.mkdir().
Next, it determines the file extension based on whether the filename ends with '.txt' or not. If the file has a '.txt' extension, self.file_extension is set to '.txt'; otherwise, it is set to '.csv'.
Finally, the function initializes the file_number to 1.

**Note**:
- Ensure that the filename and split_number parameters are provided when initializing the object.
- The function assumes that the file extension is either '.txt' or '.csv' based on the filename provided.
***
### FunctionDef split_data(self)
**split_data**: The function of split_data is to split the input csv/txt file according to the provided index.

**parameters**:
- self: The object instance.
  
**Code Description**:
The function first reads the csv/txt file using pandas and adjusts the index. It then initializes an empty DataFrame to store the split data and defines the output file path based on the directory, file number, and file extension. 

A loop iterates over the data, appends rows to the split_frame, and checks if the current index is a multiple of the split value. If true, it saves the split_frame to a new output file based on the file extension. After saving, it resets the split_frame and increments the file number. 

Finally, if there are remaining rows in split_frame after the loop, it saves them to a new output file.

**Note**:
- Ensure the file_name, directory, file_number, file_extension, and split attributes are properly set before calling this function.
- The function overwrites existing split files with the same name.
***
