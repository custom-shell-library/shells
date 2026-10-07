# raven

**Class:** aerial (Group 1 hand-launched fixed-wing UAS)  
**Generation:** 1  
**Version:** RQ-11B Raven B  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** AeroVironment  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Hand-launched, man-portable Group 1 fixed-wing unmanned aircraft system designed for local persistent surveillance and reconnaissance at the squad, platoon, and company level. The Raven is not a strategic asset; it is a **small unit organic ISR platform** that one soldier can carry in a backpack, assemble in minutes, launch by hand, and leave airborne for 60–90 minutes of continuous day/night observation. Its defining characteristics are **true man-portability** (under 5 lbs), **stabilized EO/IR gimbaled payload** (Mantis i23), and **digital data link** with a 10 km operational range. It is the most widely deployed small UAS in the world, the US Army’s Program of Record for the lowest elements of the tactical force, and the reference for a hand-launched, soldier-carried, local surveillance drone.

**Environment** — Outdoor, all-weather, day and night operations. Hand-launched from any open area; recovered by deep-stall or skid landing. Operating altitude 100–500 ft AGL typical, maximum 10,500 ft MSL. Endurance 60–90 minutes depending on payload and conditions, 75+ minutes with Mantis i23. Operating temperature range not publicly specified, but the Raven is deployed in extreme environments from desert heat to Arctic cold. Not for operations in icing conditions or severe turbulence without additional protection. The airframe is electrically powered, producing a low acoustic signature.

**Mission** — Local persistent surveillance, route reconnaissance, force protection, overwatch, target acquisition, and battle damage assessment. The Raven carries the Mantis i23 gimbaled payload with a 5 MP daylight camera, 640×512 LWIR thermal camera, four zoom levels, and a laser illuminator, delivering real-time imagery and geolocation data in day/night conditions. It is designed for rapid deployment and high mobility, providing the lowest tactical echelons with dedicated aerial observation. The Raven has also been used as an airborne communications node, extending secure communications in contested environments.

**Operator** — One soldier for launch and recovery, one operator for flight control via Ground Control Station (GCS) or Remote Video Terminal (RVT). The aircraft weighs 4.2–4.8 lbs and is hand-launched, requiring no runway or launch equipment. The soldier carries the aircraft, GCS, and payload in a backpack. The Raven is designed for rapid deployment and high mobility; setup and launch take only a few minutes.

**Reusability** — Commercial defence platform with global service. The Raven is the most widely deployed small UAS in the world. It is the US Army’s Program of Record for the lowest elements of the tactical force and has been fielded with every branch of the US military and numerous allied nations. Production and sustainment contracts continue, with the US Army awarding contracts for Raven systems and gimbaled payloads.

---

## Spec

**Physical** — Wingspan 4.5 ft (1.4 m). Length 3 ft (0.9 m). Weight 4.2–4.8 lbs (1.9–2.2 kg) depending on payload. Maximum payload weight 0.4 lbs (0.18 kg). The airframe is constructed from lightweight composite materials with a high aspect ratio wing for efficient cruise and endurance. The aircraft folds or disassembles for backpack transport. The Mantis i23 payload weighs 450 g and is a ruggedized multi-axis gimbaled sphere capable of continuous pan.

**Kinematic** — Fixed-wing, hand-launched. Recovery by deep-stall or skid landing. Control surfaces actuated by electromechanical actuators. The aircraft is electrically powered with a single pusher propeller. Cruise speed 30 mph (48 km/h, 17 kts), dash speed 60 mph (96 km/h, 44 kts). The flight control system manages all phases of flight, including hand launch, waypoint navigation, and recovery. The aircraft is designed for rapid deployment and high mobility.

**Dynamic** — Endurance 60–90 minutes (up to 90 minutes with fixed EO or IR payload; 75+ minutes with Mantis i23). Operational range 10 km (6.2 miles) line-of-sight. Operating altitude 100–500 ft AGL typical, maximum 10,500 ft MSL. The Raven’s endurance and range make it suitable for sustained local surveillance over a company or platoon area of operations. The digital data link (DDL) provides 10 km range with 4.5 Mbit/s data transfer.

**Power** — Battery-powered electric propulsion. Battery capacity not publicly specified, but sufficient for 60–90 minutes of flight. The aircraft is hand-launched, requiring no fuel logistics. The all-electric powertrain produces a low acoustic signature, making the Raven difficult to detect at low altitude. Battery charging via the GCS or a field charger.

**Thermal** — Passive cooling. The electric motor is air-cooled by ram air in forward flight. The avionics and payload are housed in the fuselage with adequate ventilation. No active thermal management required. The low thermal signature reduces detectability compared to internal combustion engines. The Mantis i23 thermal camera (640×512 LWIR) enables day/night observation.

