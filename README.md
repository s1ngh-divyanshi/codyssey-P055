# Codyssey — AI-Powered Collaborative Coding & Analytics Platform

[![Node.js](https://img.shields.io/badge/Node.js-v20%2B-green.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-v18%2B-blue.svg)](https://react.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-38bdf8.svg)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#)

**Codyssey** is an interactive learning and code evaluation platform designed for modern technical education. It combines an in-browser VS Code editor engine, isolated remote execution via Judge0, Socratic hint generation powered by Google Gemini 2.5 Flash, and student performance analytics.

---

## 🛠️ Tech Stack & System Architecture

### **Frontend (`/client`)**
- **Framework:** React.js (powered by Vite)
- **Styling:** Tailwind CSS
- **Code Editor:** Monaco Editor (`@monaco-editor/react`)
- **Data Visualization:** Recharts & Chart.js (`react-chartjs-2`)
- **Icons & Routing:** Lucide Icons & React Router DOM
- **HTTP Client:** Axios

### **Backend (`/server`)**
- **Runtime & Framework:** Node.js & Express.js
- **Database & ODM:** MongoDB & Mongoose
- **Authentication & Security:** JSON Web Tokens (JWT) & `bcryptjs`

### **External APIs & Sandboxing**
- **Code Execution:** Judge0 Remote Execution Engine
- **AI Tutoring:** Google Gemini API (`@google/genai` - Gemini 2.5 Flash)

---

## 📁 Repository Directory Tree

```text
codyssey/
├── client/          # React + Vite Frontend Application
├── server/          # Node.js + Express REST API Server
├── .gitignore       # Global Git Ignore Rules
├── package.json     # Root workspace configuration (Concurrent Runner)
└── README.md        # Main Project Documentation
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed locally before proceeding:

* **Node.js (v20+ LTS):** Run `node -v` to verify.
* **Git:** Run `git --version` to verify.
* **MongoDB Community Server:** Ensure MongoDB service is running locally on port `27017` (for local database connection).

---

### Installation & Local Setup

1. **Clone the Repository:**
```bash
git clone [https://github.com/s1ngh-divyanshi/codyssey-P055.git](https://github.com/s1ngh-divyanshi/codyssey-P055.git)
cd codyssey-P055
```


2. **Install All Project Dependencies:**
Install dependencies across the root, client, and server workspaces:
```bash
# Install root concurrently workspace runner
npm install

# Install frontend client dependencies
cd client && npm install

# Install backend server dependencies
cd ../server && npm install

# Return to project root
cd ..
```


3. **Configure Environment Variables:**
Create `.env` files in both subdirectories based on the provided templates:
**Backend Environment (`server/.env`):**
```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/codyssey_db
JWT_SECRET=your_super_secret_jwt_key
GEMINI_API_KEY=your_google_gemini_api_key
JUDGE0_API_URL=[https://judge0-ce.p.rapidapi.com](https://judge0-ce.p.rapidapi.com)
```


**Frontend Environment (`client/.env`):**
```env
VITE_API_BASE_URL=http://localhost:5000/api
```


4. **Run Client and Server Concurrently:**
From the root folder (`codyssey-P055`), run:
```bash
npm run dev
```


* **Frontend Client:** `http://localhost:5173`
* **Backend API Server:** `http://localhost:5000`



---

## 🌿 Git Workflow & Branching Guidelines

To maintain code stability, direct commits to `main` are restricted. All team members must work on dedicated feature branches.

### **Branch Naming Rules**

* **Frontend Tasks:** `feature/frontend-<feature-description>`
* **Backend Tasks:** `feature/backend-<feature-description>`

### **Branch Workflow**

```bash
# Switch to main and pull latest changes
git checkout main
git pull origin main

# Create and switch to your feature branch
git checkout -b feature/frontend-monaco-editor

# Stage, commit, and push your work
git add .
git commit -m "feat: add Monaco Editor component with theme switcher"
git push -u origin feature/frontend-monaco-editor

```

*Submit a Pull Request (PR) on GitHub for peer review before merging into `main`.*

```