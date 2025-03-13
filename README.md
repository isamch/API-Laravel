# Laravel 8 API Documentation

## 📌 Project Overview
This project is a **RESTful API** built with **Laravel 8**, implementing authentication and CRUD operations for managing users, expenses, and tags. The API is structured to be used for expense tracking systems, allowing users to manage their expenses and categorize them using tags.

## 🚀 Features
- **User Authentication** (Register, Login, Logout, Token-based Auth)
- **CRUD Operations** for Users, Expenses, and Tags
- **API Endpoints** following RESTful conventions
- **Eloquent Relationships** between models
- **Middleware Protection** using Laravel Sanctum

## 🛠 Requirements
- **PHP >= 7.4**
- **Composer**
- **Laravel 8**
- **MySQL Database**

## 📥 Installation Guide
1. Clone the repository:
   ```sh
   git clone https://github.com/API-Laravel.git
   cd API-Laravel
   ```
2. Install dependencies:
   ```sh
   composer install
   ```
3. Configure environment variables:
   ```sh
   cp .env.example .env
   ```
   - Update `.env` with database credentials.
4. Generate application key:
   ```sh
   php artisan key:generate
   ```
5. Run database migrations:
   ```sh
   php artisan migrate
   ```
6. Start the development server:
   ```sh
   php artisan serve
   ```

## 🔑 Authentication
This API uses **Laravel Sanctum** for authentication. To access secured endpoints, users must include a valid authentication token in the request header:
```
Authorization: Bearer {token}
```
### **1️⃣ Register User**
**Endpoint:** `POST /api/register`
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password"
}
```
**Response:**
```json
{
  "token": "your-auth-token",
  "user": {
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```
### **2️⃣ Login User**
**Endpoint:** `POST /api/login`
```json
{
  "email": "john@example.com",
  "password": "password"
}
```
**Response:**
```json
{
  "token": "your-auth-token"
}
```
### **3️⃣ Logout User**
**Endpoint:** `POST /api/logout`

## 📌 API Endpoints
### **1️⃣ Users API**
| Method | Endpoint         | Description         |
|--------|----------------|---------------------|
| GET    | `/api/users`    | Get all users      |
| POST   | `/api/users`    | Create a user      |
| GET    | `/api/users/{id}` | Get a single user |
| PUT    | `/api/users/{id}` | Update a user     |
| DELETE | `/api/users/{id}` | Delete a user     |

### **2️⃣ Expenses API**
| Method | Endpoint          | Description          |
|--------|------------------|----------------------|
| GET    | `/api/expenses`   | Get all expenses    |
| POST   | `/api/expenses`   | Create an expense   |
| GET    | `/api/expenses/{id}` | Get single expense |
| PUT    | `/api/expenses/{id}` | Update an expense  |
| DELETE | `/api/expenses/{id}` | Delete an expense  |

### **3️⃣ Tags API**
| Method | Endpoint       | Description        |
|--------|---------------|--------------------|
| GET    | `/api/tags`   | Get all tags      |
| POST   | `/api/tags`   | Create a tag      |
| GET    | `/api/tags/{id}` | Get a single tag |
| PUT    | `/api/tags/{id}` | Update a tag     |
| DELETE | `/api/tags/{id}` | Delete a tag     |

## 🛠 Running Tests
To run the API tests, use:
```sh
php artisan test
```

## 📌 Notes
- This API uses **Laravel Sanctum** for authentication.
- Ensure to pass the `Authorization: Bearer {token}` header for authenticated endpoints.
- All data should be sent in **JSON format**.

## 📞 Support
For any issues, please open an issue on GitHub or contact support at `support@example.com`.

