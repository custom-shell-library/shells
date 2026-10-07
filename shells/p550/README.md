# p550

**Class:** aerial (Group 2 eVTOL UAS)  
**Generation:** 1  
**Version:** 1.0.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** AeroVironment  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Autonomous electric vertical take-off and landing (eVTOL) Group 2 unmanned aircraft system designed for Long Range Reconnaissance (LRR) at the platoon and company level. The P550 is not a strategic asset; it is a **maneuver force organic ISR platform** that a small unit can deploy from a confined location, leave airborne for over five hours, and use to maintain continuous situational awareness over a local area of operations. Its defining features are **runway independence** (vertical launch and recovery), **all-battery endurance** (over 5 hours), and a **modular open systems architecture** that allows payloads and batteries to be swapped in under five minutes without tools. It is designed to provide persistent ISR, targeting, and force protection for maneuver forces in contested and GPS-challenged environments.

**Environment** — Outdoor, all-weather, day and night operations. Deployed directly from maneuver units or confined locations, including urban and complex terrain. No runway, catapult, or launch gear required. Operating altitude not publicly specified, but designed for low-altitude reconnaissance below 500 ft AGL. Not for operations in icing conditions or severe turbulence without additional protection. The aircraft is designed for rapid setup and hot-swappable components for quick mission turnarounds.

**Mission** — Long Range Reconnaissance (LRR), persistent ISR, target acquisition, force protection, communications relay, and electronic warfare. The P550 was selected for the U.S. Army’s Long Range Reconnaissance program, which provides reconnaissance capability to platoons and companies operating beyond the immediate battlefield. It supports intelligence gathering, precision targeting, and force protection in dynamic and contested environments. The modular payload bay can carry multi-sensor payloads including enhanced lethality options.

**Operator** — Small unit deployment, typically two personnel. The aircraft is designed for rapid forward deployment directly from maneuver units or confined locations. The operator provides mission-level command; the aircraft handles flight control, navigation, and AI-assisted object detection and classification autonomously. It integrates with third-party mission planning, datalinks, and ground control systems through its modular open systems architecture.

**Reusability** — Commercial defence platform with active production. The U.S. Army awarded AeroVironment a $117.3 million production contract for 82 P550 eVTOL UAS in July 2026. An earlier $13.2 million contract was awarded in December 2025 for the Army’s Long Range Reconnaissance (LRR) program. The P550 is also part of an $874 million Foreign Military Sales IDIQ to deliver UAS and C-UAS systems to allied and partner forces.

---

## Spec

**Physical** — Aircraft dimensions 17 ft × 9 ft × 2 ft (5.2 m × 2.8 m × 0.6 m), length × width × height. Pack-out dimensions 6 ft × 2 ft × 2 ft (1.8 m × 0.6 m × 0.6 m), allowing transport in a small vehicle or by two personnel. Gross take-off weight 55 lb (24.9 kg). The airframe is constructed from lightweight composite materials with an all-electric powertrain. The modular design allows payloads and batteries to be changed in the field without tools.

**Kinematic** — eVTOL configuration. The aircraft takes off and lands vertically under its own power, removing the need for runways, catapults, or launch gear. It transitions from hover to forward flight for efficient cruise, then back to hover for landing. The flight control system manages the transition seamlessly. The aircraft operates at 15–27 m/s (30–52 knots) depending on ground control station radio configuration. The modular open systems architecture supports integration of third-party payloads, datalinks, and mission software.

**Dynamic** — Endurance 5+ hours on all-battery power. Link range 40–60 km depending on GCS radio. Operating speed 15–27 m/s (30–52 knots). The extended endurance supports persistent ISR operations, overwatch, and communications relay without frequent landings. The 5+ hour endurance is class-leading for a Group 2 eVTOL UAS and enables sustained coverage of a local area of operations over an entire mission cycle.

**Power** — All-electric powertrain. Battery capacity not publicly specified, but sufficient for 5+ hours of flight. Batteries are hot-swappable in under five minutes without tools, dramatically reducing turnaround time between missions and increasing sortie rates. The all-battery design eliminates fuel logistics, which is a significant advantage for maneuver forces operating in austere environments where fuel resupply is difficult or impossible. The modular battery system allows operators to carry multiple battery sets and sustain continuous operations with minimal downtime.

**Thermal** — Passive cooling. The electric motors are air-cooled by the rotor wash in hover and by ram air in forward flight. The avionics and payload are housed in the airframe with adequate ventilation. No active thermal management is required for the operating envelope. The all-electric powertrain produces a lower thermal signature than internal combustion engines, reducing detectability by infrared sensors.

