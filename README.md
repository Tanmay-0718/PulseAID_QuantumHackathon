🚑 PulseAID — Real-Time ICU & Ambulance Tracking System
Connecting Lives to Care in Real-Time

What is PulseAID?
PulseAID is an AI-powered emergency healthcare coordination platform that eliminates the deadly delay between a medical emergency and the right care. In a crisis, patients and families waste precious minutes calling hospitals one by one, unsure of ICU availability, ambulance proximity, or whether their insurance is accepted. PulseAID solves this with a single, intelligent dashboard.

The platform provides real-time ICU bed availability across hospitals, live ambulance tracking from dispatch to arrival, and a smart matching engine that filters hospitals by insurance coverage, cost, distance, and doctor availability — all presented on an interactive map interface.

The Problem
When a medical emergency strikes, patients face a fragmented, broken system:

No centralized ICU visibility — families call hospital after hospital manually
No ambulance tracking — no way to know which ambulance is nearest or available
No insurance-aware routing — patients end up at hospitals that don't accept their scheme
No doctor availability data — a specialist may be available at Hospital A but not Hospital B on a given day
Critical time lost — every minute of delay directly impacts survival outcomes
The Solution
PulseAID is a map-first web application that provides:

Feature	What It Does
Live ICU Map	Color-coded hospital markers showing real-time bed availability
Ambulance Dispatch	Nearest ambulance auto-assigned and tracked from hospital to user
Smart Matching Engine	Filters and ranks hospitals by insurance, cost, distance, and doctor
Doctor Registry	Search doctors by name or specialty; view their hospital schedule
Hospital Portal	Hospitals update ICU counts, doctor availability, and accepted schemes
Route Simulation	Ambulance follows real road routes with live ETA countdown
Key Features
For Patients (User Portal)
Select insurance type, budget, and priority preference
View ranked list of best-matched hospitals on the map
One-tap ambulance request with live tracking
Doctor search by name or specialty with cross-hospital schedule
Real-time ETA updates as ambulance approaches
For Hospitals (Admin Portal)
Update ICU bed counts and equipment availability
Manage doctor roster with shift scheduling
Toggle accepted insurance schemes and government programs
View incoming patient location and ETA to prepare
Smart Matching Logic
The platform cross-references user profile data (insurance, budget) against hospital capabilities (schemes accepted, cost level, ICU availability, doctor schedule) to recommend the optimal hospital — not just the nearest one.

Tech Stack
Layer	Technology
Frontend	React.js (Vite)
Styling	Tailwind CSS
Maps & Routing	Mapbox GL JS + Directions API
State Management	React State (Context API)
Backend (Simulated)	Mock API service layer (replaceable with real APIs)
Hosting	Vercel / Netlify
Architecture Overview
┌─────────────────────────────────────┐
│           React Frontend             │
│  ┌──────────┐  ┌──────────────────┐ │
│  │ Map View │  │  Bottom Sheet UI │ │
│  └──────────┘  └──────────────────┘ │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│          Service Layer               │
│  hospitalService  │  doctorService  │
│  ambulanceService │  authService    │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│          Logic Layer                 │
│  Matching Engine  │  Simulation Eng  │
│  ETA Calculator   │  Route Animator  │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│       Mock Data Layer (JSON)         │
│  hospitals.json  │  ambulances.json  │
│  doctors.json    │  schemes.json     │
└─────────────────────────────────────┘
         (Replaceable with real APIs)
Quick Start
# Clone the repository
git clone https://github.com/your-username/PulseAID.git
cd PulseAID

# Install dependencies
npm install

# Add your Mapbox token to .env
echo "VITE_MAPBOX_TOKEN=your_token_here" > .env

# Start development server
npm run dev
Project Structure
PulseAID/
├── src/
│   ├── components/          # UI components
│   │   ├── MapView.jsx
│   │   ├── BottomSheet.jsx
│   │   ├── HospitalCard.jsx
│   │   ├── DoctorModal.jsx
│   │   └── StatusPanel.jsx
│   ├── services/            # API abstraction layer
│   │   ├── hospitalService.js
│   │   ├── ambulanceService.js
│   │   ├── doctorService.js
│   │   └── authService.js
│   ├── logic/               # Business logic
│   │   ├── matchingEngine.js
│   │   └── simulationEngine.js
│   ├── data/                # Mock data (replaceable)
│   │   ├── hospitals.json
│   │   ├── ambulances.json
│   │   └── doctors.json
│   └── pages/
│       ├── UserDashboard.jsx
│       └── HospitalDashboard.jsx
├── public/
├── .env
└── package.json
Demo Flow
Open app → Full-screen map loads with hospital markers
Select preferences → Insurance type, budget, priority
System ranks hospitals → Best match highlighted with tag
Request ambulance → Nearest unit assigned automatically
Live tracking begins → Ambulance moves along route on map
ETA updates live → "Arriving in 4 min", "2 min", "Arrived"
Hospital notified → Admin portal shows incoming patient and prep status
Hackathon Context
PulseAID was built for a national-level hackathon addressing the problem statement: "Patients struggle to find available ICU beds and ambulances during emergencies."

Phase 1 — Core map dashboard with ICU tracking and ambulance simulation.

Phase 2 — Full ecosystem: smart matching engine, doctor registry, dual-role portals (user + hospital), insurance-aware routing, and live ambulance dispatch simulation.

Future Roadmap
Integration with ABDM (Ayushman Bharat Digital Mission) APIs
Real ambulance GPS via WebSockets
ABHA (Ayushman Bharat Health Account) identity integration
Aadhaar-linked document verification
Mobile application (React Native)
Government emergency services API integration (112 India)
Team
Built with purpose — because in an emergency, every second counts.

PulseAID — Prototype. Built for rapid deployment, designed for real-world scale.
