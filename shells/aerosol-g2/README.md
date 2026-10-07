# aerosol-g2

**Class:** aerial (nano UAS / local stealth ISR)  
**Generation:** 1  
**Version:** 2.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Aero-Sentinel  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Ultra-quiet quadcopter designed for covert local surveillance, reconnaissance, and intelligence gathering in sensitive urban, tactical, and special operations environments. The Aerosol G2 is not a strategic asset; it is a **silent spy platform** engineered around a single core design objective: **acoustic invisibility**. Its defining characteristic is its recorded noise level of **14.9 decibels at one kilometre** — effectively inaudible in field conditions and up to 10 decibels quieter than commercial drones like the DJI Matrice 350 and Autel Alpha. It has reportedly been used in sensitive intelligence operations, including during Israel's 2025 campaign against Iranian targets, to identify and confirm high-value assets inside adversary territory.

**Environment** — Outdoor and indoor, day and night. Designed for urban areas and complex terrain where discreet observation is required. Covert operating altitude up to 150 m. Maximum wind resistance 15 knots (28 km/h). Operating temperature range not publicly specified, but the platform is designed for rapid deployment in operational environments where traditional surveillance aircraft may not be practical.

**Mission** — Covert local surveillance, intelligence gathering, target identification, infrastructure monitoring, and special operations reconnaissance. The G2 is designed to monitor areas without alerting targets on the ground. Its low acoustic output allows observation missions with a lower probability of detection. It is intended for use by intelligence and special operations units that require discreet surveillance capabilities before kinetic strikes or other operational actions.

**Operator** — Single operator. The system is designed for rapid deployment in operational environments. The G2 provides a day and night video stream via ground control station, with a flight endurance of up to 80 minutes and a range of 4–5 km.

**Reusability** — Commercial defence platform with active production. Aero-Sentinel confirmed a new order from a returning U.S. customer in March 2026 for systems used in ISR and operational surveillance missions. The company views repeat orders as the strongest validation of field performance.

---

## Spec

**Physical** — Takeoff weight 3.5–4 kg. Dimensions 60 cm × 60 cm. The airframe is a quadcopter configuration with four electric motors, optimised for low acoustic signature. Payload capacity up to 1 kg. Maximum speed 43 km/h (12 m/s).

**Kinematic** — Quadcopter configuration. Four electric motors driving four rotors. The acoustic signature is the primary engineering constraint; the motor, propeller, and airframe design are all optimised to minimise noise. Maximum flight speed 43 km/h. The aircraft is designed for stable hover and low-speed observation, not high-speed transit.

**Dynamic** — Endurance up to 80 minutes. Range 4–5 km. Covert operating altitude up to 150 m. Maximum wind resistance 15 knots (28 km/h). The acoustic signature is the defining performance metric: **74.9 dB at one metre**, **28.9 dB at 200 metres**, and **14.9 dB at one kilometre**. For comparison, the DJI Matrice 350 recorded 85.1 dB at one metre, and the Autel Alpha recorded 80.3 dB at one metre — the G2 is 5–10 dB quieter at close range and effectively silent at distance.

**Power** — Electric propulsion. Battery capacity not publicly specified, but sufficient for 80 minutes of flight. The all-electric powertrain produces the low acoustic signature that defines the platform. No fuel logistics required.

**Thermal** — Passive cooling. The electric motors are air-cooled by rotor wash. The low thermal signature reduces detectability by infrared sensors. No active thermal management is required.

**Environmental** — Designed for urban and complex terrain operations. The G2 is rapidly deployable in operational environments where traditional surveillance aircraft may not be practical. Not rated for severe weather. The low acoustic signature is the primary environmental adaptation.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The G2 is purchased as a complete system with ground control station and payload.

| Component | Notes |
|:---|:---|
| Aerosol G2 airframe | Quadcopter, 60 × 60 cm, 3.5–4 kg takeoff weight |
| Four electric motors | Optimised for low acoustic signature |
| Propellers | Noise-optimised blade design |
| HD camera | High-resolution day camera |
| Thermal imager | IR sensor for night operations |
| Encrypted communication module | Secure video and telemetry link |
| Autonomous flight system | Waypoint navigation and autonomous operation |
| Ground control station | Day and night video stream, real-time ISR data display |

