## FunctionDef counter_label(label)
**counter_label**: The function of counter_label is to display a running counter on a label.

**parameters**:
- label: A tkinter label widget where the counter will be displayed.

**Code Description**:
The `counter_label` function defines an inner function `count` that updates the label with the current counter value. It first checks if the `running` flag is set to True. If so, it formats the counter value into a string displaying hours, minutes, and seconds. The label text is then updated with this formatted string. The function uses the `after` method of the label widget to call itself every 1000 milliseconds (1 second) to update the counter. The counter is incremented by 1 in each iteration.

The `count` function is triggered initially to start the counter.

In the calling object `Start`, the `running` flag is set to True, and the `counter_label` function is called with the label parameter. This function call initiates the counter display on the label. Additionally, the states of other buttons (start, stop, reset) are updated to reflect the running state of the counter.

**Note**:
- Ensure the label parameter is a valid tkinter label widget for the function to work correctly.
- The `counter` variable needs to be initialized before calling the `counter_label` function for proper functionality.
### FunctionDef count
**count**: The function of count is to update a display label with the elapsed time in hours, minutes, and seconds.

**parameters**: This Function does not take any parameters.

**Code Description**: The count function checks if a global variable named "running" is True. If it is, the function updates the display label with the elapsed time. If the counter is 0, it displays 'Ready!'. Otherwise, it converts the counter value to a datetime object and formats it as '%H:%M:%S' to display the time. The function then updates the label text with the display value. It uses label.after(1000, count) to delay the function call by 1 second and then calls itself recursively to update the time display continuously. The counter is incremented by 1 after each update.

**Note**: This function relies on the global variables "running", "counter", and "label" to function correctly. Make sure these variables are properly initialized and accessible within the scope of the count function for it to work as intended.
***
## FunctionDef Start(label)
**Start**: The function of Start is to initiate the stopwatch counter and update the states of the start, stop, and reset buttons accordingly.

**parameters**:
- label: A tkinter label widget where the counter will be displayed.

**Code Description**:
The `Start` function sets the global variable `running` to True, which triggers the counter display on the specified label by calling the `counter_label` function with the label parameter. This function also updates the states of the start, stop, and reset buttons to reflect the running state of the counter.

In the `counter_label` function, an inner function `count` is defined to update the label with the current counter value. The function checks if the `running` flag is True, formats the counter value into a string displaying hours, minutes, and seconds, and updates the label text with this formatted string. The `after` method of the label widget is used to call the `count` function every 1000 milliseconds to update the counter, with the counter being incremented by 1 in each iteration.

The `count` function is initially triggered to start the counter, and the `Start` function further ensures the proper functioning of the counter and button states.

**Note**:
- Ensure the label parameter is a valid tkinter label widget for the function to work correctly.
- Initialize the `counter` variable before calling the `counter_label` function for the stopwatch to function accurately.
## FunctionDef Stop
**Stop**: The function of Stop is to update the state of certain buttons and set the running variable to False.
**parameters**: This Function does not take any parameters.
**Code Description**: The Stop function updates the state of the start, stop, and reset buttons by setting them to 'normal' or 'disabled'. It also sets the running variable to False, indicating that the stopwatch is not running.
**Note**: This function is essential for controlling the behavior of the stopwatch interface and managing the running state of the stopwatch.
## FunctionDef Reset(label)
**Reset**: The function of Reset is to reset the stopwatch timer to 00:00:00.

**parameters**:
- label: A reference to the label displaying the stopwatch time.

**Code Description**:
The Reset function resets the global counter variable to 0. If the stopwatch is not running when the reset button is pressed, the function disables the reset button and updates the label text to '00:00:00'. If the stopwatch is running, the function only updates the label text to '00:00:00'.

**Note**:
- Ensure to pass the correct label reference to the function for it to update the displayed time correctly.
- The function handles different scenarios based on whether the stopwatch is running or stopped.
