# Notes App

A full-stack note-taking application with real-time updates, version history, and note protection features.

## Features

- **User Authentication**: Register, login, and profile management
- **Note Management**: Create, read, update, and delete notes
- **Real-time Updates**: Get notifications when notes are modified (via Socket.IO)
- **Note Protection**: Password-protect sensitive notes
- **Version History**: Track changes to notes over time
- **Responsive UI**: Built with React and Tailwind CSS

## Project Structure

The project is divided into two main parts:

### Backend (`Note_backend`)

- Node.js and Express server
- Prisma ORM with MySQL database
- Authentication using JWT
- Socket.IO for real-time updates
- RESTful API endpoints

### Frontend (`Note_frontend`)

- React with Vite
- React Router for navigation
- Tailwind CSS for styling
- Context API for state management
- Socket.IO client for real-time updates
- Form validation with Zod

## Prerequisites

- Node.js (v14 or later)
- MySQL database
- npm or yarn

## Setup Instructions

### Backend Setup

1. Navigate to the backend directory:
   ```
   cd Note_backend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create a `.env` file with the following variables:
   ```
   DATABASE_URL="mysql://username:password@localhost:3306/notes_db"
   JWT_SECRET="your-jwt-secret-key"
   PORT=5000
   NODE_ENV=development
   SEED_DATABASE=false
   ```

4. Run database migrations:
   ```
   npx prisma migrate dev
   ```

5. (Optional) Seed the database:
   ```
   npm run seed
   ```

6. Start the development server:
   ```
   npm run dev
   ```

### Frontend Setup

1. Navigate to the frontend directory:
   ```
   cd Note_frontend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create a `.env` file with the following variables:
   ```
   VITE_API_URL=http://localhost:5000/api
   ```

4. Start the development server:
   ```
   npm run dev
   ```

5. Open your browser and navigate to `http://localhost:5173`

## API Endpoints

### Authentication Routes
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login an existing user
- `GET /api/auth/logout` - Logout current user
- `GET /api/auth/me` - Get current user info

### User Routes
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile

### Note Routes
- `GET /api/notes` - Get all notes for current user
- `POST /api/notes` - Create a new note
- `GET /api/notes/:id` - Get a specific note
- `PUT /api/notes/:id` - Update a note
- `DELETE /api/notes/:id` - Delete a note
- `GET /api/notes/:id/versions` - Get version history of a note
- `POST /api/notes/:id/unlock` - Unlock a protected note

## Technologies Used

### Backend
- Express.js
- Prisma ORM
- Socket.IO
- JSON Web Token (JWT)
- bcrypt.js

### Frontend
- React
- React Router
- Tailwind CSS
- Axios
- Socket.IO Client
- React Hot Toast
- Zod (form validation)

## License

ISC

## Author

[Your Name] 