# blackjack

**Class:** aerial (Group 3 fixed-wing UAS)  
**Generation:** 1  
**Version:** 2.0  
**Glossary:** 2026-09  
**Condition:** operational  
**Author:** Insitu (a Boeing Company)  
**Last updated:** 2026-10-06

---

## Identity

**Role** — Twin-boom, heavy-fuel, runway-independent tactical unmanned aircraft system designed for persistent maritime and expeditionary ISR (Intelligence, Surveillance, Reconnaissance). The Blackjack is not a strategic asset; it is a **shipboard and austere-site ISR platform** that a small crew can launch by pneumatic catapult from a ship deck or an austere land site, leave airborne for 16+ hours, and recover by skyhook cable capture — no runway, no arresting gear, no prepared surface. Its defining characteristics are **runway independence**, **16+ hour endurance**, and **six modular payload bays** that carry up to 39 lb (17.7 kg) of multi-INT sensors. It is the U.S. Navy and Marine Corps' Small Tactical Unmanned Aircraft System (STUAS) program of record, with over 1.3 million operational hours on the Insitu family. 

**Environment** — Outdoor, maritime, and expeditionary operations. All-weather, day and night. Designed for shipboard deployment (from frigate to carrier decks) and austere land sites. Operating ceiling up to 20,000 ft. Endurance up to 16 hours. Engine uses JP-5 or JP-8 heavy fuel, a US Navy requirement for shipboard operations. Not for operations in icing conditions or severe turbulence without additional protection. 

**Mission** — Persistent maritime domain awareness, shipboard ISR, route reconnaissance, force protection, overwatch, target acquisition, communications relay, and electronic warfare. The Blackjack carries a standard EO/IR payload with laser rangefinder and IR marker, and its six payload bays can be configured with communications relay, AIS, SIGINT, EW, and other tools. It is designed to provide actionable intelligence to commanders on the ground or at sea. 

**Operator** — Small crew for launch and recovery. Single operator for flight control via ground control station. The aircraft is launched by a pneumatic catapult and recovered by a crane-based vertical capture rope system (the STUAS Recovery System, or SRS). The system packs into standard shipping containers and is transportable via ship, V-22, C-130, CH-47, CH-53, HMMWV, or JLTV. 

**Reusability** — Commercial defence platform. Program of record for the U.S. Navy and Marine Corps. Achieved Full Rate Production in October 2016. Currently flown by Marine Unmanned Aerial Vehicle Squadrons 1 and 2 (VMU-1 and VMU-2). Available through the U.S. Navy's Foreign Military Sales program. Canada operates the CU-172 (Canadian designation for the RQ-21A). 

---

## Spec

**Physical** — Length 8.2 ft (2.5 m). Wingspan 15.7 ft (4.8 m). Maximum take-off weight 135 lb (61 kg). Maximum payload weight 39 lb (17.7 kg) across six payload bays (increased payload reduces endurance). The airframe features a twin-boom configuration with a pusher propeller, optimized for shipboard operations and long-endurance cruise. 

**Kinematic** — Fixed-wing, twin-boom configuration. Launch by pneumatic catapult. Recovery by skyhook cable capture using the STUAS Recovery System (SRS). The aircraft does not require a runway for launch or recovery. Control surfaces actuated by electromechanical actuators. The flight control system manages launch, cruise, and recovery. Cruise speed 60 knots, maximum horizontal speed 90+ knots (46.3 m/s). 

**Dynamic** — Endurance up to 16 hours. Ceiling up to 20,000 ft. Maximum horizontal speed 90+ knots (46.3 m/s). Cruise speed 60 knots. Line-of-sight operating radius beyond 50 nautical miles (92.6 km). Engine: 8 HP reciprocating engine with Electronic Fuel Injection (EFI), using JP-5 or JP-8 heavy fuel. 

