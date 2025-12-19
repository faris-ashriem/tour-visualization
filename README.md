# Tour Visualization

Interactive web application that visualizes live music tours and events on a 3D globe.  
The system allows users to search for artists, view upcoming events, and explore tour locations using real-time data from the Ticketmaster API.

---

# Features

- Visualizes concert tours and events on a 3D Cesium globe.
- Artist-based search using the Ticketmaster Discovery API.
- Interactive event markers with smooth camera fly-to animations.
- Overlay widget for browsing and selecting upcoming events.
- Graceful handling of invalid searches or no results.
- Clean and responsive UI designed for desktop use.

---

# How It Works

### 1. Data Retrieval
- The backend queries the Ticketmaster API for artists, events, and venue data.
- Event data includes artist name, venue, city, date, and geographic coordinates.

### 2. Backend Processing
- Built using a .NET 8 Minimal API.
- Acts as a secure proxy to prevent exposing the Ticketmaster API key.
- Filters and normalizes API responses before sending them to the frontend.

### 3. Frontend Visualization
- Built with Angular and CesiumJS.
- Event locations are plotted on a 3D globe using latitude and longitude.
- Selecting an event animates the camera to the event location.

### 4. User Interaction
- Users search for an artist using a debounced search input.
- Matching events appear in a widget panel.
- Selecting an event updates the globe and highlights the location.

---

# Tech Stack

### Frontend
- Angular 20
- CesiumJS
- RxJS
- PrimeNG

### Backend
- .NET 8 Minimal API
- C#
- HttpClient

---

# Dependencies

- Node.js
- Angular CLI
- .NET SDK 8.0

---

# API

This project uses the **Ticketmaster Discovery API** to retrieve:
- Artists
- Events
- Venue locations

An API key is required to run the backend service.

---

# Running the Project

### Backend
- `dotnet watch run --urls http://localhost:3000/`

### Frontend
- `ng serve --proxy-config proxy.config.json`
- Application runs at `http://localhost:4200`

---

# Notes

- Events without valid geographic coordinates will not appear on the globe.
- The backend proxy is required to protect the Ticketmaster API key.
- Designed primarily for desktop use due to 3D rendering requirements.
