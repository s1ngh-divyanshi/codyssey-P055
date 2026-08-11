### Root (`/README.md`)

```markdown
# Codyssey — AI-Powered Collaborative Coding & Analytics Platform

Codyssey is an interactive learning and code evaluation platform. It features an in-browser code editor, automated remote code execution via Judge0, AI-driven Socratic hint generation using Google Gemini 2.5 Flash, and detailed student analytics dashboards.

---

## 🛠️ Tech Stack & Architecture

- **Frontend (`/client`):** React.js (Vite), Tailwind CSS, Monaco Editor (`@monaco-editor/react`), Recharts / Chart.js, Lucide Icons, Axios, React Router.
- **Backend (`/server`):** Node.js, Express.js, MongoDB (Mongoose), JSON Web Tokens (JWT), bcryptjs.
- **External APIs:** Judge0 API (Code Sandboxing), Google Gemini API (`@google/genai`).

---

## 📁 Repository Structure

```text
codyssey/
├── client/          # React + Vite Frontend Application
├── server/          # Node.js + Express Backend API
├── .gitignore       # Root Git Ignore Rules
├── package.json     # Monorepo concurrent runner
└── README.md        # Root Documentation

```

---

## 🚀 Quick Start Guide

### Prerequisites

Ensure the following tools are installed on your machine:

* **Node.js**: v20+ LTS (`node -v`)
* **Git**: (`git --version`)
* **MongoDB Community Server**: Running locally on port `27017`

### Setup Instructions

1. **Clone the Repository:**
```bash
git clone [https://github.com/YOUR_GITHUB_USERNAME/codyssey.git](https://github.com/YOUR_GITHUB_USERNAME/codyssey.git)
cd codyssey

```


2. **Install All Dependencies:**
```bash
# Install root concurrently runner
npm install

# Install client dependencies
cd client && npm install

# Install server dependencies
cd ../server && npm install
cd ..

```


3. **Configure Environment Variables:**
* Setup `server/.env` using `server/.env.example` as reference.
* Setup `client/.env` using `client/.env.example` as reference.


4. **Run both Client and Server Concurrently:**
From the root folder, run:
```bash
npm run dev

```


* **Client App:** `http://localhost:5173`
* **Server API:** `http://localhost:5000`



---

## 🌿 Git Branching Strategy

* `main`: Protected production branch.
* Feature branches:
* Frontend members: `git checkout -b ft/frontend-<feature-name>`
* Backend members: `git checkout -b ft/backend-<feature-name>`


* Create a Pull Request (PR) on GitHub before merging into `main`.

```