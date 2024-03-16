## FunctionDef default
**default**: The function of default is to print a welcome message for starting a game of TIC TAC TOE.

**parameters**: 
This Function does not take any parameters.

**Code Description**: 
The default function is a simple function that prints a welcome message to the console when called. The message displayed is "\nWelcome! Let's play TIC TAC TOE!\n".

**Note**: 
This function serves as an initial prompt to welcome players to the TIC TAC TOE game. It does not require any input parameters and is designed to provide a friendly start to the game session.
## FunctionDef rules
**rules**: The function of rules is to display the game board layout and provide instructions on how to play the game.

**parameters**: This Function does not take any parameters.

**Code Description**: The rules() function prints out the layout of a 3 x 3 tic-tac-toe board and provides guidance on how to interact with the board. It displays the board positions numbered from 1 to 9 in a grid format, resembling the right side of a standard keyboard. The function then prompts the player to input a position between 1 and 9 to make a move.

**Note**: When using this function, ensure that the printed board layout is visible to the player to understand the position numbering and make informed moves during the game.
## FunctionDef play
The function of play is to ask the player if they are ready to play the game and return a boolean value based on the player's input.

**parameters**: 
- No parameters are passed to this function.

**Code Description**: 
The play function prompts the player with a question asking if they are ready to play the game. The player is expected to enter either 'Y' for Yes or 'N' for No. The input is then converted to uppercase using the `upper()` method, and the function checks if the input starts with 'Y'. If the input starts with 'Y', the function returns True, indicating that the player is ready to play. Otherwise, it returns False.

**Note**: 
- The function expects the player to enter 'Y' or 'N' in uppercase.
- The function is case-sensitive, so 'Y' and 'N' must be entered in uppercase for accurate results.

**Output Example**: 
Are you ready to play the game? Enter [Y]es or [N]o.
- If the player enters 'Y': 
    - Output: True
- If the player enters 'N': 
    - Output: False
## FunctionDef names
The function of names is to prompt the user to enter the names of two players for a game and return the capitalized names as a tuple.

**parameters**:
- No parameters are passed to this function.

**Code Description**:
The names() function prompts the user to enter the names of two players for a game. It then capitalizes the input names and returns them as a tuple.

**Note**:
- The function assumes that the user will input valid names.
- The function capitalizes the names entered by the user.

**Output Example**:
If the user enters "alice" for player 1 and "bob" for player 2, the function will return ('Alice', 'Bob').
## FunctionDef choice
**choice**: The function of choice is to allow players to choose between 'X' and 'O' for a tic-tac-toe game.

**parameters**: This Function does not take any parameters.

**Code Description**: The choice function prompts the first player to select 'X' or 'O' for their symbol. The function ensures that only 'X' or 'O' can be chosen by the player. If an invalid input is entered, the function will continue to prompt the player until a valid choice is made. Once the first player's choice is determined, the function assigns the opposite symbol to the second player. The function then returns a tuple containing the choices of both players.

**Note**: It is important to ensure that the players only input 'X' or 'O' when prompted to avoid errors in the game.

**Output Example**: 
If player 1 chooses 'X', the function will return ('X', 'O').
## FunctionDef first_player
**first_player**: The function of first_player is to randomly decide who will go first.

**parameters**: 
- No parameters are required for this function.

**Code Description**: 
This function utilizes the `random.choice()` method from the `random` module to randomly select either 0 or 1, representing the players. It then returns the randomly chosen value to determine the first player.

**Note**: 
Ensure that the `random` module is imported before calling this function to avoid any import errors.

**Output Example**: 
1
## FunctionDef display_board(board, avail)
**display_board**: The function of display_board is to print the tic-tac-toe board along with the available positions.

**parameters**:
- board: A list representing the current state of the tic-tac-toe board.
- avail: A list representing the available positions on the tic-tac-toe board.

**Code Description**:
The display_board function takes two parameters, board and avail, and prints the current state of the tic-tac-toe board along with the available positions. It formats and displays the board in a 3x3 grid format with the corresponding positions from the board and avail lists.