**Structure** — Quadcopter airframe with four arms. The airframe is designed with acoustic signature as the primary constraint: motor mounts, propeller selection, and airframe geometry all contribute to the 14.9 dB at 1 km figure. The payload includes a high-resolution camera and encrypted communication module. The autonomous flight system enables waypoint navigation without continuous manual control.

**Actuation** — Four brushless DC electric motors. The motor and propeller combination is the primary determinant of the acoustic signature. The G2's 74.9 dB at 1 metre is 5–10 dB quieter than commercial alternatives, which represents a significant reduction in radiated acoustic power.

**Locomotion** — Rotary-wing flight. The G2 is designed for hover and low-speed observation, with a maximum speed of 43 km/h. It is not a high-speed transit platform; its value is in remaining undetected while observing.

**Manipulation** — None. The aircraft is a sensor platform. The payload is the effector: HD camera and thermal imager for day and night observation.

**Power system** — Electric propulsion. Battery capacity not publicly specified, but sufficient for 80 minutes of endurance. The all-electric design is essential for the low acoustic signature.

**Wiring** — Internal only. Not user-accessible. Payload integration is factory-configured. The encrypted communication module provides secure video and telemetry to the ground control station.

**Custom parts** — None. All components are Aero-Sentinel proprietary. The platform is delivered as a complete system.

**Fasteners** — Proprietary. Not user-serviceable.

**Tools required** — None for assembly (factory-built). Standard tools for field maintenance. The system is designed for rapid deployment.

---

## Systems

**Manifest** — Aero-Sentinel proprietary software stack with autonomous flight and encrypted communications.

**Firmware** — The aircraft runs a proprietary flight control system with autonomous operation. The G2 supports waypoint navigation and autonomous flight. The acoustic signature is managed through motor control algorithms that optimise propeller RPM and blade loading for minimum noise.

**Middleware** — Proprietary. The encrypted communication module provides secure video and telemetry to the ground control station. The G2 is designed for operation in complex operational environments where communications may be contested.

**Perception** — High-resolution day camera and thermal imager. The G2 provides day and night video stream via ground control station. Platforms designed for special operations surveillance are typically equipped with high-resolution cameras, encrypted communication systems, and autonomous flight capabilities that allow operators to maintain observation from a distance.

**Control** — The flight control system manages hover, waypoint navigation, and autonomous flight. The operator provides mission-level command: area of interest, observation points, and payload tasking. The low acoustic signature allows the operator to position the aircraft close to the target without detection.

**Planning** — Mission planning is performed at the ground control station. The operator defines waypoints and the aircraft autonomously navigates to the location, then hovers or loiters for observation. The 80-minute endurance enables sustained observation of a target area.

**Learning** — None publicly disclosed. The aircraft uses classical control and autonomous navigation. No learning-based control is mentioned.

**Teleoperation** — Single operator via ground control station. The operator provides mission-level command and monitors the day/night video feed. The autonomous flight system reduces operator workload during observation.

**Safety** — The low acoustic signature is the primary safety feature: the aircraft is difficult to detect by acoustic sensors. The encrypted communication link reduces the risk of interception. The autonomous flight system reduces the risk of loss due to operator error. The G2's acoustic invisibility at distance allows it to operate in environments where conventional drones would be detected and engaged.

**Logging** — Mission data, sensor data, and flight telemetry are logged. Specific logging details are not publicly disclosed, but the system is designed for ISR missions where evidence capture and target identification are important.

**Networking** — Encrypted communication module for secure video and telemetry. Range 4–5 km. The G2 operates in complex operational environments where traditional surveillance aircraft may not be practical.

**Config files** — Proprietary. No user-accessible config files.

**Launch files** — N/A (proprietary defence software).

**Dependencies** — Aero-Sentinel ground control station software. Encrypted communication module. Payload-specific software (EO/IR).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Aero-Sentinel flight control | Proprietary | Aero-Sentinel | Control/Flight |
| Acoustic optimisation | Proprietary | Aero-Sentinel | Control/Acoustic |
| Encrypted data link | Proprietary | Aero-Sentinel | Comms/Encrypted |
| GCS software | Proprietary | Aero-Sentinel | GCS |
| Payload integration software | Proprietary | Aero-Sentinel | Payload/Integration |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, battery state, system health. Sensor data: HD day video, thermal IR video.

