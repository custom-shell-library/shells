# skydio

**Class:** aerial (Group 1 small UAS / drone-in-a-box)  
**Generation:** 1  
**Version:** X10 / X10D  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Skydio  
**Last updated:** 2026-10-06

---

## Identity

**Role** — AI-autonomous small unmanned aircraft system designed for local persistent surveillance, Drone as First Responder (DFR) operations, infrastructure inspection, and tactical ISR. The X10 is not a strategic asset; it is a **local autonomy platform** that can be hand-launched in under 40 seconds from a backpack, or launched from an automated dock in under 20 seconds, and left to fly autonomously without a pilot, GPS, or communications link. Its defining characteristics are **360° obstacle avoidance via six 32MP navigation cameras**, **NVIDIA Jetson Orin onboard compute**, **GPS-denied navigation via visual-inertial odometry**, and **drone-in-a-box persistent operation**. It is the drone carrying the largest single-vendor small-drone order in US Army history — more than 2,500 X10Ds for over $52 million.

**Environment** — Outdoor and indoor, all-weather, day and night. IP55 rated, tested to fly in light rain, dust, and wind gusts up to 28 mph (45 km/h). Operating temperature −20 °C to +45 °C. Service ceiling 15,000 ft density altitude. Deploys from a backpack in under 40 seconds when hand-launched; airborne in as little as 20 seconds from Dock for X10. Flies in GPS-denied environments including parking garages, under bridges, and inside structures via visual-inertial odometry. Not for operations in icing conditions or severe turbulence.

**Mission** — Persistent local surveillance, Drone as First Responder (DFR), search and rescue, infrastructure inspection, site security, and tactical ISR. The X10 supports three sensor packages (VT300-L, VT300-Z, V100-L) with modular payloads including 50 MP wide-angle, 64 MP narrow, 48 MP telephoto zoom (up to 128x system zoom), and Teledyne FLIR Boson+ radiometric thermal sensors. The VT300-Z can detect a person at 8,200 feet or a vehicle at 7.5 miles. The aircraft is designed for persistent overwatch, subject search and tracking, and general reconnaissance.

**Operator** — Single operator via Skydio Flight Deck controller or browser-based Remote Ops. The X10 flies autonomously with AI-based obstacle avoidance and GPS-denied navigation; the operator provides mission-level command and monitors the sensor feed. DFR Command enables drone-as-first-responder workflows. The X10D supports MAVLink and QGroundControl for third-party GCS integration.

**Reusability** — Commercial product with active production and defence procurement. The X10D cleared Blue UAS in 2024; in July 2026 the X10, Dock for X10, and R10 joined it, making Skydio the first manufacturer to put its complete active lineup on the Pentagon's Blue UAS roster. The US Army ordered more than 2,500 X10Ds for over $52 million in March 2026, the largest single-vendor small-drone purchase in its history.

---

## Spec

**Physical** — Weight <4.7 lb (2.13 kg). Unfolded with propellers 31.1 × 25.6 × 5.7 in (79.0 × 65.0 × 14.5 cm). Folded without battery 13.8 in. Four modular payload attachment bays with 340 g maximum payload. The airframe folds for backpack transport and deploys in under 40 seconds.

**Kinematic** — Quadcopter configuration. Six 32MP custom navigation cameras provide 360° coverage for obstacle avoidance. Max speed 45 mph (20 m/s). Max service ceiling 15,000 ft density altitude. The aircraft flies autonomously with AI-based obstacle avoidance; the operator does not manually pilot around obstacles. NightSense enables zero-light autonomous flight using visible or IR illumination (X10D).

**Dynamic** — Endurance rated 40 minutes of flight and 35 minutes of hover under ideal lab conditions. Endurance depends on payload and environmental conditions; temperature, wind, and mission type affect flight time. The X10 carries four modular payload bays, enabling multi-sensor configurations without sacrificing flight time beyond the 340 g payload limit. The aircraft has demonstrated 400 flights in three weeks in Spokane and has saved lives on day one in DFR operations.

