## ClassDef ZipBruter
**ZipBruter**: The function of ZipBruter is to perform brute force attacks on zip files using a word list of passwords.

**attributes**:
- file: The path to the target zip file.
- word_list: The path to the word list file containing passwords.
- threads: The number of threads to use for the brute force attack.
- queue: A FIFO queue to manage the distribution of passwords to worker threads.

**Code Description**:
The ZipBruter class is designed to brute force zip files by trying passwords from a word list. Upon initialization, the class takes the file path of the target zip file, the path to the word list file, and the number of threads to use for the attack. It creates a FIFO queue to manage the distribution of passwords to worker threads.

The class includes the following methods:
1. **\_\_init\_\_**: Initializes the ZipBruter object by setting the file, word_list, threads attributes, and creating a queue.
2. **worker**: Listens to the queue, retrieves target passwords, and checks if the zip file can be extracted using the password.
3. **start_workers**: Starts the specified number of worker threads to perform the brute force attack.
4. **main**: The main entry point for the program, starts worker threads, reads passwords from the word list, and distributes them to worker threads for processing.
5. **read_wordlist**: Reads the word list file and yields target passwords for the brute force attack.

The ZipBruter class utilizes multi-threading to improve the efficiency of the brute force attack by distributing the workload among multiple worker threads. It reads passwords from the word list file, attempts to extract the zip file using each password, and prints the password if successful.

**Note**: Ensure that the word list file contains a list of potential passwords to be used in the brute force attack. The number of threads should be chosen carefully to balance performance and system resources.
### FunctionDef __init__(self, file, word_list, threads)
**__init__**: The function of __init__ is to initialize the ZipBruter object with the provided file, word list, and number of threads.

**parameters**:
- file: The file to be brute-forced.
- word_list: The list of words to be used for brute-forcing.
- threads: The number of threads to be used for parallel processing.

**Code Description**:
The __init__ function initializes the ZipBruter object by assigning the provided file, word list, and number of threads to the respective attributes. Additionally, it creates a FIFO (First In, First Out) queue named 'queue' for managing the tasks in a sequential order.

**Note**:
Ensure that the file, word list, and threads are provided correctly when initializing the ZipBruter object to avoid any errors during the brute-forcing process.
***
### FunctionDef worker(self)
**worker**: The function of worker is to listen to a queue, retrieve target passwords from a FIFO queue, and check if the provided zip password is correct.

**parameters**:
- No external parameters are passed explicitly to this function. It relies on the internal state of the object.

**Code Description**:
The worker function continuously listens to a queue to retrieve target passwords. It dequeues a password from the queue, marks the task as done, and then attempts to extract a zip file using the retrieved password. If the password is correct, it prints a message indicating the found password. The function is designed to run in a loop until a None value is encountered in the queue, at which point it breaks out of the loop.

In the try block, the function attempts to extract the contents of a zip file using the provided password. If the password is incorrect or any exception such as RuntimeError or BadZipfile occurs during the extraction process, it is caught and the function continues without interrupting the loop.

**Note**:
- The worker function is intended to be run in a multi-threaded environment, where multiple instances of this function can be executed concurrently to process tasks from the queue efficiently.
- It is crucial to ensure that the queue is properly populated with target passwords before starting the worker threads using the start_workers function to avoid any unexpected behavior.
***
### FunctionDef start_workers(self)
**start_workers**: The function of start_workers is to initiate multiple worker threads to process tasks concurrently.

**parameters**:
- No external parameters are passed explicitly to this function. It relies on the internal state of the object.

**Code Description**:
The start_workers function starts a specified number of worker threads to handle tasks concurrently. It iterates over the number of threads defined in the object's state and initiates a new thread for each by calling the worker function without passing any explicit parameters. This enables parallel processing of tasks by the worker threads.

The worker threads created by start_workers function continuously listen to a queue for target passwords. The worker function retrieves passwords from the queue, attempts to extract a zip file using the retrieved password, and prints a message if the correct password is found. The worker function runs in a loop until it encounters a None value in the queue, at which point it stops processing tasks.

It is important to ensure that the queue is properly populated with target passwords before invoking the start_workers function to ensure efficient processing of tasks by the worker threads.

**Note**:
- The start_workers function is designed to work in conjunction with the worker function to enable multi-threaded processing of tasks efficiently.
- Properly populating the queue with target passwords is crucial for the correct functioning of the worker threads initiated by the start_workers function.
***
### FunctionDef main(self)
**main**: The function of main is the main entry point for the program.
**parameters**:
- No external parameters are passed explicitly to this function. It relies on the internal state of the object.
**Code Description**:
The main function serves as the primary entry point for the program's execution flow. It initiates the worker threads by calling the start_workers function, reads target passwords from a wordlist using the read_wordlist function, and populates a queue with the passwords for processing. Subsequently, it adds None values to the queue to signal the end of processing for each thread. Finally, the main function waits for all threads to finish their tasks by calling queue.join(). This function orchestrates the overall workflow of the program, ensuring efficient handling of tasks in a multi-threaded environment.
**Note**:
- The main function coordinates the execution of worker threads, wordlist reading, and task processing, making it a crucial component of the program's functionality.
***
### FunctionDef read_wordlist(self)
**read_wordlist**: The function of read_wordlist is to read a given wordlist file and yield target passwords.

**parameters**: 
- self: The instance of the class.
  
**Code Description**: 
The read_wordlist function opens the specified wordlist file in read mode and iterates through each line, yielding the stripped version of each line. This allows the caller to retrieve each password from the wordlist file one by one.

In the project, this function is called within the main function of the ZipBruter class. After starting the workers, the main function iterates over the passwords yielded by read_wordlist and puts each password into a queue for processing. Once all passwords are added to the queue, the function adds a None value to the queue for each thread to signal the end of processing. Finally, the main function waits for all threads to finish processing by calling queue.join().

**Note**: 
- Ensure that the word_list attribute of the class instance is set to the correct path of the wordlist file before calling read_wordlist.
- The read_wordlist function is designed to be used with a generator to efficiently handle large wordlists without loading them entirely into memory.
***
