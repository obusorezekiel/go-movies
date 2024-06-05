# Movie API

This project is a simple RESTful API for managing a collection of movies. It allows you to perform basic CRUD (Create, Read, Update, Delete) operations on a movie database. The API is built using Go and the Gorilla Mux router.

## Features

- **Get all movies**: Retrieve a list of all movies in the collection.
- **Get a single movie**: Retrieve details of a specific movie by its ID.
- **Create a new movie**: Add a new movie to the collection.
- **Update a movie**: Update details of an existing movie by its ID.
- **Delete a movie**: Remove a movie from the collection by its ID.

## Installation

1. **Clone the repository**:
    ```sh
    git clone https://github.com/yourusername/movie-api.git
    cd movie-api
    ```

2. **Install dependencies**:
    Make sure you have Go installed on your machine. Then, run:
    ```sh
    go get -u github.com/gorilla/mux
    ```

3. **Run the application**:
    ```sh
    go run main.go
    ```

4. **Access the API**:
    The API will be running on `http://localhost:8000`.

## API Endpoints

### Get All Movies

- **URL**: `/movies`
- **Method**: `GET`
- **Response**: JSON array of all movies

### Get a Single Movie

- **URL**: `/movies/{id}`
- **Method**: `GET`
- **URL Params**: `id=[string]` - The ID of the movie to retrieve
- **Response**: JSON object of the requested movie

### Create a New Movie

- **URL**: `/movies`
- **Method**: `POST`
- **Request Body**: JSON object containing movie details (excluding ID)
- **Response**: JSON object of the created movie

### Update a Movie

- **URL**: `/movies/{id}`
- **Method**: `PUT`
- **URL Params**: `id=[string]` - The ID of the movie to update
- **Request Body**: JSON object containing updated movie details (excluding ID)
- **Response**: JSON object of the updated movie

### Delete a Movie

- **URL**: `/movies/{id}`
- **Method**: `DELETE`
- **URL Params**: `id=[string]` - The ID of the movie to delete
- **Response**: JSON array of remaining movies

## Code Explanation

### Structs

- `Movie`: Represents a movie with fields for ID, ISBN, title, and a pointer to a director.
- `Director`: Represents a director with fields for first name and last name.

### Handlers

- `getMovies`: Retrieves and responds with the list of all movies.
- `getMovie`: Retrieves and responds with a single movie based on the provided ID.
- `createMovie`: Creates a new movie with the provided details and a generated ID, and adds it to the collection.
- `updateMovie`: Updates the details of an existing movie based on the provided ID.
- `deleteMovie`: Deletes a movie from the collection based on the provided ID.

### Main Function

1. **Router setup**: Creates a new Gorilla Mux router.
2. **Initial data**: Adds two sample movies to the `movies` slice.
3. **Route handling**: Sets up routes and associates them with their respective handler functions.
4. **Server startup**: Starts the HTTP server on port 8000.

### Example Data

```go
movies = append(movies, Movie{ID: "1", Isbn: "43890", Title: "Movie One", Director: &Director{Firstname: "John", Lastname: "Doe"}})
movies = append(movies, Movie{ID: "2", Isbn: "43891", Title: "Movie Two", Director: &Director{Firstname: "Peter", Lastname: "Smith"}})
```

These example movies are pre-loaded into the application for initial testing.

## Contributing

Feel free to fork this repository and make improvements. Pull requests are welcome!

## License

This project is open-source and available under the MIT License.

---

This `README.md` provides a comprehensive overview of the project, including setup instructions, API endpoint details, and a brief explanation of the code.