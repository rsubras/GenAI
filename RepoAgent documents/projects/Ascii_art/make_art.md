## FunctionDef print_out_ascii(array)
**print_out_ascii**: The function of print_out_ascii is to print the coded image with symbols.
**parameters**:
- array: A 2D array representing the coded image.

**Code Description**:
The print_out_ascii function iterates through each row in the input array and then iterates through each element in the row. It selects a symbol based on the type of coding by using the modulus operator with the length of the symbols_list. The selected symbol is then printed without a newline character using the 'end=""' parameter in the print function. After printing all symbols in a row, a newline character is printed to move to the next row.

**Note**:
- Ensure that the symbols_list is defined and contains the symbols to be used for printing the coded image.
- The input array should be properly formatted to represent the coded image accurately.
## FunctionDef img_to_ascii(image)
**img_to_ascii**: The function of img_to_ascii is to convert an input image into a numeric coded image suitable for ASCII art representation.

**parameters**:
- image: The input image to be converted into ASCII art.

**Code Description**:
The img_to_ascii function takes an input image and resizes it to fit a printing screen by adjusting its dimensions. It then creates a thresholded image based on the input image and a list of predefined thresholds. The function assigns numeric values to each pixel of the resized image based on the threshold applied, resulting in a numeric coded image suitable for ASCII art representation.

**Note**:
- Ensure that the input image is in a format that can be processed by the function.
- Adjust the resizing parameters if the output does not fit the desired screen size.

**Output Example**:
[[0, 1, 0, 2, 1],
 [1, 2, 1, 3, 2],
 [0, 1, 0, 2, 1],
 [2, 3, 2, 4, 3],
 [1, 2, 1, 3, 2]]
