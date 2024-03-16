## FunctionDef light_theme
The function of light_theme is to display a digital clock with a light theme.

**parameters**:
- No parameters are passed to this function.

**Code Description**:
The light_theme function creates a frame with a white background to display a digital clock. It initializes a label (lbl_1) with a specific font, background color, and foreground color. The time function is defined within the light_theme function to update the text of lbl_1 with the current time in the format 'HH:MM:SS AM/PM' every second using the strftime function. This function is then called to start the clock.

**Note**:
- This function relies on the tkinter library for GUI elements, so make sure the necessary library is imported before calling this function.
- The clock will continuously update every second until the program is terminated.
### FunctionDef time
**time**: The function of time is to update the text of a label with the current time in the format 'HH:MM:SS AM/PM'.

**parameters**: 
- No parameters are passed to this function.

**Code Description**: 
The time function retrieves the current time in the 'HH:MM:SS AM/PM' format using the strftime method. It then updates the text property of a label (lbl_1) with the obtained time string. After updating the label, the function schedules itself to be called again after 1000 milliseconds using the after method. This recursive behavior ensures that the label is continuously updated with the current time every second.

**Note**: 
- This function is designed to be used in a GUI application where a clock display needs to be updated in real-time.
- Ensure that the lbl_1 variable is defined and refers to the label widget where the time should be displayed before calling this function.
***
## FunctionDef dark_theme
**dark_theme**: The function of dark_theme is to create a dark-themed digital clock interface with a blue background and white text displaying the current time in hours, minutes, seconds, and AM/PM format.

**parameters**: This Function does not take any parameters.

**Code Description**: The dark_theme function creates a Frame widget with a blue background color, places it within the root window, and then adds a Label widget inside the frame to display the time. The time function is defined within dark_theme to continuously update the displayed time every second using the strftime function from the time module. The Label widget is configured to show the time string and update itself every second by calling the time function recursively using the after method.

**Note**: This code snippet uses the tkinter library for creating GUI elements in Python. The dark_theme function is designed to provide a visually appealing dark theme for a digital clock interface.
### FunctionDef time
**time**: The function of time is to update the text of a label with the current time in the format of hours, minutes, seconds, and AM/PM.

**parameters**: This Function does not take any parameters.

**Code Description**: The time function uses the strftime method to format the current time as '%I:%M:%S %p', which represents hours in 12-hour clock, minutes, seconds, and AM/PM respectively. It then updates the text of a label (lbl_2) with this formatted time. After updating the text, the function uses the after method to call itself after 1000 milliseconds (1 second), creating a continuous loop to update the time display every second.

**Note**: This function is designed to continuously update the time display in a graphical user interface (GUI) application. The after method is used to create a recurring event, ensuring that the time is updated every second.
***
## FunctionDef time
**time**: The function of time is to update a label with the current time in the format of hours, minutes, seconds, and AM/PM.

**parameters**: This Function does not take any parameters.

**Code Description**: The time function uses the strftime method to format the current time as hours, minutes, seconds, and AM/PM. It then updates the text of a label (lbl) with this formatted time. After updating the label, the function schedules itself to run again after 1000 milliseconds (1 second) using the after method. This recursive behavior ensures that the label is continuously updated with the current time every second.

**Note**: This function is designed to be used in a graphical user interface (GUI) application where a clock display needs to be updated in real-time. The recursive nature of the function ensures that the clock display stays up to date.
