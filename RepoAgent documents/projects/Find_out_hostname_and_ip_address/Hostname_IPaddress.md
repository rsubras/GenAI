## FunctionDef get_hostname_IP
**get_hostname_IP**: The function of get_hostname_IP is to prompt the user to enter a website address (URL), retrieve the hostname and IP address of the entered website, and handle any errors that may occur during the process.

**parameters**:
- No parameters are passed to this function explicitly.

**Code Description**:
The get_hostname_IP function first prompts the user to enter a website address (URL) using the input() function. It then attempts to retrieve the hostname and IP address of the entered website using the socket.gethostbyname() function. If the hostname is valid, it prints the hostname and corresponding IP address. However, if an invalid hostname is entered, a socket.gaierror exception is caught, and an error message indicating the invalid hostname is displayed.

**Note**:
- Ensure that the entered website address (URL) is valid to retrieve the corresponding hostname and IP address.
- Handle any potential errors that may arise when resolving the hostname to an IP address.
