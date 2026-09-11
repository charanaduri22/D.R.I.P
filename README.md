# DRIP — Disaster Relocation Intelligence Platform

An intelligent disaster-relocation decision-support prototype built with a high-tech "Blue Cyberpunk HUD / Terminal" aesthetic inspired by sci-fi command systems.

## Features

- **Split View Layout (60/40)**:
  - **Left Panel (60%)**: Interactive Leaflet Map with CartoDB Dark Matter tiles, glowing risk markers, popups, and smooth flyTo navigation.
  - **Right Panel (40%)**: Cyberpunk Command Terminal with dynamic habitation registry, risk gauges, composite donut ring chart, and protocol override controls.
- **Cyberpunk HUD Aesthetics**:
  - CRT Scanline overlay effect.
  - Bracket corner styling on panels (`hud-panel`, `hud-corners`).
  - Strict monospace typography (`Fira Code`).
  - Dark mode pitch-black background with cyan/blue accents (`#00f0ff`) and neon red alert highlights (`#ff0033`).
- **Two-Way Interactivity**:
  - **Map Marker → Terminal**: Clicking any glowing marker on the map syncs selection with the right panel command terminal and updates risk telemetry.
  - **Terminal → Map**: Clicking `[ ANALYZE ]` on any habitation row in the terminal highlights the row and smoothly flies the map to the target coordinates.
- **Relocation Intelligence Execution Sequence (`> EXECUTE`)**:
  - **Terminal Loading Simulation**: Staggered terminal execution logs (`>> ANALYZING HAZARD EXPOSURE...`, `>> EVALUATING CARRYING CAPACITY...`, `>> OPTIMIZING SAFE RELOCATION ROUTE...`).
  - **Recommended Safe Zone Card**: Animated slide-in HUD card displaying designated safe location ("Zone Beta — High Plateau"), recommended heading (`↗ NORTH-EAST (4.2 km)`), shelter capacity (`1,200 / 1,850`), and real-time occupancy load indicator.
  - **Interactive Map Overlays**: Drops a glowing green marker for Safe Zone Beta, draws a glowing cyan dashed polyline connecting the target habitation directly to the safe zone, and auto-fits map bounds.

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
