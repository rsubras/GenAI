## FunctionDef banner
**banner**: The function of banner is to print a decorative banner for the InstagramProfile data grabber.

**parameters**: This Function does not take any parameters.

**Code Description**: The banner function is responsible for printing a decorative banner that visually separates different sections of the program. It prints a stylized text that says "InstagramProfile data grabber" enclosed in a series of double quotation marks. This banner function serves as a visual marker to indicate the beginning of the InstagramProfile data grabber process.

In the project, the banner function is called at the beginning of the main function in the main.py file. It helps to visually distinguish the start of the main process of fetching Instagram profile details for a given username. By displaying the banner, it enhances the readability and provides a clear indication of the start of the program execution.

**Note**: The banner function is a simple utility function used for visual representation and does not have any direct impact on the functionality of fetching Instagram profile details. It is designed to improve the overall user experience and readability of the program.
## FunctionDef main(username)
**main**: The function of main is to accept an Instagram username and return a dictionary object containing the profile details.

**parameters**:
- username: A string representing the Instagram username for which the profile details are to be fetched.

**Code Description**:
The main function begins by calling the banner function to print a decorative banner for the InstagramProfile data grabber. It then constructs a URL using the provided username, sends a request to the Instagram page, and extracts relevant profile information such as followers, following, posts, name, and about information. The function then organizes this data into a dictionary object representing the Instagram profile. If the data extraction is successful, the function sets the 'success' key to True; otherwise, it sets it to False.

The main function encapsulates the process of fetching and structuring Instagram profile details, providing a convenient way to retrieve essential information about a user's profile.

**Note**: The main function relies on the banner function to enhance the visual representation of the program's execution. It utilizes web scraping techniques to extract data from the Instagram page based on the provided username. The function is designed to handle both successful and unsuccessful data extraction scenarios, ensuring a structured output format for further processing.

**Output Example**:
{
    'success': True,
    'profile': {
        'name': 'John Doe',
        'profileurl': 'https://www.instagram.com/johndoe/?hl=en',
        'username': 'johndoe',
        'followers': '1M',
        'following': '500',
        'posts': '1000',
        'aboutinfo': 'Photographer and traveler'
    }
}
