# Overpass-Radar

> **An advanced OSINT & Military Intelligence Radar Interface**

Overpass-Radar is a high-performance, professional-grade web application built to identify, track, and map military installations and restricted areas globally. Utilizing Leaflet, OpenStreetMap, and the Overpass API, it provides intelligent spatial clustering and visualization of base perimeters, sub-units, and restricted zones.

## Features

* **Global Coverage:** Fetch and visualize military infrastructure data from around the world.
* **Intelligent Spatial Clustering:** Seamlessly merges nearby military structures and scattered data points into coherent base perimeters.
* **Interactive Radar UI:** A dark-themed, enterprise-grade radar interface for an immersive investigative experience.
* **Dynamic Search:** Navigate to any country or coordinate instantly using the built-in geolocation search functionality.
* **Detailed Asset Breakdown:** View categorized military points (bunkers, barracks, airfields, communication arrays) within identified bases.
* **Real-time Overpass Integration:** Pulls up-to-date node, way, and relation data from OpenStreetMap.

## Technology Stack

* **Frontend:** React, React-Leaflet, Web Animations API, Vite
* **Backend:** Node.js, Express, Axios (for Overpass API querying)
* **Mapping:** Leaflet, OpenStreetMap CartoDB Dark Matter tiles

## Getting Started

### Prerequisites

* Node.js (v18 or higher)
* npm (Node Package Manager)



2. **Setup Backend:**
   ```bash
   cd backend
   npm install
   npm start
   ```
   *The backend server will run on `http://localhost:5000` by default.*

3. **Setup Frontend:**
   Open a new terminal window/tab:
   ```bash
   cd frontend
   npm install
   npm run dev
   ```
   *The frontend application will be available at `http://localhost:5173` (or the port specified by Vite).*

## Disclaimer

This tool leverages publicly available Open Source Intelligence (OSINT) data derived from OpenStreetMap. It is intended for educational, research, and OSINT analysis purposes only. 

## License

This project is licensed under the MIT License.

<img width="1916" height="956" alt="image" src="https://github.com/user-attachments/assets/bc45b4d2-0d01-4046-a99e-492e99dc8729" />

<img width="1913" height="957" alt="image" src="https://github.com/user-attachments/assets/fd8797c9-735e-4450-85c8-62ea3722ca54" />

<img width="1912" height="959" alt="image" src="https://github.com/user-attachments/assets/5bd11b7c-e0f6-409b-b1aa-2a377ead6647" />

<img width="1923" height="958" alt="image" src="https://github.com/user-attachments/assets/695940dc-1ea1-4581-b2d8-83ef3bc5d3bd" />