**Environmental** — Designed for all-weather operations. The Raven is deployed in extreme environments from desert heat to Arctic cold. Not rated for icing conditions without additional protection. The composite airframe is resistant to UV degradation and environmental exposure. The hand-launched design enables deployment from any open area, including confined spaces and small clearings.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The Raven is purchased as a complete system with GCS, RVT, and modular payloads.

| Component | Notes |
|:---|:---|
| RQ-11B Raven airframe | Composite construction, 4.5 ft wingspan, 4.2–4.8 lbs weight |
| Electric motor | Brushless DC, pusher propeller |
| Battery | Rechargeable, 60–90 minutes endurance |
| Mantis i23 gimbaled payload | Dual 5 MP EO/IR + LWIR thermal, 4x zoom, laser illuminator, 450 g |
| Digital Data Link (DDL) | 10 km range, 4.5 Mbit/s data transfer |
| Ground Control Station (GCS) | Operator interface for flight control and payload tasking |
| Remote Video Terminal (RVT) | Handheld video terminal for remote viewing |
| Interchangeable payloads | Fixed EO, fixed IR, or gimbaled EO/IR |

**Structure** — Lightweight composite airframe with high aspect ratio wing. The fuselage houses the electric motor, battery, avionics, and payload bay. The aircraft is designed for hand launch and deep-stall or skid recovery. The Mantis i23 payload is a gimbaled sphere mounted in the fuselage, providing continuous pan and stabilized EO/IR imagery. The airframe disassembles or folds for backpack transport. The Raven B introduced the digital data link (DDL) and stabilized gimbaled payload, replacing the earlier analog data link and fixed camera.

**Actuation** — Single brushless DC electric motor driving a pusher propeller. Control surfaces actuated by electromechanical actuators. The flight control system manages hand launch, waypoint navigation, and recovery autonomously. The aircraft is hand-launched, requiring no runway or launch equipment. The Mantis i23 gimbal is actuated by a multi-axis stabilization system.

**Locomotion** — Fixed-wing flight. Hand-launched and recovered by deep-stall or skid landing. Cruise speed 30 mph, dash speed 60 mph. The Raven flies a conventional fixed-wing profile during cruise, loiter, and search patterns. The hand-launched design enables deployment from any open area, including confined spaces and small clearings.

**Manipulation** — None. The aircraft is a sensor platform. The payload is the effector: EO/IR cameras, thermal imager, and laser illuminator. The Mantis i23 provides stabilized day/night imagery with 4x zoom and laser illumination for targeting and observation.

**Power system** — Battery-powered electric propulsion. Battery capacity not publicly specified, but sufficient for 60–90 minutes of flight. The aircraft is hand-launched and requires no fuel logistics. The all-electric powertrain produces a low acoustic signature. Battery charging via the GCS or a field charger. The Raven B can also be equipped with a communications relay payload, turning the aircraft into a secure comms node.

**Wiring** — Internal only. Not user-accessible. Payload integration via the modular payload bay. The Mantis i23 payload is a line-replaceable unit (LRU). The digital data link (DDL) provides encrypted video and telemetry to the GCS and RVT.

**Custom parts** — None. All components are AeroVironment proprietary or certified third-party. The modular payload bay supports interchangeable EO, IR, and gimbaled EO/IR payloads. The Raven B system includes the aircraft, GCS, RVT, EO/IR payloads, and batteries in a backpack configuration.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for rapid assembly and recovery by a single soldier, with modular components for field assembly and maintenance.

**Tools required** — None for assembly (factory-built). No tools required for payload changes. The aircraft assembles and launches in minutes by a single soldier.

---

## Systems

**Manifest** — AeroVironment proprietary software stack with digital data link and modular payload integration.

**Firmware** — The aircraft runs a proprietary flight control system with autonomous operation, including hand launch, waypoint navigation, and recovery. The Raven B uses a digital data link (DDL) that provides 10 km range and 4.5 Mbit/s data transfer, replacing the earlier analog data link. The flight control system manages all phases of flight. The aircraft can be operated manually or programmed for GPS-based autonomous navigation.

**Middleware** — AeroVironment proprietary. The digital data link (DDL) provides encrypted video and telemetry to the GCS and RVT. The GCS and RVT are interchangeable; both can control the aircraft and display video. The RVT allows remote viewing by units other than the launch crew. The DDL has a 10 km range and 4.5 Mbit/s data transfer rate.

**Perception** — Mantis i23 gimbaled payload:
- **Dual 5 MP EO/IR**: 5 MP daylight camera and 640×512 px LWIR thermal camera with four zoom levels.
- **Laser illuminator**: Integrated for low-light illumination and targeting.
- **Stabilized gimbal**: Multi-axis sphere with continuous pan for stabilized imagery.
- **Interchangeable payloads**: Fixed EO, fixed IR, or gimbaled EO/IR payloads are fielded with each system.
- **Mantis i23 D**: Dual 18 MP EO payload option.

