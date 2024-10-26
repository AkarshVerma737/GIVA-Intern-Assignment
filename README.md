Product Management System

This is a simple Product Management System built with React, Node.js, and PostgreSQL. This application allows users to view, add, edit, and delete products within a personal account, ideal for small-scale e-commerce platforms or inventory management.

Features:

View a list of products with details like name, description, price, and quantity.
Add new products.
Edit existing products.
Delete products.
User authentication to manage personal product lists.

Prerequisites: Make sure you have the following installed on your machine:

Node.js (version 14 or above)
PostgreSQL (version 12 or above)
Git

Getting Started:

Clone the Repository

Set Up the Database:
    Start the PostgreSQL service and open the PostgreSQL shell: psql -U postgres
    Create a new database: CREATE DATABASE product_management_db;
    Connect to the new database: \c product_management_db;
    Create a products table: CREATE TABLE products ( id SERIAL PRIMARY KEY, name TEXT NOT NULL, description TEXT, price FLOAT, quantity INTEGER );
    Create a users table for authentication: CREATE TABLE users ( id SERIAL PRIMARY KEY, username TEXT UNIQUE NOT NULL, password TEXT NOT NULL );

Configure Environment Variables:
    In the backend folder, create a .env file with the following values: DATABASE_URL=postgresql://username
    @localhost:5432/product_management_db JWT_SECRET=your_jwt_secret
    Replace username, password, and your_jwt_secret with your actual PostgreSQL username, password, and a custom JWT secret key.

Install Dependencies:

    Backend: In the backend folder: cd backend npm install

    Frontend: In the frontend folder: cd ../frontend npm install

Run the Application:

    Start the Backend Server: In the backend folder: npm start The backend server will start at http://localhost:5000.

    Start the Frontend Server: In the frontend folder: npm start The frontend will run at http://localhost:3000.

API Routes:

Products:
    GET /api/products - Get all products for the authenticated user.
    POST /api/products - Add a new product.
    PUT /api/products/
    - Update an existing product by ID.
    DELETE /api/products/
    - Delete a product by ID.

Authentication:
    POST /api/auth/register - Register a new user.
    POST /api/auth/login - Log in and get an authentication token.