**Power** — Single 8 HP reciprocating engine with EFI, running on JP-5 or JP-8 heavy fuel. The heavy-fuel engine is a US Navy requirement for shipboard operations and provides logistics commonality with other maritime platforms. On-board power for payloads is not publicly specified, but the aircraft carries up to 39 lb of modular payloads. 

**Thermal** — Passive cooling. The engine is air-cooled with a ram-air intake. The twin-boom configuration places the engine and pusher propeller at the rear, reducing infrared signature from the front. The heavy-fuel engine has a lower fire hazard than gasoline-powered engines, which is critical for shipboard operations.

**Environmental** — Designed for maritime and expeditionary operations. The aircraft is launched by pneumatic catapult and recovered by cable capture, enabling operations from ship decks and austere land sites without runways. Not rated for icing conditions without additional protection. The composite airframe is resistant to salt spray and UV degradation. Transportable via ship, cargo aircraft (V-22, C-130 or larger), cargo helicopters (CH-47, CH-53), and vehicles (HMMWV, JLTV). 

---

## Frame

**Bill of materials** — Commercial defence platform. Not a DIY build. The Blackjack is purchased as a complete system with ground control stations, launch and recovery equipment, and modular payloads.

| Component | Notes |
|:---|:---|
| RQ-21A Blackjack airframe | Twin-boom, composite construction, 2.5 m length, 4.8 m wingspan, 61 kg MTOW |
| 8 HP EFI reciprocating engine | JP-5/JP-8 heavy fuel, pusher propeller |
| Pneumatic catapult launcher | Launch from ship deck or austere land site |
| STUAS Recovery System (SRS) | Crane-based vertical capture rope system for skyhook recovery |
| Modular payload bays (6×) | 39 lb (17.7 kg) total capacity, open architecture |
| EO/IR turret ball | Standard payload: 1.1°–25° optical FOV, 4x digital zoom, MWIR 2°–25° FOV, laser rangefinder, IR marker |
| Communications relay | Standard payload, enables network extension |
| AIS receiver | Automatic Identification System for maritime vessel tracking |
| Ground control stations (2×) | Operator interface for mission command and payload control |
| Launch and recovery systems | Pneumatic launcher and SRS crane |

**Structure** — Twin-boom composite airframe with a pusher propeller. The fuselage houses the engine, fuel, avionics, and six modular payload bays. The twin-boom configuration provides a stable platform for the EO/IR turret and other sensors, with a clear field of view. The aircraft is designed for shipboard and austere-site operations, with a runway-independent launch and recovery system. The open payload architecture enables rapid integration of new sensors and mission systems. 

**Actuation** — Single 8 HP reciprocating engine with EFI, driving a pusher propeller. Control surfaces actuated by electromechanical actuators. The pneumatic catapult provides launch energy; the SRS provides recovery. The aircraft is certified to launch at a higher weight than the SRS is rated to recover, which limits the payload configurations that can be recovered. 

**Locomotion** — Fixed-wing flight. Pneumatic catapult launch, skyhook cable recovery. The aircraft flies a conventional fixed-wing profile during cruise. Cruise speed 60 knots, maximum speed 90+ knots. The runway-independent launch and recovery system enables operations from ship decks and austere land sites. 

**Manipulation** — None. The aircraft is a sensor and communications platform. The payload is the effector: EO/IR sensors, laser rangefinder, IR marker, communications relay, AIS, SIGINT, EW, and other tools. The six modular payload bays allow rapid reconfiguration for different mission profiles. 

**Power system** — Single 8 HP reciprocating engine with EFI, running on JP-5 or JP-8 heavy fuel. The engine provides propulsion and electrical power for the avionics and payloads. The heavy-fuel design is a US Navy requirement for shipboard operations and provides logistics commonality with other maritime platforms. 

**Wiring** — Internal only. Not user-accessible. Payload integration via six modular payload bays with an open architecture. The aircraft is compliant with relevant NATO and industry standards for interoperability across joint, coalition, and allied forces. 

**Custom parts** — None. All components are Insitu/Boeing proprietary or certified third-party. The open payload architecture supports customization with imagers, communication systems, electronic warfare payloads, signals intelligence capabilities, and other tools. 