**Environmental** — Designed for all-environment operation. The aircraft is built for rapid setup in the field and supports hot-swappable components for quick mission turnarounds. It operates in dynamic and contested environments, including urban and complex terrain. The modular open systems architecture supports integration of third-party payloads and datalinks. Not rated for icing conditions without additional protection. The all-electric powertrain reduces acoustic and thermal signatures compared to internal combustion engines.

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The P550 is purchased as a complete system with ground control station and modular payload integration.

| Component | Notes |
|:---|:---|
| P550 airframe | Composite construction, 17 × 9 × 2 ft, 55 lb GTOW |
| All-electric powertrain | Battery-powered electric motors for vertical lift and forward cruise |
| Hot-swappable batteries | Changed in under 5 minutes without tools |
| Modular payload bay | Up to 15 lb (6.8 kg) multi-sensor payload capacity |
| AI autonomy module | Built-in autonomy for flight profiles, object detection, classification |
| Modular open systems architecture | Supports third-party payloads, datalinks, mission software, GCS |
| Ground control station | Operator interface for mission command and payload control |
| EO/IR sensor payload | Multi-sensor payload options for ISR and targeting |
| Communications relay payload | Optional communications relay for network extension |
| Electronic warfare payload | Optional EW payload for contested environments |

**Structure** — Lightweight composite airframe with an all-electric powertrain. The aircraft is designed for rapid deployment from confined locations; it packs into a 6 × 2 × 2 ft case and can be transported by two personnel or in a small vehicle. The modular open systems architecture allows payloads and batteries to be swapped without tools, enabling rapid reconfiguration for different mission profiles. The airframe is built for durability and repeated deployment in austere environments.

**Actuation** — All-electric powertrain. The aircraft uses electric motors for vertical lift and forward cruise. The flight control system manages the transition from hover to forward flight seamlessly. The aircraft operates at 15–27 m/s (30–52 knots). Control surfaces and motor controllers are managed by the AI autonomy module, which reduces operator workload and improves mission reliability.

**Locomotion** — eVTOL flight. Vertical take-off and landing, transition to forward flight for efficient cruise, and transition back to hover for landing. The aircraft is runway-independent, enabling deployment from maneuver units or confined locations. The 5+ hour endurance supports persistent ISR, overwatch, and communications relay without frequent landings.

**Manipulation** — None. The aircraft is a sensor and communications platform. The payload is the effector: EO/IR sensors, communications relay equipment, electronic warfare systems, or enhanced lethality options. The modular payload bay allows rapid reconfiguration for different mission profiles.

**Power system** — All-electric powertrain with hot-swappable batteries. The batteries are changed in under five minutes without tools, reducing turnaround time and increasing sortie rates. The all-battery design eliminates fuel logistics. Power distribution includes redundant buses for flight-critical avionics and payloads. The battery capacity is sufficient for 5+ hours of flight.

**Wiring** — Internal only. Not user-accessible. Payload integration via the modular payload bay. The modular open systems architecture supports third-party payloads, datalinks, and mission software, enabling evolving capabilities without extensive redesign.

**Custom parts** — None. All components are AeroVironment proprietary or certified third-party. The modular open systems architecture enables integration of third-party payloads and mission equipment. The hot-swappable payload and battery system allows operators to adapt sensors and mission equipment without tools.

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for rapid deployment and recovery by a small crew; maintenance is at the module level (payloads, batteries, arms).

**Tools required** — None for assembly (factory-built). No tools required for payload and battery changes. Standard tools for field maintenance and payload integration.

---

## Systems

**Manifest** — AeroVironment proprietary software stack with AI autonomy and modular open systems architecture.

**Firmware** — The aircraft runs a proprietary flight control system with built-in autonomy and AI capabilities. Advanced autonomy enables the P550 to execute complex flight profiles, transition seamlessly from hover to forward flight, and assist in object detection and classification. The autonomy reduces operator workload and improves mission reliability. The aircraft is designed for GPS-challenged environments, with autonomy that assists in navigation and target detection when GPS is degraded or denied.

**Middleware** — AeroVironment proprietary. The modular open systems architecture supports integration of third-party datalinks and mission software. The aircraft integrates with third-party mission planning, datalinks, and ground control systems. This future-ready design lets operators adapt sensors and mission equipment without extensive redesign, enabling evolving capabilities without extensive downtime or technical risk.

