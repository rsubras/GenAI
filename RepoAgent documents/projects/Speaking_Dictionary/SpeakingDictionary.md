## ClassDef Speak
**Speak**: The function of Speak is to speak out the provided audio using the pyttsx3 library.

**attributes**: 
- audio: The audio input that needs to be spoken out.

**Code Description**: 
The Speak class contains a method called SpeakWord, which initializes the pyttsx3 engine with 'sapi5' as the speech API. It then retrieves the available voices and sets the first voice as the active voice. The method then speaks out the provided audio using the selected voice and waits for the speech to complete before returning.

**Note**: 
- Make sure to have the pyttsx3 library installed to use this Speak class effectively.
- Ensure that the audio input is in a format that can be spoken out by the pyttsx3 engine.
### FunctionDef SpeakWord(self, audio)
**SpeakWord**: The function of SpeakWord is to speak the provided audio using the pyttsx3 library.

**parameters**:
- audio: The text or speech input that needs to be spoken out loud.

**Code Description**:
The SpeakWord function initializes a pyttsx3 speech engine using the 'sapi5' driver. It then retrieves the available voices and sets the engine to use the first voice in the list. After setting the voice, the function uses the say method to speak the provided audio input and then runs the engine to wait until the speech is completed.

**Note**:
- Ensure that the pyttsx3 library is installed in the environment where this function is being used.
- Make sure that the 'sapi5' driver is compatible with the system where the function is executed to enable speech synthesis.
***
