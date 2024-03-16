## FunctionDef getMovieDetails(movieName)
**getMovieDetails**: The function of getMovieDetails is to retrieve detailed information about a movie from IMDB based on the provided movie name.

**parameters**:
- movieName: A string representing the name of the movie for which details are to be fetched.

**Code Description**:
The function starts by defining the base URL of the IMDB website and a query to find the movie title. It then initializes an empty dictionary to store movie details. The function constructs a query using the provided movie name, retrieves the webpage, and parses it using BeautifulSoup. It extracts the first movie that appears in the title section and retrieves the movie link. Subsequently, it fetches the page with movie details, including the year, genres, rating, runtime, and release date. It also obtains information about directors, writers, and cast members. In case writer details are not available, it handles the exception accordingly. Additionally, it makes another request to fetch the plot summary of the movie. Finally, the function returns a dictionary containing all the extracted movie details.

**Note**:
- This function relies on the BeautifulSoup library for web scraping and parsing HTML content.
- It uses requests library to make HTTP requests to fetch web pages.
- The function handles exceptions for cases where certain details are not available on the webpage.

**Output Example**:
{
    'name': 'The Shawshank Redemption',
    'year': '1994',
    'genres': ['Drama'],
    'rating': '9.3',
    'runtime': '142 min',
    'release_date': '14 October 1994',
    'directors': ['Frank Darabont'],
    'writers': ['Stephen King', 'Frank Darabont'],
    'cast': ['Tim Robbins', 'Morgan Freeman'],
    'plot': 'Two imprisoned men bond over a number of years, finding solace and eventual redemption through acts of common decency.'
}