**Power** — Electric propulsion. Battery capacity 9,600 mAh. Charging via Dock for X10 automated charging or manual battery swap. The all-electric powertrain produces low acoustic and thermal signatures. Runtime 40 minutes flight / 35 minutes hover. The Dock for X10 provides autonomous recharging for persistent operations without operator intervention.

**Thermal** — Passive cooling. The NVIDIA Jetson Orin and Qualcomm QRB5165 processors generate heat under load; the airframe provides convection cooling during flight. Operating temperature −20 °C to +45 °C. No active refrigeration required. The thermal sensor (FLIR Boson+) has thermal sensitivity <30 mK NEDT, enabling detection of heat signatures through fog, smoke, and low-contrast environments.

**Environmental** — IP55 rated. Tested to fly in light rain, dust, and wind gusts up to 28 mph (45 km/h). Operating temperature −20 °C to +45 °C. The X10D supports NightSense for zero-light autonomous flight. The Dock for X10 has built-in HVAC to maintain safe operating temperature for the drone in −4 °F to 122 °F and can withstand intense rainstorms; flight operations from Dock are possible in moderate rain and winds up to 28 mph, day or night.

---

## Frame

**Bill of materials** — Commercial product. Not a DIY build. The X10 is purchased as a complete system with controller, payloads, and optional dock.

| Component | Notes |
|:---|:---|
| Skydio X10 / X10D airframe | Quadcopter, <4.7 lb (2.13 kg), folds to 13.8 in, deploys in <40 sec |
| NVIDIA Jetson Orin + Qualcomm QRB5165 | Onboard AI compute for autonomy and perception |
| Six 32MP navigation cameras | 360° obstacle avoidance coverage |
| VT300-L payload | 50 MP wide + 64 MP narrow + FLIR Boson+ thermal + LED flashlight |
| VT300-Z payload | 64 MP narrow + 48 MP telephoto zoom (128x) + FLIR Boson+ thermal |
| V100-L payload | 50 MP wide + 64 MP narrow + LED flashlight (no thermal) |
| AES-256 encryption | Secure data link |
| IP55 rating | Dust and splash resistant |
| GNSS | GPS, GLONASS, Galileo, BeiDou + ADS-B In receiver |
| Dock for X10 | Automated drone-in-a-box with HVAC, auto-charging, 5G connectivity |
| Skydio Flight Deck | Controller with Cloud API, Extend API, Mobile SDK, Attachment ICD |
| X10D MAVLink support | Open MAVLink protocol for third-party GCS (QGroundControl compatible) |

**Structure** — Quadcopter airframe with folding arms for backpack transport. Six navigation cameras distributed around the airframe for 360° obstacle avoidance. Four modular payload bays accept sensor packages and accessories including parachute, microphone, and spotlight (340 g max). The NVIDIA Jetson Orin provides onboard AI compute for autonomy, obstacle avoidance, and subject tracking. The X10D adds hardened communications (Doodle Labs Mesh Rider radio options), MAVLink support, and RAS-A v1.2 compliance.

**Actuation** — Four brushless DC motors driving four rotors. The aircraft flies autonomously with AI-based obstacle avoidance; the operator provides mission-level command. Max speed 45 mph (20 m/s). NightSense enables zero-light autonomous flight using visible or IR illumination on the X10D.

**Locomotion** — Rotary-wing flight. Hand-launched in under 40 seconds or launched from Dock for X10 in under 20 seconds. GPS-denied navigation via visual-inertial odometry enables flight in parking garages, under bridges, and inside structures. The aircraft transitions seamlessly between GNSS-enabled and GNSS-denied environments. 5G/LTE via Connect Fusion enables unlimited range for remote operations.

**Manipulation** — None. The aircraft is a sensor platform. The payload is the effector: wide-angle, narrow, telephoto zoom, and thermal cameras. Accessory payloads include parachute, microphone, and spotlight. Four attachment bays with 340 g maximum payload.