**Perception** — Multi-sensor payload capacity of up to 15 lb (6.8 kg). Payload options include EO/IR sensors for ISR and targeting, communications relay equipment, electronic warfare systems, and enhanced lethality options. The AI autonomy module assists in object detection and classification, enhancing situational awareness in contested or GPS-challenged environments. Specific sensor details are not publicly disclosed, but the modular open systems architecture allows rapid integration of third-party sensors.

**Control** — The AI autonomy module manages flight control, navigation, and object detection/classification. The operator provides mission-level command: area of interest, search patterns, and payload tasking. The aircraft executes complex flight profiles autonomously, including hover-to-forward-flight transitions. The autonomy reduces operator workload, allowing the small unit to focus on mission execution rather than piloting. The aircraft operates in GPS-challenged environments with autonomy-assisted navigation.

**Planning** — Mission planning is performed at the ground control station. The operator defines the area of interest and the aircraft autonomously navigates to the location, then loiters or performs search patterns. The AI autonomy assists in object detection and classification, providing actionable intelligence to the operator. The modular open systems architecture supports integration with third-party mission planning software.

**Learning** — The AI autonomy module provides object detection and classification, but no learning-based control is publicly disclosed for safety-critical functions. The AI assists in situational awareness and target detection, but the flight control and weapons release (if armed) remain under human authorization.

**Teleoperation** — Single operator via ground control station. The operator provides mission-level command and manages the payload. The aircraft handles flight control, navigation, and AI-assisted object detection autonomously. The ground control station integrates with third-party mission planning, datalinks, and ground control systems through the modular open systems architecture.

**Safety** — The AI autonomy reduces operator workload and improves mission reliability. The aircraft executes complex flight profiles autonomously, reducing the risk of human error. The all-electric powertrain eliminates fuel-related hazards. The hot-swappable batteries and payloads reduce turnaround time and the risk of maintenance errors. The aircraft is designed for operation in contested and GPS-challenged environments, with autonomy that assists in navigation and target detection when GPS is degraded. Human-in-the-loop for weapons release (if armed).

**Logging** — Mission data, sensor data, and flight telemetry are logged. The AI autonomy module assists in object detection and classification, providing actionable intelligence. Specific logging details are not publicly disclosed, but the system is designed for ISR missions where evidence capture and target tracking are important.

**Networking** — The modular open systems architecture supports integration of third-party datalinks and mission software. The aircraft integrates with third-party ground control systems. Link range 40–60 km depending on GCS radio. The aircraft can carry communications relay payloads for network extension.

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through the ground control station.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — AeroVironment ground control station software. AI autonomy module. Payload-specific software (EO/IR, communications relay, EW). Third-party datalinks and mission software (via modular open systems architecture).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| AeroVironment flight control | Proprietary | AeroVironment | Control/Flight |
| AI autonomy module | Proprietary | AeroVironment | Autonomy/AI |
| Ground control station | Proprietary | AeroVironment | GCS |
| Payload integration software | Proprietary | Various | Payload/Integration |
| Modular open systems architecture | Open standards | AeroVironment | Architecture/Open |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, battery state, system health. Sensor data: EO/IR imagery, object detection and classification data, target tracks. Communications relay signals (if configured). Network data: datalink status, connected systems.

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Communications relay configuration. Payload commands. Weapons authorization (human-in-the-loop, if armed).

**Serves** — Persistent ISR services. Target acquisition and tracking. Communications relay services. Force protection services.

**Executes** — Autonomous navigation. eVTOL take-off and landing. Persistent ISR over a local area. Target acquisition. Communications relay. Electronic warfare (if equipped).

**Extensions** — Modular payload bay (15 lb capacity). EO/IR sensors, communications relay equipment, electronic warfare systems, enhanced lethality options. Third-party payloads, datalinks, and mission software via modular open systems architecture.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in m/s or knots. Altitude in feet MSL or AGL.

**Units** — SI and aviation standard. Metres, feet, knots, kilograms, pounds.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for EO/IR and other payloads. Flight control system calibrated for eVTOL transition and forward flight. AI autonomy module calibrated for object detection and classification.

**Dynamics** — Proprietary. The aircraft’s aerodynamic model is used for flight control and autonomy. The eVTOL configuration presents unique challenges during transition from hover to forward flight; the AI autonomy module manages this transition seamlessly. The all-electric powertrain and composite airframe provide efficient cruise and long endurance.

