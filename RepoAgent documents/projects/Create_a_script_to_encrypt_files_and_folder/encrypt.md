## FunctionDef encrypt_dir(path)
**encrypt_dir**: The function of encrypt_dir is to iterate through files in a directory and encrypt each file using the encrypt_file function.

**parameters**:
- path: A string representing the directory path to be encrypted.

**Code Description**:
The encrypt_dir function iterates through the files in the specified directory using the os.walk method. For each file found, it constructs the full file path, prints a message indicating that the file is being encrypted, and then calls the encrypt_file function to encrypt the file.

The encrypt_dir function relies on the encrypt_file function to perform the actual encryption process. By calling encrypt_file for each file in the directory, encrypt_dir ensures that all files are encrypted using the AES encryption algorithm and saved with a ".bin" extension.

**Note**:
- The encrypt_dir function does not handle subdirectories within the specified directory; it only encrypts files found directly within the specified directory.
- Ensure that the encrypt_file function is correctly implemented and accessible within the project to enable the encryption of files by encrypt_dir.
## FunctionDef encrypt_file(path)
**encrypt_file**: The function of encrypt_file is to encrypt a file using the AES encryption algorithm and save the encrypted content to a new file with a ".bin" extension.

**parameters**:
- path: A string representing the file path of the file to be encrypted.

**Code Description**:
The encrypt_file function first reads the plaintext content of the file specified by the 'path' parameter. It then generates a key of length 16 bytes and an initialization vector (iv) using the AES encryption algorithm. The function encrypts the plaintext using the key and iv, and then writes the ciphertext to a new file with the ".bin" extension.

When called, the encrypt_file function takes the file path as input, reads the content of the file, encrypts it, and saves the encrypted content to a new file. This function is called by the encrypt_dir function in the same project, which iterates through files in a directory and encrypts each file using the encrypt_file function.

**Note**:
- Ensure that the key length is either 16, 24, or 32 bytes for AES encryption.
- The encrypted content is saved in a new file with a ".bin" extension.
