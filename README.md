# User Management System

A beautiful, premium, and fully-featured User Management web application built with a modern stack consisting of a React frontend and an Express/Node.js backend with MongoDB.

---

## 🚀 Features

- **User Administration**: Add, edit, update, and delete users seamlessly.
- **Modern User Interface**: Clean, glassmorphic UI built using React 19, Tailwind CSS v4, and Lucide icons.
- **Robust REST API**: Complete Express-based backend API handling all user management operations.
- **MongoDB Database**: Persisted and structured user details using Mongoose schemas.
- **Global Error Handling**: Comprehensive backend error handling middleware covering validation, CastError, and duplicate key issues.

---

## 📂 Project Structure

This project is separated into decoupled frontend and backend applications:

```text
├── Backend/            # Express REST API (See Backend/README.md)
│   ├── APIs/           # Express router endpoints
│   ├── Models/         # Mongoose schema definitions
│   ├── server.js       # Main server entrypoint
│   ├── package.json    # Backend configuration and dependencies
│   └── req.http        # Sample HTTP requests for quick API testing
│
├── Frontend/           # React Single Page App (See Frontend/README.md)
│   ├── src/            # React components, pages, hooks, and logic
│   │   ├── Components/ # Reusable UI components
│   │   ├── main.jsx    # Frontend entry point
│   │   └── App.jsx     # Main App component with routing
│   ├── index.html      # Vite standard HTML template
│   ├── package.json    # Frontend configuration and packages
│   └── vite.config.js  # Vite bundler configurations
│
└── README.md           # Master root overview page
```

> [!TIP]
> For more granular technical specifications, please check out the dedicated **[Backend README](file:///Users/alampallypraneeth/Desktop/week-8-main/Backend/README.md)** and **[Frontend README](file:///Users/alampallypraneeth/Desktop/week-8-main/Frontend/README.md)** documents.

---

## 🛠️ Setup & Installation

### Prerequisites

- [Node.js](https://nodejs.org/) (v16+)
- [MongoDB](https://www.mongodb.com/) (Local instance or Atlas cloud connection string)

### 1. Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd Backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the `Backend` directory and define your environment variables:
   ```env
   PORT=5001
   DB_URL=your_mongodb_connection_string
   ```
4. Start the server:
   - Development mode (with nodemon): `npm run dev`
   - Production mode: `npm run start`

### 2. Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd ../Frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Run the development server:
   ```bash
   npm run dev
   ```
4. Build the application for production:
   ```bash
   npm run build
   ```

---

## 📡 API Endpoints

The backend exposes a highly robust user API under the prefix `/user-api`:

- `GET /user-api/users` - Retrieve all users.
- `GET /user-api/users/:id` - Fetch details for a specific user.
- `POST /user-api/user` - Create a new user record.
- `PUT /user-api/user/:id` - Update details of an existing user.
- `DELETE /user-api/user/:id` - Remove a user from the database.

---

## ✨ Authors & Contribution

Developed as part of the **User Management Application**. Built with passion, clean code, and premium UX principles.