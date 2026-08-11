# Codyssey — Frontend Client Application

[![React](https://img.shields.io/badge/React-v18%2B-blue.svg)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-v6%2B-646CFF.svg)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-38bdf8.svg)](https://tailwindcss.com/)

This directory houses the user interface for **Codyssey**, featuring an in-browser VS Code editor engine, real-time Socratic AI hint panels, interactive student analytics, and responsive problem-solving workspaces.

---

## 🛠️ Key Libraries & Packages

- **Vite & React 18:** Ultra-fast local HMR dev server and component-based UI platform.
- **Tailwind CSS v4:** Utility-first CSS styling integrated via the native `@tailwindcss/vite` plugin.
- **`@monaco-editor/react`:** Browser-based VS Code editor with full language syntax highlighting and theme control.
- **`recharts` & `chart.js` / `react-chartjs-2`:** Interactive performance visualization graphs for student analytics.
- **`axios`:** HTTP client for communicating with the Express REST API backend.
- **`lucide-react`:** Clean, flexible SVG icon library.
- **`react-router-dom`:** Dynamic client-side SPA routing.

---

## 📁 Directory Structure

```text
client/
├── public/              # Static assets (favicons, manifest)
├── src/
│   ├── assets/          # Static media files (SVGs, logos)
│   ├── components/      # Reusable UI components
│   │   ├── Editor/      # Monaco Editor wrapper, language selector, theme toggle
│   │   ├── Analytics/   # Recharts / Chart.js performance graphs
│   │   ├── Navigation/  # Navbar, Sidebar, and Footer
│   │   └── Common/      # Modals, Loading Spinners, Buttons
│   ├── context/         # React Context (AuthContext, ThemeContext)
│   ├── hooks/           # Custom React hooks (e.g., useAuth, useExecution)
│   ├── pages/           # Application route views (Dashboard, ProblemList, Workspace)
│   ├── services/        # Axios instances and API service endpoints
│   ├── App.jsx          # Top-level routing layout
│   ├── main.jsx         # Application entry point
│   └── index.css        # Tailwind CSS import directives (@import "tailwindcss";)
├── .env.example         # Client environment variable template
├── index.html           # Single Page Application HTML root
├── package.json         # Frontend manifest & script shortcuts
└── vite.config.js       # Vite build configuration with Tailwind plugin
```

---

## ⚙️ Development Commands

Ensure all commands are executed from inside the `client/` directory:

```bash
# 1. Install client dependencies
npm install

# 2. Start local development server (http://localhost:5173)
npm run dev

# 3. Build optimized production bundle
npm run build

# 4. Preview production build locally
npm run preview
```

---

## 🔐 Environment Variables

Create a local `.env` file in the `client/` root directory (refer to `.env.example`):

```env
VITE_API_BASE_URL=http://localhost:5000/api
```
