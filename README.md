MERN Authentication Project

A simple MERN stack project with user registration, login, logout using MongoDB, Express, React, Node.js, and Redux Toolkit.
Uses Bootstrap for simple responsive design.

Folder Structure
backend/
├── controllers/
│   ├── authController.js
│   └── index.js
├── models/
│   ├── User.js
│   └── index.js
├── routes/
│   ├── authRoutes.js
│   └── index.js
├── server.js
├── package.json
└── .env

frontend/
├── src/
│   ├── pages/
│   │   ├── Login.js
│   │   ├── Register.js
│   │   └── Dashboard.js
│   ├── redux/
│   │   ├── store.js
│   │   └── slices/
│   │       └── authSlice.js
│   ├── App.js
│   └── index.js
├── package.json
└── public/index.html

Installation & Setup
Backend

Navigate to backend folder:

cd backend


Install dependencies:

npm install


Create .env file:

MONGO_URI=mongodb://127.0.0.1:27017/mern_auth
JWT_SECRET=your_jwt_secret
PORT=5000


Run server (development with nodemon):

npm run dev


Server will run on:

http://localhost:5000

Frontend

Navigate to frontend folder:

cd frontend


Install dependencies:

npm install


Start React app:

npm start


Frontend will run on:

http://localhost:3000

Main Functionality

Register a new user with name, email, and password.

Login with registered email and password.

Logout to clear session/token.

Dashboard page shows logged-in user info.

Uses JWT authentication for secure API access.

API URLs
Method	Endpoint	Description
POST	/api/auth/register	Register a new user
POST	/api/auth/login	Login user and get token
POST	/api/auth/logout	Logout user

Example Request (Register/Login):

{
  "name": "John Doe",       // only for register
  "email": "john@example.com",
  "password": "123456"
}


Example Response:

{
  "user": {
    "_id": "12345",
    "name": "John Doe",
    "email": "john@example.com"
  },
  "token": "jwt_token_here"
}

Tech Stack

Frontend: React.js, Redux Toolkit, Bootstrap

Backend: Node.js, Express.js

Database: MongoDB

Authentication: JWT + bcrypt
