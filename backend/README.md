# Internal Banking System

This is the Internal Banking System project, consisting of a backend built with Node.js, Express, and MySQL.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Starting the Server](https://github.com/Liviru-Nava/Internal-Bank-System/tree/main/backend#setting-up-environment-variables)
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
   git clone https://github.com/Liviru-Nava/Internal-Bank-System.git
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

### Setting Up Environment Variables
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

### Start the server
  Start the Node.js server: Run the following command in the backend folder:
   ```bash
   npm start
   ```
   **Verify the server is running:** Open your browser or Postman and navigate to http://localhost:5000. If everything is set up correctly, you should see a response from the server.

### API Endpoints 

   Below is a list of primary API endpoints available:

    Authentication:
   
        POST /auth/login - Log in and receive a JWT token.
        POST /auth/register - Register a new user (restricted to admins).

    Customer Management:
   
        GET /customers/:nic - Retrieve customer details by NIC.
        POST /customers/create - Create a new customer.
        PUT /customers/:customer_id - Update customer details.

    Bank Account Management:
   
        GET /accounts/next-account - Fetch the next available account number.
        POST /accounts/create - Create a new bank account.
        GET /accounts/:account_no - Get details of an account by account number.
        GET /accounts - Get all accounts.

    Transactions:
   
        POST /transactions/withdraw - Withdraw an amount from an account.
        POST /transactions/deposit - Deposit an amount to an account.
        GET /transactions/:account_no - Get transaction history for a specific account.
        GET /transactions/branch/:branch_id - Get transactions for a specific branch.

### Git Ignore Configuration 
   Include the following content in the .gitignore file to prevent sensitive files like node_modules and .env from being uploaded to the repository:

 **.gitignore**
   ```bash
   # Node modules
   node_modules/

   # Environment variables
   .env

   # Logs
   logs
   *.log
   npm-debug.log*
   yarn-debug.log*
   pids
   *.pid
   *.seed
   *.pid.lock

   # Coverage directory
   coverage/

   # Debug
   *.local

   # Miscellaneous
   .DS_Store
   Thumbs.db

