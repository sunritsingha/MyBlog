# MyBlog

**MyBlog** is a comprehensive blog platform designed to manage and publish blog posts with user authentication, profile management, and file upload capabilities. Built with Express and MongoDB, it provides a robust backend for handling various blog-related functionalities.

## Features

### User Authentication
- **Register**: Create a new user account with a username and password.
- **Login**: Authenticate users and issue a JWT token for session management.
- **Profile Management**: Access user profile information and manage authentication state.
- **Logout**: End the user session and clear the authentication token.

### Post Management
- **Create Post**: Submit a new blog post with a title, summary, content, and an optional cover image.
- **Update Post**: Edit existing blog posts, including updating the cover image.
- **View Posts**: Retrieve a list of all posts or a specific post by ID.
- **File Uploads**: Supports uploading and associating cover images with blog posts.

### File Handling
- **Multer Integration**: Uses Multer for handling file uploads, specifically for post cover images.
- **File Storage**: Uploaded files are stored in the `uploads/` directory and served via a static route.

## Tech Stack

- **Backend Framework**: Express - Provides a minimalist and flexible Node.js web application framework.
- **Database**: MongoDB - A NoSQL database for storing user and post data.
- **Object Data Modeling (ODM)**: Mongoose - Manages database schemas and interactions.
- **Authentication**: JWT (JSON Web Tokens) and bcryptjs - Secure user authentication and password hashing.
- **File Handling**: Multer - Middleware for handling multipart/form-data, used for file uploads.
- **Middleware**: 
  - **CORS** - Configured to handle cross-origin requests.
  - **Cookie-Parser** - Parses cookies attached to the client request object.

## Installation

To set up the project locally, follow these steps:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/sunritsingha/MyBlog.git
    ```

2. **Navigate to the Project Directory**:
    ```bash
    cd MyBlog
    ```

3. **Install Dependencies**:
    ```bash
    npm install
    ```

4. **Start the Server**:
    ```bash
    npm start
    ```

   The server will start and listen on port `4000`.

## API Endpoints

### User Authentication

- **POST `/register`**: Registers a new user. Requires `username` and `password` in the request body.
- **POST `/login`**: Authenticates a user and returns a JWT token. Requires `username` and `password` in the request body.
- **GET `/profile`**: Returns the profile information of the logged-in user. Requires a valid JWT token in cookies.
- **POST `/logout`**: Logs out the user and clears the authentication token.

### Post Management

- **POST `/post`**: Creates a new blog post. Requires `title`, `summary`, and `content` in the request body, and optionally a file upload for the cover image.
- **PUT `/post`**: Updates an existing blog post. Requires `id`, `title`, `summary`, and `content` in the request body. Optionally, a new file can be uploaded for the cover image.
- **GET `/post`**: Retrieves a list of all posts, sorted by creation date.
- **GET `/post/:id`**: Retrieves a specific post by ID.

## Notes

- Ensure MongoDB is properly set up and the connection string in `index.js` is configured with your database credentials.
- The project uses environment variables for sensitive data like JWT secrets and database connection strings. Configure these appropriately in a `.env` file or your hosting environment.


