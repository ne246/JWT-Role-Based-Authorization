# Bookstore MongoDB

## Overview

In class, this project secured the Bookstore API with JWT authentication and added a `USER` role to protect the `POST /api/books` endpoint. This assignment extends the same project to implement role-based authorization for the delete operation so that only users with the `ADMIN` role can delete books.

##  Competed Requirements

1. Add the DELETE endpoint in `BookController.java`

Add a DELETE endpoint to the existing `BookController` that deletes a book by its ID:

`DELETE /api/books/{id}`

The endpoint should return `200 OK` with a success message when the book is deleted, and `404 Not Found` if the book ID does not exist.

2. Protect the endpoint in `SecurityConfig.java`

Configure Spring Security so only users with the `ADMIN` role can access the delete endpoint.

3. Register an ADMIN user

Using Postman, register a new user with both `USER` and `ADMIN` roles through `/api/auth/register`.

4. Test Scenario 1 - ADMIN can delete

Log in as the admin user, copy the JWT token, and make a `DELETE` request to `/api/books/{id}` with the token in the `Authorization` header. The book should be deleted successfully and return `200 OK`.

5. Test Scenario 2 - USER cannot delete

Register a second user with only the `USER` role. Log in as that user, copy the JWT token, and make a `DELETE` request to `/api/books/{id}` with that token. The response must be `403 Forbidden`, not `401 Unauthorized`.


## Postman Screenshots

1. Register the ADMIN user (200 OK response)  
   ![Register ADMIN](screenshots/1.png)

2. Login as ADMIN and token visible in response  
   ![Login ADMIN](screenshots/2.png)

3. DELETE request as ADMIN - 200 OK with success message  
   ![DELETE as ADMIN](screenshots/3.png)

4. DELETE request as USER - 403 Forbidden response  
5. ![DELETE as USER](screenshots/4.png)
   ![DELETE as USER](screenshots/5.png)
