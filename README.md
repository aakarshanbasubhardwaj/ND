# ND

Access ND at - https://aakarshanbasubhardwaj.github.io/ND/

ND is a high-performance ADS-B Navigation Display application designed for web browsers. It provides real-time situational awareness of global air traffic using a custom-built HTML5 Canvas engine.

## Technical Implementation

### Multi-Threaded Processing
The application utilizes an Inline Web Worker to handle heavy data processing. JSON parsing and Haversine trigonometric calculations are performed on a background thread. This ensures the main UI thread remains responsive and provides 60 FPS animations even when tracking thousands of aircraft.

### Motion Interpolation
To eliminate the visual jumping associated with periodic API updates, the engine implements dead reckoning. It uses ground speed and heading vectors to mathematically predict aircraft position between data refreshes, resulting in smooth, continuous movement.

### Responsive Design
The display is engineered to be resolution-independent. It automatically scales its coordinate system and visual assets to fit any viewport, from mobile devices to desktop monitors. The interface adapts to changes in orientation and sidebar state in real-time.

### Spatial Hash Grid
Collision detection for mouse and touch interaction is optimized using a spatial hash grid. This reduces interaction complexity from O(N) to O(1), allowing for instant aircraft selection in high-density traffic environments.

## Features

- Dynamic vector-based aircraft icons categorized by altitude.
- Historical breadcrumb trails showing recent flight maneuvers.
- Interactive rotary range control from 10 NM to 320 NM.
- Mouse wheel and touch pinch-to-zoom support.
- Live telemetry cards featuring real-time data and aircraft photography.
- Emergency squawk monitoring with visual alert flashing.

## Controls

- Left Click or Tap: Select aircraft for telemetry.
- Scroll Wheel or Pinch: Change radar range scale.
- ICAO Search: Center map on specific airport coordinates.
- Device GPS: Center map on current hardware location.

## Data Credits

- Traffic Data: Airplanes.live and ADSB.fi
- Geocoding: OpenStreetMap Nominatim
- Imagery: Planespotters.net API