**Power system** — Electric propulsion with 9,600 mAh battery. Charging via Dock for X10 automated charging or manual battery swap. The Dock provides autonomous recharging for 24/7 persistent operations. Power distribution includes AES-256 encrypted data links for secure communications.

**Wiring** — Internal only. Not user-accessible. Payload integration via four attachment bays with Attachment ICD (mechanical/electrical specs) for custom payloads. The X10D supports Doodle Labs Mesh Rider radio options for defence communications.

**Custom parts** — None. All components are Skydio proprietary or certified third-party. The Extend API and Attachment ICD enable third-party integration for workflow and custom payloads.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for rapid deployment and recovery by a single operator, with modular payloads for field reconfiguration.

**Tools required** — None for assembly (factory-built). No tools required for payload changes. Standard tools for field maintenance. The aircraft deploys from a backpack in under 40 seconds.

---

## Systems

**Manifest** — Skydio proprietary autonomy stack with Cloud API, Extend API, and Mobile SDK for third-party integration.

**Firmware** — Proprietary Skydio Autonomy software. The aircraft flies autonomously with 360° obstacle avoidance, GPS-denied navigation via visual-inertial odometry, and NightSense zero-light autonomous flight (X10D). The NVIDIA Jetson Orin provides onboard AI compute for real-time perception, obstacle avoidance, and subject tracking. The X10D supports MAVLink and QGroundControl for third-party GCS.

**Middleware** — Skydio proprietary. The X10 uses Wi-Fi-based control/video link with AES-256 encryption; 5G/LTE via Connect Fusion provides unlimited range for remote operations. The X10D uses Doodle Labs Mesh Rider radio options with multi-band operation and RAS-A v1.2 compliance. Remote Ops enables browser-based remote piloting from any location. DFR Command enables drone-as-first-responder workflows.

**Perception** — Three sensor packages:
- **VT300-L**: 50 MP wide-angle (1" f/1.95), 64 MP narrow (1/1.7" f/1.8), Teledyne FLIR Boson+ 640×512 radiometric thermal, integrated LED flashlight.
- **VT300-Z**: 64 MP narrow, 48 MP telephoto zoom (190mm f/2.2, ~128x system zoom), Teledyne FLIR Boson+ thermal. Detects a person at 8,200 ft or a vehicle at 7.5 miles.
- **V100-L**: 50 MP wide, 64 MP narrow, integrated LED flashlight (no thermal).
- **Six 32MP navigation cameras**: 360° obstacle avoidance.
- **RTK/PPK attachment**: Optional for centimeter-level geospatial accuracy.

**Control** — AI-autonomous flight with obstacle avoidance. The operator provides mission-level command and monitors the sensor feed. The aircraft flies without a pilot, GPS, or communications link in GPS-denied environments via visual-inertial odometry. NightSense enables zero-light autonomous flight. Subject search and tracking are supported via onboard AI.

**Planning** — Mission planning via Skydio Flight Deck or Cloud API. DFR Command enables drone-as-first-responder workflows with automated launch from Dock for X10. Point-and-click mission planning is supported. The aircraft can be deployed from Dock for X10 in under 20 seconds for automated persistent surveillance.

**Learning** — Skydio Autonomy uses onboard AI for obstacle avoidance, subject tracking, and GPS-denied navigation. The specific learning architecture is not publicly disclosed, but the Jetson Orin provides the compute for real-time inference. The autonomy is designed for reliability and predictability in safety-critical operations.

**Teleoperation** — Single operator via Skydio Flight Deck controller or browser-based Remote Ops. The X10 Controller supports Skydio Flight Deck only; the X10D supports MAVLink and QGroundControl for third-party GCS. Remote Ops enables browser-based remote piloting from any location. The aircraft flies autonomously; the operator provides mission-level command.

**Safety** — 360° obstacle avoidance via six navigation cameras. GPS-denied navigation via visual-inertial odometry. NightSense zero-light autonomous flight. ADS-B In receiver for traffic awareness. Parachute payload option available. RAS-A v1.2 compliance for the X10D. AES-256 encryption for secure data links. IP55 rating for dust and splash resistance.