**Control** — The flight control system manages all phases of flight autonomously. The operator provides mission-level command: area of interest, search patterns, and payload tasking. The Raven B is controlled via the GCS or RVT. The aircraft can be manually or autonomously navigated while providing real-time situational awareness and actionable intelligence. The Raven B has been used as an airborne communications node, extending secure communications in contested environments.

**Planning** — Mission planning is performed at the GCS. The operator defines the area of interest and the aircraft autonomously navigates to the location, then loiters or performs search patterns. The aircraft can be retasked in flight. Hand launch and deep-stall recovery enable rapid deployment from forward positions or confined spaces. The Raven is designed for rapid deployment and high mobility.

**Learning** — None publicly disclosed. The aircraft uses classical control, autonomous navigation, and sensor fusion. No learning-based control is mentioned for safety-critical functions.

**Teleoperation** — One soldier for launch and recovery, one operator for flight control via GCS or RVT. The operator provides mission-level command and manages the payload. The aircraft handles flight control, navigation, and recovery. The GCS and RVT are interchangeable, allowing remote viewing by units other than the launch crew.

**Safety** — The aircraft is hand-launched, reducing the risk of launch failures associated with catapults or runways. The digital data link (DDL) provides encrypted video and telemetry, reducing the risk of interception. The low acoustic and thermal signatures reduce detectability. The Raven B has been used as a secure comms node in contested environments, demonstrating resilience. The aircraft is recovered by deep-stall or skid landing, reducing the risk of damage during recovery.

**Logging** — Mission data, sensor data, and flight telemetry are logged. The Raven is the most widely deployed small UAS in the world, with extensive operational use. Specific logging details are not publicly disclosed, but the system is designed for ISR missions where evidence capture and target tracking are important.

**Networking** — Digital Data Link (DDL) with 10 km range and 4.5 Mbit/s data transfer. The DDL provides encrypted video and telemetry to the GCS and RVT. The Raven can carry a communications relay payload for network extension. The GCS and RVT are interchangeable, enabling distributed viewing and control.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through the GCS.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — AeroVironment GCS software. Remote Video Terminal (RVT). Mantis i23 payload software. Digital Data Link (DDL) software.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| AeroVironment flight control | Proprietary | AeroVironment | Control/Flight |
| Digital Data Link (DDL) | Proprietary | AeroVironment | Comms/Datalink |
| Ground Control Station (GCS) | Proprietary | AeroVironment | GCS |
| Remote Video Terminal (RVT) | Proprietary | AeroVironment | GCS |
| Mantis i23 payload software | Proprietary | AeroVironment | Sensors/EOIR |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, battery state, system health. Sensor data: EO/IR imagery, thermal imagery, laser illumination status. Network data: DDL link status, relay node status (if equipped).

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Payload commands. Hand launch and recovery commands.

**Serves** — Local persistent ISR services. Route reconnaissance. Force protection. Target acquisition. Communications relay services.

**Executes** — Autonomous hand launch, waypoint navigation, persistent ISR over a local area, target acquisition, deep-stall recovery. Return-to-base in comms-denied environment.

**Extensions** — Modular payload bay (interchangeable EO, IR, gimbaled EO/IR). Communications relay payload. Mantis i23 and Mantis i23 D payloads.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in mph or knots. Altitude in feet MSL or AGL.

**Units** — SI and aviation standard. Metres, feet, miles, kilometres, miles per hour, kilometres per hour, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for Mantis i23 EO/IR and laser illuminator. Flight control system calibrated for hand launch and deep-stall recovery. Digital data link calibrated for 10 km range.

**Dynamics** — Proprietary. The aircraft’s aerodynamic model is used for flight control and autonomy. The high aspect ratio wing provides efficient cruise and 60–90 minutes of endurance. The electric motor provides sufficient thrust for the 4.2–4.8 lb MTOW and the 0.4 lb payload. The Mantis i23 gimbal is stabilized for continuous pan and clear imagery.

**Sensor transforms** — Mantis i23 payload mounted in the fuselage with continuous pan. Fixed EO or IR payloads mounted in the nose. Communications relay payload mounted in the fuselage.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of motor, battery, flight control system, and payloads.

**Integration** — Payload integration in the modular bay. Flight control system verification. Digital Data Link (DDL) verification. Mantis i23 gimbal and EO/IR verification. Communications relay payload verification.

