# PostgreSQL-App

In my final 3MTT mini project, I created a simple Expree.js API to store and retrieve data that connects to a PostgreSQL database and perform basic database operations (CRUD - create, read, update, delete).

Project Overview
Goal: Build a REST API with endpoints to Create, Read, Update, and Delete users from a PostgreSQL database.

Dependencies:

express – Web framework

pg – PostgreSQL client for Node.js

cors – Enable cross-origin requests

morgan – Request logging

Testing with Postman
Create a user
POST http://localhost:3000/users
Content-Type: application/json

{
  "name": "Tijani",
  "email": "tijani@example.com",
  "age": 28
}
Get all users
GET http://localhost:3000/users

Get user by ID
GET http://localhost:3000/users/1

Update user
PUT http://localhost:3000/users/1
Content-Type: application/json

{
  "name": "Tijani Updated",
  "email": "tijani@newmail.com",
  "age": 29
}

Delete user
DELETE http://localhost:3000/users/1

Plan to add migration script:
Add dbInit.js file that:

Connects to PostgreSQL.

Checks if users table exists.

Creates it if not present.

Modify server.js to run migration on startup automatically.

Updated Structure
dbInit.js – Migration logic

server.js – Runs dbInit() before starting Express server

Included in Docker setup (works automatically inside container)

Thank you

Get all usersGet all users
