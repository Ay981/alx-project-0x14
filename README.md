# alx-project-0x14

## API Overview

The MoviesDatabase API provides access to a comprehensive database of movies, TV shows, and related metadata. It allows users to search for titles, retrieve detailed information about movies and TV series, access cast and crew data, and explore trending or popular content. The API is designed for developers building applications that require up-to-date movie and TV information.

## Version

v2 (as per the latest MoviesDatabase API documentation)

## Available Endpoints

- `/titles/search/title` - Search for movies or TV shows by title.
- `/titles/{id}` - Retrieve detailed information about a specific movie or TV show by its unique ID.
- `/titles/popular` - Get a list of currently popular movies or TV shows.
- `/titles/trending` - Fetch trending movies or TV shows.
- `/titles/{id}/cast` - Get cast and crew information for a specific title.
- `/genres` - List all available genres.

## Request and Response Format

Requests are made using standard HTTP methods (GET, POST). Most endpoints require query parameters or path variables. Responses are returned in JSON format.

**Example Request:**
```
GET /titles/search/title?title=Inception
Headers: { 'x-api-key': 'YOUR_API_KEY' }
```

**Example Response:**
```json
{
  "results": [
    {
      "id": "tt1375666",
      "title": "Inception",
      "year": 2010,
      "genres": ["Action", "Sci-Fi", "Thriller"],
      "cast": ["Leonardo DiCaprio", "Joseph Gordon-Levitt"]
    }
  ],
  "totalResults": 1
}
```

## Authentication

All requests require an API key, which must be included in the request headers as `x-api-key`. You can obtain an API key by registering on the MoviesDatabase API provider's website.

**Example Header:**
```
x-api-key: YOUR_API_KEY
```

## Error Handling

Common error responses include:
- `401 Unauthorized`: Missing or invalid API key.
- `404 Not Found`: The requested resource does not exist.
- `429 Too Many Requests`: Rate limit exceeded.
- `500 Internal Server Error`: An error occurred on the server.

Handle errors by checking the HTTP status code and parsing the error message from the response body.

## Usage Limits and Best Practices

- The API enforces rate limits (e.g., 1000 requests per day per API key).
- Avoid making unnecessary repeated requests.
- Cache responses where possible to reduce API calls.
- Always check for updated documentation for new features or changes.
