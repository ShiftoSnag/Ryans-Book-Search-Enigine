## RYan book search enigine
## Description

Repository containing the code for the Book Search engine application. This is a full MERN stack application utilizing GraphQL for data retrieval. The application is simple in nature: 
- if the user is logged in: 
    - the user can search for books
    - on the search page, the user can mark the books for further review
    - the user can visit their "account" area where they can review the previously marked books
    - in the account page, the user can remove previously selected books.

- if the user is NOT logged in: 
    - the user can search for books

The "account" section of the page is protected, and the user must be logged in to proceed. Expired login will redirect the user to the main page. The authentication is handled by a JSON Web Token simplifying the authentication process.

## Table of Contents

- [Installation](#installation)
- [Functionality](#functionality)
- [Usage](#usage)
- [Credits](#credits)
- [Tests](#tests)
- [License](#license)
- [Walktrough](#walkthrough)
- [Future Development](#future-development)
- [Contact](#contact)

## Installation

No special installation requirements. visit  to use the application.


back to [Table of Contents](#table-of-contents)


## Functionality

The following discusses at a high level about some of the features of the website. Detailed code implementation can be found as comments in the JS files.


### MERN:

The application is based on the MERN stack which is:
- MongoDb: in this simple application, there's only one collection (User) that houses the data. The listing of books is a schema that is part of the User collection. GraphQL is used to handle the communication with the database.
- Express: this is the server library that is used to handle the back end
- React: this is the front end of the application. It handles all requests and interactions from the user as well as displays information to the user.
- Node: along with express, Node is part of the back end and both along with Express are responsible for the smooth operation of the server. 

### JWT:

JSON Web Token (JWT) is part of the authentication process ensuring authenticated users can access restricted parts of the page. JWT is a hashed-base64 encoded string of characters that is passed with the headers for every client request to the server. The token is then verified against expiration and validity and then the response is sent back. This ensures safe communication between the parties. 

### GraphQL:

GraphQL via the Apollo Server is the way to communicate with the database without having the need to create special API routes. The GraphQL requires:
- a definition of the queries and mutations that will be executed at the front end (client side).
- type definitions at the back end
- resolvers (or query implementations) at the back end that correspond with the type definitions.

back to [Table of Contents](#table-of-contents)

## Usage

To access application
1. Go to  to access the application
2. Before logging in/setting up an account
    1. search for books and observe the cards - you will not see any buttons to save the books
2. Log in or create an account (top right corner menu)
    1. search for books and observe the cards - you will see "Save this Book!" button at the bottom of each card.
    2. for books that you like, click on the button
3. Go to your Saved books (top right corner menu)
    1. view your existing saved books; notice the red button at the bottom to "delete" book.
    2. for books that you don't want, click on the "delete" button. Deleting a book will only remove it from your listing; it will not remove it from google.
4. Allow 2 hours pass by (max life of a token is 2 hours)
    1. attempt to either: access the ```/saved``` route, click on the "delete" button, or click on the "save book" button - you should be redirected to the main page and the login button will not be visible


back to [Table of Contents](#table-of-contents)

## Tests

All tests have been performed manually using Chrome.

back to [Table of Contents](#table-of-contents)