The function first prints the top row of the board, displaying the values at positions 7, 8, and 9 from the board list, along with the available positions at the same positions from the avail list. Then, it prints a horizontal line to separate the rows. Next, it prints the middle row of the board with positions 4, 5, and 6, followed by another horizontal line. Finally, it prints the bottom row of the board with positions 1, 2, and 3, along with the available positions at those positions.

This function provides a visual representation of the tic-tac-toe board, allowing players to see the current state of the game and the available positions for their next move.

**Note**:
- Ensure that the board and avail lists are correctly populated before calling the display_board function to display an accurate representation of the game board.
- The function does not return any value but directly prints the board to the console.
## FunctionDef player_choice(board, name, choice)
**player_choice**: The function of player_choice is to prompt the player to choose a position on the board and validate the input to ensure it is within the valid range and not already occupied.

**parameters**:
- board: The game board to select a position on.
- name: The name of the player making the choice.
- choice: The symbol representing the player's choice (e.g., 'X' or 'O').

**Code Description**: 
The player_choice function initializes the position as 0 and enters a while loop to repeatedly prompt the player to input a position until a valid and unoccupied position within the range of 1-9 is entered. It utilizes the space_check function to validate the chosen position on the board. Once a valid position is selected, it returns the chosen position.

This function ensures that the player's move is legitimate and prevents selecting an already occupied position or an invalid position outside the board range. It enhances the player experience by guiding them to make valid moves in the game.

**Note**: Developers can use this function to handle player input and validate their choices in a Tic-tac-toe game scenario, ensuring fair gameplay and adherence to the game rules.

**Output Example**: 
5
## FunctionDef CompAI(board, name, choice)
**CompAI**: The function of CompAI is to determine the best move for the computer player in a tic-tac-toe game based on the current board state and player choices.
**parameters**:
- board: A list representing the current state of the tic-tac-toe board.
- name: A string representing the player's name (not utilized in the function).
- choice: A character ('X' or 'O') representing the player's choice.

**Code Description**:
The CompAI function first identifies available positions on the board where a move can be made. It then iterates through possible moves for both the computer player and the opponent to determine potential winning moves or moves to block the opponent from winning. The function creates a copy of the board for each move to analyze the outcome. If a winning move is found, the function returns the position to make that move. Otherwise, it prioritizes corners, the center, and edges as the next move options.

The function utilizes the win_check function to determine winning patterns on the board and the selectRandom function to choose random positions when necessary.

**Note**:
- Ensure the board list is not empty when calling this function.
- The name parameter is not utilized within the function and can be any string value.
- The function does not modify the original board; it operates on a copy of the board to analyze moves.

**Output Example**:
3
## FunctionDef selectRandom(board)
**selectRandom**: The function of selectRandom is to randomly select an element from a given list.

**parameters**:
- board: A list representing the game board.

**Code Description**:
The selectRandom function first imports the random module to generate random numbers. It then determines the length of the board list. Next, it selects a random index within the range of the board list length and returns the element at that index.

In the calling object CompAI, the selectRandom function is used to choose a random position from a list of possible moves. If there are open corners available, the function selects a random corner position. If the center position (5) is available, it is chosen. Otherwise, a random edge position is selected.

**Note**:
- This function is dependent on the random module for generating random numbers.
- It is crucial to ensure that the board list is not empty when calling this function.

**Output Example**:
If the board list is [0, 'X', 'O', 'X', 'O', 'X', 'O', 'X', 'O'], the selectRandom function may return 'O' as the randomly selected element.
## FunctionDef place_marker(board, avail, choice, position)
**place_marker**: The function of place_marker is to mark or replace a specific position on the board list with a given choice.

**parameters**:
- board: The list representing the game board.
- avail: The list of available positions on the board.
- choice: The marker (X or O) to be placed on the board.
- position: The position on the board where the marker will be placed.

**Code Description**:
The place_marker function takes four parameters: board, avail, choice, and position. It updates the board list by placing the specified choice (marker) at the given position. Additionally, it updates the avail list by marking the position as ' ' (empty) after placing the marker on the board.

