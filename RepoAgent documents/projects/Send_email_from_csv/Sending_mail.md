## FunctionDef get_credentials(filepath)
**get_credentials**: The function of get_credentials is to read email credentials from a file and return them as a tuple.

**parameters**:
- filepath: A string representing the path to the file containing email credentials.

**Code Description**:
The get_credentials function reads the email address and password from a file named "credentials.txt" and returns them as a tuple. It takes a filepath parameter specifying the location of the credentials file. The function opens the file in read mode, reads the email address and password from the file, and then returns them as a tuple.

In the project structure, get_credentials is called by the send_mail function located in the Sending_mail.py file. In the send_mail function, the email credentials obtained from get_credentials are used to log in to the SMTP server for sending emails.

**Note**:
Ensure that the "credentials.txt" file exists in the specified filepath with email address on the first line and password on the second line.

**Output Example**:
If the contents of "credentials.txt" are:
```
example@gmail.com
password123
```
The output of get_credentials(filepath) would be:
```
("example@gmail.com", "password123")
```
## FunctionDef login(email_address, email_pass, s)
**login**: The function of login is to authenticate the email address and password with the SMTP server to enable sending emails securely.

**parameters**:
- email_address: The email address used for authentication.
- email_pass: The password associated with the email address.
- s: The SMTP server object used for sending emails.

**Code Description**:
The login function initiates the email server connection, starts TLS for security, and then authenticates the email address and password with the server. Once authenticated, it prints "login" to indicate a successful login.

In the project, the login function is called within the send_mail function. In the send_mail function, an SMTP server is created, email credentials are obtained from a file, and then the login function is called with the email address, password, and SMTP server object. This enables the sending of emails securely after successful authentication.

**Note**:
It is essential to ensure that the email address and password provided are correct to successfully authenticate with the SMTP server.
## FunctionDef send_mail
**send_mail**: The function of send_mail is to send emails to multiple recipients listed in a CSV file using the provided SMTP server and email message content.

**parameters**:
- No parameters are directly passed to the send_mail function. However, it internally calls other functions to retrieve email credentials and login to the SMTP server.

**Code Description**:
The send_mail function establishes a connection to the SMTP server hosted at "smtp.gmail.com" on port 587. It then retrieves email credentials by calling the get_credentials function, logs in to the SMTP server using the obtained credentials by calling the login function, and prepares an email message with a subject and body content. The function reads email addresses from a CSV file named "emails.csv", sends the prepared message to each recipient, and prints a confirmation message for each email sent. Finally, it terminates the SMTP session and prints "sent" to indicate the completion of the email sending process.

The send_mail function is dependent on the get_credentials function to obtain email credentials and the login function to authenticate with the SMTP server. By utilizing these functions, send_mail streamlines the process of sending personalized emails to multiple recipients stored in a CSV file.

**Note**:
- Ensure that the "credentials.txt" file exists with the correct email address and password format.
- The CSV file "emails.csv" should contain a list of email addresses to which the messages will be sent.
- Verify the SMTP server settings and network connectivity to ensure successful email delivery.
