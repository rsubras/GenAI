## FunctionDef record_voice
**record_voice**: The function of record_voice is to capture audio input from the user, convert it to text using Google's speech recognition API, and return the recognized phrase.

**parameters**: 
- No parameters are passed to this function.

**Code Description**: 
The record_voice function initializes a speech recognizer object from the speech_recognition library. It then captures audio input from the user using the microphone and adjusts for ambient noise. After capturing the audio, it attempts to recognize the speech using Google's speech recognition service with the English language setting. If the recognition is successful, the recognized phrase is returned. If an UnknownValueError occurs during the recognition process, indicating that the speech could not be understood, a default message is returned.

**Note**: 
- Make sure to have the necessary permissions to access the microphone on the device running this code.
- Ensure that the speech_recognition library is installed in the Python environment where this code is executed.

**Output Example**: 
"I didn't understand what you said"
