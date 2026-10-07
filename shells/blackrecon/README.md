# blackrecon

**Class:** aerial (micro UAS / vehicle-integrated persistent ISR)  
**Generation:** 1  
**Version:** 1.0.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Teledyne FLIR Defense  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Vehicle-integrated autonomous micro-drone system for continuous, untethered reconnaissance and real-time targeting data in contested environments. The Black Recon is not a man-portable system; it is a **launch-and-recover platform** that mounts on military vehicles and fixed installations, autonomously deploying up to three micro-UAVs in rotation to provide persistent situational awareness without the crew ever leaving the safety of their vehicle.

**Environment** — Outdoor, all-weather, day and night. Deployed from military vehicles and fixed installations. Designed for operation in GPS-denied and RF-contested environments. Each UAV weighs less than 450 grams.

**Mission** — Continuous reconnaissance, surveillance, target acquisition, and force protection for ground forces. The Black Recon enables crews to launch, operate, recover, and recharge up to three UAS without leaving their platform, reducing risk and accelerating decision-making.

**Operator** — Vehicle crew or fixed-installation operator. Autonomous launch, recovery, and recharge from the safety of the platform.

**Reusability** — Commercial defence platform. Market launch at Eurosatory 2026. Deliveries expected to begin in 2027. Compatible operation with Black Hornet 4 nano-drone.

---

## Spec

**Physical** — Each UAV weighs less than 450 grams (15.9 oz). System allows three UAVs in rotation. Open mission-module architecture with optional 100-gram modules.

**Kinematic** — Rotary-wing micro-drone. Autonomous launch from vehicle-mounted launcher. Speeds up to 25 m/s (56 mph / 90 km/h) per UAV to support continuous target tracking and rapid threat detection.

**Dynamic** — Flight time 50 to 60 minutes per UAV. Endurance enables continuous target tracking. Three-UAV rotation provides near-continuous overwatch.

**Power** — Electric propulsion. Autonomous recharging from the vehicle launcher between sorties.

**Thermal** — Passive cooling. Thermal payload for night operations.

**Environmental** — Designed for contested environments. GNSS-denied operation enabled by advanced sensors and visual navigation. Radio-silent missions using Visual Inertial Navigation without reliance on RF links. Operational temperature range and wind limits not publicly specified.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build.

| Component | Notes |
|:---|:---|
| Black Recon micro-UAV (×3) | <450 g each, 50–60 min flight time |
| Vehicle-mounted launcher | Autonomous launch, recovery, and recharge |
| Thermal and visible payloads | Real-time imagery and targeting data |
| Visual Inertial Navigation | Radio-silent, GNSS-denied operation |
| Onboard relay capability | Extended range and radio coverage |
| Optional 100-gram mission modules | Future lethality, sensor, and CBRN payloads |

**Structure** — Vehicle-integrated autonomous system. Each UAV launches autonomously, performs reconnaissance, surveillance, and target acquisition missions, then returns to the launcher for capture, docking and recharging.

**Actuation** — Rotary-wing electric propulsion.

**Locomotion** — Vertical take-off and landing from vehicle-mounted launcher.

**Manipulation** — None. Sensor platform.

**Power system** — Electric. Autonomous recharge from launcher.

**Wiring** — Internal. Vehicle integration via launcher.

**Custom parts** — Open mission-module architecture designed to evolve with operational requirements. Planned future modules include lethality payloads and CBRN detection sensors.

**Fasteners** — Proprietary.

**Tools required** — None for field operation. Standard tools for vehicle integration.

---

## Systems

**Manifest** — Teledyne FLIR proprietary software stack with autonomous navigation and GNSS-denied operation.

**Firmware** — Autonomous navigation allows missions to continue in GPS-jammed or spoofed environments. Visual Inertial Navigation for radio-silent missions.

**Middleware** — Proprietary. Onboard relay capability for extended range and radio coverage.

**Perception** — Thermal and visible payloads for real-time imagery and targeting data.

**Control** — Fully autonomous. Autonomous launch, reconnaissance, target acquisition, and recovery.

**Planning** — Autonomous mission execution with continuous target tracking.

**Learning** — None publicly disclosed.

**Teleoperation** — Vehicle crew monitors ISR data from within the platform.

**Safety** — GNSS-denied operation for contested environments. Radio-silent capability. Autonomous recovery reduces exposure.

**Logging** — Mission data and sensor data logged. Real-time transmission to vehicle crew.

**Networking** — Onboard relay capability for extended range.

**Config files** — Proprietary.

**Launch files** — N/A.

**Dependencies** — Teledyne FLIR Black Recon launcher and GCS. Compatible with Black Hornet 4.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Teledyne FLIR autonomy | Proprietary | Teledyne FLIR | Autonomy/Navigation |
| Visual Inertial Navigation | Proprietary | Teledyne FLIR | Navigation/GNSS-Denied |
| Launcher control | Proprietary | Teledyne FLIR | Control/Launcher |
| Payload integration | Proprietary | Teledyne FLIR | Payload/Integration |

---

## Interface

**Emits** — Real-time imagery and targeting data. Vehicle telemetry.

**Accepts** — Mission commands. Autonomous launch/recovery commands.

**Serves** — Continuous reconnaissance and targeting data.

**Executes** — Autonomous launch, reconnaissance, target acquisition, recovery, and recharge.

**Extensions** — Optional 100-gram mission modules (lethality, sensor, CBRN).

**Frame conventions** — Geographic coordinates. NED for navigation.

**Units** — SI and military standard.

---

## Model

**URDF / Xacro** — Not applicable.

**SDF** — Not applicable.

**Calibration** — Factory calibrated.

**Dynamics** — Proprietary.

**Sensor transforms** — Thermal and visible payloads.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested.

**Integration** — Vehicle integration and launcher verification.

**Field** — Market launch at Eurosatory 2026. Deliveries expected to begin in 2027.

**Endurance** — 50–60 minutes per UAV.

**Environmental** — GNSS-denied and RF-contested environments.

**Known limitations** — Not yet in service (deliveries begin 2027). Vehicle-integrated only; not man-portable. Operational temperature and wind limits not publicly specified.

---

## Log

**Build history** — Market launch at Eurosatory 2026. Deliveries expected to begin in 2027.

**Open issues** — Mission module qualification (lethality, CBRN). Vehicle integration for additional platforms.

**Changelog** — Version 1.0: initial production configuration.

**Lessons learned** — Vehicle-integrated autonomous launch, recovery, and recharge eliminates the need for crew exposure. Three-UAV rotation provides persistent surveillance. Visual Inertial Navigation enables radio-silent missions in GNSS-denied environments.

**Cost actual** — Not publicly disclosed.

---

## Status

**Condition** — operational (market launch 2026; deliveries expected 2027).

**Blockers** — None.

**Next steps** — Deliveries to begin 2027. Qualification of optional mission modules. Vehicle integration expansion.

---

**Note on this Shell:** The blackrecon is a distinct class in the library: a **vehicle-integrated micro UAS** designed for **autonomous, persistent ISR in contested environments**. Unlike the wraith (man-portable, 70–178 g) or the puma (hand-launched, Group 2), the Black Recon is a system-of-systems approach: three <450 g UAVs launched, recovered, and recharged autonomously from a vehicle-mounted launcher, providing 50–60 minutes of flight time per UAV and near-continuous overwatch without crew exposure. The Visual Inertial Navigation enables radio-silent missions in GNSS-denied environments, and the open mission-module architecture is designed to evolve from persistent reconnaissance to hazard detection and active engagement.
