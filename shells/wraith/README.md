# wraith

**Class:** aerial (nano UAS / local stealth ISR)  
**Generation:** 1  
**Version:** 1.0.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Teledyne FLIR / Vantage Robotics  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Nano-scale unmanned aircraft system designed for covert local surveillance, reconnaissance, and intelligence gathering in confined and contested environments. The Wraith is not a strategic asset; it is a **pocket-sized spy platform** that a single dismounted soldier or operator can carry on a utility belt, hand-launch in seconds, and use to see over walls, around corners, and inside buildings without exposing themselves to enemy fire. Its defining characteristics are **near-silent acoustic signature** (<37 dBA at 25 m), **near-invisible visual signature** (not visible at 30 ft against terrain), **GPS-denied autonomous navigation**, and **day/night EO/IR imaging** in a package weighing under 200 grams. It represents the extreme end of the local surveillance spectrum: a drone that is functionally a flying sensor, small enough to be mistaken for a bird or insect, and quiet enough to be undetectable at conversational distances.

**Environment** — Outdoor and indoor, all-weather, day and night. IP52 rated (rain up to 7.6 mm/hr). Operating temperature not publicly specified, but deployed from desert heat to Arctic cold. Wind tolerance 25 knots + gusts (13 m/s). Maximum speed 10–25 m/s depending on configuration. Endurance 25–60 minutes depending on platform variant. Deployed from hand, utility belt, or armored vehicle. Not for operations in severe icing conditions without additional protection.

**Mission** — Covert local surveillance, beyond-line-of-sight reconnaissance, force protection, urban warfare, building clearing, cave and tunnel exploration, and threat detection without exposing the operator. The Wraith transmits live video and HD still images back to the operator through an encrypted data link with a range up to 3+ km. It is designed for the dismounted soldier, special operations forces, and law enforcement tactical teams. The platform bridges the gap between aerial and ground-based sensors: it provides the situational awareness of a larger UAV with the threat-location capabilities of a UGV, but at a fraction of the size and acoustic signature.

**Operator** — Single operator. The system weighs 1.3 kg total and fits on a utility belt. The ground control station (GCS) has integral UAV containers and requires minimal training. The operator hand-launches the aircraft, controls it via the GCS with a sunlight-readable display, and views live video and still imagery. For vehicle-integrated operations, the operator can launch, recover, and recharge up to three UAVs without leaving the platform.

**Reusability** — Commercial defence platform with active production and global service. Over 35,000 Black Hornet units supplied to users in over 45 countries. The Black Hornet 4 was approved for the Defense Innovation Unit's Blue UAS List in 2025. The platform is combat-proven with NATO forces and has been used operationally in Ukraine, Afghanistan, Iraq, and border security missions.

---

## Spec

**Physical** — Rotor diameter 190 mm (7.5 in). Total length 255 mm (10 in). Weight 70 grams (2.5 oz) for the Black Hornet 4; 153–178 grams for the Trace. Total system weight 1.3 kg, small enough for a dismounted soldier to carry on a utility belt. The airframe is a quadcopter or coaxial helicopter configuration with composite construction. The Black Hornet 4 uses a helicopter-like form factor with a single main rotor and tail rotor, while the Trace uses a conventional quadcopter with folding arms.

**Kinematic** — Quadcopter or coaxial helicopter configuration. Maximum speed 10–25 m/s (36–90 km/h) depending on variant. The Black Hornet 4 is wind tolerant up to 25 knots + gusts (13 m/s) and has ground speeds up to 10 m/s. The Trace has a top speed of 52 km/h (32 mph). The aircraft is hand-launched and recovered by hand or autonomous landing. For vehicle integration (Black Recon), autonomous launch, recovery, and recharge from military vehicles and fixed installations enable three-UAV rotation for persistent surveillance.

**Dynamic** — Endurance 25 minutes (Black Hornet 3), 30+ minutes (Black Hornet 4), 50–60 minutes (Black Recon), or 36–45 minutes (Trace). Range 2 km (Black Hornet 3), 3+ km (Black Hornet 4), or 6 km LOS / 500 m NLOS (Trace). The Black Hornet 4 can operate in GPS-denied environments, rain, and 25-knot winds. The Trace has an acoustic signature under 37 dBA at 25 m and remains completely unseen and inaudible at 30 ft.

