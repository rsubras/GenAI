## FunctionDef hashFile(filename)
**hashFile**: The function of hashFile is to calculate the MD5 hash value of a file in a memory-efficient manner.

**parameters**:
- filename: The path to the file for which the hash value needs to be calculated.

**Code Description**:
The hashFile function takes a filename as input and calculates the MD5 hash value of the file. It reads the file in blocks of 65536 bytes to prevent memory overflow for large files. The function iterates through each block, updates the hash value, and finally returns the hexadecimal digest of the hash.

**Note**:
It is important to ensure that the file path provided is correct and the file is accessible for reading.

**Output Example**:
'098f6bcd4621d373cade4e832627b4f6'
