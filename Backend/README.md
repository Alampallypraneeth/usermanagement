# 🖥️ User Management System - Backend API

This is the robust backend service for the **User Management System**, built using **Node.js**, **Express.js**, and **MongoDB** (via Mongoose). It offers a clean RESTful API with automated input validation, comprehensive error handlers, and soft-delete features.

---

## 🚀 Features

- **Robust REST API**: Complete CRUD (Create, Read, Update, Delete) capability for managing user profiles.
- **MongoDB Integration**: Managed models using Mongoose with timestamps and field validations.
- **Unified Global Error Handler**: Custom middleware that intercepts and standardizes:
  - Mongoose `ValidationError` (400 Bad Request)
  - Mongoose `CastError` for invalid MongoDB ObjectIDs (400 Bad Request)
  - Duplicate email/key entries (`code 11000`) (409 Conflict)
  - Unexpected application errors (500 Internal Server Error)
- **JSON Requests**: Support for raw JSON payload formatting.
- **CORS Configured**: Pre-configured standard CORS middleware for secure frontend-backend integration.
- **HTTP Client Test Script**: Bundled `req.http` file for rapid endpoint verification right within your IDE (VS Code / JetBrains / etc.).

---

## 📂 Project Structure

```text
Backend/
├── APIs/
│   └── userapi.js       # Express Router containing CRUD routes
├── Models/
│   └── UserModel.js     # Mongoose Schema & User model definition
├── node_modules/        # Vendor dependencies (ignored)
├── .env                 # Local environment config variables (ignored)
├── package.json         # Project manifests and package scripts
├── req.http             # Visual Studio Code HTTP Client test requests
└── server.js            # Main application bootstrap and DB connector
```

---

## 🛠️ Setup & Installation

### 1. Prerequisites
- **Node.js** (version 16 or newer recommended)
- **MongoDB** (a local instance running on `localhost` or an Atlas connection URI)

### 2. Install Dependencies
Run the following inside the `Backend` directory:
```bash
npm install
```

### 3. Configure Environment Variables
Create a file named `.env` in the root of the `Backend/` directory:
```env
PORT=5000
DB_URL=mongodb://localhost:27017/usermanagement
```
> [!NOTE]
> Adjust the `DB_URL` connection string to your MongoDB host, database name, or MongoDB Atlas cluster credentials.

### 4. Start the Application

- **Development Mode** (Runs with `nodemon` for auto-reloading upon file changes):
  ```bash
  npm run dev
  ```

- **Production Mode**:
  ```bash
  npm run start
  ```

---

## 📡 API Reference & Endpoints

All backend endpoints are prefixed with `/user-api`.

### 1. User Schema Fields
| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `name` | `String` | Yes | Full name of the user |
| `email` | `String` | Yes | Email address of the user |
| `age` | `Number` | Yes | Age in years |
| `dateOfBirth` | `Date` | Yes | Birthday timestamp (YYYY-MM-DD) |
| `mobileNumber` | `Number` | Yes | Contact number |
| `status` | `Boolean` | No | Operational status (Active/Inactive) |

---

### 2. Endpoints Details

#### Create a User
* **Method**: `POST`
* **Route**: `/user-api/user` or `/user-api/users`
* **Payload**:
  ```json
  {
    "name": "Samraksh",
    "email": "sam@gmail.com",
    "age": 20,
    "dateOfBirth": "2003-05-12",
    "mobileNumber": 9999999999,
    "status": true
  }
  ```
* **Success Response**: `201 Created`

#### Get All Users
* **Method**: `GET`
* **Route**: `/user-api/user` or `/user-api/users`
* **Success Response**: `200 OK`

#### Get User by ID
* **Method**: `GET`
* **Route**: `/user-api/users/:id`
* **Success Response**: `200 OK`

#### Update User details (Full/Partial)
* **Method**: `PUT`
* **Route**: `/user-api/users/:id`
* **Payload**:
  ```json
  {
    "mobileNumber": 8888888888
  }
  ```
* **Success Response**: `200 OK`

#### Activate User
* **Method**: `PATCH`
* **Route**: `/user-api/users/:id`
* **Payload**:
  ```json
  {
    "status": true
  }
  ```
* **Success Response**: `200 OK`

#### Soft / Hard Delete User
* **Method**: `DELETE`
* **Route**: `/user-api/users/:id`
* **Success Response**: `200 OK` or `201 Created`

---

## ⚠️ Global Error Handling & Validations

The server incorporates robust error interceptors to return meaningful JSON responses to the frontend client:

1. **Mongoose `ValidationError` (`400 Bad Request`)**: Returns a map of validation errors.
2. **Mongoose `CastError` (`400 Bad Request`)**: Returns `{"message": "Invalid ID format"}` when query parameters contain ill-formatted MongoDB `ObjectIDs`.
3. **Duplicate Key Error (`409 Conflict`)**: Returns `{"message": "Duplicate field value"}` if duplicate emails or unique keys are attempted.

---

## 🛠️ Local API Testing
For quick and convenient verification, install the **REST Client** extension in VS Code, open the [req.http](file:///Users/alampallypraneeth/Desktop/week-8-main/Backend/req.http) file, and click **"Send Request"** above any method block.
