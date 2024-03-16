## ClassDef Snake
**Snake**: The function of Snake is to create a snake object in the Snake Game.

**attributes**: 
- body_size: Represents the size of the snake's body parts.
- coordinates: Stores the coordinates of each body part of the snake.
- squares: Contains the graphical representation of each body part on the canvas.

**Code Description**: 
The Snake class initializes the snake object by setting the body size, coordinates, and squares. It creates the initial body parts of the snake by iterating over the range of BODY_PARTS (presumably defined elsewhere) and appending [0, 0] to the coordinates list. Then, for each set of coordinates, it creates a square on the canvas using the tkinter canvas.create_rectangle method with the specified dimensions and color, adding the square to the squares list.

**Note**: 
- Ensure that the canvas variable is defined and accessible within the scope of the Snake class for the squares to be created successfully.
- Make sure that the constants BODY_PARTS, SPACE_SIZE, and SNAKE_COLOR are defined and imported or declared before instantiating the Snake object.
### FunctionDef __init__(self)
**__init__**: The function of __init__ is to initialize the Snake object with body parts, coordinates, and squares.

**parameters**: 
· self: The instance of the class.
  
**Code Description**: 
In this function, the Snake object is initialized with the following attributes:
- body_size: Initialized with the value of BODY_PARTS.
- coordinates: An empty list to store the coordinates of the snake's body parts.
- squares: An empty list to store the graphical representation of each body part on the canvas.

A loop is used to populate the coordinates list with [0, 0] for each body part. Then, another loop iterates over the coordinates list to create a square on the canvas using the create_rectangle method of the canvas object. Each square represents a body part of the snake and is filled with the color defined by SNAKE_COLOR. The tag "snake" is assigned to each square for identification purposes, and the square is added to the squares list.

**Note**: 
- This function is crucial for setting up the initial state of the Snake object in the Snake Game.
- Ensure that the canvas object is defined and accessible within the scope of this function for creating the squares correctly.
***
## ClassDef Food
**Food**: The function of Food is to create a food object at a random location on the canvas for the snake to consume.

**attributes**:
- coordinates: A list containing the x and y coordinates of the food object on the canvas.

**Code Description**:
The Food class initializes by generating random x and y coordinates within the game boundaries. It then creates an oval shape representing the food on the canvas with the specified color. This class provides a crucial element for the snake game by placing food for the snake to eat, triggering score increments and game progression.

In the project, the `next_turn` function is responsible for handling the movement of the snake and interactions with the food object. When the snake's head reaches the coordinates of the food object, the score increases, the food object is removed from the canvas, and a new Food object is created at a different location. This interaction demonstrates the dependency of the game logic on the Food class to manage the game's progression and scoring mechanism.

**Note**:
It's essential to ensure that the Food class is appropriately instantiated and utilized within the game to provide a consistent gameplay experience.
### FunctionDef __init__(self)
**__init__**: The function of __init__ is to initialize the Food object with random coordinates within the game boundaries and create a food item on the canvas.

**parameters**:
- self: Represents the instance of the class.

**Code Description**:
The __init__ function first generates random x and y coordinates within the game grid by using the random.randint() function. The x coordinate is calculated as a random integer between 0 and (GAME_WIDTH / SPACE_SIZE) - 1 multiplied by SPACE_SIZE, ensuring that the food item aligns with the grid. Similarly, the y coordinate is calculated within the game height boundaries.

Next, the function assigns the calculated coordinates to the 'coordinates' attribute of the Food object.

Finally, the function creates a circular food item on the canvas using the canvas.create_oval() method. The oval is drawn with the top-left corner at (x, y) and the bottom-right corner at (x + SPACE_SIZE, y + SPACE_SIZE). The fill color of the oval is set to FOOD_COLOR, and it is tagged as "food" for identification.

