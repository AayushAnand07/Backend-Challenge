
# Backend Challange
This server development challange consists of various backend services development challanges.
### Comment Service 
    addComment(comment: Object): Promise<Object>
Adds a new comment to the specified post. Returns the updated post.

    updateComment(comment: Object): Promise<Object>
Updates an existing comment based on the provided comment object. Returns the updated comment.

    deleteComment(id: string): Promise<Object | null>
Deletes a comment with the specified ID. Returns the deleted comment or null if not found.

###  Post Service 
    getAllPosts(): Promise<Array<Object>>
Retrieves all posts available.

    getOnePost(id: string): Promise<Object | null>
Retrieves a specific post by its ID. If the post is found, additional information such as the creator's name and image URL is included.

    getPostByUserID(userId: string): Promise<Array<Object>>
Retrieves posts created by a specific user based on their ID.

    addPost(post: Object): Promise<Object>
Adds a new post to the system.


    updatePost(post: Object): Promise<Object | null>
Updates an existing post based on the provided post object. Returns the updated post or null if not found.

    deletePost(id: string): Promise<Object | null>
Deletes a post with the specified ID. Returns the deleted post or null if not found.

### User Service


    getAllUsers(): Promise<Array<Object>>
Retrieves all users available.

    getOneUser(id: string): Promise<Object | null>
Retrieves a specific user by their ID. The password field is excluded in the response.

    addUser(user: Object): Promise<Object>
Adds a new user to the system.

    updateUser(user: Object): Promise<Object | null>
Updates an existing user based on the provided user object. Handles both profile and password updates.

    deleteUser(id: string): Promise<Object | null>
Deletes a user with the specified ID. Returns the deleted user or null if not found

## Authentication
 This API provides endpoints for user signup and login.

### Signup
    Endpoint: POST /signup

Request:

    
    {
    "user": {
        "userName": "string",
        "email": "string",
        "password": "string"
    }
    }

Response:

    
        {
        "_id": "string",
        "userName": "string",
        "email": "string",
        "imagePath": "string"
        }

Errors:

    
        {
        "email": "Email already exists"
        }

### Login
    Endpoint: POST /login

Request:

    
    {
    "user": {
        "email": "string",
        "password": "string"
    }
    }

Response:

    
    {
    "token": "string"
    }

Errors:

    
    {
    "email": "Email not found"
    }
    {
    "error": "Incorrect password"
    }

