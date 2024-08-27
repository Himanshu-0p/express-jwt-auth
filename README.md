# express-jwt-auth
A Node.js-based authentication system using Express and JWT for secure user login and API access. This project demonstrates basic user authentication, token generation, and protected routes using JSON Web Tokens. Ideal for anyone looking to implement secure authentication in a Node.js application.

#Steps to Run this project

To run your Express application and test it using Postman, follow these steps:

Step 1: Start the Express Server
Ensure your server is running:
Open a terminal in your project directory.

Run the following command:

bash
Copy code
node index.js
If the server starts successfully, you should see:

arduino
Copy code
Server running on port 3000
Step 2: Set Up Postman for Testing
Open Postman:

Launch Postman, a popular API client used for testing RESTful APIs.
Testing the /signin Route (POST Request):

Create a new request:

Click on "New" > "HTTP Request" or use an existing workspace to create a new request.
Set the request method to POST.
Enter the URL: http://localhost:3000/signin.
Set the Request Body:

Click on the "Body" tab.

Select "raw" and then "JSON" from the dropdown.

Enter the JSON body with the username and password:

json

{
    "username": "himanshu@gmail.com",
    "password": "123"
}
Send the Request:

Click "Send".
You should receive a response with a JSON Web Token (JWT) if the username and password match an entry in the ALL_USERS array.
Example Response:

json

{
    "token": "your_jwt_token_here"
}
Testing the /users Route (GET Request):

Create a new request:

Set the request method to GET.
Enter the URL: http://localhost:3000/users.
Set Authorization Header:

Click on the "Headers" tab.
Add a new header with the following values:
Key: Authorization
Value: Bearer your_jwt_token_here
Replace your_jwt_token_here with the token you received from the /signin request.
Send the Request:

Click "Send".
You should receive a list of users, excluding the one whose token was used.
Example Response:

json

[
    {
        "username": "swami@gmail.com",
        "password": "abc",
        "name": "swami patil"
    },
    {
        "username": "krushna@gmail.com",
        "password": "pwd",
        "name": "krushna patil"
    }
]

Summary of Steps in Postman:
POST to /signin with a JSON body to receive a token.
GET from /users using the received token in the Authorization header.
If everything is set up correctly, these steps should allow you to authenticate users and retrieve data using your Express application with Postman.
