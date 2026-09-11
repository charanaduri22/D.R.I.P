# DRIP — Disaster Relocation Intelligence Platform

An intelligent disaster-relocation decision-support prototype built for **SIH 26191** with a high-tech "Blue Cyberpunk HUD / Terminal" aesthetic inspired by sci-fi command systems.

## About

We are building an intelligent disaster-relocation decision-support platform. The prototype analyzes hazard intensity, population vulnerability, disaster history, geographical factors, and local infrastructure to identify high-risk habitations and classify their risk level.

The system evaluates safer areas based on accessibility and carrying capacity and recommends suitable relocation zones and directions for vulnerable communities.

Our goal is to help disaster-management authorities make **faster, data-driven, explainable, and proactive relocation decisions** instead of responding only after a disaster occurs.

The prototype focuses on being **simple, affordable, scalable, and practical**, using an explainable risk engine with optional ML assistance rather than relying on complex or expensive infrastructure.

## Features

- **Split View Layout (60/40)**:
  - **Left Panel (60%)**: Interactive Leaflet Map with CartoDB Dark Matter tiles, glowing risk markers (red/cyan/amber by priority), popups with full risk telemetry, and smooth flyTo navigation.
  - **Right Panel (40%)**: Cyberpunk Command Terminal with dynamic habitation registry, risk gauges, composite donut ring chart, and protocol override controls.
- **Cyberpunk HUD Aesthetics**:
  - CRT Scanline overlay effect.
  - Bracket corner styling on panels (`hud-panel`, `hud-corners`).
  - Strict monospace typography (`Fira Code`).
  - Dark mode pitch-black background with cyan/blue accents and neon red alert highlights.
- **Two-Way Interactivity**:
  - **Map Marker → Terminal**: Clicking any glowing marker on the map syncs selection with the right panel command terminal and updates risk telemetry.
  - **Terminal → Map**: Clicking `[ ANALYZE ]` on any habitation row in the terminal highlights the row and smoothly flies the map to the target coordinates.
- **Dynamic Dataset (Uttarakhand)**:
  - **4 Habitations**: Joshimath Sector 3, Dharchula Lower Slope, Kedarnath Valley Habitation, Munsiyari East Ridge.
  - **2 Safe Zones**: Pipalkoti Plateau (SZ-01), Pithoragarh Safe Sector B (SZ-02).
  - **3 Priority Levels**: CRITICAL (red), HIGH (cyan), MODERATE (amber) — each with distinct glowing marker animations.
  - **Data Fields**: `population`, `vulnerable`, `hazard`, `risk_score`, `safe_zone_id`, safe zone `capacity` and `occupied`.
- **Relocation Intelligence Execution Sequence (`> EXECUTE`)**:
  - **Dynamic Safe-Zone Lookup**: Uses the selected habitation's `safe_zone_id` to find the correct safe zone from the `safe_zones` array.
  - **Terminal Loading Simulation**: Staggered terminal execution logs (`>> ANALYZING HAZARD EXPOSURE...`, `>> EVALUATING CARRYING CAPACITY...`, `>> OPTIMIZING SAFE RELOCATION ROUTE...`).
  - **Recommended Safe Zone Card**: Animated slide-in HUD card displaying the matched safe zone's name, dynamically computed compass direction and distance, shelter capacity with occupancy gauge.
  - **Interactive Map Overlays**: Drops a glowing green marker at the matched safe zone's coordinates, draws a glowing cyan dashed polyline connecting the selected habitation to the safe zone, and auto-fits map bounds.

## Dataset

```json
{
  "habitations": [
    { "id": "HAB-01", "name": "Joshimath Sector 3",          "risk_score": 89.7, "priority": "CRITICAL", "hazard": "Landslide / Subsidence",   "population": 1284, "vulnerable": 327, "safe_zone_id": "SZ-01" },
    { "id": "HAB-02", "name": "Dharchula Lower Slope",       "risk_score": 78.4, "priority": "HIGH",     "hazard": "Flash Flood",              "population": 840,  "vulnerable": 190, "safe_zone_id": "SZ-02" },
    { "id": "HAB-03", "name": "Kedarnath Valley Habitation",  "risk_score": 92.1, "priority": "CRITICAL", "hazard": "Glacial Lake Outburst",    "population": 2100, "vulnerable": 510, "safe_zone_id": "SZ-01" },
    { "id": "HAB-04", "name": "Munsiyari East Ridge",        "risk_score": 45.2, "priority": "MODERATE", "hazard": "Soil Erosion",             "population": 620,  "vulnerable": 85,  "safe_zone_id": "SZ-02" }
  ],
  "safe_zones": [
    { "id": "SZ-01", "name": "Pipalkoti Plateau",          "capacity": 3500, "occupied": 1200, "distance_km": 14.2 },
    { "id": "SZ-02", "name": "Pithoragarh Safe Sector B",  "capacity": 2200, "occupied": 650,  "distance_km": 8.7 }
  ]
}
```

## Getting Started

### Option 1: Direct Browser Access (Zero Setup)
Simply open `index.html` in any modern web browser. All dependencies (React 18, Babel, Tailwind CSS 3, Leaflet 1.9, Fira Code font) are included via fast CDN links — no `npm install` or build tools required.

### Option 2: Local HTTP Server
You can serve the folder using any HTTP server, for example with Node/npx:

```bash
npx serve .
```

Or Python:

```bash
python -m http.server 8000
```