**Fasteners** — Proprietary. Not user-serviceable. The aircraft is designed for shipboard and expeditionary operations, with modular components for field assembly and maintenance. A single Blackjack system includes five UAVs, two ground control stations, various payloads, and a set of launch and recovery systems. 

**Tools required** — None for assembly (factory-built). Standard tools for payload mounting and field maintenance. The system is designed for expeditionary deployment from ship decks and austere land sites.

---

## Systems

**Manifest** — Insitu/Boeing proprietary software stack with open payload architecture and multi-INT capability.

**Firmware** — The aircraft runs a proprietary flight control system with autonomous operation, including pneumatic catapult launch, waypoint navigation, and skyhook cable recovery. The aircraft is runway-independent and designed for expeditionary operations from land and sea. The flight control system manages all phases of flight. 

**Middleware** — Insitu/Boeing proprietary. The command and control data link is encrypted and enables a line-of-sight operating radius beyond 50 nm (92.6 km). The data link has electromagnetic shielding to support customized communications and RF sensor payloads. The aircraft is compliant with relevant NATO and industry standards for interoperability across joint, coalition, and allied forces. 

**Perception** — Standard payload configuration includes:
- **EO/IR turret ball**: Electro-optic imager with 1.1°–25° optical field of view and 4x digital zoom; mid-wave infrared imager with 2°–25° field of view; laser rangefinder; IR marker.
- **Communications relay**: Enables network extension.
- **AIS**: Automatic Identification System for maritime vessel tracking.
- **Modular payload bays (6×)**: Can be configured with electronic warfare, signals intelligence, communications relay, and other tools to give the warfighter a look ahead in operational environments. The open payload architecture supports plug-and-play multi-intelligence capability. 

**Control** — The flight control system manages all phases of flight autonomously. The operator provides mission-level command: area of interest, search patterns, and payload tasking. The aircraft is launched by pneumatic catapult and recovered by skyhook cable capture. The ground control stations provide mission planning, payload control, and data exploitation. The aircraft is designed for persistent detection, classification, and tracking. 

**Planning** — Mission planning is performed at the ground control station. The operator defines the area of interest and the aircraft autonomously navigates to the location, then loiters or performs search patterns. The aircraft can be retasked in flight. The runway-independent launch and recovery system enables rapid deployment from ship decks and austere land sites. 

**Learning** — None publicly disclosed. The aircraft uses classical control, autonomous navigation, and sensor fusion. No learning-based control is mentioned for safety-critical functions.

**Teleoperation** — Small crew for launch and recovery, single operator for flight control via ground control station. The operator provides mission-level command and manages the payload. The aircraft handles flight control, navigation, and recovery autonomously. The encrypted command and control data link enables operation beyond 50 nm line-of-sight. 

**Safety** — The aircraft is runway-independent, reducing the risk of runway excursions or launch failures. The encrypted data link and electromagnetic shielding provide resilience against jamming and interference. The heavy-fuel engine reduces fire hazard compared to gasoline-powered engines. The open payload architecture and NATO interoperability standards ensure compatibility with allied forces. The SRS has been the subject of improvement efforts due to recovery weight limitations and damage during capture. 

**Logging** — Mission data, sensor data, and flight telemetry are logged. The Insitu family has accumulated over 1.3 million operational hours. Specific logging details are not publicly disclosed, but the system is designed for ISR missions where evidence capture and target tracking are important. 

**Networking** — Encrypted command and control data link with line-of-sight operating radius beyond 50 nm (92.6 km). Electromagnetic shielding supports customized communications and RF sensor payloads. The aircraft can carry communications relay payloads for network extension. Compliant with NATO and industry standards for interoperability. 

**Config files** — Proprietary. No user-accessible config files. Mission parameters and payload configurations are set through the ground control station.

**Launch files** — N/A (proprietary UAS software).