**Note**:
- Ensure that the position provided is within the range of the board list to avoid index out of range errors.
- After calling this function, the board and avail lists will be updated with the new marker at the specified position.
## FunctionDef space_check(board, position)
**space_check**: The function of space_check is to check whether a given position on the board is empty or occupied.
**parameters**:
- board: The game board to check the position on.
- position: The position on the board to be checked.

**Code Description**: 
The space_check function takes in a game board and a position as parameters. It checks if the position on the board is empty by comparing the value at that position with a space character (' '). If the position is empty, the function returns True, indicating that the position is available for a move.

This function is utilized in other parts of the Tic-tac-toe game project. For example, in the player_choice function, space_check is used to ensure that the player's chosen position is valid and not already occupied before making a move. Similarly, in the full_board_check function, space_check is used to determine if the board is full, indicating a draw in the game.

**Note**: Developers can use this function to validate positions on the game board before making moves to ensure the game's integrity.

**Output Example**: 
True
## FunctionDef full_board_check(board)
**full_board_check**: The function of full_board_check is to check if the game board is full, indicating a draw in the game.
**parameters**:
- board: The game board to be checked for fullness.

**Code Description**: 
The full_board_check function iterates through the positions on the board to determine if any position is empty. If all positions are filled, the function returns True, indicating that the board is full and the game is a draw. This function relies on the space_check function to verify if a specific position on the board is empty or occupied.

The full_board_check function plays a crucial role in the game logic by determining the game's outcome when all positions on the board are occupied. It ensures that the game can correctly identify a draw scenario based on the board's status.

**Note**: Developers can utilize this function to implement the draw condition in a Tic-tac-toe game by checking if the board is full and no player has won.

**Output Example**: 
True
## FunctionDef win_check(board, choice)
**win_check**: The function of win_check is to determine if a player has won the tic-tac-toe game based on the current board state and player's choice.

**parameters**:
- board: A list representing the current state of the tic-tac-toe board.
- choice: A character ('X' or 'O') representing the player's choice.

**Code Description**:
The win_check function checks the board for winning patterns in tic-tac-toe, including horizontal, vertical, and diagonal patterns. It returns True if any of these patterns are found for the specified player's choice, indicating a win.

In the calling object CompAI, the win_check function is used to determine potential winning moves for the computer player or to block the opponent's potential winning moves. The function iterates through possible moves, creates a copy of the board for each move, and checks if the move results in a win using the win_check function. If a winning move is found, the function returns the position to make that move. Otherwise, it prioritizes corners, center, and edges as the next move options.

**Note**:
- The board parameter should be a list with index positions representing the tic-tac-toe board. Index 0 is not used for gameplay.
- The choice parameter should be either 'X' or 'O' to represent the player's move.
- The win_check function does not modify the original board; it operates on a copy of the board to check for winning patterns.

**Output Example**:
True
## FunctionDef delay(mode)
**delay**: The function of delay is to pause the program execution for 2 seconds if the mode parameter is equal to 2.
**parameters**:
· mode: An integer value representing the mode of the delay.
**Code Description**:
The delay function checks if the mode parameter is equal to 2. If the condition is met, the function imports the time module and then pauses the program execution for 2 seconds using the time.sleep() function.
**Note**:
- Ensure that the mode parameter is an integer value to avoid any unexpected behavior.
- This function is useful for introducing delays in the program flow, especially in scenarios where timing is crucial.
## FunctionDef replay
**replay**: The function of replay is to prompt the user to input whether they want to play the game again and return a boolean value based on the user's input.

**parameters**: 
- No parameters are passed to this function.

**Code Description**:
The replay function uses the input() function to ask the user whether they want to play the game again. The user is prompted to enter either 'Y' for Yes or 'N' for No. The input is then converted to lowercase using the lower() method, and the startswith() method is used to check if the input starts with 'y'. If the input starts with 'y', the function returns True, indicating that the user wants to play again. Otherwise, it returns False.

**Note**: 
- The user input is case-insensitive due to the use of the lower() method.
- The function expects the user to input either 'Y' or 'N' to determine whether to replay the game.

**Output Example**: 
Do you want to play again? Enter [Y]es or [N]o: 
- User input: 'Y'
- Output: True
