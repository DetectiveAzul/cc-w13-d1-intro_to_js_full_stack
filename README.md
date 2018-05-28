# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using no frameworks, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?

```
The server/routers/games_router.js file is responsible for defining these routes. These are handled by the result of using express.Router() and defining the routes inside of this object. Lastly, server/routers/index_routers.js connect this file with the whole route call ('/api/games')
```
2. How is the server configured to know about the route definitions for the `games` resource?
```
Server requires and uses (express().use()) the index_router that connects with the games routers file
```
3. What is the responsibility of server.js?
```
1. Starting the server
2. Starting the server to listen to user commands
3. To connect the controllers (the routes) with the views (index.html)
```
4. What are the responsibilities of the `indexRouter`?
```
1. Load the database
2. Store it on a variable to handle any CRUD operations
3. Assign the database to the games routes controller
4. Handle the game route file and any other possible route files
```
5. What are the responsibilities of the `gamesRouter`?
```
1. Handle what any RESTful route does when there is a request on api/games/<request> and to call the different CRUD operations needed on the mongoDB
```
6. Which of the games API routes does the front-end application consume?
```
The src uses GET, POST, DELETE. HTML file only uses GET and POST.
```

## Extensions

1. What are we using the [MongoDB Driver API](http://mongodb.github.io/node-mongodb-native/) for?
```
To use mongo CRUD commands directly from our node/express server.
```
2. Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver API?
```
So EXPRESS can create 24 byte hex unique ID's for every entry on our database collections
```