**Field** — The most widely deployed small UAS in the world. US Army Program of Record for the lowest elements of the tactical force. Fielded with every branch of the US military and numerous allied nations. Used in Afghanistan, Iraq, and other operational theaters. Used as an airborne communications node in contested environments. US Army awarded contracts for Raven systems and gimbaled payloads (2013, 2017). US Air Force awarded contract for Raven RQ-11B (2018).

**Endurance** — 60–90 minutes (up to 90 minutes with fixed EO or IR payload; 75+ minutes with Mantis i23). Operational range 10 km (6.2 miles) line-of-sight. Operating altitude 100–500 ft AGL typical, maximum 10,500 ft MSL.

**Environmental** — All-weather operations. Deployed in extreme environments from desert heat to Arctic cold. Not for icing conditions without additional protection.

**Known limitations** — The Raven is a Group 1 UAS with a 0.4 lb payload capacity; it cannot carry large sensors or heavy equipment. The 60–90 minute endurance is shorter than larger fixed-wing or hybrid VTOL platforms. The aircraft requires a soldier to carry and launch it, and a second operator for flight control. The Raven B requires the Mantis i23 gimbaled payload for day/night observation; fixed EO or IR payloads have shorter endurance. The aircraft is not stealth; it relies on low acoustic and thermal signatures, altitude, and small size for survivability. The deep-stall or skid recovery requires a suitable landing area and may damage the airframe in rough terrain.

---

## Log

**Build history** — RQ-11 Raven developed by AeroVironment. RQ-11A introduced in 2003; RQ-11B Raven B introduced with digital data link (DDL) and stabilized gimbaled payload. The Raven is the US Army’s Program of Record for the lowest elements of the tactical force. It is the most widely deployed small UAS in the world. The Mantis i23 gimbaled payload was introduced in 2013; US Army awarded $13.5 million for Raven systems and gimbaled payloads (2013). US Army awarded $16.5 million for Raven systems with miniature gimbaled payload (2017). US Air Force awarded contract for Raven RQ-11B (2018). US Army awarded avionics and data link upgrade packages for the Raven (2021).

**Open issues** — Integration of new payloads (communications relay, SIGINT). Expansion of digital data link capabilities. Production scaling to meet demand. Export control and ITAR restrictions.

**Changelog** — RQ-11A: initial production configuration. RQ-11B Raven B: digital data link (DDL) and stabilized gimbaled payload. Mantis i23: 5 MP EO/IR + LWIR, 4x zoom, laser illuminator (2013). Mantis i23 D: dual 18 MP EO (later). US Army avionics and data link upgrades (2021).

**Lessons learned** — The hand-launched, man-portable design is the key enabler of small unit organic ISR. The stabilized gimbaled payload (Mantis i23) dramatically improves troops’ capabilities by providing continuous pan and day/night imagery. The digital data link (DDL) provides 10 km range and 4.5 Mbit/s data transfer, enabling real-time video and telemetry. The Raven can be used as an airborne communications node, extending secure communications in contested environments. The Raven is the most widely deployed small UAS in the world, validating the platform’s reliability and effectiveness.

**Cost actual** — US Army awarded $13.5 million for Raven systems and gimbaled payloads (2013). US Army awarded $16.5 million for Raven systems with miniature gimbaled payload (2017). US Air Force awarded contract for Raven RQ-11B (2018). Unit cost varies by configuration, payload, and quantity.

---

## Status

**Condition** — operational. Fielded with every branch of the US military and numerous allied nations. The most widely deployed small UAS in the world. US Army Program of Record for the lowest elements of the tactical force.

**Blockers** — None. Active production and global service.

**Next steps** — Integration of new payloads (communications relay, SIGINT). Continued fielding with US Army, US Marine Corps, US Air Force, and allied nations. Expansion of digital data link capabilities. Production scaling to meet demand. Development of successor systems with enhanced endurance and autonomy.

---

**Note on this Shell:** The raven is a distinct class in the library: a Group 1 hand-launched fixed-wing UAS designed for **small unit organic ISR** with 60–90 minutes of endurance and a 0.4 lb modular payload capacity. Unlike the puma (Group 2, 5.5–6.5 hours, 5.5 lb payload) or the skydio (Group 1 quadcopter, 40 minutes, 340 g payload), the Raven is a true backpack-portable, hand-launched aircraft that a single soldier can carry, assemble, and launch in minutes. Its stabilized Mantis i23 gimbaled payload provides day/night EO/IR imagery with 4x zoom and a laser illuminator, delivering real-time imagery and geolocation data to the GCS and RVT. The digital data link (DDL) provides 10 km range and 4.5 Mbit/s data transfer, and the Raven can be used as an airborne communications node in contested environments. As the most widely deployed small UAS in the world and the US Army’s Program of Record for the lowest tactical echelons, the Raven is the reference for a hand-launched, soldier-carried, local surveillance drone with long-endurance persistence for its size.
