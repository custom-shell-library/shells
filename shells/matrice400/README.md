# Matrice 400

**Class:** aerial<br>
**Generation:** 1<br>
**Version:** 1.0.0<br>
**Glossary:** 2026-09<br>
**Condition:** operational<br>
**Author:** DJI<br>
**Last updated:** 2026-10-04

---

## Identity

**Role** — Enterprise flagship multirotor platform with power-line-level obstacle sensing, multi-payload capability, and extended endurance for inspection, public safety, mapping, and emergency response operations.<br>
**Environment** — Indoor/outdoor. IP55 rated for dust and rain (up to 100 mm/24 hr). Operating temperature −20 °C to +50 °C. Max takeoff altitude 7,000 m. Max wind resistance 12 m/s during takeoff and landing.<br>
**Mission** — Power line inspection, emergency response, search and rescue, firefighting, large-scale mapping, infrastructure inspection, maritime patrol, hazmat response.<br>
**Operator** — Single operator via DJI RC Plus 2 controller. Supports autonomous waypoint missions and advanced automation workflows.<br>
**Reusability** — Commercial platform. Not a DIY build.

---

## Spec

**Physical** — 9,740 ± 40 g with batteries. 5,020 ± 20 g without batteries. Unfolded dimensions (with landing gear): 980 × 760 × 480 mm. Folded dimensions (with landing gear and gimbal): 490 × 490 × 480 mm. Diagonal wheelbase 1,070 mm. Max takeoff weight 15.8 kg. 6061-T6 aluminum alloy and carbon fiber composite airframe.

**Kinematic** — Quadcopter, 4 rotors. Foldable arms. Max ascent speed 10 m/s. Max descent speed 8 m/s. Max horizontal speed 25 m/s (no wind, sea level).

**Dynamic** — Max payload 6 kg. Up to 7 simultaneous payloads. Max flight time 59 minutes (forward flight with H30T, ~10 m/s, to 0% battery). Hover time 53 minutes.

**Power** — TB100 Intelligent Flight Battery. Single battery operation (does not require two batteries). Hot-swappable with 45-second internal capacitor backup. BS100 charging station: 45 min fast charge (220V), 110 min silent mode. Battery health and cycle data logged to DJI Pilot 2. USB-C ports and onboard storage on BS100.

**Thermal** — −20 °C to +50 °C operating range. Passive cooling.

**Environmental** — IP55 rating (dust and water resistant). Tested under IEC60529 standard. IP rating is not permanently effective and may decrease due to wear. Do not fly in rain heavier than 100 mm/24 hr.

---

## Frame

**Bill of materials** — Commercial product. Not a DIY build. The aircraft is purchased as a complete system.

| Component | Notes |
|:---|:---|
| DJI Matrice 400 aircraft | 9,740 g with batteries |
| TB100 Intelligent Flight Battery | Single battery operation, hot-swappable |
| BS100 Battery Station | Fast charge 45 min (220V), silent 110 min |
| DJI RC Plus 2 controller | High-gain phased array antenna, IP54, hybrid O4/4G |
| Zenmuse H30 Series gimbal | Wide-angle + zoom + thermal + laser range finder + NIR |
| Zenmuse L3 gimbal | 1535 nm LiDAR + dual 100MP RGB mapping cameras |
| Zenmuse P1 gimbal | Full-frame sensor, interchangeable fixed-focus lenses |
| Zenmuse S1 spotlight | LEP technology, high brightness, long illumination |
| Zenmuse V1 speaker | High volume, long broadcast distance |
| Manifold 3 | 100 TOPS compute, ~120 g |
| E-Port V2 kits | 4 ports, single port up to 120W |
| DJI Cellular Dongle 2 | Dual cellular support, auto-switch to better network |
| D-RTK 3 / D-RTK 2 | GNSS station for centimeter-level positioning |

**Structure** — Foldable quadcopter airframe. Aluminum alloy and carbon fiber composite. IP55 sealed. Integrated rotating LiDAR, upward LiDAR, downward 3D infrared range sensor, and six-direction mmWave radar.

**Actuation** — 4 brushless DC motors with foldable propellers. Motor specifications not publicly detailed.

**Locomotion** — Aerial. Quadcopter configuration. Forward flight up to 25 m/s.

**Manipulation** — None. Payload is sensor and accessory only.

**Power system** — TB100 battery. XT90 or proprietary connector. 45-second hot-swap capability. BS100 charging station for battery management.

**Wiring** — Internal. Not user-accessible. E-Port V2 provides power and data to payloads.

**Custom parts** — None. All components are DJI proprietary or certified third-party.

**Fasteners** — Proprietary. Not user-serviceable.

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and antenna connection.

---

## Systems

**Manifest** — DJI proprietary firmware and software ecosystem.

**Firmware** — DJI proprietary flight controller firmware. O4 Enterprise Enhanced Video Transmission firmware. Regular firmware updates via DJI Pilot 2 or DJI Assistant 2.

**Middleware** — DJI proprietary. Payload SDK (PSDK) for third-party payload integration. Onboard SDK (OSDK) for advanced autonomous control. Mobile SDK (MSDK) for custom mobile applications.