**Power** — Electric propulsion. Battery capacity not publicly specified, but sufficient for the endurance figures above. The aircraft is hand-launched, requiring no fuel logistics. The all-electric powertrain produces a near-silent acoustic signature. For vehicle-integrated operations, autonomous recharge from the launcher enables continuous operations without battery swaps.

**Thermal** — Passive cooling. The electric motors are air-cooled by rotor wash. The avionics and payload are housed in the fuselage with adequate ventilation. The low thermal signature reduces detectability by infrared sensors compared to larger platforms. The Black Hornet 4 and Trace carry thermal imagers for day/night operation.

**Environmental** — IP52 rated (Black Hornet 4: 7.6 mm rain/hr; Trace: IP67 protective field case for the GCS). Wind tolerance 25 knots + gusts. Operating temperature range not publicly specified, but deployed in extreme environments. The composite airframe is resistant to UV degradation and environmental exposure. The hand-launched design enables deployment from confined spaces.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The Wraith is purchased as a complete system with GCS and payload.

| Component | Notes |
|:---|:---|
| Nano UAS airframe | Black Hornet 4: 70 g, 190 mm rotor; Trace: 153–178 g, 12 in span |
| Electric motors | Brushless DC, near-silent operation |
| Replaceable payload | Yes (Black Hornet 3/4); integrated gimbal (Trace) |
| Day imager | 12 MP (Black Hornet 4); 48 MP EO (Trace) |
| Night imager | High-resolution thermal imager (Black Hornet 4); 320p IR (Trace) |
| Obstacle avoidance | Black Hornet 4: advanced; Trace: 7 laser range finders |
| GNSS-denied navigation | Visual inertial navigation, visual-based navigation |
| Encrypted data link | AES-256, range up to 3+ km |
| Ground control station | 7" sunlight-readable display, integral UAV containers |
| Black Recon launcher | Autonomous launch, recovery, recharge for 3 UAVs |

**Structure** — Nano-scale airframe with composite construction. The Black Hornet 4 uses a helicopter-like form factor with a single main rotor and tail rotor, optimized for hover and low-speed observation. The Trace uses a conventional quadcopter with folding arms and a 12-inch span, optimized for stability and sensor performance. Both are designed for hand launch and recovery. The Black Recon system adds a vehicle-mounted launcher that autonomously launches, recovers, and recharges up to three UAVs in rotation.

**Actuation** — Electric motors driving rotors. The Black Hornet 4 uses a coaxial or single-rotor helicopter configuration; the Trace uses four brushless DC motors. The aircraft is hand-launched and recovered by hand or autonomous landing. For vehicle-integrated operations, the Black Recon launcher autonomously handles launch, recovery, and recharge.

**Locomotion** — Rotary-wing flight. Hand-launched and recovered. The Black Hornet 4 is wind tolerant up to 25 knots and can operate in GPS-denied environments via visual navigation. The Trace has a top speed of 52 km/h and can fly in 25-knot winds. The Black Recon system enables autonomous launch, recovery, and recharge from military vehicles, providing persistent surveillance without operator exposure.

**Manipulation** — None. The aircraft is a sensor platform. The payload is the effector: EO and IR cameras. The Black Hornet 4 carries a 12 MP daytime camera and a high-resolution thermal imager. The Trace carries a gimbal-stabilized 48 MP EO camera and 320p IR camera with 24x zoom. The Black Hornet 3/4 has a replaceable payload.

**Power system** — Electric propulsion with rechargeable batteries. The aircraft is hand-launched and requires no fuel logistics. The Black Recon system enables autonomous recharge from the launcher. The Trace has a 30-minute flight time on a standard battery and up to 45 minutes with the endurance battery. The Black Hornet 4 flies for over 30 minutes. The Black Recon UAVs have 50- to 60-minute flight times.

**Wiring** — Internal only. Not user-accessible. The Black Hornet 3/4 has a replaceable payload. The Trace has an integrated gimbal payload. The GCS has integral UAV containers and a 7-inch sunlight-readable display.

**Custom parts** — None. All components are Teledyne FLIR or Vantage Robotics proprietary. The Black Recon system has an open mission-module architecture with optional 100-gram mission modules for future lethality, sensor, and CBRN payloads.

