## FunctionDef countdown(t)
**countdown**: The function of countdown is to display a countdown timer in minutes and seconds until the timer reaches zero.

**parameters**:
- t: Represents the total time in seconds for the countdown timer.

**Code Description**:
The countdown function takes a parameter t, which is the total time in seconds for the countdown. It then enters a while loop that runs until t reaches zero. Inside the loop, the total time t is converted into minutes and seconds using the divmod function. The timer string is formatted to display the minutes and seconds in a 'MM:SS' format. The timer is printed to the console using the print function with the end parameter set to "\r" to overwrite the previous timer display. The function then waits for 1 second using the time.sleep(1) function before decrementing the total time t by 1. Once the countdown reaches zero, the function prints 'Timer completed!' to indicate the end of the countdown.

**Note**:
- Ensure to import the time module before using the countdown function to avoid any NameError.
- The countdown timer will display the time in minutes and seconds until it reaches zero.
