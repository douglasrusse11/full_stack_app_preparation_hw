# Homework: Full Stack Games Hub App

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

![Data flow diagram](img/data_flow_diagram.svg)

### Questions

1. What is responsible for defining the routes of the `games` resource?
<details>
<summary>Answer</summary>
The routes of the `games` resource are defined by the helper function `createRouter` in `server/helpers/create_router.js` which creates routes prepended by `/api/games`.
</details>
2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?
<details>
<summary>Answer</summary>
The client is responsible for providing the user interface and making requests to the server. The server is responsible listening for requests from the client, amending the database as necessary, and providing a response to the client.
</details>
3. What are the the responsibilities of server.js?
<details>
<summary>Answer</summary>
`server.js` is responsible for connecting to the database, listening for API requests, amending the database, and providing a response to the client.
</details>
4. What are the responsibilities of the `gamesRouter`?
<details>
<summary>Answer</summary>
`gamesRouter` is responsible for providing RESTful API routes prepended by `/api/games` to provide CRUD functionality.
</details>
5. What process does the the client (front-end) use to communicate with the server?
<details>
<summary>Answer</summary>
The client uses `GamesService` process to communicate with the server via the `fetch` method.
</details>
6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs
<details>
<summary>Answer</summary>
The `fetch` method takes an optional second argument which is an `init` object which allows details of the HTTP request to be specified.
</details>
7. Which of the games API routes does the front-end application consume (i.e. make requests to)?
<details>
<summary>Answer</summary>
The client makes requests to `/api/games/ [GET]`, `/api/games [POST]`, and `/api/games/:id [DELETE]`.
</details>
8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?
<details>
<summary>Answer</summary>
The MongoDB Driver is being used to connect to and interact with the database via javascript.
</details>
## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?
<details>
<summary>Answer</summary>
We need to use `ObjectId` from the MongoDB driver because the ID provided by MongoDB and stored on the key `_id` are instances of `ObjectId`. 
</details>