**Fasteners** — Proprietary. Not user-serviceable. The system is designed for field deployment by a single operator with minimal training.

**Tools required** — None for assembly (factory-built). No tools required for field operation. The system requires minimal training.

---

## Systems

**Manifest** — Teledyne FLIR / Vantage Robotics proprietary software stack with GNSS-denied navigation and encrypted data links.

**Firmware** — The aircraft runs a proprietary flight control system with autonomous operation, including hand launch, waypoint navigation, and recovery. The Black Hornet 4 uses enhanced vision-based navigation for GPS-denied environments. The Trace uses downward-facing visual sensors and an integrated scene illuminator for low-light operation, maintaining full position control without GPS. The Black Recon system uses Visual Inertial Navigation for radio-silent missions without reliance on RF links.

**Middleware** — Proprietary. The encrypted data link uses AES-256 encryption with ranges up to 3+ km. The Black Hornet 4's software has been adapted to integrate with vehicle digital infrastructure (Piranha 8×8 armored engineering vehicle program), enabling live video, target data, and coordinates to be shared across onboard displays. The Trace features MAVLink and RAS-A compliant connection standards and is compatible with industry-leading GCS including Vantage Vision 2, Kutta KTAC, S20 TE, Tomahawk Mimic & Grip, QGC, ATAK, WMI, and RAC2.

**Perception** —
- **Black Hornet 4**: 12 MP daytime camera and high-resolution thermal imager. Advanced obstacle avoidance.
- **Trace**: 2-axis stabilized 48 MP EO camera and 320p IR camera with 24x zoom. Seven laser range-finding sensors for obstacle avoidance. Full position control without GPS through downward-facing visual sensors. Integrated scene illuminator for low-light operation.
- **Black Recon**: Thermal and visible payloads for real-time imagery and targeting data. GNSS-denied operation via advanced sensors and visual navigation. Radio-silent missions using Visual Inertial Navigation. Optional 100-gram mission modules for future lethality, sensor, and CBRN payloads.

**Control** — The flight control system manages all phases of flight autonomously. The operator provides mission-level command via the GCS. The Black Hornet 4 can be controlled manually or automatically through GPS. The Trace maintains full position control without GPS through visual sensors. The Black Recon system enables autonomous launch, recovery, and recharge, with three-UAV rotation for near-continuous overwatch.

**Planning** — Mission planning is performed at the GCS. The operator defines waypoints and the aircraft autonomously navigates to the location. The Black Hornet 4 can receive waypoints from vehicle Integrated Combat Solution (ICS) and generate target points for the vehicle's Remote Weapon Station. The Black Recon system enables autonomous launch from the vehicle, reconnaissance, and return to the launcher for capture, docking, and recharging.

**Learning** — The Black Hornet 4 has advanced obstacle avoidance and enhanced vision-based navigation. The Trace has AI-powered capabilities. The specific learning architectures are not publicly disclosed, but the autonomy is designed for reliability and predictability in safety-critical operations.

**Teleoperation** — Single operator via GCS with 7-inch sunlight-readable display. The system weighs 1.3 kg total and requires minimal training. The Black Hornet 4's GCS has removable mission data SD cards, increased processing capability, improved user interface, robust chargers, and enhanced vision-based navigation. The Trace is compatible with industry-leading GCS including ATAK and QGC.

**Safety** — The aircraft is hand-launched, reducing the risk of launch failures. The near-silent acoustic signature and near-invisible visual signature reduce the risk of detection. The encrypted data link (AES-256) reduces the risk of interception. The Trace weighs 153 grams, well below the FAA's intrinsically safe weight threshold, meaning it can be used in more settings without risk to personnel or bystanders. The Black Hornet 4 is IP52 rated and wind tolerant up to 25 knots.

**Logging** — Mission data, sensor data, and flight telemetry are logged. The GCS has removable mission data SD cards. Specific logging details are not publicly disclosed, but the system is designed for ISR missions where evidence capture and target tracking are important.

