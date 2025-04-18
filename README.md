# medical appointment booking


# Medical Appointment Booking

A web application designed to facilitate the booking, management, and viewing of medical appointments. It includes user authentication features allowing users to manage their own appointments securely.

## Table of Contents

*   [Features](#features)
*   [Tech Stack](#tech-stack)
*   [Prerequisites](#prerequisites)
*   [Installation](#installation)
*   [Environment Variables](#environment-variables)
*   [Running the Application](#running-the-application)
*   [API Endpoints (Example)](#api-endpoints-example)
*   [Project Structure (Example)](#project-structure-example)

## Features

*   **User Authentication:**
    *   New user registration with password hashing (bcryptjs).
    *   User login with JWT (JSON Web Tokens) for session management.
*   **Appointment Management:**
    *   Book a new medical appointment.
    *   View booked appointments (for the logged-in user).
    *   Update details of an existing appointment.
    *   Cancel/Delete an appointment.

## Tech Stack

*   **Frontend:**
    *   HTML
    *   CSS
    *   JavaScript
*   **Backend:**
    *   Node.js
    *   Express.js
    *   Sequelize (ORM for MySQL)
    *   MySQL2 (Database Driver)
    *   jsonwebtoken (JWT for Authentication)
    *   bcryptjs (Password Hashing)
    *   express-validator (Input Validation)
    *   cors (Cross-Origin Resource Sharing)
    *   dotenv (Environment Variable Management)
*   **Database:**
    *   MySQL
*   **Development:**
    *   Nodemon (Automatic server restart during development)

## Prerequisites

Before you begin, ensure you have the following installed:

*   [Node.js](https://nodejs.org/) (which includes npm)
*   [MySQL Server](https://dev.mysql.com/downloads/mysql/)
*   A code editor (e.g., [VS Code](https://code.visualstudio.com/))
*   [Git](https://git-scm.com/) (Optional, for cloning)

## Installation

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd medical-appointment-booking
    ```

2.  **Navigate to the backend directory:**
    *(Adjust this step if your `package.json` is in the root or another location)*
    ```bash
    cd backend
    ```

3.  **Install backend dependencies:**
    ```bash
    npm install
    ```

4.  **Set up the database:**
    *   Ensure your MySQL server is running.
    *   Create a database for the application. You can use a tool like MySQL Workbench or the command line:
        ```sql
        CREATE DATABASE medical_appointments_db; -- Or your preferred name
        ```

5.  **Configure Environment Variables:**
    *   In the `backend` directory, create a file named `.env`.
    *   Copy the contents of `.env.example` (if you have one) or add the necessary variables (see [Environment Variables](#environment-variables) section below).
    *   Update the `.env` file with your specific database credentials and JWT secret.

6.  **Database Migration/Sync:**
    *   Depending on your Sequelize setup, models might sync automatically when the server starts.
    *   If you are using Sequelize migrations, run the migration command (e.g., `npx sequelize-cli db:migrate`). Ensure your Sequelize CLI is configured correctly if you use this method.

## Environment Variables

Create a `.env` file in the `backend` directory with the following variables:

```env
# Database Configuration
DB_HOST=localhost
DB_USER=your_mysql_username
DB_PASSWORD=your_mysql_password
DB_NAME=medical_appointments_db # Or the name you chose
DB_PORT=3306 # Default MySQL port
DB_DIALECT=mysql

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key # Choose a strong, random secret
JWT_EXPIRES_IN=1h # Example: Token expiry time

# Server Configuration
PORT=5000 # Or any port you prefer for the backend server

# CORS Configuration (Optional - adjust as needed)
# CLIENT_URL=http://127.0.0.1:5500 # Example: URL of your frontend if served separately
