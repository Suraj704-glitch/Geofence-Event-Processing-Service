# Geofence Event Service

A MERN stack application that tracks vehicle movements and detects when they enter or exit specific geographic zones.

## 🚀 Setup Instructions

### Prerequisites
* Node.js
* MongoDB (running locally)

### 1. Backend Setup
1. Navigate to the backend folder: `cd backend`
2. Install dependencies: `npm install`
3. Start the server: `npm run dev` (Runs on Port 5000)

### 2. Frontend Setup (Dashboard)
1. Navigate to the frontend folder: `cd frontend`
2. Install dependencies: `npm install`
3. Start the UI: `npm start` (Runs on Port 3000)

## 🏗️ Design Decisions
* **Architecture:** Used **MVC (Model-View-Controller)** to separate business logic from routing and data storage.
* **Database:** Used **MongoDB** to persist vehicle state. This ensures we don't lose the "last known location" if the server restarts.
* **Math:** Used `geolib` library for accurate Haversine distance calculations instead of manual math implementation to ensure precision.

## 🧪 Assumptions
* Zones are circular and defined by a center point and radius.
* GPS updates arrive in chronological order.
* Zones do not overlap (logic prioritizes the first zone found).

## 🔮 Future Improvements
* **Redis Caching:** Use Redis to store the latest vehicle state for faster lookups instead of hitting MongoDB every time.
* **WebSockets:** Replace HTTP polling with WebSockets for real-time dashboard updates.
* **Unit Tests:** Add Jest/Supertest to automate API testing.