**Networking** — Encrypted data link with AES-256 encryption, range up to 3+ km. The Black Hornet 4's software integrates with vehicle digital infrastructure (ICS) for live video, target data, and coordinates sharing across onboard displays. The Trace features MAVLink and RAS-A compliant connection standards. The Black Recon system has onboard relay capability for extended range and radio coverage.

**Config files** — Proprietary. No user-accessible config files. Mission parameters are set through the GCS.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — Teledyne FLIR / Vantage Robotics GCS software. Payload-specific software (EO/IR). Vehicle integration software (ICS, Kongsberg Defence & Aerospace) for Black Hornet 4. ATAK, QGC, and other GCS for Trace.

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Teledyne FLIR flight control | Proprietary | Teledyne FLIR | Control/Flight |
| Vantage Robotics flight control | Proprietary | Vantage Robotics | Control/Flight |
| Vision-based navigation | Proprietary | Teledyne FLIR / Vantage | Navigation/GNSS-Denied |
| Encrypted data link | Proprietary | Teledyne FLIR / Vantage | Comms/Encrypted |
| GCS software | Proprietary | Teledyne FLIR / Vantage | GCS |
| Vehicle integration (ICS) | Proprietary | Kongsberg | Command/Control |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, battery state, system health. Sensor data: EO/IR imagery, HD still images, thermal imagery, laser range-finding data. Network data: encrypted data link status, relay node status.

**Accepts** — Mission commands (waypoints, search patterns, payload tasking). Navigation commands. Payload commands. Vehicle integration commands (ICS waypoints, target points).

**Serves** — Covert local ISR services. Beyond-line-of-sight reconnaissance. Force protection. Urban warfare support. Building clearing. Cave and tunnel exploration. Threat detection.

**Executes** — Hand launch, waypoint navigation, hover, persistent ISR over a local area, autonomous landing. GNSS-denied navigation. Radio-silent missions (Black Recon). Autonomous launch, recovery, and recharge (Black Recon).

**Extensions** — Replaceable payload (Black Hornet 3/4). Optional 100-gram mission modules for lethality, sensor, and CBRN payloads (Black Recon). Vehicle integration (ICS, Kongsberg).

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Altitude in feet MSL or AGL.

**Units** — SI and aviation standard. Metres, feet, kilometres, miles per hour, kilometres per hour, grams, pounds.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for EO/IR and laser range finders. Vision-based navigation calibrated for GPS-denied environments. Visual inertial navigation calibrated for radio-silent missions.

**Dynamics** — Proprietary. The aircraft's aerodynamic model is used for flight control and autonomy. The nano-scale airframe presents unique challenges: low Reynolds number aerodynamics, gust sensitivity, and limited payload capacity. The vision-based navigation and visual inertial navigation systems enable operation without GPS.

**Sensor transforms** — EO/IR sensors and thermal imagers mounted in the fuselage or gimbal. Laser range finders distributed for obstacle avoidance. Visual navigation sensors mounted downward-facing.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of motors, batteries, flight control system, and payloads.

**Integration** — Payload integration (replaceable for Black Hornet 3/4, integrated for Trace). Flight control system verification. Vision-based navigation verification. Encrypted data link verification. Vehicle integration (ICS) for Black Hornet 4.

**Field** — Over 35,000 Black Hornets supplied to users in over 45 countries. Combat-proven with NATO forces. Used operationally in Ukraine (Kursk oblast), Afghanistan, Iraq, and border security missions. US Army border surveillance (2025). Swiss contract for Piranha 8×8 armored engineering vehicle program ($17.5M, 2026). Black Hornet 4 Blue UAS List approved 2025. Black Recon launched 2026 for vehicle integration.

**Endurance** — 25 minutes (Black Hornet 3), 30+ minutes (Black Hornet 4), 50–60 minutes (Black Recon), 36–45 minutes (Trace).

**Environmental** — IP52 rated (Black Hornet 4: 7.6 mm rain/hr; Trace: IP67 protective field case for GCS). Wind tolerance 25 knots + gusts. Operating temperature range not publicly specified, but deployed in extreme environments.