**Perception** — Omnidirectional binocular vision system (surround view via full-color fisheye vision sensors), horizontal rotating LiDAR (905 nm, Class 1 eye-safe), upward LiDAR (3D ToF, 0.5–25 m), downward 3D infrared range sensor (0.3–8 m), six-direction mmWave radar. Obstacle sensing at speeds up to 25 m/s when directly facing a 21.6 mm steel-core aluminum stranded wire. mmWave radar unavailable in some countries/regions.

**Control** — DJI proprietary flight controller. Supports cruise mode, smart track, POI, real-time terrain follow, AR projection, ship-based takeoff/landing. Advanced automation workflows via DJI Pilot 2 and FlightHub 2.

**Planning** — Autonomous waypoint missions. Real-time terrain follow automatically adjusts altitude for consistent mapping. Smart AR projection overlays flight paths, obstacle warnings, and landmark data onto the RC Plus 2 controller. Ship-based takeoff/landing recognizes landing pad patterns on vessel decks for dynamic ship landing.

**Learning** — None native. Manifold 3 provides 100 TOPS for onboard AI inference.

**Teleoperation** — DJI RC Plus 2 controller. High-gain phased array antenna. O4 Enterprise Enhanced transmission. Sub2G frequency support. Dual cellular via DJI Cellular Dongle 2. Airborne relay video transmission. Up to 40 km transmission range.

**Safety** — ADS-B In (20 km reception, dual antenna). IP55 weather sealing. Omnidirectional obstacle sensing. Return-to-home. Failsafe. Geofencing. Night navigation lights (2).

**Logging** — Flight logs via DJI Pilot 2. Battery analytics logged to app. Data export via SD card or FlightHub 2.

**Networking** — O4 Enterprise Enhanced (2.4/5.8 GHz), sub2G, dual cellular via dongle. 10-antenna array on aircraft. High-gain phased array on controller. Up to 40 km range.

**Config files** — Managed via DJI Pilot 2. No user-accessible config files.

**Launch files** — N/A.

**Dependencies** — DJI Pilot 2 app. DJI FlightHub 2 (optional cloud platform). DJI Assistant 2 (firmware updates).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| DJI Pilot 2 | Latest | DJI | Ground station |
| DJI FlightHub 2 | Latest | DJI | Fleet management |
| DJI Assistant 2 | Latest | DJI | Firmware update |
| DJI Terra | Latest | DJI | Mapping and photogrammetry |
| DJI PSDK | Latest | DJI | Payload SDK |
| DJI OSDK | Latest | DJI | Onboard SDK |
| DJI MSDK | Latest | DJI | Mobile SDK |

---

## Interface

**Emits** — O4 Enterprise Enhanced video transmission to RC Plus 2. Telemetry: attitude, position, battery, GPS, obstacle warnings, payload status. Up to 40 km transmission range.

**Accepts** — RC Plus 2 commands. Autonomous mission commands via Pilot 2. Payload commands via PSDK.

**Serves** — Arming, calibration, parameter access via DJI Pilot 2.

**Executes** — Waypoint missions, RTL, smart track, POI, cruise mode, terrain follow, ship-based takeoff/landing.

**Extensions** — Third-party payloads via E-Port V2 and PSDK. Manifold 3 for onboard compute.

**Frame conventions** — DJI proprietary.

**Units** — SI and DJI proprietary.

---

## Model

**URDF / Xacro** — Not applicable (proprietary).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. RTK GNSS for centimeter-level positioning. IMU, compass, and vision system calibration via DJI Pilot 2.

**Dynamics** — Proprietary.

**Sensor transforms** — Proprietary.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Customer acceptance test on delivery.

**Integration** — Payload mounting and connection verification. Transmission range test. Obstacle sensing verification. RTK positioning verification.

**Field** — Power line inspection at 25 m/s. Ship-based takeoff/landing. Terrain follow mapping. Emergency response scenarios.

**Endurance** — 59 min forward flight. 53 min hover.

**Environmental** — IP55 verified. −20 °C to +50 °C operating. 7,000 m max takeoff altitude.

**Known limitations** — mmWave radar unavailable in some countries/regions. IP rating not permanent. Cannot fly in rain heavier than 100 mm/24 hr. Payload compatibility limited to DJI ecosystem and certified third-party. Single downward gimbal max 1.4 kg, dual downward gimbal max 950 g, third gimbal connector max 3 kg (quick release) or 6 kg (screw lock).

---

## Log

**Build history** — Released June 10, 2025. Firmware updates ongoing.

**Open issues** — mmWave radar regional availability. Third-party payload certification.

**Changelog** — Battery settings added return-to-home reserve. 4G enhanced transmission data usage prompts. Advanced operation modes. LiDAR contamination detection for cleaning maintenance.

**Lessons learned** — N/A (commercial product).

**Cost actual** — $10,450 (aircraft only, no payload). $11,618 with Zenmuse L2. $13,090+ for combo configurations. Payloads and batteries sold separately. TB100 battery: $2,187. TB100C tethered battery: $2,627.

---

## Status

**Condition** — operational.

**Blockers** — None. Commercial availability.

**Next steps** — Payload configuration selection based on mission profile. Operator training and certification. Integration with FlightHub 2 for fleet operations.

---

**Note on this Shell:** The DJI Matrice 400 is a commercial, closed-platform system. Unlike the other Shells in this repo, it cannot be built from a BOM or modified at the firmware level. This Shell exists as a reference for what a fully integrated, production-grade enterprise platform looks like — the capabilities, specifications, and integration depth that a custom build would need to match.
