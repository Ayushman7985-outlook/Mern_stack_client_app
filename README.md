
# 📚 Book Management System

A full-stack web application for managing book records through a responsive web interface. The application provides user authentication, book management, search functionality, pagination, and a dashboard interface.

The frontend is developed using React and Vite and communicates with a separately hosted REST API built using Node.js and Express.js.

---

## 📌 Project Overview

The Book Management System is designed to simplify the process of maintaining and organizing book records.

Users can register and log in to access the application dashboard. Once authenticated, they can add new books, view existing records, update book information, delete records, and search for books by title or author.

The application follows a component-based architecture and uses API integration to communicate with the backend.

### Problem Statement

Managing book records manually can become difficult when the number of books increases. Searching, updating, and maintaining records manually can consume time and lead to inconsistencies.

This application provides a centralized interface to manage book information efficiently.

---

## 🎯 Project Objectives

- Develop a user-friendly book management application.
- Implement user registration and login functionality.
- Understand JWT-based authentication.
- Perform CRUD operations on book records.
- Integrate frontend components with backend REST APIs.
- Implement search and pagination.
- Maintain application state using React Context API.
- Create a responsive dashboard interface.

---

## 🛠️ Technology Stack

### Frontend

| Technology | Purpose |
|---|---|
| React 19.2.0 | Component-based UI development |
| Vite 7.2.4 | Development server and build tool |
| React Router DOM 7.13.0 | Client-side routing |
| Axios 1.13.4 | HTTP requests and API integration |
| Context API | Global authentication state |
| CSS | Application styling |

### Backend (Separate Repository)

| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime |
| Express.js | Backend API development |
| MongoDB | Database |
| Mongoose | MongoDB object modeling |
| JWT | Authentication |

---

## 🚀 Key Features

### 1. User Authentication

- User registration.
- User login.
- JWT-based authentication.
- Token storage using localStorage.
- Protected application routes.
- Automatic logout on invalid or expired authentication tokens.

### 2. Book Management

- Add new books.
- View book records.
- Edit existing book information.
- Delete book records.
- Manage book title, author, and publication year.

### 3. Search Functionality

- Search books by title.
- Search books by author.
- Dynamic search through the backend API.

### 4. Pagination

- Backend-driven pagination.
- Navigate between pages.
- Dynamic page number buttons.
- Previous and next navigation.

### 5. User Experience

- Loading indicators.
- Login progress indicator.
- Success and error messages.
- Disabled buttons during loading.
- Confirmation before deleting records.
- Interactive onboarding tour for first-time users.

### 6. Responsive Dashboard

The application provides a dashboard layout consisting of:

- Navigation bar.
- Sidebar navigation.
- Main content area.
- Responsive interface for different screen sizes.

---

## 🏗️ System Architecture

The application follows a frontend-backend architecture.

```text
             USER
               |
               v
        REACT FRONTEND
               |
               v
         AXIOS REQUESTS
               |
               v
       NODE.JS / EXPRESS API
               |
               v
          MONGODB
```

### Frontend Responsibilities

- Display application pages.
- Handle user interactions.
- Manage authentication state.
- Send HTTP requests to the backend.
- Display API responses.
- Manage book records through the user interface.

### Backend Responsibilities

- Process authentication requests.
- Validate user credentials.
- Generate and verify JWT tokens.
- Handle book CRUD operations.
- Communicate with MongoDB.
- Provide API responses to the frontend.

**Note:** The backend source code is maintained separately from this frontend repository.

---

## 📂 Project Structure

