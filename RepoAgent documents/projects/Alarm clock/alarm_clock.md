## FunctionDef Threading
**Threading**: The function of Threading is to create a new thread that executes the `alarm` function concurrently.

**parameters**:
- No parameters are passed to this function.

**Code Description**:
The `Threading` function initializes a new thread `t1` using the `Thread` class from the `threading` module. This thread is then started using the `start` method. By doing this, the `alarm` function is executed concurrently in a separate thread while the main program continues to run.

The `Threading` function is essential for running the `alarm` function independently without blocking the main program's execution. It enables the alarm functionality to continuously check the current time against the set alarm time without affecting other operations in the program.

**Note**:
- Ensure that the necessary imports for threading and other modules used in the `alarm` function are included in the main program.
- Be cautious when working with threads to avoid potential race conditions or synchronization issues in the program.
## FunctionDef alarm
**alarm**: The function of alarm is to continuously check the current time against a set alarm time and trigger an alarm when they match.

**parameters**:
- No parameters are passed to this function.

**Code Description**:
The `alarm` function runs an infinite loop where it sets an alarm time based on the values of `hour`, `minute`, and `second` variables. It then compares this set alarm time with the current time every second. If the set alarm time matches the current time, it prints "Time to Wake up" and plays a sound from a file named "sound.wav" using the `winsound` module.

This function utilizes the `time` and `datetime` modules for time-related operations, as well as the `winsound` module for playing sounds. It continuously prints the current time and the set alarm time for monitoring purposes.

**Note**:
- Ensure that the file "sound.wav" exists in the working directory for the sound to be played successfully.
- The function runs in an infinite loop, so it may need to be stopped manually to exit the program.
