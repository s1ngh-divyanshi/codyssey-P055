# Codyssey — Backend Server API

[![Node.js](https://img.shields.io/badge/Node.js-v20%2B-green.svg)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-v4.x-000000.svg)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248.svg)](https://www.mongodb.com/)
[![Gemini API](https://img.shields.io/badge/Google_Gemini-2.5_Flash-8E75B2.svg)](https://ai.google.dev/)

This directory houses the REST API server for **Codyssey**, handling user authentication, MongoDB database management, remote sandboxed code execution via Judge0, and Socratic hint generation using Google Gemini 2.5 Flash.

---

## 🛠️ Key Libraries & Services

- **Express.js:** Web application framework managing RESTful API routes and middleware pipelines.
- **Mongoose ODM:** Schema-based data modeling for MongoDB (Users, Problems, Submission logs).
- **`jsonwebtoken` & `bcryptjs`:** JWT-based stateless authentication, protected routes, and password hashing.
- **`@google/genai`:** Official SDK for Google Gemini 2.5 Flash API to generate real-time Socratic hints.
- **Judge0 API:** Sandboxed remote execution engine for compiling and evaluating code across multiple programming languages.
- **`cors` & `dotenv`:** Cross-Origin Resource Sharing management and environment variable loading.

---

## 📁 Directory Structure

```text
server/
├── src/
│   ├── config/          # Database connection setup (db.js)
│   ├── controllers/     # Business logic handlers (Auth, Problems, Submissions, AI)
│   ├── middleware/      # JWT authorization verify, error handling, validation
│   ├── models/          # Mongoose Schemas (User.js, Problem.js, Submission.js)
│   ├── routes/          # Express REST API routes
│   ├── utils/           # Gemini API client & Judge0 payload helpers
│   └── server.js        # Server entry point & Express app configuration
├── .env.example         # Template for environment configurations
└── package.json         # Server package manifest & script definitions
```

---

## ⚙️ Development Commands

Ensure all commands are executed from inside the `server/` directory:

```bash
# 1. Install server dependencies
npm install

# 2. Start server in development mode (with nodemon auto-reload)
npm run dev

# 3. Start server in production mode
npm start
```

---

## 🔐 Environment Variables Configuration

Create a local `.env` file in the `server/` root directory (refer to `.env.example`):

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/codyssey_db
JWT_SECRET=your_super_secret_jwt_key
GEMINI_API_KEY=your_google_gemini_api_key
JUDGE0_API_URL=[https://judge0-ce.p.rapidapi.com](https://judge0-ce.p.rapidapi.com)
```

---

## 🛰️ Base REST API Routes

| Endpoint | Method | Description | Protected (JWT) |
| --- | --- | --- | --- |
| `/api/health` | `GET` | Server health check status | No |
| `/api/auth/register` | `POST` | Register a new user account | No |
| `/api/auth/login` | `POST` | Authenticate user and issue JWT | No |
| `/api/auth/me` | `GET` | Get authenticated user profile | Yes |
| `/api/problems` | `GET` | Fetch list of coding problems | No |
| `/api/problems/:id` | `GET` | Fetch specific problem details | No |
| `/api/problems` | `POST` | Create a new problem (Admin) | Yes |
| `/api/submissions/run` | `POST` | Execute code against sample test cases via Judge0 | Yes |
| `/api/submissions/submit` | `POST` | Submit code solution for evaluation & logging | Yes |
| `/api/ai/generate-hint` | `POST` | Generate Socratic guidance using Gemini API | Yes |