**Dependencies** — Insitu/Boeing ground control station software. Pneumatic catapult launcher. STUAS Recovery System (SRS). Payload-specific software (EO/IR, communications relay, AIS, SIGINT, EW).

### Software Manifest

| Package | Version | Source | Software ref |
|:---|:---|:---|:---|
| Insitu flight control | Proprietary | Insitu | Control/Flight |
| Ground control station | Proprietary | Insitu | GCS |
| EO/IR payload software | Proprietary | Insitu | Sensors/EOIR |
| Communications relay software | Proprietary | Insitu | Comms/Relay |
| AIS software | Proprietary | Insitu | Sensors/AIS |
| SIGINT/EW payload software | Proprietary | Various | Payload/Integration |

---

## Interface

**Emits** — Aircraft telemetry: attitude, position, altitude, airspeed, fuel state, engine status, system health. Sensor data: EO/IR imagery, laser rangefinder data, AIS tracks, communications relay signals, SIGINT/EW data.

**Accepts** — Mission commands (area of interest, search patterns, payload tasking). Navigation commands (waypoints, loiter locations). Payload commands. Launch and recovery commands.

**Serves** — Persistent ISR services. Maritime domain awareness. Target acquisition and tracking. Communications relay services. Electronic warfare services.

**Executes** — Pneumatic catapult launch, waypoint navigation, persistent ISR over a local or regional area, maritime surveillance, signals intelligence collection, skyhook cable recovery.

**Extensions** — Six modular payload bays (39 lb capacity). EO/IR, communications relay, AIS, SIGINT, EW, and other tools via open payload architecture.

**Frame conventions** — Geographic coordinates (latitude, longitude, altitude). NED for navigation. FRD for body. Airspeed in knots. Altitude in feet MSL.

**Units** — SI and aviation standard. Metres, feet, knots, kilometres, pounds, kilograms.

---

## Model

**URDF / Xacro** — Not applicable (proprietary defence platform).

**SDF** — Not applicable.

**Calibration** — Factory calibrated. Sensor calibration for EO/IR, laser rangefinder, and other payloads. Flight control system calibrated for catapult launch and skyhook recovery.

**Dynamics** — Proprietary. The aircraft's aerodynamic model is used for flight control and autonomy. The twin-boom configuration provides a stable platform for the EO/IR turret. The 8 HP EFI engine provides sufficient thrust for the 61 kg MTOW and the 17.7 kg payload. The heavy-fuel engine provides 16+ hours of endurance.

**Sensor transforms** — EO/IR turret mounted in the fuselage. Modular payload bays distributed across the airframe. Communications relay and AIS antennas mounted for optimal coverage.

**Collision geometry** — Proprietary.

**Visual geometry** — Proprietary.

---

## Trials

**Bench** — Factory tested. Component-level testing of engine, pneumatic launcher, SRS, flight control system, and payloads.

**Integration** — Payload integration in the six modular payload bays. Flight control system verification. Encrypted data link verification. Pneumatic catapult and SRS integration. NATO interoperability verification.

**Field** — Over 1.3 million operational hours on the Insitu family. Program of record for the U.S. Navy and Marine Corps. Achieved Full Rate Production October 2016. Currently flown by VMU-1 and VMU-2 supporting expeditionary operations worldwide. Operated from ship decks and austere land sites. Deployed with international defense, government, and commercial customers. Canada operates the CU-172. 

**Endurance** — Up to 16 hours. Ceiling up to 20,000 ft. Line-of-sight operating radius beyond 50 nm (92.6 km).

**Environmental** — Shipboard and expeditionary operations. Not for icing conditions without additional protection. Transportable via ship, V-22, C-130, CH-47, CH-53, HMMWV, and JLTV.

