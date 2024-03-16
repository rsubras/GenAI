## FunctionDef get_word
**get_word**: The function of get_word is to retrieve a random word from a list stored in a JSON file and return it in uppercase.

**parameters**: 
- No parameters are required for this function.

**Code Description**: 
The get_word function reads a JSON file named 'words.json' to obtain a list of words. It then selects a random word from the list, converts it to uppercase, and returns the word.

This function is utilized in the main function of the hangman game. In the main function, get_word is called to retrieve a word for the player to guess. If the player chooses to play again, get_word is called again to get a new word for the next round.

**Note**: 
- Ensure that the 'words.json' file exists and contains a valid list of words.
- The returned word is in uppercase format.

**Output Example**: 
If the 'words.json' file contains the following list: {"word_list": ["apple", "banana", "cherry"]}, the get_word function may return "BANANA" as the selected word.
## FunctionDef play(word)
**play**: The function of play is to allow a player to guess letters or the full word in a Hangman game until they either guess the word correctly or run out of tries.

**parameters**:
- word: A string representing the word that the player needs to guess.

**Code Description**:
The `play` function initializes the game by displaying the word with underscores representing each letter, the hangman drawing, and the length of the word. It then enters a loop where the player can guess letters or the full word until they either win by guessing the word correctly or lose by running out of tries. The function handles different scenarios such as correct and incorrect guesses, updating the word display, and displaying the hangman drawing corresponding to the number of remaining tries. At the end of the game, a message is displayed to inform the player whether they won or lost.

The `play` function calls the `display_hangman` function to show the hangman drawing at each step of the game based on the number of remaining tries. Additionally, the `play` function is called by the `main` function to start the game with a randomly selected word and allow the player to play multiple rounds if desired.

**Note**:
- Ensure that user input is validated to prevent errors during the game.
- The game loop continues until the player either wins or loses, providing a clear outcome message in each case.
## FunctionDef display_hangman(tries)
**display_hangman**: The function of display_hangman is to return a specific stage of the hangman drawing based on the number of tries left.

**parameters**:
- tries: An integer representing the number of tries left for the player.

**Code Description**:
The `display_hangman` function takes an integer `tries` as input and returns a specific stage of the hangman drawing stored in the `stages` list based on the number of tries left. The hangman stages are represented as ASCII art and each stage corresponds to a different number of remaining tries. The function retrieves the appropriate hangman stage from the `stages` list based on the `tries` parameter and returns it.

In the calling object `play` in the `hangman.py` file, the `display_hangman` function is used to display the hangman drawing at each step of the game based on the number of remaining tries. It is called within a loop to update the hangman drawing as the player makes guesses and progresses through the game.

**Note**:
- Ensure that the `tries` parameter passed to the `display_hangman` function is within the valid range to prevent index out of bounds errors.
- The ASCII art in the `stages` list represents different stages of the hangman drawing, with each stage corresponding to a specific number of remaining tries.

**Output Example**:
```
                    --------
                    |      |
                    |      0
                    |     \|/
                    |      |
                    |     / \
                    -
```
## FunctionDef main
**main**: The function of main is to control the flow of the Hangman game by retrieving a word, allowing the player to play, and prompting for a new game if desired.

**parameters**:
- No parameters are required for this function.

**Code Description**:
The main function initiates the Hangman game by first obtaining a word using the get_word function. It then proceeds to allow the player to play the game. After each round, the player is prompted to play again by asking for input. If the player chooses to continue, a new word is retrieved using get_word, and the game continues. This loop of playing and asking for a new game continues until the player decides to stop.

The main function serves as the entry point for the Hangman game, orchestrating the gameplay by coordinating the word retrieval, gameplay, and the option to play multiple rounds. It encapsulates the core logic of the game and interacts with the get_word function to provide words for the player to guess.

**Note**:
- Ensure that the player input for playing again is validated to prevent unexpected behavior.
- The main function relies on the get_word function to retrieve random words for the player to guess in each round.