```text
mern_stack_client_app/
│
├── public/
│
├── src/
│   │
│   ├── api/
│   │   └── axios.js
│   │
│   ├── components/
│   │   ├── Navbar.jsx
│   │   ├── Sidebar.jsx
│   │   └── ProtectedRoute.jsx
│   │
│   ├── context/
│   │   └── AuthContext.jsx
│   │
│   ├── pages/
│   │   ├── Home.jsx
│   │   ├── Login.jsx
│   │   ├── Register.jsx
│   │   └── Books.jsx
│   │
│   ├── styles/
│   │   ├── books.css
│   │   ├── auth.css
│   │   ├── navbar.css
│   │   └── dashboard.css
│   │
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
│
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

---

## 🔐 Authentication Workflow

The application uses JSON Web Tokens (JWT) for authentication.

```text
       USER REGISTRATION
               |
               v
        USER LOGIN
               |
               v
       BACKEND VALIDATION
               |
               v
        JWT TOKEN RETURNED
               |
               v
       TOKEN IN LOCALSTORAGE
               |
               v
       AXIOS INTERCEPTOR
               |
               v
       AUTHORIZED API REQUEST
               |
               v
       PROTECTED DASHBOARD
               |
               v
       TOKEN EXPIRED / INVALID
               |
               v
          AUTO LOGOUT
```

### Authentication Implementation

- `AuthContext.jsx` manages global authentication state.
- Login and logout functions update authentication information.
- JWT tokens are stored in browser localStorage.
- Axios request interceptors attach the token to API requests.
- Protected routes restrict access to authenticated users.
- The response interceptor handles invalid or expired JWT responses.

---

## 🔗 API Integration

Axios is used to communicate with the backend REST API.

The frontend uses the following API operations:

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/auth/register` | Register a new user |
| POST | `/auth/login` | Authenticate a user |
| GET | `/books` | Retrieve book records |
| POST | `/books` | Create a book |
| PUT | `/books/:id` | Update a book |
| DELETE | `/books/:id` | Delete a book |

The book listing endpoint supports pagination and search parameters.

Example:

```text
GET /books?page=1&limit=5&search=Java
```

The API base URL is configured using a Vite environment variable.

---

## ⚙️ Installation and Setup

### Prerequisites

- Node.js and npm.
- Git.
- A backend API instance.
- A MongoDB database configured on the backend.

### Step 1: Clone the Repository

```bash
git clone https://github.com/nischalare/mern_stack_client_app.git
```

### Step 2: Navigate to the Project

```bash
cd mern_stack_client_app
```

### Step 3: Install Dependencies

```bash
npm install
```

### Step 4: Configure Environment Variables

Create a `.env` file in the project root directory.

```env
VITE_API_BASE_URL=http://localhost:8800/api
```

Replace the URL with the actual backend API address you intend to use.

Do not commit private credentials or secret environment variables to GitHub.

### Step 5: Start the Development Server

```bash
npm run dev
```

The Vite development server will provide a local URL, usually:

```text
http://localhost:5173
```

---

## 🌐 Live Deployment

### Frontend

https://nischalaremanda-react-vite-crud-app.vercel.app/

### Backend

https://nischalare-mern-crud-app.onrender.com/

The availability of these deployments may vary.


---

## 📚 Learning Outcomes

This project provides an opportunity to understand:

- React functional components and hooks.
- Component-based application architecture.
- React Router and protected routes.
- State management using Context API.
- REST API integration using Axios.
- JWT-based authentication.
- CRUD operations.
- Search and pagination.
- Frontend and backend communication.
- Responsive web application development.

---

## 👨‍💻 Project Contributions

This section should be updated with the work actually completed while studying and customizing the project.

### Work Completed

- [ ] Studied the existing project structure.
- [ ] Understood React components and hooks.
- [ ] Explored routing and protected routes.
- [ ] Studied authentication using JWT.
- [ ] Understood Axios API integration.
- [ ] Explored book CRUD operations.
- [ ] Tested application functionality.

### Customizations and Improvements

Add your actual modifications here after implementing them.

- [ ] UI and dashboard improvements.
- [ ] Additional book management features.
- [ ] Improved form validation.
- [ ] Improved error handling.
- [ ] Additional usability improvements.

---

## 🙏 Acknowledgements

This project is based on the original Book Management System repository.

**Original Repository:**

https://github.com/nischalare/mern_stack_client_app

**Original Author:**

Nischal Aremanda

The original repository is acknowledged as the source project. Any additional modifications should be documented separately.

---

## 📌 Project Purpose

The purpose of this project is to study and understand the development of a full-stack web application using the MERN technology stack.

It demonstrates how frontend development, backend APIs, authentication, database operations, and user interface design work together to build a functional application.