**Accepts** — Mission commands (waypoints, observation points, payload tasking). Navigation commands. Payload commands.

**Serves** — Covert local ISR services. Target identification. Infrastructure monitoring. Special operations reconnaissance.

**Executes** — Autonomous waypoint navigation, hover and observation, day/night video capture. Return-to-base.

**Extensions** — Payload configured at factory. The platform is delivered as a complete system with HD camera, thermal imager, encrypted communication module, and autonomous flight system.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body.

**Units** — SI and aviation standard. Metres, kilometres, kilometres per hour, decibels, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for HD camera and thermal imager. Acoustic signature characterised through independent testing.

**Dynamics** — Proprietary. The aircraft's aerodynamic and acoustic models are used for flight control and noise optimisation. The 14.9 dB at 1 km figure is the result of integrated design across motor, propeller, and airframe.

**Sensor transforms** — HD camera and thermal imager mounted in the fuselage.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of motors, propellers, flight control system, and payloads.

**Integration** — Payload integration. Flight control system verification. Encrypted data link verification. Acoustic signature verification.

**Field** — Independent acoustic testing: 74.9 dB at 1 metre, 28.9 dB at 200 metres, 14.9 dB at 1 kilometre. Comparison testing: 5–10 dB quieter than DJI Matrice 350 and Autel Alpha at 1 metre. Operational use: reportedly used during Israel's 2025 campaign against Iranian targets for covert reconnaissance and target confirmation. U.S. customer order confirmed March 2026.

**Endurance** — 80 minutes. Range 4–5 km. Covert altitude up to 150 m.

**Environmental** — Urban and complex terrain. Maximum wind 15 knots (28 km/h).

**Known limitations** — The G2 is a quadcopter with a 1 kg payload capacity; it cannot carry large sensors. The 80-minute endurance is limited compared to fixed-wing platforms. The 4–5 km range is shorter than larger tactical UAS. The acoustic signature, while exceptional, is still detectable at close range (74.9 dB at 1 m). The platform is optimised for covert observation, not for high-speed transit or wide-area search.

---

## Log

**Build history** — Aerosol G2 developed by Aero-Sentinel (Israel). Acoustic testing results published October 2025. Operational use reported during Israel's 2025 campaign against Iranian targets. U.S. customer order confirmed March 2026.

**Open issues** — Expansion of payload options. Production scaling to meet demand. Export control and ITAR restrictions.

**Changelog** — G2: initial production configuration. G2 Premium: enhanced acoustic performance, 14.9 dB at 1 km.

**Lessons learned** — Acoustic signature is a critical survivability feature for covert surveillance drones. The G2's 14.9 dB at 1 km makes it effectively inaudible in field conditions, allowing observation missions with a lower probability of detection. The platform's operational use in sensitive intelligence operations validates its effectiveness. The U.S. customer repeat order is the strongest validation of field performance.

**Cost actual** — Not publicly disclosed. Unit cost varies by configuration and quantity.

---

## Status

**Condition** — operational. Fielded with Israeli special operations and intelligence units. U.S. customer orders confirmed.

**Blockers** — None. Active production and procurement.

**Next steps** — Integration of new payloads. Expansion of export sales. Production scaling to meet demand.

---

**Note on this Shell:** The aerosol-g2 is a distinct class in the library: a **nano UAS optimised specifically for acoustic invisibility** in covert local surveillance and reconnaissance. Unlike the wraith (Black Hornet/Trace, 70–178 g, 25–45 min endurance, <37 dBA at 25 m) or the puma (Group 2, 5.5 h endurance), the G2 is engineered around a single design constraint: **silence**. Its 14.9 dB at 1 km is the lowest recorded acoustic signature of any operational quadcopter in its class, and it has been used in sensitive intelligence operations to identify high-value targets. The platform represents the extreme end of the stealth surveillance spectrum: a drone that is functionally undetectable by acoustic sensors at operational distances, designed for special operations and intelligence units that require discreet observation before kinetic action.
