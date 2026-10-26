# SIT Student Management System (CA-03)

Full-stack web application developed for **Continuous Assessment 03 (CA-03)**, Symbiosis Institute of Technology (SIT), Section B.

Based on the repository: [https://github.com/somesh-chutel/25070521060-CA-03.git](https://github.com/somesh-chutel/25070521060-CA-03.git)

---

## 🌟 Features

- **MongoDB Compass Integration**: Connected to local MongoDB instance (`mongodb://127.0.0.1:27017`), database `sitSecB`, collection `student`.
- **Full CRUD Support**:
  - `GET /getall`: Fetch all student records.
  - `GET /get/:id`: View detailed student info by MongoDB `_id`.
  - `POST /create`: Register a new student with password encryption.
  - `PUT /update/:id`: Update academic status (Active, Intern, Placed).
  - `DELETE /delete/:id`: Delete a student record.
- **Enterprise Security**:
  - Passwords securely hashed with **Bcrypt** (salt rounds: 10).
  - Stateless authentication with **JSON Web Tokens (JWT)**.
- **Modern Responsive UI**:
  - Built with **React 19**, **Vite**, **Bootstrap 4**, and custom CSS.
  - Real-time statistics counters (Total, Active, Intern, Placed).
  - Search by Name/Email and Filter by Academic Status.
  - Interactive modals for adding, editing, and viewing students.
  - Complete pages: **Home**, **About**, **Services**, and **Contact**.

---

## 🚀 Quick Start Guide

### 1. Prerequisites
- **Node.js** (v18 or higher installed)
- **MongoDB Server & MongoDB Compass** running on `localhost:27017`

### 2. Start the Backend Server (Express + MongoDB)
Open a terminal in the project directory:
```bash
cd server
npm start
```
The server will start on `http://localhost:5000` and automatically seed initial students into `sitSecB.student` if the collection is empty.

### 3. Start the Frontend Application (React + Vite)
In a second terminal:
```bash
cd client
npm run dev
```
Open your browser and navigate to:
```
http://localhost:5173
```

---

## 📡 API Endpoints Reference

| Method | Endpoint | Description | Request Body |
| :--- | :--- | :--- | :--- |
| `GET` | `/` | Health check & database connection status | None |
| `GET` | `/getall` | Retrieve all student records | None |
| `GET` | `/get/:id` | Retrieve student by MongoDB ObjectId | None |
| `POST` | `/create` | Register/Create student | `{"name", "email", "age", "status", "password"}` |
| `POST` | `/login` | Authenticate student and get JWT | `{"email", "password"}` |
| `PUT` | `/update/:id` | Update student status | `{"status"}` |
| `DELETE` | `/delete/:id` | Delete student by ObjectId | None |
| `POST` | `/seed` | Seed demo students | None |

---

## 📂 Project Directory Structure

```
e:/new project 1/
├── server/
│   ├── .env                 # Port, MongoDB URI, JWT Secret
│   ├── package.json         # Express, MongoDB, Bcrypt, JWT, CORS
│   └── server.js            # Express application with MongoDB connection
├── client/
│   ├── index.html           # HTML5 template with Bootstrap 4 & Fonts
│   ├── package.json         # React 19, Vite, React Router DOM
│   ├── vite.config.js       # Vite configuration with API proxy
│   ├── public/              # Icons and favicon
│   └── src/
│       ├── main.jsx         # React root & BrowserRouter
│       ├── App.jsx          # App router, Auth state, modals, toasts
│       ├── App.css          # Custom styling & animations
│       ├── index.css        # Base reset & typography
│       ├── nav.jsx          # Responsive navbar with user badge
│       ├── home.jsx         # Home page controller
│       ├── homeComp/
│       │   ├── header.jsx   # Hero banner & DB status
│       │   ├── mainContentCont.jsx # Stats, Search, CRUD table & modals
│       │   └── footer.jsx   # Footer with tech stack
│       ├── about.jsx        # Project specs & architecture
│       ├── services.jsx     # Portal services showcase
│       └── contact.jsx      # Interactive contact form
└── README.md                # Project documentation
```
