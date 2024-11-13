Sure! Here's a combined **`README.md`** for the **To-Do Application** project, explaining both the frontend (React) and backend (Node.js/Express) setup, functionality, and how to run the full application.

---

# To-Do Application

## Overview
The **To-Do Application** is a full-stack web app built using **React.js** for the frontend and **Node.js with Express** for the backend. It allows users to register, log in, manage their profiles, and visualize project statuses with data graphs. Users can add and manage projects, and each project can have images, descriptions, and status updates. The backend uses **MongoDB** for data storage and **JWT tokens** for secure authentication. **Cloudinary** is integrated for image uploads.

---

## Key Features

- **User Registration & Login**: Allows users to sign up, log in, and manage their authentication tokens.
- **Profile Management**: Users can view and update their profile, including username, email, phone, bio, and profile image.
- **Project Management**: Users can create new projects, view existing projects, update project status, and delete projects.
- **Data Visualization**: Project status is visualized using **Chart.js** in bar chart format.
- **Image Uploads**: Projects can include images uploaded via **Cloudinary**.
- **Responsive Design**: The frontend is fully responsive and works across various devices.
- **JWT Authentication**: Secure API routes protected with JWT tokens to ensure only authenticated users can access or modify their data.

---

## Project Structure

### Frontend (React) Directory Structure
```
├── src
│   ├── Components
│   │   ├── AddProject
│   │   │   ├── AddProject.jsx
│   │   │   └── AddProject.css
│   │   ├── Dashboard
│   │   │   ├── GraphPage.jsx
│   │   │   └── GraphPage.css
│   │   ├── Header
│   │   │   ├── Header.jsx
│   │   │   └── Header.css
│   │   ├── Login
│   │   │   ├── EmployeeLogin.jsx
│   │   │   └── EmployeeLogin.css
│   │   ├── Register
│   │   │   ├── Register.jsx
│   │   │   └── Register.css
│   │   ├── Profile
│   │   │   ├── Profile.jsx
│   │   │   └── Profile.css
│   │   ├── Sidebar
│   │   │   ├── Sidebar.jsx
│   │   │   └── Sidebar.css
│   │   └── Home
│   │       ├── Home.jsx
│   │       └── Home.css
│   ├── App.jsx
│   └── App.css
└── README.md
```

### Backend (Node.js + Express) Directory Structure
```
├── controllers
│   ├── authController.js
│   ├── profileController.js
│   └── projectController.js
├── middleware
│   └── authMiddleware.js
├── models
│   ├── Project.js
│   └── User.js
├── routes
│   ├── auth.js
│   ├── profile.js
│   └── project.js
├── .env
├── index.js
└── server.js
```

---

## Setup & Installation

This is a **full-stack application** with separate frontend and backend components. Below are the setup instructions for both parts.

---

### Prerequisites
Make sure you have the following installed:
- **Node.js** (LTS version)
- **npm** or **yarn** (Node package manager)
- **MongoDB** (either locally or MongoDB Atlas)
- **Cloudinary account** (for handling image uploads)

---

### 1. Backend Setup

#### Clone the Backend Repository
Clone the backend repository to your local machine:

```bash
git clone https://github.com/your-repo/to-do-app-backend.git
cd to-do-app-backend
```

#### Install Dependencies
Run the following command to install all the required backend dependencies:

```bash
npm install
```

#### Configure Environment Variables
Create a `.env` file in the root directory of the backend project and add the following variables:

```
MONGODB_URI=mongodb://localhost:27017/todo-app or Atlas uri  # MongoDB URI
JWT_SECRET=your_jwt_secret_here               # JWT secret for signing tokens
PORT=5000                                      # The port the backend server will run on
CLOUDINARY_URL=your_cloudinary_url_here       # Cloudinary URL (for image uploads)
```

#### Start the Backend Server
To start the backend server, run:

```bash
npm start
```

The backend server will run on [http://localhost:5000](http://localhost:5000).

---

### 2. Frontend Setup

#### Clone the Frontend Repository
Clone the frontend repository to your local machine:

```bash
git clone https://github.com/your-repo/to-do-app-frontend.git
cd to-do-app-frontend
```

#### Install Dependencies
Run the following command to install all the required frontend dependencies:

```bash
npm install
```

#### Configure API URL
In your frontend code, make sure to update the API URL to point to your local backend server. This is typically done in an environment variable or directly in the code (e.g., `http://localhost:5000`).

#### Start the Frontend Development Server
To start the frontend server, run:

```bash
npm start
```

The frontend will run on [http://localhost:3000](http://localhost:3000).

---

## How to Use the Application

1. **Registration & Login**: 
   - Navigate to the **Registration page** (`/register`) to create a new account. 
   - After registration, you'll be redirected to the **Login page** (`/login`).
   - Use the credentials to log in.

2. **Profile Management**:
   - After logging in, you can view and edit your profile information on the **Profile page** (`/profile`).
   - You can update your name, email, bio, and profile image.

3. **Add a Project**:
   - Go to the **Add Project** page (`/add-project`) and enter your project details such as title, description, client, budget, and project images.

4. **View Projects**:
   - Navigate to the **Dashboard** to view all your projects and their current statuses.
   - You can update the status of each project and visualize them in a **bar chart** on the **Graph page**.

5. **Logout**:
   - You can log out from the application at any time by clicking the **Logout** button in the header.

---

## API Endpoints (Backend)

The following API endpoints are used by the frontend to communicate with the backend:

### 1. **Authentication**
- **POST `/register`**: Register a new user (requires `username`, `email`, `password`, and `profileImage`).
- **POST `/login`**: Login an existing user (requires `email` and `password`).

### 2. **Profile Management**
- **GET `/profile`**: Retrieve the logged-in user's profile.
- **PUT `/profile`**: Update the user's profile (requires `name`, `email`, `phone`, `bio`, `profileImage`).

### 3. **Project Management**
- **POST `/project`**: Create a new project (requires `title`, `basicDescription`, `totalDescription`, `client`, `budget`, and `images`).
- **GET `/projects`**: Get all projects of the authenticated user.
- **PUT `/project/:id/status`**: Update project status and GitHub link (requires `status` and `githubLink`).
- **DELETE `/project/:id`**: Delete a project by its ID.

### 4. **Authentication Middleware**
- **JWT Authentication**: All protected routes (e.g., `/profile`, `/projects`) require a valid JWT token in the `Authorization` header.

---

## Contributing

Feel free to contribute to this project! Fork the repository, make your changes, and submit a pull request. When contributing, ensure the following:
- Follow coding standards and best practices.
- Provide clear commit messages.
- If you add or change any API endpoints, update the documentation accordingly.


---

## Notes

- Ensure both the frontend and backend servers are running simultaneously for the application to work.
- You can use **Postman** or any other API testing tool to test the backend endpoints.

