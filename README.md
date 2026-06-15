# ✦ AI Trip Planner ✦

Welcome to the **AI Trip Planner** project! This is a state-of-the-art, premium web application designed to generate, manage, and customize personalized travel itineraries using AI. Featuring a responsive **glassmorphic "Cosmic" dark design system**, interactive mapping, real-time weather forecasts, high-fidelity PDF exporting, and fully-featured Admin RBAC with EmailJS-driven 2FA authentication, it delivers an exceptional user and administrator experience.

---

## 🌌 Key Highlights & Features

### 👤 Traveler Experience
- **Interactive AI Generation Dashboard**: Input destinations, choose travel duration, select budget profiles, specify traveler compositions (solo, couple, family, friends), pick areas of interest, and generate custom AI itineraries.
- **Saved Trips Console**: Access, view, edit, and delete saved itineraries.
- **High-Fidelity PDF Exporter**: Export generated itineraries into beautiful, print-ready PDF files with custom styles, headers, and structured tables.
- **Maps & Weather Integration**: Embedded maps and weather forecasts corresponding to chosen destinations for seamless travel preparation.

### 🛡️ Administrative Controls & Security
- **Role-Based Access Control (RBAC)**: Custom routing middleware (`ProtectedRoutes.js`) separating regular travelers (`USER`) and system operators (`ADMIN`).
- **2FA OTP Verification**: The Admin Portal uses EmailJS to send a 2-Factor Authentication One-Time Password (OTP) to registered admin emails for verification during login.
- **Admin Management Hub**: View and manage all registered users, generated trips, and bookings.

---

## 🛠️ Technology Stack

- **Framework**: [React 19](https://react.dev/) & [React Router DOM v7](https://reactrouter.com/)
- **UI Styling**: Vanilla CSS + [Bootstrap 5](https://getbootstrap.com/) for fluid responsive grids, enhanced with a custom **Cosmic Glassmorphic Design System** (custom input elements, smooth floating animations, gradient accents, and dark/space theme styling utilizing the modern **Outfit** font).
- **Mapping & Geo-Location**: [Leaflet](https://leafletjs.com/) & [React Leaflet v5](https://react-leaflet.js.org/) for interactive tile-map renderings.
- **PDF Generation**: [jsPDF](https://github.com/parallax/jsPDF) for client-side document layout design and distribution.
- **Communications**: [@emailjs/browser](https://www.emailjs.com/) for secure OTP email dispatching.
- **Client Networking**: [Axios](https://axios-http.com/) for API requests.

---

## 📁 Directory & File Layout

Below is the layout of the project, detailing the roles of the main files:

```bash
AI Trip Planner/
├── package.json              # Root dependencies (package aliases)
└── frontend/                 # Main frontend application workspace
    ├── package.json          # Frontend dependencies & scripts
    ├── .env                  # Configuration variables (EmailJS keys, etc.)
    ├── public/               # Public assets & static index template
    └── src/                  # Application source code
        ├── App.js            # Main React router config and layout setup
        ├── App.css           # Global fallback styling
        ├── index.js          # App entry point (ReactDOM mounting, CSS imports)
        ├── index.css         # Cosmic Glassmorphic Design System configuration
        ├── components/       # Reusable user interface widgets
        │   ├── Navbar.js            # Cosmic navigation bar (RBAC-aware)
        │   ├── ProtectedRoutes.js   # Route guards verifying token/role
        │   ├── Weather.js           # Live destination weather widgets
        │   ├── MapComponent.js      # Map display interface
        │   └── TripImage.js         # Contextual image fetcher for destinations
        ├── pages/            # View pages mapped to application routes
        │   ├── Home.js              # Introduction landing page
        │   ├── login.js             # User login portal
        │   ├── Signup.js            # User registration portal
        │   ├── Dashboard.js         # The AI trip planner customization wizard
        │   ├── SavedTrips.js        # Traveler saved itineraries dashboard
        │   ├── AdminLogin.js        # Admin login portal with 2FA/OTP execution
        │   ├── AdminSignup.js       # Admin registration page
        │   ├── AdminDashboard.js    # Operational overview metrics console
        │   ├── ManageUsers.js       # User accounts lookup/deletion controls
        │   ├── ManageTrips.js       # Custom generated trips review center
        │   └── ManageBookings.js    # Booking logs administration interface
        └── services/         # API clients and utilities
            ├── api.js               # Centralized Axios base & API requests
            └── pdfExporter.js       # Advanced jsPDF layout creator
```

---

## 🚀 Setting Up the Project

### 1. Installation
To get started with the project, clone this repository, install the dependencies, and configure the project:

```bash
# 1. Install frontend packages
cd frontend
npm install
```

### 2. Configure Environment Variables
Inside the `frontend` folder, locate the `.env` file and replace the placeholder credentials with your **EmailJS** details:

```env
# EmailJS Configurations for Admin 2FA OTP
REACT_APP_EMAILJS_SERVICE_ID=your_service_id_here
REACT_APP_EMAILJS_TEMPLATE_ID=your_template_id_here
REACT_APP_EMAILJS_PUBLIC_KEY=your_public_key_here
```

### 3. Run the Development Server
Run the local server inside the `frontend` directory:

```bash
npm start
```
The application will launch by default at [http://localhost:3000](http://localhost:3000).

---

## 🎨 Theme Guidelines & Design System

The application's theme is defined in `frontend/src/index.css` using modern CSS variables. Key variables include:
- `--bg-space`: Base dark theme background color.
- `--gradient-cosmic`: Vibrant violet-to-cyan gradient for high-quality accents and primary interactive elements.
- `--card-glass`: Semi-transparent card styling with blur effects (`backdrop-filter: blur(16px)`).
- Typography: Uses the **Outfit** Google Font for high-readability modern typography.
