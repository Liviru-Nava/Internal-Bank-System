# Internal Banking System

This is the Internal Banking System project, consisting of a backend built with Node.js, Express, and MySQL.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Setting Up Environment Variables](#setting-up-environment-variables)
- [Starting the Server](#starting-the-server)
- [API Endpoints](#api-endpoints)
- [Database Setup](#database-setup)
- [Security Considerations](#security-considerations)
- [Git Ignore Configuration](#git-ignore-configuration)

## Features
- User authentication with JWT tokens.
- CRUD operations for customer and bank account management.
- Secure account creation and transaction management.
- Password hashing using bcryptjs and reCAPTCHA validation.
- Role-based access control for Managers, Assistant Managers, Clerks, and Tellers.
- RESTful API endpoints for seamless integration with the frontend.

## Prerequisites
- [Node.js](https://nodejs.org/) (v14+)
- [MySQL](https://www.mysql.com/) server
- npm or yarn package manager

## Getting Started
To set up the project on your local machine, follow the instructions below.

### Installation
1. **Clone the repository:**
   ```bash
   git clone <repository_url>
   cd Internal-Banking-System/backend

2. **Install dependencies:**
  Run the following command to install the required Node.js packages:
   ```bash
   npm install axios bcryptjs body-parser cors dotenv express express-validator helmet jsonwebtoken jwt-decode multer mysql2 path winston nodemon
   ```
   Open package.json file and add this line code to the "scripts": section
   ```bash
   "scripts":{
    "start": "node server.js",
    "dev": "nodemon server.js"
   }
   ```

3. **Setting Up Environment Variables:**
  a. **Create a .env file in the backend folder root:**
   ```bash
   touch .env
  ``` 
  b. **Add the following environment variables to the .env file:**
  ```bash
    PORT = 5000
    DB_HOST = your_db_host
    DB_USER = your_db_user
    DB_PASSWORD = your_db_password
    DB_NAME = your_db_name
    JWT_SECRET = your_jwt_secret_key
    RECAPTCHA_SECRET_KEY = your_recaptcha_secret_key
  ```
  Replace your_db_host, your_db_user, your_db_password, your_db_name, and your_jwt_secret_key with your actual MySQL database credentials and a secret key for JWT tokens.

4. **Start the server:**
  Start the Node.js server: Run the following command in the backend folder:
   ```bash
   npm start
   ```
   **Verify the server is running:** Open your browser or Postman and navigate to http://localhost:5000. If everything is set up correctly, you should see a response from the server.

5. ****

