# Internal-Bank-System

## | Contributors: [Liviru-Nava](https://github.com/Liviru-Nava),  [Rsarith](https://github.com/SarithRanathunge), [MR.NHIP](https://github.com/8hirantha) & [ Tharun Perera ](https://github.com/TharunPerera)

The Internal Banking System is a backend application designed to manage customer and account information, perform secure transactions, and ensure role-based access control for different banking staff. Built using Node.js, Express, and MySQL, the system provides robust functionality and security, making it ideal for internal banking operations.

## Features
- **Customer Management**: Register new customers, search by NIC, and update customer details as needed.
- **Account Management**: Create bank accounts with preloaded account numbers and manage account types with interest rates.
- **Transaction Handling**: Process withdrawals and deposits with automated transaction logging, ensuring accuracy and transparency.
- **User Authentication & Authorization**: Secure login with JWT tokens and role-based access control for Managers, Assistant Managers, Clerks, and Tellers.
- **Security**: Password hashing with bcryptjs, reCAPTCHA integration to prevent bots, and express-validator for input validation.

## Tech Stack
- **Backend**: Node.js, Express.js, MySQL
- **Authentication**: JSON Web Tokens (JWT)
- **Validation**: bcryptjs, express-validator, Google reCAPTCHA

## How It Works
1. **User Authentication**: Users log in with their credentials. JWT tokens are issued for maintaining sessions and ensuring secure communication.
2. **Customer & Account Management**: Allows for registering new customers and creating bank accounts. Existing customers can be searched using their NIC, and their details can be updated.
3. **Transaction Processing**: Enables deposits and withdrawals, updates account balances, and logs each transaction for record-keeping.
4. **Role-Based Access Control**: Managers and Assistant Managers access managerial functionalities, while Clerks and Tellers have access to customer and transaction management features.

## Project Structure
- `server.js`: Entry point for the server, setting up routes and middleware.
- `controllers/`: Contains logic for handling requests for authentication, customer management, account management, and transactions.
- `routes/`: Defines the API endpoints for handling different features.
- `models/`: Includes database models and queries for interacting with MySQL tables.
- `middleware/`: Houses middleware functions like authentication verification.

## API Overview
- **Authentication**:
  - `POST /auth/login` - Log in and receive a JWT token.
  - `POST /auth/register` - Register a new user (restricted to admins).

- **Customer Management**:
  - `GET /customers/:nic` - Retrieve customer details by NIC.
  - `POST /customers` - Create a new customer.

- **Account Management**:
  - `GET /accounts/next-account` - Fetch the next available account number.
  - `POST /accounts` - Create a new bank account.

- **Transactions**:
  - `POST /transactions/withdraw` - Withdraw an amount from an account.
  - `POST /transactions/deposit` - Deposit an amount to an account.
