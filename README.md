# Al Qalqali MPA 3D Reef Mapping & Turtle Photo-ID Survey

> **Interactive side-by-side photogrammetric digital twin viewer for benthic habitat assessment and marine fauna biometrics in the Al Qalqali Marine Protected Area (Khor Fakkan, UAE).**

🌐 **Live Web Application**: [https://parkar4308-cell.github.io/alqalqali-reef-3d/](https://parkar4308-cell.github.io/alqalqali-reef-3d/)

---

## 🌊 Overview

This application bridges underwater ROV video transects with reconstructed 3D digital twins, allowing marine biologists, MPA managers, and surveyors to directly compare the source footage against the generated 3D surface model ("*Using this video, we made this*").

Key surveying capabilities:
- **Side-by-side synchronized view**: Source ROV footage on the left, interactive 60 FPS WebGL 3D model on the right.
- **Keyframe alignment bracket**: Visual indicator on the transport timeline marking the exact 0.0–1.5 s video interval used for photogrammetric reconstruction.
- **Three rendering modes**:
  - `Colour`: Continuous UV-mapped photorealistic coral surface texture.
  - `Height`: Digital Elevation Model (DEM) with Turbo color-ramp depth legend.
  - `Seabed type`: Quantitative benthic habitat classification (Live Coral, Macroalgae, Sand/Rock).
- **Ecological rugosity metric ($R_s$)**: Surface 3D area vs. planar footprint ratio on a calibrated gauge.
- **Targeted turtle Photo-ID & biometrics**: Automatically activated only when turtles are verified (carapace length, 3D pinned coordinate, and SMS-RC catalog matching). Suppressed completely on pure reef transects.
- **Open standard exports**: 1-click download of survey summary reports (`.JPG`), 3D meshes (`.OBJ`), and metric tables (`.JSON`).

---

## 📍 Survey Geodetic Reference

- **Site**: Al Qalqali Marine Protected Area, Khor Fakkan, Gulf of Oman / UAE East Coast
- **Coordinate System**: WGS 84 / UTM Zone 40N (EPSG:32640)
- **Altitude Datum**: Mean Sea Level (MSL), depths referenced to chart datum (CD)
- **Scale Basis**: ROV altitude assumed 1.75 m above seabed

---

## 🚀 Architecture & Zero-Backend Deployment

The web application is built as a pure, dependency-free static client:
- **Renderer**: Vanilla WebGL 1.0 shader pipeline with orbit controls and 2D HUD canvas overlay.
- **Data format**: Inline coordinate arrays and high-compression continuous UV texture maps (`demo_data.js`).
- **Hosting**: 100% static, served directly via GitHub Pages with native HTTP `Range` request support for smooth MP4 video scrubbing.

---

## 💻 Local Development

To run the local preview server with HTTP Range support:

```bash
python -m attempt_2.web_server
# Accessible at http://localhost:8080
```

---

## 📜 License & Citation

Survey and photogrammetry models developed for marine conservation and benthic habitat monitoring. Distributed under the MIT License.
