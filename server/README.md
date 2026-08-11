
### Server Directory (`/server/README.md`)

```markdown
# Codyssey — Backend Server API

This directory contains the Express.js REST API server, MongoDB Mongoose ODM layer, and third-party integrations for Judge0 and Google Gemini API.

---

## 🛠️ Key Libraries & Services

- **Express.js:** Web application framework for Node.js.
- **Mongoose:** Object Data Modeling (ODM) library for MongoDB.
- **JWT (`jsonwebtoken`) & `bcryptjs`:** User authentication, authorization middleware, and password hashing.
- `@google/genai`: Official Google Gemini API client for Socratic hint generation.
- **Judge0 API:** Remote sandboxed engine for multi-language code compilation and evaluation.
- `cors` & `dotenv`: Cross-Origin Resource Sharing handling and configuration loading.

---

## 📁 Directory Structure

```text
server/
├── src/
│   ├── config/          # Database configuration (db.js)
│   ├── controllers/     # Controller logic (Auth, Problems, Submissions, AI)
│   ├── middleware/      # JWT auth verification, error handling
│   ├── models/          # Mongoose Schemas (User.js, Problem.js, Submission.js)
│   ├── routes/          # Express REST API routes
│   ├── utils/           # Gemini API & Judge0 helpers
│   └── server.js        # Express application entry point
├── .env.example         # Server environment variable template
└── package.json         # Backend package manifest

```

---

## ⚙️ Development Commands

Run all commands inside the `server/` folder:

```bash
# Install backend dependencies
npm install

# Start server using nodemon (auto-reload)
npm run dev

# Start server in production mode
npm start

```

---

## 🔐 Environment Variables Configuration

Create a `.env` file inside the `server/` directory:

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/codyssey_db
JWT_SECRET=your_super_secret_jwt_key
GEMINI_API_KEY=your_google_gemini_api_key
JUDGE0_API_URL=[https://judge0-ce.p.rapidapi.com](https://judge0-ce.p.rapidapi.com)

```

---

## 🛰️ Base API Routes

* **Health Check:** `GET /api/health`
* **Authentication:** `/api/auth` (`/register`, `/login`, `/me`)
* **Problems:** `/api/problems` (`GET /`, `GET /:id`, `POST /`)
* **Execution & Judge0:** `/api/submissions` (`POST /run`, `POST /submit`)
* **AI Hints:** `/api/ai/hint` (`POST /generate-hint`)

```

```