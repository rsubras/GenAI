## FunctionDef player(x, y)
**player**: The function of player is to display the player image on the screen at the specified coordinates.

**parameters**:
- x: The x-coordinate where the player image will be displayed on the screen.
- y: The y-coordinate where the player image will be displayed on the screen.

**Code Description**:
The player function takes the x and y coordinates as parameters and uses the `blit` method to draw the player image on the screen at the specified position.

**Note**:
- Make sure to have the `screen` object available in the scope where the player function is called.
- Ensure that the `playerimg` variable containing the player image is defined and accessible in the scope of the player function.
## FunctionDef enemy(x, y, i)
**enemy**: The function of enemy is to display an enemy image on the screen at a specified position.

**parameters**:
- x: The x-coordinate of the enemy's position on the screen.
- y: The y-coordinate of the enemy's position on the screen.
- i: The index of the enemy image to be displayed.

**Code Description**:
The enemy function takes three parameters: x, y, and i. It uses the screen.blit method to draw the enemy image specified by the index i at the position (x, y) on the screen.

**Note**:
Ensure that the enemyimg list contains the necessary enemy images corresponding to the indices used in the function to avoid errors in displaying the enemies on the screen.
## FunctionDef fire_bullet(x, y)
**fire_bullet**: The function of fire_bullet is to set the bullet_state to "fire" and display the bullet image on the screen at the specified coordinates.

**parameters**:
- x: The x-coordinate where the bullet will be displayed.
- y: The y-coordinate where the bullet will be displayed.

**Code Description**:
The fire_bullet function takes in the x and y coordinates as parameters. It then updates the global variable bullet_state to "fire" to indicate that a bullet has been fired. Finally, it uses the screen.blit method to display the bullet image at the specified coordinates (x+53, y+10) on the screen.

**Note**:
Ensure that the necessary resources, such as the bullet image (bulletimg) and the screen, are properly initialized before calling the fire_bullet function to avoid any errors in displaying the bullet on the screen.
## FunctionDef is_collision(enemyX, enemyY, playerx, playery)
**is_collision**: The function of is_collision is to determine if a collision has occurred between two objects based on their coordinates.

**parameters**:
- enemyX: The x-coordinate of the enemy object.
- enemyY: The y-coordinate of the enemy object.
- playerx: The x-coordinate of the player object.
- playery: The y-coordinate of the player object.

**Code Description**:
The is_collision function calculates the distance between the enemy object and the player object using the Euclidean distance formula. If the distance is less than 27 units, the function returns True, indicating a collision has occurred. Otherwise, it returns False.

**Note**:
- Ensure that the coordinates provided are numerical values.
- The function assumes a circular collision detection with a radius of 27 units.

**Output Example**:
True
## FunctionDef showscore(x, y)
**showscore**: The function of showscore is to display the score on the screen at the specified coordinates.

**parameters**:
- x: The x-coordinate where the score will be displayed.
- y: The y-coordinate where the score will be displayed.

**Code Description**:
The showscore function takes in the x and y coordinates as parameters. It renders the text "Score : " concatenated with the score value converted to a string using the font. The rendered text is then displayed on the screen at the specified coordinates (x, y) using the blit method.

**Note**:
- Make sure to set the appropriate font before calling the showscore function to ensure the text is displayed correctly.
- Ensure that the screen variable is defined and accessible in the scope where the showscore function is called.
## FunctionDef game_over
**game_over**: The function of game_over is to display a "GAME OVER" message on the screen.

**parameters**: 
- No parameters are passed to this function.

**Code Description**: 
The game_over function uses the render method of the OVER object to create a text surface with the message "GAME OVER" displayed in blue color. This text surface is then blitted onto the screen at coordinates (250, 250) to inform the player that the game is over.

**Note**: 
- This function does not take any parameters, so it is a standalone function that simply displays the "GAME OVER" message on the screen.
- Make sure that the screen variable is defined and accessible before calling this function to ensure that the message is displayed correctly.
## FunctionDef final_score
**final_score**: The function of final_score is to render and display the total score on the screen.

**parameters**:
- No parameters are passed to this function explicitly, but it relies on the value of the variable "score_value" to display the total score.

**Code Description**:
The final_score function first creates a text surface with the total score using the render method from the final object. It concatenates the string "Total Score : " with the value of the score_value variable converted to a string. The text is rendered in green color (0,255,0) with anti-aliasing enabled (True). 

After rendering the text, the function then blits (draws) the finalscore surface onto the screen at the coordinates (280,350) to display the total score to the player.

**Note**:
- Ensure that the variable "score_value" is updated with the correct total score value before calling the final_score function to display the accurate score.
- The position (280,350) where the total score is displayed on the screen can be adjusted as needed for better visibility in the game interface.
## FunctionDef author_name
**author_name**: The function of author_name is to render a copyright text on the screen.

**parameters**:
- No parameters are passed to this function.

**Code Description**:
The `author_name` function uses the `author.render` method to create a text surface with the copyright information "Copyright ©2020 TheKnight All Right Reserved By TheKnight" in green color. This text surface is then displayed on the screen at coordinates (170, 580) using the `screen.blit` method.

**Note**:
- This function does not take any parameters, so the copyright text and its position are hardcoded within the function.
- Ensure that the necessary modules (such as `author` and `screen`) are imported and initialized before calling this function to avoid any errors.
