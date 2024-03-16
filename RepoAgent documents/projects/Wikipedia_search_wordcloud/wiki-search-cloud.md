## FunctionDef gen_cloud(topic)
**gen_cloud**: The function of gen_cloud is to generate a word cloud based on the content of a Wikipedia page related to a specified topic.

**parameters**:
- topic: A string representing the topic for which the word cloud will be generated.

**Code Description**:
The gen_cloud function first attempts to retrieve the content of the Wikipedia page related to the specified topic. If successful, it creates a word cloud using the retrieved content. If an error occurs during the content retrieval process, an error message is displayed, and the program exits.

After obtaining the content, the function adds the '==' symbol to the set of stopwords to be excluded from the word cloud. It then initializes a WordCloud object with the specified stopwords, maximum number of words, background color, width, and height parameters. Finally, it generates the word cloud based on the content and returns it.

**Note**:
It is important to ensure that the specified topic is relevant to a Wikipedia page to retrieve meaningful content for the word cloud generation.

**Output Example**:
A WordCloud object representing a visual representation of the most frequent words in the content of the specified Wikipedia page.
## FunctionDef save_cloud(wordcloud)
**save_cloud**: The function of save_cloud is to save the generated word cloud image to a file named "wordcloud.png".

**parameters**:
- wordcloud: Represents the word cloud object that needs to be saved as an image.

**Code Description**:
The save_cloud function takes a word cloud object as input and saves it as an image file named "wordcloud.png" in the current directory. This function utilizes the to_file method of the wordcloud object to save the image.

**Note**:
Make sure to have the necessary permissions to write to the current directory where the image file will be saved.
## FunctionDef show_cloud(wordcloud)
**show_cloud**: The function of show_cloud is to display a word cloud image.

**parameters**:
- wordcloud: A word cloud object to be displayed.

**Code Description**:
The show_cloud function takes a word cloud object as input and displays it as an image using matplotlib's imshow function with interpolation set to 'bilinear'. It then removes the axis from the plot using plt.axis("off") and finally shows the plot using plt.show().

**Note**:
- Make sure to have matplotlib installed to use this function.
- Ensure the word cloud object is properly generated before passing it to the show_cloud function.