**Known limitations** — The Blackjack is a Group 3 UAS with a 39 lb payload capacity; it cannot carry large sensors or heavy weapons. The 16-hour endurance is impressive but limited compared to larger MALE/HALE platforms. The SRS recovery system has been the subject of improvement efforts due to recovery weight limitations and damage during capture; the SRS is rated to recover the RQ-21A at a weight below the maximum weight with which the air vehicle is certified to launch, which limits the payload configurations that can be recovered. The aircraft requires a pneumatic catapult and a crane-based recovery system, which adds logistics footprint compared to VTOL platforms. The heavy-fuel engine requires JP-5 or JP-8, which is available on US Navy ships but may not be available in all austere environments. 

---

## Log

**Build history** — RQ-21A Blackjack developed by Insitu Inc. (a wholly owned subsidiary of The Boeing Company) in partnership with the U.S. Department of the Navy. Program of record for the U.S. Navy and Marine Corps Small Tactical Unmanned Aircraft System (STUAS). Achieved Full Rate Production October 2016. Operated by VMU-1 and VMU-2. Available through the U.S. Navy's Foreign Military Sales program. Canada operates the CU-172. U.S. Navy ordered RQ-21A and ScanEagle UAVs for $102M in February 2025. Canada awarded Insitu $8.6M contract to sustain and upgrade CU-172 fleet in April 2026. 

**Open issues** — SRS recovery weight limitations and damage during capture. Expansion of payload options (SIGINT, EW). Integration with emerging battle-management systems. Export control and ITAR restrictions.

**Changelog** — RQ-21A Blackjack: initial production configuration. 2016: Full Rate Production. 2025: U.S. Navy order for RQ-21A and ScanEagle UAVs ($102M). 2026: Canada CU-172 sustainment and upgrade contract ($8.6M).

**Lessons learned** — The runway-independent launch and recovery system (pneumatic catapult + skyhook cable recovery) is the key enabler of shipboard and austere-site operations. The six modular payload bays and open architecture enable multi-INT capability and rapid reconfiguration. The heavy-fuel engine (JP-5/JP-8) provides logistics commonality with US Navy ships. The encrypted data link and electromagnetic shielding provide resilience against jamming and interference. The SRS recovery system requires further refinement to reduce damage and expand the recoverable payload envelope. Over 1.3 million operational hours on the Insitu family validates the platform's reliability and effectiveness. 

**Cost actual** — U.S. Navy ordered RQ-21A Blackjack and ScanEagle UAVs for $102 million in February 2025. Canada awarded Insitu $8.6 million to sustain and upgrade the CU-172 fleet in April 2026. Unit cost varies by configuration, payload, and quantity. 

---

## Status

**Condition** — operational. Program of record for the U.S. Navy and Marine Corps. Full Rate Production achieved October 2016. Over 1.3 million operational hours on the Insitu family.

**Blockers** — None. Active production and global service.

**Next steps** — SRS recovery system improvement. Integration of new payloads (SIGINT, EW). Continued service with U.S. Navy, U.S. Marine Corps, and international customers. Foreign Military Sales expansion. Development of successor systems with enhanced endurance and autonomy.

---

**Note on this Shell:** The blackjack is a distinct class in the library: a Group 3 twin-boom, heavy-fuel, runway-independent tactical UAS designed for **shipboard and expeditionary ISR** with 16+ hours of endurance and 39 lb of modular payload capacity across six bays. Unlike the scaneagle (Group 2, 18+ hours, 17 lb payload) or the integrator (Group 3, 27.5 hours, 50 lb payload), the Blackjack is specifically designed for the U.S. Navy and Marine Corps' Small Tactical Unmanned Aircraft System (STUAS) program, with a pneumatic catapult launch and skyhook cable recovery system that enables operations from ship decks and austere land sites without runways. Its heavy-fuel engine (JP-5/JP-8) is a US Navy requirement for shipboard operations. The six modular payload bays and open architecture enable multi-INT capability including EO/IR, communications relay, AIS, SIGINT, and EW. With over 1.3 million operational hours on the Insitu family, Full Rate Production since 2016, and service with the U.S. Navy, Marine Corps, and international customers, the Blackjack is the reference for a mature, shipboard-capable, long-endurance ISR platform with modular payloads and runway independence.
