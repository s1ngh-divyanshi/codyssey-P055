# Codyssey — Frontend Client Application

This directory contains the user interface for Codyssey, built with React, Vite, Tailwind CSS, and the Monaco Editor engine.

---

## 🛠️ Key Libraries & Packages

- **Vite & React 18:** Ultra-fast frontend development build tool and component architecture.
- **Tailwind CSS v4:** Utility-first styling framework integrated via `@tailwindcss/vite`.
- `@monaco-editor/react`: VS Code editor integration for in-browser coding.
- `recharts` / `chart.js` & `react-chartjs-2`: Interactive analytics dashboards.
- `axios`: HTTP client for backend REST API integration.
- `lucide-react`: Modern SVG icon collection.
- `react-router-dom`: Client-side routing.

---

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

=======
## 📁 Directory Structure

```text
client/
├── public/              # Static assets
├── src/
│   ├── assets/          # SVGs, images
│   ├── components/      # Reusable UI components
│   │   ├── Editor/      # Monaco Editor wrapper and controls
│   │   └── Analytics/   # Recharts / Chart.js graphs
│   ├── context/         # React Context (AuthContext, ThemeContext)
│   ├── hooks/           # Custom React hooks (e.g., useAuth, useExecution)
│   ├── pages/           # Views (Dashboard, ProblemList, Workspace)
│   ├── services/        # Axios API instances & API calls
│   ├── App.jsx          # App entry routing
│   ├── main.jsx         # React root initialization
│   └── index.css        # Tailwind CSS import directives
├── .env.example         # Client environment variable template
├── index.html           # HTML entry point
├── package.json         # Frontend package manifest
└── vite.config.js       # Vite configuration with Tailwind plugin

```

---

## ⚙️ Development Commands

Run all commands inside the `client/` folder:

```bash
# Install client dependencies
npm install

# Start local development server (http://localhost:5173)
npm run dev

# Build production bundle
npm run build

# Preview production build locally
npm run preview

```

---

## 🔐 Environment Variables

Create a `.env` file in `client/`:

```env
VITE_API_BASE_URL=http://localhost:5000/api

```
