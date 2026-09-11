# DRIP — Disaster Relocation Intelligence Platform

An intelligent disaster-relocation decision-support prototype built with a high-tech "Blue Cyberpunk HUD / Terminal" aesthetic inspired by sci-fi command systems.

## Features

- **Split View Layout (60/40)**:
  - **Left Panel (60%)**: Interactive map system placeholder (`>> MAP_SYSTEM_OFFLINE // LEAFLET_PENDING`).
  - **Right Panel (40%)**: Cyberpunk Command Terminal.
- **Cyberpunk HUD Aesthetics**:
  - CRT Scanline overlay effect.
  - Bracket corner styling on panels.
  - Monospace font (`Fira Code`).
  - Dark mode pitch-black background with cyan/blue accents and neon red alert highlights.
- **Interactive Command Terminal**:
  - **Habitations Registry**: Interactive list of high-risk habitations with risk tiers (CRITICAL / HIGH).
  - **Selection State**: Click `[ ANALYZE ]` to highlight habitations and load real-time telemetry.
  - **Risk Metrics & Donut Chart**: Dynamic SVG donut chart and sub-metric breakdown (Hazard Intensity, Population Vulnerability, Infrastructure Deficit).
  - **Override Action**: Interactive `> EXECUTE` button with glow hover animations.

## Getting Started

### Option 1: Direct Browser Access (Zero Setup)
Simply open `index.html` in any modern web browser. All dependencies (React 18, Babel, Tailwind CSS, Fira Code font) are included via fast CDN links.

### Option 2: Local Server
You can serve the folder using any HTTP server, for example with Node/npx:

```bash
npx serve .
```

Or Python:

```bash
python -m http.server 8000
```
