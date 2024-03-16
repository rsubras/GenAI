## FunctionDef clean_str(sentence)
**clean_str**: The function of clean_str is to replace consecutive "#" and "." characters with a single "#" character in a given sentence.

**parameters**:
- sentence: A string representing the input sentence to be cleaned.

**Code Description**:
The clean_str function takes a sentence as input and uses the re.sub method from the re module to substitute any consecutive "#" and "." characters with a single "#" character. The cleaned sentence is then returned.

In the project, the clean_str function is called by the get_text_list function in the same utils.py file. The get_text_list function reads lines from a file, strips each line, and then applies the clean_str function to clean the text before returning a list of cleaned sentences.

**Note**:
It is important to ensure that the input to the clean_str function is a string to avoid any errors.

**Output Example**:
If the input sentence is "Hello...world###", the clean_str function will return "Hello#world#".
## FunctionDef get_text_list(data_path, toy)
**get_text_list**: The function of get_text_list is to read text data from a specified file path, clean each line of text using the clean_str function, and return a list of cleaned sentences based on the specified conditions.

**parameters**:
- data_path: A string representing the path to the data file to be read.
- toy: A boolean flag indicating whether to limit the number of cleaned sentences returned.

**Code Description**:
The get_text_list function opens the file specified by the data_path parameter, reads the lines from the file, strips each line of leading and trailing whitespaces, and then applies the clean_str function to clean each line of text. The function returns a list of cleaned sentences based on the value of the toy parameter. If toy is False, the function returns the first 200,000 cleaned sentences; otherwise, it returns the first 50 cleaned sentences.

The clean_str function is responsible for replacing consecutive "#" and "." characters with a single "#" character in a given sentence. This cleaning operation ensures that the text data is processed uniformly before being returned by the get_text_list function.

The get_text_list function is called by other functions in the project, such as build_dict and build_dataset, to preprocess text data before further processing or analysis.

**Note**:
It is essential to provide a valid file path as the data_path parameter to ensure successful reading of the text data. Additionally, the toy parameter controls the number of cleaned sentences returned by the function.

**Output Example**:
If the input file contains the following lines:
"Hello...world###"
"Python...is...fun###"

The get_text_list function with toy=False will return:
["Hello#world#", "Python#is#fun"]
## FunctionDef build_dict(step, toy)
**build_dict**: The function of build_dict is to create a dictionary mapping words to unique integer indices based on the input text data. It processes the text data to generate a word dictionary, a reversed dictionary, and sets maximum lengths for article and summary text.

**parameters**:
- step: A string indicating the processing step, either "train" or "valid".
- toy: A boolean flag to limit the amount of data processed.

**Code Description**:
The build_dict function first checks the step parameter to determine whether to build a new word dictionary during the training step or load an existing one during the validation step. It utilizes the get_text_list function to retrieve cleaned text data from specified paths. The function then tokenizes the words, creates a word counter, and generates a dictionary mapping words to unique indices. The resulting word dictionary is saved to a file during the training step. Additionally, a reversed dictionary is created to map indices back to words. Finally, the function sets maximum lengths for article and summary text and returns the word dictionary, reversed dictionary, article maximum length, and summary maximum length.

The build_dict function relies on the get_text_list function to preprocess text data efficiently. It ensures that the text data is properly tokenized and indexed for further processing in the project.

**Note**:
Ensure to provide a valid step parameter ("train" or "valid") to specify the processing step correctly. The toy parameter can be used to limit the amount of data processed, especially during testing or debugging phases.

**Output Example**:
{
    "word_dict": {"<padding>": 0, "<unk>": 1, "<s>": 2, "</s>": 3, "word1": 4, "word2": 5, ...},
    "reversed_dict": {0: "<padding>", 1: "<unk>", 2: "<s>", 3: "</s>", 4: "word1", 5: "word2", ...},
    "article_max_len": 50,
    "summary_max_len": 15
}
## FunctionDef build_dataset(step, word_dict, article_max_len, summary_max_len, toy)
**build_dataset**: The function of build_dataset is to preprocess text data by tokenizing, converting words to indices based on a word dictionary, and padding sequences to a specified maximum length for both articles and summaries.

**parameters**:
- step: A string indicating the current step, either "train" or "valid".
- word_dict: A dictionary mapping words to indices, including special tokens like "<unk>" and "<padding>".
- article_max_len: An integer representing the maximum length of an article sequence.
- summary_max_len: An integer representing the maximum length of a summary sequence.
- toy: A boolean flag indicating whether to limit the number of processed sentences.

**Code Description**:
The build_dataset function first reads text data based on the step parameter using the get_text_list function. It then tokenizes the text data, converts words to indices using the provided word dictionary, and pads sequences to match the specified maximum lengths for articles and summaries. If the step is "valid", only the processed articles are returned. Otherwise, both processed articles and summaries are returned.

The function ensures that the input text data is properly preprocessed and formatted for further processing, such as training a model for text summarization tasks. It relies on the get_text_list function to retrieve and clean text data before tokenization and indexing operations.

**Note**:
- Ensure that the word_dict parameter contains necessary special tokens like "<unk>" and "<padding>" for proper word indexing.
- The article_max_len and summary_max_len parameters control the maximum lengths of article and summary sequences, respectively.
- The toy parameter can be used to limit the number of processed sentences for quick testing or debugging purposes.

**Output Example**:
If the processed article and summary sequences are as follows:
Processed articles: [[10, 20, 30, 40, 0, 0, 0], [15, 25, 35, 0, 0, 0, 0]]
Processed summaries: [[5, 10, 15, 0, 0, 0], [8, 12, 16, 20, 0, 0]]
## FunctionDef batch_iter(inputs, outputs, batch_size, num_epochs)
**batch_iter**: The function of batch_iter is to generate batches of input and output data for a specified batch size and number of epochs.

**parameters**:
- inputs: The input data to be divided into batches.
- outputs: The output data corresponding to the input data.
- batch_size: The size of each batch.
- num_epochs: The number of times to iterate through the entire dataset.

**Code Description**:
The `batch_iter` function takes input and output data along with batch size and number of epochs as parameters. It converts the inputs and outputs into numpy arrays and calculates the number of batches per epoch based on the input size and batch size. Then, it iterates through each epoch and generates batches of data by slicing the input and output arrays according to the batch size.

**Note**:
- This function is useful for efficiently iterating through large datasets in machine learning or deep learning models.
- Ensure that the input and output data are compatible and have the same length to avoid errors during batch generation.
## FunctionDef get_init_embedding(reversed_dict, embedding_size)
**get_init_embedding**: The function of get_init_embedding is to load pre-trained Glove word vectors, retrieve word vectors for words in a given dictionary, and assign random vectors to specific tokens if needed.

**parameters**:
- reversed_dict: A dictionary containing words as keys and their corresponding indices as values.
- embedding_size: An integer representing the size of the word embedding vectors.

**Code Description**:
The function first loads pre-trained Glove word vectors from a pickle file. It then iterates through the words in the reversed_dict, retrieves the word vectors from the loaded Glove vectors, and appends them to a list. If a word is not found in the Glove vectors, a zero vector of the specified embedding size is used instead. Finally, random vectors are assigned to specific tokens in the list before returning the list as a NumPy array.

**Note**:
- Ensure that the pickle file containing the Glove word vectors is available at the specified path.
- The function assumes that specific tokens are located at indices 2 and 3 in the word_vec_list.

**Output Example**:
array([[ 0.123,  0.456,  0.789, ...],
       [ 0.987,  0.654,  0.321, ...],
       [ 0.231, -0.456,  0.789, ...],
       ...])