**Logging** — Cloud API enables mission planning, fleet management, and media sync. Extend API enables workflow integration for evidence management and inspection platforms. The aircraft logs mission data, sensor data, and flight telemetry for post-mission analysis.

**Networking** — Wi-Fi-based control/video link with AES-256 encryption (X10). 5G/LTE via Connect Fusion for unlimited range (optional). X10D: Doodle Labs Mesh Rider radio options with multi-band operation. The Dock for X10 supports 5G connectivity for unlimited flight range.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through Skydio Flight Deck or Cloud API.

**Launch files** — N/A (proprietary UAS software). The X10D supports MAVLink for third-party GCS integration.

**Dependencies** — Skydio Flight Deck controller (X10). QGroundControl compatible (X10D). Cloud API, Extend API, Mobile SDK, Attachment ICD. Dock for X10 for automated persistent operations.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Skydio Autonomy | Proprietary | Skydio | Autonomy/AI |
| Skydio Flight Deck | Proprietary | Skydio | Ground control |
| Cloud API | Proprietary | Skydio | Fleet/mission |
| Extend API | Proprietary | Skydio | Workflow integration |
| Mobile SDK | Proprietary | Skydio | Android apps |
| Attachment ICD | Proprietary | Skydio | Custom payloads |
| MAVLink (X10D) | Open standard | MAVLink | Third-party GCS |
| DFR Command | Proprietary | Skydio | Drone as First Responder |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, battery state, system health. Sensor data: wide-angle, narrow, telephoto zoom, and thermal imagery. Network data: Wi-Fi/5G link status, mesh radio status (X10D).

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Payload commands. Remote Ops commands via browser. Third-party GCS commands via MAVLink (X10D).

**Serves** — Persistent local ISR services. Drone as First Responder services. Infrastructure inspection. Search and rescue. Site security.

**Executes** — Autonomous hand launch or dock launch, persistent ISR over a local area, subject search and tracking, GPS-denied navigation, autonomous landing. Return-to-base in comms-denied environment.

**Extensions** — Four modular payload bays (340 g max). VT300-L, VT300-Z, V100-L sensor packages. Parachute, microphone, spotlight accessories. RTK/PPK attachment for centimeter-level mapping. Dock for X10 for automated persistent operations. Attachment ICD for custom payloads.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in mph or m/s. Altitude in feet MSL or AGL.

**Units** — SI and aviation standard. Metres, feet, miles, kilometres, miles per hour, metres per second, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary commercial platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for VT300-L, VT300-Z, and V100-L payloads. Navigation cameras calibrated for 360° obstacle avoidance. Visual-inertial odometry calibrated for GPS-denied navigation. RTK/PPK attachment calibrated for centimeter-level geospatial accuracy.

**Dynamics** — Proprietary. The aircraft's aerodynamic model is used for autonomy and obstacle avoidance. The six navigation cameras and onboard NVIDIA Jetson Orin provide real-time perception for 360° obstacle avoidance. The aircraft flies autonomously without a pilot, GPS, or communications link in GPS-denied environments.

**Sensor transforms** — Six navigation cameras distributed for 360° coverage. Payload sensors mounted in four attachment bays. RTK/PPK attachment mounted for geospatial accuracy.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of motors, batteries, autonomy stack, and payloads.

**Integration** — Payload integration in four attachment bays. Skydio Autonomy verification. GPS-denied navigation verification. Dock for X10 integration and automated launch verification. 5G/Connect Fusion verification.

**Field** — Spokane DFR pilot: 400 flights in three weeks. Port St. Lucie: saved a life on day one. Florida: found a lost man at 3 a.m. on thermal. Kishwaukee River: helped rescue three people. US Army ordered 2,500+ X10Ds for $52 million (March 2026). USAFCENT $9 million deal for X10s on Middle East bases (April 2026). X10D Blue UAS cleared 2024; X10, Dock for X10, R10 joined July 2026.

