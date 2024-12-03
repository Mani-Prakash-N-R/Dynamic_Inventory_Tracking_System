# Dynamic_Inventory_Tracking_System-WEB_DEVELOPMENT

Dynamic Inventory Tracking System
The Dynamic Inventory Tracking System is a web-based application designed to help businesses manage their inventory efficiently. It provides a user-friendly interface to track product stock levels in real-time, manage products, and ensure secure access through user authentication. Built with modern technologies, this system features a frontend developed using Angular, a backend powered by Node.js and Express.js, and a robust MySQL database for data storage.

Features
Manage Products: Add, edit, and delete products in the inventory.
Real-Time Stock Levels: Track and monitor product stock levels in real-time.
Secure User Authentication: Login and authentication system to ensure secure access.
Product Search & Filter: Search and filter products by category, name, or product ID.
Responsive Design: Access the system from any device, thanks to the responsive Angular frontend.

Tech Stack
Frontend: Angular (TypeScript, HTML, CSS)
Backend: Node.js, Express.js
Database: MySQL
Authentication: JWT (JSON Web Token) for secure user authentication
API Requests: HTTP REST API using Express.js
Development Tools: npm, Angular CLI

Installation
To run the Dynamic Inventory Tracking System on your local machine, follow the steps below:

1. Clone the Repository
Start by cloning the project repository to your local machine:


cd Dynamic_Inventory_Tracking_System

2. Setup the Backend
Navigate to the backend directory:

code
cd backend
Install Dependencies
Use npm to install the required dependencies:

code
npm install
Configure MySQL Database
Update the MySQL database configuration in the file config/db.config.js to match your MySQL setup:

code
module.exports = {
    HOST: "localhost",
    USER: "root",
    PASSWORD: "password",
    DB: "inventory_db"
};
Make sure you replace "localhost", "root", and "password" with your MySQL host, user, and password.

Start the Backend Server
To start the backend server, run the following command:

code
npm start
The backend will now be running at http://localhost:3000.

3. Setup the Frontend
Navigate to the frontend directory:

code
cd frontend
Install Angular Dependencies
Use npm to install the necessary Angular dependencies:

code
npm install
Set the API Endpoint
In the file src/environments/environment.ts, set the API URL to point to your backend server:

code
export const environment = {
  production: false,
  apiUrl: 'http://localhost:3000/api'
};

Start the Angular Frontend
Now, start the Angular frontend:
code
ng serve
The Angular frontend will be running at http://localhost:4200.

4. Database Setup
If you haven’t already, create a MySQL database and set up a user with the required privileges.

Create the Database
Run the following SQL command to create the database:

code
CREATE DATABASE inventory_db;
Create a MySQL User
Create a user with the necessary privileges to interact with the inventory_db:

code
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON inventory_db.* TO 'user'@'localhost';
Make sure you replace 'user' and 'password' with your desired database username and password.

Running the Application
Ensure both the frontend (http://localhost:4200) and backend (http://localhost:3000) servers are running.
Open http://localhost:4200 in your browser to access the Dynamic Inventory Tracking System.
API Endpoints
The backend exposes the following REST API endpoints for interacting with the inventory system:

POST /api/products: Add a new product to the inventory.

Request body:
code
{
  "name": "Product Name",
  "category": "Product Category",
  "quantity": 100,
  "price": 20.50
}
GET /api/products: Retrieve a list of all products in the inventory.

GET /api/products/:id: Get the details of a specific product by its ID.

PUT /api/products/:id: Update product details (name, category, quantity, price) for a given product ID.

Request body:
code
{
  "name": "Updated Product Name",
  "category": "Updated Category",
  "quantity": 120,
  "price": 22.00
}
DELETE /api/products/:id: Delete a product from the inventory by its ID.

User Authentication
The system supports secure user authentication using JWT (JSON Web Tokens).

To authenticate, send a POST request to /api/auth/login with your username and password.
On successful login, the server will return a JWT token, which should be included in the Authorization header for subsequent API requests.
Example:

code
{
  "username": "admin",
  "password": "password123"
}

Challenges
Data Consistency: Ensuring that data is consistently updated across the frontend, backend, and database can be challenging, especially when multiple users are accessing the system simultaneously.
Scalability: As the product catalog grows, managing large amounts of data efficiently can lead to performance issues. Optimizing queries and improving backend processing is essential.
User Authentication: Implementing secure and reliable user authentication with JWT tokens requires careful attention to session management and token expiration.
Error Handling: Proper error handling and input validation are crucial for maintaining system stability and preventing unexpected crashes or data corruption.