**Sensor transforms** — Payload sensors mounted in the modular payload bay. Specific transforms depend on the payload configuration.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of motors, batteries, flight control system, and AI autonomy module.

**Integration** — Payload integration in the modular bay. Flight control system verification. AI autonomy module verification. Datalink and ground control station integration. Hot-swappable payload and battery verification.

**Field** — 5+ hour endurance test. Link range test (40–60 km). eVTOL take-off and landing from confined locations. Persistent ISR mission profiles. Target acquisition and tracking. Communications relay. GPS-challenged navigation test. U.S. Army LRR program evaluation. $117.3 million production contract for 82 units awarded July 2026.

**Endurance** — 5+ hours on all-battery power. Hot-swappable batteries for extended operations with minimal downtime.

**Environmental** — All-environment operations. Deployed from maneuver units or confined locations. Not for icing conditions without additional protection. All-electric powertrain reduces acoustic and thermal signatures.

**Known limitations** — The P550 is a Group 2 UAS with a 15 lb payload capacity; it cannot carry large sensors or heavy communications equipment. It is not a tactical strike platform in its baseline configuration, although enhanced lethality options are available. The 5+ hour endurance is class-leading for a Group 2 eVTOL but limited compared to larger MALE/HALE platforms. The aircraft requires battery charging infrastructure in the field; hot-swappable batteries mitigate this to some extent, but sustained operations require multiple battery sets and charging capability. The AI autonomy module assists in object detection and classification but does not replace human judgment for weapons release. The modular open systems architecture enables third-party integration but requires careful integration testing for each new payload configuration.

---

## Log

**Build history** — P550 developed by AeroVironment. Unveiled October 2024. U.S. Army awarded $13.2 million contract in December 2025 for the Long Range Reconnaissance (LRR) program. U.S. Army awarded $117.3 million production contract for 82 units in July 2026. Part of an $874 million Foreign Military Sales IDIQ to deliver UAS and C-UAS systems to allied and partner forces. Designed to provide reconnaissance capability to platoons and companies operating beyond the immediate battlefield.

**Open issues** — Expansion of payload options. Integration with emerging communications systems. Battery charging infrastructure in austere environments. Production scaling to meet demand. Export control and ITAR restrictions.

**Changelog** — P550: initial production configuration. 2024: unveiled. 2025: $13.2M LRR contract. 2026: $117.3M production contract for 82 units.

**Lessons learned** — The eVTOL configuration eliminates the need for runways, catapults, or launch gear, enabling rapid forward deployment directly from maneuver units or confined locations. The all-battery endurance of 5+ hours supports persistent ISR operations, overwatch, and communications relay without frequent landings. The modular open systems architecture supports quick integration of third-party payloads, datalinks, and mission software, enabling evolving capabilities without extensive redesign. Hot-swappable payloads and batteries reduce turnaround time between missions and increase sortie rates. The AI autonomy module reduces operator workload and improves mission reliability.

**Cost actual** — $117.3 million for 82 units, or approximately $1.43 million per aircraft, including ground control stations, payloads, and support. This is significantly lower than larger MALE/HALE platforms, making the P550 affordable for platoon and company-level deployment.

---

## Status

**Condition** — operational. U.S. Army production contract awarded for 82 units.

**Blockers** — None. Active production and procurement.

**Next steps** — Delivery of 82 units to the U.S. Army under the LRR program. Integration with emerging payloads (EW, communications relay, enhanced lethality). Expansion of Foreign Military Sales to allied and partner forces. Development of successor systems with enhanced endurance and autonomy.

---

**Note on this Shell:** The p550 is a distinct class in the library: a Group 2 eVTOL UAS designed for **local, persistent ISR** at the platoon and company level. Unlike the k1000ule (solar-powered, 75-hour endurance, Group 2) or the orion (tethered, 50-hour endurance, fixed position), the P550 is a free-flying, runway-independent aircraft with 5+ hours of all-battery endurance and a 15 lb modular payload capacity. It is designed for maneuver forces operating beyond the immediate battlefield, providing reconnaissance, target acquisition, and force protection from a platform that can be deployed from a confined location and left airborne for over five hours. The modular open systems architecture and hot-swappable payloads/batteries enable rapid reconfiguration and high sortie rates. The AI autonomy module reduces operator workload and assists in object detection and classification in GPS-challenged environments. With a unit cost of approximately $1.43 million, the P550 is affordable for platoon and company-level deployment, making it the reference for a small, long-endurance, eVTOL ISR platform for local persistent surveillance.