**Endurance** — 40 minutes flight, 35 minutes hover (ideal lab conditions). Depends on payload and environmental conditions.

**Environmental** — IP55 rated. Tested in light rain, dust, and wind gusts up to 28 mph (45 km/h). Operating temperature −20 °C to +45 °C. GPS-denied navigation in parking garages, under bridges, and inside structures.

**Known limitations** — The X10 is a Group 1 small UAS with a 340 g payload capacity; it cannot carry large sensors or heavy equipment. The 40-minute endurance is shorter than fixed-wing or hybrid VTOL platforms. The X10 Controller supports Skydio Flight Deck only; third-party GCS requires the X10D. The aircraft is not stealth; it relies on low acoustic signature, autonomous obstacle avoidance, and GPS-denied navigation for survivability. The Dock for X10 is a fixed installation; the system requires a dock site for persistent operations.

---

## Log

**Build history** — Skydio X10 launched September 2023. X10D cleared Blue UAS 2024. US Army ordered 2,500+ X10Ds for $52M March 2026. X10, Dock for X10, R10 joined Blue UAS July 2026. Spokane DFR pilot 400 flights in three weeks (July 2026). Port St. Lucie life saved day one (June 2026). USAFCENT $9M deal (April 2026).

**Open issues** — Expansion of third-party payload integration via Attachment ICD. Dock for X10 site selection and installation. Export control and ITAR restrictions for X10D. Integration with emerging battle-management systems.

**Changelog** — X10: initial production configuration (September 2023). X10D: defence variant with hardened comms, MAVLink, RAS-A compliance (Blue UAS 2024). Dock for X10: automated drone-in-a-box (2024). R10: ruggedized controller. Full lineup Blue UAS cleared July 2026.

**Lessons learned** — 360° obstacle avoidance via six navigation cameras and onboard AI compute is the key enabler of autonomous flight in cluttered environments. GPS-denied navigation via visual-inertial odometry enables flight in parking garages, under bridges, and inside structures. Drone-in-a-box (Dock for X10) enables 24/7 persistent operations without operator intervention. The Blue UAS clearance of the complete Skydio lineup makes it the reference for NDAA-compliant small UAS. DFR operations have saved lives on day one and logged 400 flights in three weeks, demonstrating operational readiness.

**Cost actual** — $16,000 to $25,000 per unit in public safety deployments. US Army: 2,500+ X10Ds for over $52 million (March 2026). USAFCENT: $9 million (April 2026).

---

## Status

**Condition** — operational. Fielded with US Army (2,500+ X10Ds), USAFCENT, and public safety agencies across the United States.

**Blockers** — None. Active production and procurement.

**Next steps** — Continued delivery of 2,500+ X10Ds to US Army. Expansion of Dock for X10 installations for persistent surveillance. Integration of RTK/PPK attachment for mapping and inspection. Expansion of Foreign Military Sales. Development of successor systems with enhanced endurance and autonomy.

---

**Note on this Shell:** The skydio is a distinct class in the library: a Group 1 small UAS designed for **local persistent surveillance** with **drone-in-a-box autonomy**. Unlike the puma (hand-launched, 5.5-hour endurance, Group 2) or the teal 2 (30-minute endurance, Group 1), the X10 combines 360° obstacle avoidance via six navigation cameras, onboard NVIDIA Jetson Orin compute, GPS-denied navigation via visual-inertial odometry, and automated dock operations into a single platform that flies without a pilot, GPS, or communications link. The Dock for X10 enables 24/7 persistent operations with automated launch in under 20 seconds and autonomous recharging. The Blue UAS clearance of the complete Skydio lineup makes it the reference for NDAA-compliant small UAS procurement. With the largest single-vendor small-drone order in US Army history (2,500+ X10Ds for $52M), DFR operations that saved lives on day one, and 400 flights in three weeks, the X10 is the reference for a small, autonomous, AI-powered local surveillance drone with drone-in-a-box persistent capability.
