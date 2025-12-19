Tour Visualization

An interactive web application that visualizes live music tours and events on a 3D globe.
Users can search for artists, explore upcoming events, and see tour locations rendered spatially using a Cesium-powered Earth visualization.

How It Works
1. Data Retrieval

The backend queries the Ticketmaster API for artists, events, and venue data.

Event information includes artist name, venue, city, date, and geographic coordinates.

Results are filtered and formatted before being sent to the frontend.

2. Backend Processing

Built using a .NET 8 Minimal API.

Acts as a secure proxy between the frontend and the Ticketmaster API.

Handles API key protection, request validation, and response normalization.

3. Frontend Visualization

Built with Angular 20.

Uses CesiumJS to render a 3D globe displaying event locations.

Events are plotted as markers on the globe based on latitude and longitude.

Selecting an event animates the camera to the event location.

4. User Interaction

Users search for an artist using a debounced search input.

Matching events are displayed in a widget panel.

Selecting an event updates the globe view and highlights the event.

Features

Visualizes concert tours on a 3D globe.

Artist-based event search using the Ticketmaster API.

Interactive Cesium globe with smooth camera transitions.

Clean, responsive UI with overlay widgets.

Graceful handling of empty results or invalid searches.

Backend API abstraction to protect sensitive API keys.

Tech Stack
Frontend

Angular 20

CesiumJS

RxJS

PrimeNG (UI components)

Backend

.NET 8 Minimal API

C#

HttpClient

Dependencies
Frontend

Node.js

Angular CLI

CesiumJS

Backend

.NET SDK 8.0

Dataset / API

This project uses live data from the Ticketmaster Discovery API.

Artist search

Event listings

Venue locations

An API key is required to run the backend.

Running the Project
Backend

Start the backend server using:

dotnet watch run --urls http://localhost:3000/

The backend exposes API endpoints under /api.

Frontend

Start the Angular development server using:

ng serve --proxy-config proxy.config.json

The application runs on http://localhost:4200.

Notes

Events without valid geographic coordinates will not appear on the globe.

The application focuses on live and upcoming events.

The backend proxy is required to avoid exposing the Ticketmaster API key.

Designed primarily for desktop use due to 3D rendering requirements.