**Known limitations** — The Wraith is a nano UAS with a 70–178 gram airframe; it cannot carry large sensors or heavy equipment. The 25–60 minute endurance is significantly shorter than larger fixed-wing or hybrid VTOL platforms. The encrypted data link has a range of 2–6 km, which is shorter than larger platforms. The aircraft is not stealth in the radar-evading sense; it relies on its extremely small size, near-silent acoustic signature, and near-invisible visual signature for survivability. The Trace has a 12-inch span, which is larger than the Black Hornet 4 but still pocket-sized. The Black Recon system requires vehicle integration for autonomous launch and recovery.

---

## Log

**Build history** — Black Hornet developed by Prox Dynamics (Norway), acquired by Teledyne FLIR. PD-100 Black Hornet first prototype weighed <15 g with 100 mm rotor diameter (2008). Black Hornet 3 introduced with 25-minute endurance, 2 km range (2013–2015). Black Hornet 4 introduced with 30+ minute endurance, 3+ km range, IP52 rating, 25-knot wind tolerance (2024–2025). Vantage Robotics Trace introduced 2024 with 153 g weight, <37 dBA acoustic signature, 48 MP EO / 320p IR gimbal. Black Recon launched June 2026 for autonomous vehicle-integrated operations. Over 35,000 Black Hornets supplied to 45+ countries.

**Open issues** — Expansion of payload options (CBRN, lethality, SIGINT). Vehicle integration for additional platforms. Production scaling to meet demand. Export control and ITAR restrictions for nano UAS.

**Changelog** — Black Hornet PD-100: 16 g, 20–25 min, 1.6 km range. Black Hornet 3: 33 g, 25 min, 2 km range. Black Hornet 4: 70 g, 30+ min, 3+ km range, IP52, 25-knot wind. Black Recon: autonomous vehicle-integrated system, 3-UAV rotation, 50–60 min, <450 g. Trace: 153 g, 36–45 min, 6 km LOS, <37 dBA.

**Lessons learned** — The nano-scale form factor is the key enabler of covert local surveillance. The near-silent acoustic signature (<37 dBA at 25 m) and near-invisible visual signature make the aircraft functionally undetectable at close range. Vision-based navigation and visual inertial navigation enable operation in GPS-denied and radio-silent modes. The encrypted data link (AES-256) provides secure video and telemetry. Vehicle integration (Black Recon) enables persistent surveillance without operator exposure. The Black Hornet has been combat-proven in Ukraine, Afghanistan, and Iraq, validating the platform's reliability and effectiveness.

**Cost actual** — $17.5 million Swiss contract for Black Hornet 4 (2026). Black Hornet 4 Blue UAS List approved 2025. Unit cost varies by configuration, payload, and quantity. The Trace is positioned as a lower-cost alternative for public safety and law enforcement.

---

## Status

**Condition** — operational. Fielded with NATO forces, US Army, and over 45 countries. Over 35,000 units supplied. Blue UAS List approved.

**Blockers** — None. Active production and global service.

**Next steps** — Integration of new mission modules (CBRN, lethality, SIGINT). Expansion of vehicle integration to additional platforms. Continued fielding with US Army, NATO forces, and international customers. Production scaling to meet demand. Development of successor systems with enhanced endurance and autonomy.

---

**Note on this Shell:** The wraith is a distinct class in the library: a **nano UAS** designed for **local, covert surveillance and reconnaissance** with an emphasis on **stealth, spy, and persistence**. Unlike the puma (hand-launched, 5.5-hour endurance, Group 2) or the raven (hand-launched, 60–90 minute endurance, Group 1), the Wraith is a true nano-scale platform weighing 70–178 grams, with a near-silent acoustic signature (<37 dBA at 25 m) and near-invisible visual signature (not visible at 30 ft against terrain). It is designed for the dismounted soldier, special operations forces, and law enforcement tactical teams who need to see over walls, around corners, and inside buildings without exposing themselves. The Black Hornet 4 and Trace represent the current state of the art in nano UAS: 30–45 minute endurance, 3–6 km range, EO/IR imaging, GPS-denied navigation, and encrypted data links. The Black Recon system extends this to vehicle-integrated operations with autonomous launch, recovery, and recharge for three UAVs in rotation, providing persistent surveillance without operator exposure. With over 35,000 Black Hornets supplied to 45+ countries and combat-proven performance in Ukraine, Afghanistan, and Iraq, the Wraith is the reference for a nano-scale, stealthy, local surveillance drone with spy capabilities.
