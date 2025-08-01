PostgreSQL APP
In my final 3MTT mini project, I Create a simple Express.js API that connects to a PostgreSQL database and perform basic database operations (CRUD - create, read, update, delete).

Project Overview
Goal: Build a REST API with endpoints to Create, Read, Update, and Delete users from a PostgreSQL database.

Dependencies:

express – Web framework

pg – PostgreSQL client for Node.js

cors – Enable cross-origin requests

morgan – Request logging

## Setup with Docker

1. Copy `.env.example` to `.env`:
```
cp .env.example .env
```

2. Build and run containers:
```
docker-compose up --build
```

3. Create `users` table:
```
docker exec -it <db_container_id> psql -U postgres -d mydb -c "
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name HASSAN(100),
  email HASSAN(100),
  age INTEGER
);
"
```

4. API is available at `http://localhost:3000`

---

## Endpoints

- **GET /** – Test API
- **GET /users** – Retrieve all users
- **GET /users/:id** – Retrieve single user
- **POST /users** – Create new user
- **PUT /users/:id** – Update user
- **DELETE /users/:id** – Delete user

---

## Example Postman Requests

### Create User
```
POST http://localhost:3000/users
Content-Type: application/json

{
  "name": "Tijani",
  "email": "tijani@example.com",
  "age": 25
}
```

### Get All Users
```
GET http://localhost:3000/users
```

### Get User By ID
```
GET http://localhost:3000/users/1
```

### Update User
```
PUT http://localhost:3000/users/1
Content-Type: application/json

{
  "name": "Tijani Updated",
  "email": "tijani@newmail.com",
  "age": 26
}
```

### Delete User
```
DELETE http://localhost:3000/users/1
```
