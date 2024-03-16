## FunctionDef insert(path, txt)
**insert**: The function of insert is to embed a text message into the Y-plane of an image using Discrete Cosine Transform (DCT) coefficients for steganography purposes.

**parameters**:
- path: The file path of the image to be processed.
- txt: The text message to be hidden in the image.

**Code Description**:
The insert function reads an image from the specified path and converts it to the YUV color space. It then quantizes the Y-plane into blocks of DCT coefficients. The function iterates through each block and embeds the message data by calling the encode function. After encoding the message, the function reconstructs the image with the hidden data and saves it as a new image file. The use of DCT coefficients allows for data embedding even in compressed image formats like JPEG, making it a robust steganography technique.

The insert function ensures that the message data does not exceed the capacity of the image blocks to prevent message overflow. By utilizing the Y-plane for data embedding, the function maintains the visual quality of the image while hiding the message effectively.

**Note**:
It is crucial to verify that the message data size does not exceed the capacity of the image blocks to avoid potential data loss or corruption.
Ensure that the input image format is compatible with the OpenCV library for successful image processing.

**Output Example**: "image_dct_embedded.jpg"
## FunctionDef encode(blocks, data)
**encode**: The function of encode is to embed data into the DCT coefficients of image blocks using a steganography technique.

**parameters**:
- blocks: A list of DCT coefficient blocks extracted from the image.
- data: The data to be encoded into the image.

**Code Description**:
The encode function takes the input data and converts it to its ASCII value. It then iterates through each block of DCT coefficients and embeds the data bit by bit based on the pixel intensity values of the blocks. The function calculates the maximum and minimum values of the coefficients in each block and adjusts them according to a predefined threshold (ALPHA) to hide the data effectively. If the data bit is 1, the function swaps the maximum and minimum values; otherwise, it keeps them as they are. This process ensures that the data is hidden within the image without significantly altering its visual appearance.

In the project structure, the encode function is called by the insert function in the dct.py file. The insert function reads an image, converts it to the YUV color space, and quantizes the Y-plane into blocks of DCT coefficients. It then calls the encode function to embed the message data into these blocks. Finally, the insert function reconstructs the image with the hidden data and saves it as a new image file.

**Note**:
It is essential to ensure that the data to be encoded does not exceed the capacity of the image blocks to avoid message overflow. The use of the DCT algorithm allows for embedding data even in compressed image formats like JPEG, making it a robust steganography technique.
## FunctionDef decode(blocks)
**decode**: The function of decode is to extract a character from a list of blocks based on specific conditions and return the corresponding character.

**parameters**:
- blocks: A list of blocks containing information used to extract the character.

**Code Description**:
The `decode` function iterates through the blocks and checks a condition for each block. If the condition is met, it performs a bitwise operation to extract a character. The function then returns the character extracted from the blocks.

In the calling object `extract`, the `decode` function is utilized to extract characters from blocks in order to decode a message hidden in an image. The extracted characters are concatenated to form the decoded message.

**Note**: 
- The `decode` function is dependent on the values of LOC_MAX and LOC_MIN in the blocks.
- Ensure that the blocks provided to the `decode` function are structured correctly to avoid errors in character extraction.

**Output Example**:
If the extracted character is 'A', the function will return 'A'.
## FunctionDef extract(path)
**extract**: The function of extract is to decode a hidden message from an image using Discrete Cosine Transform (DCT) and specific decoding techniques.

**parameters**:
- path: A string representing the file path of the image from which the message will be extracted.

**Code Description**:
The `extract` function reads an image from the provided path and converts it to the YUV color space. It then extracts the luminance component (Y) and divides it into 8x8 blocks. Each block undergoes DCT and quantization. The function decodes the message hidden in these blocks by utilizing the `decode` function. The message length is extracted first, followed by the message characters until the end of the message is reached. The extracted message is returned as a string.

The `extract` function relies on the `decode` function to extract characters from the blocks and decode the hidden message within the image. By iterating through the blocks and utilizing the `decode` function, the `extract` function reconstructs the hidden message from the image data.

**Note**:
- Ensure the input image contains a hidden message encoded using the same method to avoid decoding errors.
- The successful extraction of the message depends on the correct implementation of the decoding logic within the `decode` function.

**Output Example**:
If the hidden message extracted from the image is "Hello, World!", the function will return "Hello, World!".
