## FunctionDef shutdown
**shutdown**: The function of shutdown is to initiate a system shutdown or hibernation based on the operating system detected.

**parameters**: This Function does not take any parameters.

**Code Description**: The shutdown function first checks the operating system using the platform.system() method. If the system is identified as Windows, the function executes the command 'shutdown -s' using the os.system() method to initiate a system shutdown. If the system is identified as Linux or macOS (Darwin), the function executes the command 'shutdown -h now' to hibernate the system. If the operating system is not recognized, the function prints "Os not supported!".

**Note**: Ensure that the necessary permissions are granted to execute system shutdown commands. This function may behave differently on different operating systems, so it is essential to test it on the target system.
## FunctionDef restart
**restart**: The function of restart is to restart the device based on the operating system. 
**parameters**: This Function does not take any parameters.
**Code Description**: The restart function first checks the operating system using the platform.system() method. If the operating system is Windows, it executes the command "shutdown -t 0 -r -f" to restart the device immediately. If the operating system is Linux or Darwin (macOS), it executes the command 'reboot now' to restart the device. If the operating system is not recognized, it prints "Os not supported!".
**Note**: Ensure that the necessary permissions are granted to execute the shutdown or reboot commands.