**Note**:
It is important to ensure that the SPACE_SIZE, GAME_WIDTH, GAME_HEIGHT, and FOOD_COLOR variables are appropriately defined and accessible within the scope of the Food class for the __init__ function to work correctly.
***
## FunctionDef next_turn(snake, food)
**next_turn**: The function of next_turn is to handle the movement of the snake on the canvas, update its position based on the specified direction, manage interactions with the food object, handle score increments, and trigger game progression.

**parameters**:
- snake: Represents the snake object with its current coordinates and body parts.
- food: Represents the food object with its coordinates on the canvas.

**Code Description**:
The next_turn function first determines the new coordinates for the snake's head based on the current direction of movement. It then updates the snake's position on the canvas by inserting a new square representing the head at the calculated coordinates.

If the snake's head reaches the coordinates of the food object, the function increments the score, updates the score display on the canvas, removes the current food object, and creates a new Food object at a random location. Otherwise, it removes the last element of the snake's body to simulate movement.

The function then checks for collisions using the check_collisions function. If a collision is detected, the game_over function is called to end the game. Otherwise, the function schedules the next turn after a specified time interval to continue the game loop.

The interaction between the next_turn function, the Food class, check_collisions function, and game_over function forms the core gameplay logic of the snake game. The function relies on the Food class to manage food creation, scoring, and game progression, while utilizing the check_collisions function to ensure game boundaries and snake collisions are properly handled.

**Note**:
- Ensure that the snake and food objects are correctly passed to the function for seamless gameplay.
- The function's recursive call within the window.after method ensures continuous gameplay by updating the snake's position and managing game events.
## FunctionDef change_direction(new_direction)
**change_direction**: The function of change_direction is to update the global variable direction based on the new direction input, ensuring that the snake in the game can only change direction to a valid direction that is not opposite to the current direction.

**parameters**:
- new_direction: Represents the new direction input to change the snake's direction in the game.

**Code Description**:
The change_direction function takes a new_direction parameter and checks if the new direction is valid for the snake to change. It first accesses the global variable direction. Then, it compares the new_direction with the current direction to ensure that the snake does not reverse its direction, which would lead to self-collision. If the new_direction is valid, it updates the direction to the new_direction.

**Note**:
It is essential to provide valid input for new_direction ('left', 'right', 'up', 'down') to ensure the snake moves correctly in the game.
## FunctionDef check_collisions(snake)
**check_collisions**: The function of check_collisions is to determine if the snake has collided with the game boundaries or itself.

**parameters**:
- snake: Represents the snake object with its current coordinates.

**Code Description**:
The check_collisions function first retrieves the x and y coordinates of the snake's head. It then checks if the snake has collided with the game boundaries by comparing the x and y coordinates with the game width and height. If a collision with the boundaries is detected, the function returns True.

Next, the function iterates through the snake's body parts starting from the second element to check if the head has collided with any part of the snake's body. If a collision with the body is found, the function returns True.

If no collisions are detected, the function returns False, indicating that the snake is safe.

In the calling code snippet, the check_collisions function is used to determine if the snake has collided with itself or the game boundaries. If a collision is detected, the game_over function is called to end the game. Otherwise, the next_turn function continues the game by updating the snake's position and handling interactions with food.

**Note**:
- Ensure that the snake object passed to the function contains valid coordinates.
- The function assumes a global variable GAME_WIDTH and GAME_HEIGHT are defined to represent the game boundaries.

**Output Example**:
True
## FunctionDef game_over
**game_over**: The function of game_over is to display a "GAME OVER" message in red color at the center of the canvas.

**parameters**: This function does not take any parameters.

**Code Description**: The `game_over` function clears the canvas, then creates a text object displaying "GAME OVER" at the center of the canvas with a red color and a specific font. This function is called when a collision is detected in the game, indicating the end of the game.

In the calling situation, the `game_over` function is invoked within the `next_turn` function. When a collision is detected between the snake and the boundaries or itself, the `check_collisions` function returns true, triggering the `game_over` function. This stops the game and displays the "GAME OVER" message to the player.

**Note**: Ensure that the `canvas` variable is accessible within the scope of the `game_over` function for it to work correctly.
