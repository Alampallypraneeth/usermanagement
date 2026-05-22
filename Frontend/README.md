# 🎨 User Management System - Frontend Client

This is the premium, modern single-page application (SPA) client for the **User Management System**. Built on **React 19**, **Vite**, **Tailwind CSS v4**, and **React Router v7**, it provides an intuitive, high-performance dashboard to manage user data interactively.

---

## 🌟 Key Features

- **Glassmorphic Aesthetic UI**: Beautiful, premium dark-theme elements with smooth HSL gradient overrides, high-end styling, and immersive shadows.
- **Dynamic Routing**: Managed cleanly using React Router v7 with active path indicators and animated page layouts.
- **Dynamic Dashboards**: Comprehensive analytics widgets showing active/inactive statistics, age demographics, and recent signups.
- **Advanced Interactive User Grid**:
  - Full search filters to locate users instantly by name, email, or mobile.
  - Interactive Status Toggles (Active / Inactive) that patch user status instantly.
  - Responsive cards/tables for desktop, tablet, and mobile displays.
- **Validating Form Fields**: Direct validation for name, email formatting, age limits, date-of-birth, and mobile contact configurations.
- **Elegant Iconography**: Rich UI elements enriched with clean, responsive vector SVGs powered by `lucide-react`.

---

## 📂 Component Layout

```text
Frontend/
├── public/              # Static assets and browser favicons
├── src/
│   ├── assets/          # Static local image resources
│   ├── Components/      # Modular layout and page containers
│   │   ├── AddUser.jsx    # User creation and validation forms
│   │   ├── Footer.jsx     # Shared footer component
│   │   ├── Header.jsx     # Shared navigation header bar
│   │   ├── Home.jsx       # Analytics dashboard and welcome views
│   │   ├── RootLayout.jsx # Parent template wrapper for app routing
│   │   ├── User.jsx       # Individual user visual card presentation
│   │   └── UserList.jsx   # Managed list grid with controls & search filters
│   ├── App.css          # App-wide visual enhancements
│   ├── App.jsx          # React Router router definition & bootstrapping
│   ├── config.js        # Global app settings (API endpoints, environment fallbacks)
│   ├── index.css        # Core Tailwind CSS configuration & import rules
│   └── main.jsx         # React application DOM mounter
├── eslint.config.js     # Code quality and syntax rulesets
├── index.html           # Document template shell
├── package.json         # Scripts, configurations, and packages list
└── vite.config.js       # Vite build configurations
```

---

## 🛠️ Setup & Installation

### 1. Prerequisites
- **Node.js** (version 18 or newer recommended)
- Running instance of the [Backend API](file:///Users/alampallypraneeth/Desktop/week-8-main/Backend/README.md)

### 2. Install Dependencies
Run the following inside the `Frontend` directory:
```bash
npm install
```

### 3. API Connection Configuration
The application communicates with the backend API via the configuration located in `src/config.js`. 
By default, the frontend relies on the environment variable `VITE_API_URL`.

If you are running the backend server locally (e.g. on port `5000`), specify the URL before starting or let the system default to the fallback endpoint:
```env
VITE_API_URL=http://localhost:5000
```

### 4. Run the Application

- **Development Server** (Fast refresh enabled on save):
  ```bash
  npm run dev
  ```

- **Build for Production**:
  ```bash
  npm run build
  ```
  *This builds optimized static files inside the `dist/` folder.*

- **Local Preview**:
  ```bash
  npm run preview
  ```
  *Serves the production build locally to test speed and loading performance.*

---

## 🚀 Technologies Implemented

- **React 19**: Utilizing modern functional components, standard hooks, and the Virtual DOM for highly optimized renders.
- **Vite 7**: Ultra-fast hot module replacement (HMR) and instantaneous build processes.
- **Tailwind CSS v4**: Utility-first CSS compiling utilizing the new Vite integration engine for minimal build footprints.
- **React Router v7**: Responsive client-side routing.
- **Lucide React**: Premium UI icons rendering SVG vectors.
