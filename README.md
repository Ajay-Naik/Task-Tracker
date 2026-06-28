# Task Tracker

A full-stack Task Tracker web application built with the MERN stack. Users can register, log in, and manage their tasks with full CRUD functionality, priority levels, status tracking, and due dates.

## Live Demo

[https://task-tracker-xi-red.vercel.app/](https://task-tracker-xi-red.vercel.app/)

## Features

- JWT-based user authentication (register/login/logout)
- Create, edit, and delete tasks
- Task fields: title, description, status, priority, due date
- Filter tasks by status (Todo, In Progress, Done)
- Sort tasks by newest, oldest, or priority
- Interactive stat cards for quick filtering
- Dynamic updates without page refresh
- Responsive UI
- Past date prevention on due date picker

## Tech Stack

**Frontend:** React, Vite, React Router, Axios

**Backend:** Node.js, Express.js

**Database:** MongoDB Atlas, Mongoose

**Deployment:** Vercel (frontend), Render (backend)

## Project Structure

```
task-tracker/
├── client/                 # React frontend (Vite)
│   ├── src/
│   │   ├── api/
│   │   │   └── axios.js        # Axios instance with auth interceptor
│   │   ├── components/
│   │   │   ├── TaskCard.jsx    # Individual task card with actions
│   │   │   └── TaskModal.jsx   # Add/edit task modal form
│   │   ├── context/
│   │   │   └── AuthContext.jsx # Auth state and token management
│   │   └── pages/
│   │       ├── Login.jsx       # Login page
│   │       ├── Register.jsx    # Register page
│   │       └── Dashboard.jsx   # Main task dashboard
└── server/                 # Express backend
    ├── middleware/
    │   └── auth.js             # JWT verification middleware
    ├── models/
    │   ├── User.js             # User schema
    │   └── Task.js             # Task schema
    ├── routes/
    │   ├── auth.js             # Register and login routes
    │   └── tasks.js            # CRUD task routes
    └── index.js                # Entry point
```

## API Endpoints

### Auth
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/auth/register | Register new user |
| POST | /api/auth/login | Login and get token |

### Tasks (all protected)
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/tasks | Get all tasks for user |
| POST | /api/tasks | Create new task |
| PUT | /api/tasks/:id | Update task |
| DELETE | /api/tasks/:id | Delete task |

## Local Setup

### Prerequisites
- Node.js v18+
- MongoDB Atlas account

### Backend

```bash
cd server
npm install
```

Create `server/.env`:
```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=5000
```

```bash
node index.js
# MongoDB connected
# Server running on port 5000
```

### Frontend

```bash
cd client
npm install
```

Create `client/.env`:
```
VITE_API_URL=http://localhost:5000/api
```

```bash
npm run dev
# App running at http://localhost:5173
```

## Deployment

- **Frontend** deployed on [Vercel](https://vercel.com) — set `VITE_API_URL` in environment variables
- **Backend** deployed on [Render](https://render.com) — set `MONGO_URI` and `JWT_SECRET` in environment variables
