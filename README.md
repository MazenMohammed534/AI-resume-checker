# AI Resume Checker

A modern MERN-stack application that helps users evaluate and improve their resumes with AI-powered ATS insights, rewrite suggestions, version history, and a polished dashboard experience.

## Overview

AI Resume Checker is designed to make resume optimization simpler and more actionable. Users can upload a resume, receive an ATS-style score, identify weak areas, compare versions, and apply AI-generated rewrites tailored to a target role or job description.

## Key Features

- Resume upload and parsing
- ATS score analysis with actionable feedback
- AI-generated bullet rewrites and keyword suggestions
- Version tracking and change comparison
- Dashboard with performance insights and history
- Authentication and protected user data
- Responsive, modern UI built with React and Vite

## Tech Stack

### Frontend

- React
- Vite
- React Router
- Tailwind CSS
- Framer Motion
- Axios
- React Query

### Backend

- Node.js
- Express
- MongoDB with Mongoose
- JWT authentication
- Multer for file handling
- PDF parsing
- Google Gemini AI integration

## Project Structure

```text
AI Resume Checker
├── backend/
│   └── src/
│       ├── config/
│       ├── middleware/
│       ├── models/
│       ├── routes/
│       ├── services/
│       └── utils/
└── frontend/
    └── src/
        ├── api/
        ├── components/
        ├── context/
        ├── hooks/
        └── pages/
```

### Simple Architecture Diagram

```text
User → Frontend (React/Vite)
          │
          ▼
   API Requests
          │
          ▼
Backend (Express/Node.js)
          │
   ├── Auth & Users
   ├── Resume Upload & Parsing
   ├── ATS Analysis & AI Rewrites
   └── MongoDB Storage
```

### Flow of a Resume Review

```text
Upload Resume
   ↓
Parse & Store
   ↓
Analyze ATS Score
   ↓
Suggest Improvements
   ↓
Save New Version
   ↓
Show Dashboard & History
```

## Prerequisites

Before running the project locally, make sure you have:

- Node.js 20 or higher
- npm or pnpm
- MongoDB running locally or a MongoDB Atlas connection string
- A Google Gemini API key

## Installation

1. Clone the repository

   ```bash
   git clone <your-repo-url>
   cd "AI Resume Checker"
   ```

2. Install backend dependencies

   ```bash
   cd backend
   npm install
   ```

3. Install frontend dependencies
   ```bash
   cd ../frontend
   npm install
   ```

## Environment Variables

Create a `.env` file inside the backend folder with the following variables:

```env
PORT=5000
NODE_ENV=development
MONGO_URI=mongodb://127.0.0.1:27017/ai-resume-checker
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=7d
COOKIE_NAME=arr_token
CLIENT_ORIGIN=http://localhost:5173
GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-2.5-flash
```

## Running the Application

### With Docker

```bash
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env
docker compose up --build
```

This will start:

- MongoDB on port 27017
- Backend on port 5000
- Frontend on port 5173

> For local development, you can edit the copied .env files without committing them.

### Start the backend

```bash
cd backend
npm run dev
```

The backend will run on:

```text
http://localhost:5000
```

### Start the frontend

```bash
cd frontend
npm run dev
```

The frontend will run on:

```text
http://localhost:5173
```

## API Overview

The backend exposes REST endpoints for:

- Authentication (`/api/auth`)
- Resume management (`/api/resumes`)
- Dashboard data (`/api/dashboard`)
- Insights and analytics (`/api/insights`)
- Version history (`/api/versions`)
- History tracking (`/api/history`)
- Health checks (`/api/health`)

## Development Notes

- The frontend uses Vite for fast development and build tooling.
- The backend uses modular route and service structure for scalability.
- AI analysis is powered through the Gemini service layer.

## License

This project is licensed under the ISC License.

## Contributing

Contributions are welcome. If you want to improve the project, feel free to open an issue or submit a pull request.
