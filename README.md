# JWT Authentication & Notes CRUD Application

A full-stack Notes Management application built with **React**, **Node.js**, **Express**, **MongoDB Atlas**, **JWT Authentication**, and **bcrypt**. Users can register, log in securely, and manage their personal notes using protected REST API endpoints.

---

# Features

## User Authentication

* User Registration
* User Login
* Password hashing with **bcryptjs**
* JWT-based authentication
* Protected API routes
* User Logout

## Notes Management

* Create new notes
* View all personal notes
* Edit existing notes
* Delete notes
* Notes are accessible only to the authenticated user

## Frontend

* React functional components
* React Hooks (`useState`, `useEffect`)
* Responsive user interface
* Login and Registration forms
* Error and success messages
* Simple and clean design

## Backend

* RESTful API using Express.js
* MongoDB Atlas database
* Mongoose ODM
* JWT Authentication Middleware
* Password encryption using bcryptjs
* CORS enabled
* Environment variable support using dotenv

---

# Technologies Used

## Frontend

* React
* JavaScript (ES6)
* CSS3
* Fetch API

## Backend

* Node.js
* Express.js
* MongoDB Atlas
* Mongoose
* JWT (jsonwebtoken)
* bcryptjs
* dotenv
* CORS

---

# Project Structure

```text
project/
│
├── backend/
│   ├── index.js
│   ├── .env
│   ├── package.json
│
├── frontend/
│   ├── src/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   ├── main.jsx
│   ├── package.json
│
└── README.md
```

---

# Installation

## Clone the Repository

```bash
git clone https://github.com/your-username/jwt-notes-app.git
cd jwt-notes-app
```

---

# Backend Setup

Navigate to the backend folder:

```bash
cd backend
```

Install dependencies:

```bash
npm install
```

Required packages:

```bash
npm install express mongoose cors dotenv bcryptjs jsonwebtoken
```

Create a **.env** file inside the backend folder.

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
PORT=5000
```

Start the backend server:

```bash
npm start
```

The server will run at:

```
http://localhost:5000
```

---

# Frontend Setup

Navigate to the frontend folder:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the React application:

```bash
npm run dev
```

The frontend will run at:

```
http://localhost:5173
```

---

# API Endpoints

## Register

**POST**

```
/register
```

Request Body

```json
{
  "username": "alice",
  "password": "1234"
}
```

Response

```json
{
  "message": "Account created! You can now log in."
}
```

---

## Login

**POST**

```
/login
```

Request Body

```json
{
  "username": "alice",
  "password": "1234"
}
```

Response

```json
{
  "token": "JWT_TOKEN"
}
```

---

## Get Notes

**GET**

```
/notes
```

Header

```
Authorization: Bearer JWT_TOKEN
```

---

## Create Note

**POST**

```
/notes
```

Header

```
Authorization: Bearer JWT_TOKEN
```

Request Body

```json
{
  "text": "My first note"
}
```

---

## Update Note

**PUT**

```
/notes/:id
```

Request Body

```json
{
  "text": "Updated note"
}
```

---

## Delete Note

**DELETE**

```
/notes/:id
```

---

# Authentication Flow

1. Register a new account.
2. Login using your credentials.
3. The server verifies the username and password.
4. A JWT token is generated and returned.
5. The frontend stores the token.
6. Every protected request includes:

```
Authorization: Bearer <JWT_TOKEN>
```

7. The backend verifies the token before allowing access to notes.

---

# MongoDB Collections

### Users

```json
{
  "_id": "...",
  "username": "alice",
  "password": "hashed_password"
}
```

### Notes

```json
{
  "_id": "...",
  "username": "alice",
  "text": "My first note",
  "createdAt": "...",
  "updatedAt": "..."
}
```

---

# Screens

* Register Page
* Login Page
* Notes Dashboard
* Add Note
* Edit Note
* Delete Note

---

# Security Features

* Passwords are hashed using bcrypt.
* JWT authentication protects all note routes.
* Users can only access their own notes.
* Environment variables are used for sensitive credentials.
* MongoDB Atlas stores user and note data securely.

---

# Future Enhancements

* Persistent login using localStorage
* Refresh Tokens
* User profile management
* Search notes
* Pagination
* Dark mode
* Form validation
* Password reset
* Unit testing
* Docker support

---

# Dependencies

### Backend

* express
* mongoose
* cors
* dotenv
* bcryptjs
* jsonwebtoken

### Frontend

* react
* react-dom
* vite

---

# License

This project is developed for educational purposes and is free to use, modify, and distribute.

---

# Author

**JWT Authentication & Notes CRUD Application**

Built using:

* React
* Express.js
* MongoDB Atlas
* Mongoose
* JWT Authentication
* bcrypt Password Hashing
* REST API Development
* Full-Stack JavaScript
