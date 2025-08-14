# MERN Authentication Project

A simple MERN stack project with user registration, login, logout using MongoDB, Express, React, Node.js, and Redux Toolkit.  
Uses Bootstrap for simple responsive design.

## Folder Structure

```plaintext
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
```

## Installation & Setup

### Backend

1. Navigate to backend folder:
   ```sh
   cd backend
   ```
2. Initialize Node.js project and install dependencies:
   ```sh
   npm init -y
   npm install express mongoose bcryptjs jsonwebtoken cors dotenv
   ```
   - **Total dependencies installed:** 6
     - express
     - mongoose
     - bcryptjs
     - jsonwebtoken
     - cors
     - dotenv
3. Create `.env` file:
   ```env
   MONGO_URI=mongodb://127.0.0.1:27017/mern_auth
   JWT_SECRET=your_jwt_secret
   PORT=5000
   ```
4. Run server (development with nodemon):
   ```sh
   npm run dev
   ```
- Server will run on: [http://localhost:5000](http://localhost:5000)

### Frontend

1. Navigate to frontend folder:
   ```sh
   cd frontend
   ```
2. Create React app and install dependencies:
   ```sh
   npx create-react-app .
   npm install react-redux @reduxjs/toolkit axios react-router-dom bootstrap
   ```
   - **Total dependencies installed:** 5 (after create-react-app)
     - react-redux
     - @reduxjs/toolkit
     - axios
     - react-router-dom
     - bootstrap
3. Start React app:
   ```sh
   npm start
   ```
- Frontend will run on: [http://localhost:3000](http://localhost:3000)

## Main Functionality

- Register a new user with name, email, and password
- Login with registered email and password
- Logout to clear session/token
- Dashboard page shows logged-in user info
- Uses JWT authentication for secure API access

## API URLs

| Method | Endpoint              | Description            |
|--------|-----------------------|------------------------|
| POST   | `/api/auth/register`  | Register a new user    |
| POST   | `/api/auth/login`     | Login user and get token |
| POST   | `/api/auth/logout`    | Logout user            |

### Example Request (Register/Login)

```json
{
  "name": "John Doe",       // only for register
  "email": "john@example.com",
  "password": "123456"
}
```

### Example Response

```json
{
  "user": {
    "_id": "12345",
    "name": "John Doe",
    "email": "john@example.com"
  },
  "token": "jwt_token_here"
}
```

## Tech Stack

- **Frontend:** React.js, Redux Toolkit, Bootstrap
- **Backend:** Node.js, Express.js
- **Database:** MongoDB
- **Authentication:** JWT + bcrypt
