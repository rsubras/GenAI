## FunctionDef insert(path, txt)
**insert**: The function of insert is to embed a message into an image using the least significant bit steganography technique.
**parameters**:
- path: A string representing the file path of the image.
- txt: A string containing the message to be embedded into the image.

**Code Description**:
The insert function reads an image from the provided file path and calculates the maximum number of bytes that can be embedded based on the image dimensions. It formats the message to include its length and a flag, ensuring it does not exceed the image capacity. The function then reshapes the image data into a one-dimensional array and iterates over the message characters, encoding each character into the image using the encode function. Once the message is embedded, the image is reconstructed, saved with the embedded message, and returned.

In the process, the encode function is utilized to embed data into the image by manipulating the least significant bits of the image blocks. This ensures that the message is hidden within the image data without significantly altering the image appearance. The final image file is saved with the embedded message for later extraction.

**Note**:
- It is essential to ensure that the message to be embedded does not exceed the image capacity to prevent data loss or corruption.
- The use of lossless encoding formats like PNG is recommended to ensure the embedded message can be correctly extracted without loss of information.

**Output Example**:
'example_lsb_embeded.png'
## FunctionDef extract(path)
**extract**: The function of extract is to decode a hidden message from an image using the least significant bits (LSB) technique.

**parameters**:
- path: A string representing the file path of the image from which the message needs to be extracted.

**Code Description**: 
The `extract` function reads an image file using OpenCV, reshapes the image data, and then iterates through the data to extract the hidden message. It first decodes the message length and then proceeds to decode the actual message by applying the LSB technique. The function ensures the correctness of the input image and returns the extracted message.

In the code, the `decode` function from the same module is utilized to decode the hidden message from the image data. By leveraging the `decode` function, the `extract` function successfully retrieves the hidden message embedded in the image using LSB steganography.

**Note**: 
- It is essential to provide the correct file path of the image to extract the hidden message accurately.
- The function assumes that the image contains a hidden message encoded using the LSB technique.

**Output Example**: 
If the extracted message is "Secret message", the function will return the string "Secret message".
## FunctionDef encode(block, data)
**encode**: The function of encode is to embed data into the least significant bits of a block.

**parameters**:
- block: A list representing a block of data where the information will be encoded.
- data: The data to be encoded into the block.

**Code Description**:
The encode function takes a block of data and embeds the provided data into it by manipulating the least significant bits. It first converts the data into its ASCII value using the ord() function. Then, it iterates over each element in the block and performs bitwise operations to encode the data into the block. The data is spread across the block by shifting it by a specific number of bits determined by the index of the element in the block.

In the calling object "insert", the encode function is used to embed a message into an image by dividing the image data into blocks and encoding each character of the message into the corresponding block using the encode function. The message is first formatted to include its length and a flag, and then the data is reshaped to a one-dimensional array for encoding. Finally, the image is reconstructed with the embedded message and saved as a new image file.

**Note**:
- The encode function is crucial for embedding data into images using the least significant bit steganography technique.
- Ensure that the block size is sufficient to accommodate the data to be encoded to prevent data loss.
## FunctionDef decode(block)
**decode**: The function of decode is to extract and decode a message from a given block of data using the least significant bits (LSB) technique.

**parameters**:
- block: A block of data containing the encoded message.

**Code Description**: 
The `decode` function takes a block of data as input and iterates through each element in the block. It extracts the least significant bits of each element and combines them to form the decoded message. The function then returns the decoded message as a character.

In the calling code located in `projects\steganography\lsb.py/extract`, the `decode` function is used to extract a hidden message from an image. The function decodes the message length first and then decodes the actual message by iterating through the data blocks and extracting the hidden information using the LSB technique.

**Note**: 
- The `decode` function assumes that the input data has been encoded using the LSB technique.
- It is crucial to ensure that the correct parameters are passed to the function to decode the message accurately.

**Output Example**: 
If the decoded message is "Hello, World!", the function will return the string "Hello, World!".
